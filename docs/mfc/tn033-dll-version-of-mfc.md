---
title: 'TN033: MFC의 DLL 버전'
ms.date: 06/28/2018
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
ms.openlocfilehash: c627f891efc893f4eb8dae4bfb0b3b78f7af1a46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215935"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC의 DLL 버전

이 정보는 MFC 응용 프로그램 및 MFC 확장명 Dll을 사용 하 여 MFCxx.DLL 및 MFCxxD.DLL (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리를 사용 하는 방법을 설명 합니다. 일반 MFC Dll에 대 한 자세한 내용은 [dll의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)을 참조 하세요.

이 기술 참고 사항은 Dll의 세 가지 측면을 다룹니다. 마지막 두 가지는 고급 사용자를 위한 것입니다.

- [MFC 확장 DLL을 빌드하는 방법](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC의 DLL 버전을 사용 하는 MFC 응용 프로그램을 빌드하는 방법](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC 공유 동적 연결 라이브러리를 구현 하는 방법](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Mfc가 아닌 응용 프로그램에서 사용할 수 있는 MFC를 사용 하 여 DLL을 빌드하는 방법에 관심이 있는 경우 (이를 일반 MFC DLL 이라고 함) [기술 참고 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)을 참조 하세요.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL 지원 개요: 용어 및 파일

**일반 MFC dll**: 일반 mfc dll을 사용 하 여 일부 mfc 클래스를 사용 하 여 독립 실행형 DLL을 빌드합니다. 앱/DLL 경계의 인터페이스는 "C" 인터페이스 이며, 클라이언트 응용 프로그램은 MFC 응용 프로그램 일 필요가 없습니다.

이 버전은 MFC 1.0에서 지원 되는 DLL 지원 버전입니다. [기술 정보 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 및 MFC 고급 개념 샘플 [DLLScreenCap](../overview/visual-cpp-samples.md)에 설명 되어 있습니다.

> [!NOTE]
> Visual C++ 버전 4.0을 기준으로 **USRDLL** 라는 용어는 사용 되지 않으며, 정적으로 mfc에 링크 하는 일반 mfc DLL로 대체 되었습니다. MFC에 동적으로 연결 되는 일반 MFC DLL을 빌드할 수도 있습니다.

MFC 3.0 이상에서는 OLE 및 데이터베이스 클래스를 비롯 한 모든 새로운 기능을 사용 하 여 일반 MFC Dll을 지원 합니다.

**AFXDLL**:이를 MFC 라이브러리의 공유 버전이 라고도 합니다. 이는 MFC 2.0에 추가 된 새 DLL 지원입니다. MFC 라이브러리 자체는 여러 Dll (아래 설명 참조)에 있으며 클라이언트 응용 프로그램 또는 DLL은 필요한 Dll을 동적으로 연결 합니다. 응용 프로그램/DLL 경계의 인터페이스는 c + +/MFC 클래스 인터페이스입니다. 클라이언트 응용 프로그램은 MFC 응용 프로그램 이어야 합니다. 이는 모든 MFC 3.0 기능을 지원 합니다 (예외: 데이터베이스 클래스에 대해 유니코드가 지원 되지 않음).

> [!NOTE]
> Visual C++ 버전 4.0을 통해이 DLL 유형을 "확장 DLL" 이라고 합니다.

이 메모는 MFCxx.DLL을 사용 하 여 다음을 포함 하는 전체 MFC DLL 집합을 참조 합니다.

- Debug: MFCxxD.DLL (결합) 및 MFCSxxD (정적).

- Release: MFCxx.DLL (결합) 및 MFCSxx (정적).

- 유니코드 디버그: MFCxxUD.DLL (결합) 및 MFCSxxD (정적).

- 유니코드 릴리스: MFCxxU.DLL (결합) 및 MFCSxxU (정적).

> [!NOTE]
> MFCSxx [U] [D]입니다. LIB 라이브러리는 MFC 공유 Dll과 함께 사용 됩니다. 이러한 라이브러리에는 응용 프로그램 또는 DLL에 정적으로 연결 되어야 하는 코드가 포함 되어 있습니다.

응용 프로그램은 해당 하는 가져오기 라이브러리에 연결 됩니다.

- 디버그: Mfcxxd.dll

- 릴리스: Mfcxx.dll

- 유니코드 디버그: MFCxxUD

- 유니코드 릴리스: MFCxxU

"MFC 확장명 DLL"은 MFCxx.DLL (및/또는 다른 MFC 공유 Dll)을 기반으로 하는 DLL입니다. 여기서 MFC 구성 요소 아키텍처가 시작 됩니다. MFC 클래스에서 유용한 클래스를 파생 시키거나 다른 MFC 유사 도구 키트를 빌드하는 경우 DLL에 삽입할 수 있습니다. 해당 DLL은 최종 클라이언트 응용 프로그램과 마찬가지로 MFCxx.DLL를 사용 합니다. 이렇게 하면 다시 사용할 수 있는 리프 클래스, 재사용 가능한 기본 클래스 및 다시 사용할 수 있는 뷰/문서 클래스를 사용할 수 있습니다.

## <a name="pros-and-cons"></a>장점 및 단점

MFC의 공유 버전을 사용 해야 하는 이유

- 공유 라이브러리를 사용 하면 더 작은 응용 프로그램이 생성 될 수 있습니다 (대부분의 MFC 라이브러리를 사용 하는 최소 응용 프로그램은 10K 미만).

- 공유 버전의 MFC는 MFC 확장명 Dll 및 일반 MFC Dll을 지원 합니다.

- 공유 MFC 라이브러리를 사용 하는 응용 프로그램을 빌드하는 것은 MFC 자체를 연결할 필요가 없기 때문에 정적으로 연결 된 MFC 응용 프로그램을 빌드하는 것 보다 더 빠릅니다. 이는 특히 디버그 정보를 포함 하는 DLL과 연결 하 여 링커가 디버그 정보를 압축 해야 하는 **디버그** 빌드에서는 응용 프로그램 내에서 압축할 디버그 정보가 더 작은 경우에 특히 그렇습니다.

공유 버전의 MFC를 사용 하지 않는 이유는 다음과 같습니다.

- 공유 라이브러리를 사용 하는 응용 프로그램을 제공 하려면 프로그램에 MFCxx.DLL 및 기타 라이브러리를 제공 해야 합니다. MFCxx.DLL은 많은 Dll 처럼 자유롭게 재배포할 수 있지만 설치 프로그램에 DLL을 설치 해야 합니다. 또한 프로그램 및 MFC Dll 자체에서 사용 되는 C 런타임 라이브러리를 포함 하는 MSVCRTxx.DLL를 제공 해야 합니다.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC 확장 DLL을 작성 하는 방법

MFC 확장 DLL은 MFC 클래스의 기능을 embellish 위해 작성 된 클래스 및 함수를 포함 하는 DLL입니다. MFC 확장 DLL은 응용 프로그램에서 사용 하는 것과 동일한 방식으로 공유 MFC Dll을 사용 합니다. 몇 가지 추가 고려 사항이 있습니다.

- 빌드 프로세스는 몇 가지 추가 컴파일러 및 링커 옵션으로 공유 된 MFC 라이브러리를 사용 하는 응용 프로그램을 빌드하는 것과 비슷합니다.

- MFC 확장 DLL에는 `CWinApp` 파생 클래스가 없습니다.

- MFC 확장 DLL은 특수를 제공 해야 합니다 `DllMain` . 응용 프로그램 마법사는 `DllMain` 수정할 수 있는 함수를 제공 합니다.

- Mfc 확장 dll은 일반적으로 `CDynLinkLibrary` mfc 확장 dll이 `CRuntimeClass` 응용 프로그램에 또는 리소스를 내보내려는 경우를 만드는 초기화 루틴을 제공 합니다. `CDynLinkLibrary`MFC 확장 DLL에서 응용 프로그램 별 데이터를 유지 관리 해야 하는 경우의 파생 클래스를 사용할 수 있습니다.

이러한 고려 사항은 아래에 자세히 설명 되어 있습니다. 또한 다음을 보여 주므로 MFC 고급 개념 샘플 [DLLHUSK](../overview/visual-cpp-samples.md) 을 참조 해야 합니다.

- 공유 라이브러리를 사용 하 여 응용 프로그램 빌드 DLLHUSK.EXE는 MFC 라이브러리 뿐만 아니라 다른 Dll에 동적으로 연결 되는 MFC 응용 프로그램입니다.

- MFC 확장 DLL 빌드 ( `_AFXEXT` MFC 확장 DLL을 빌드하는 데 사용 되는 등의 특수 플래그를 적어둡니다.)

- MFC 확장 Dll의 두 가지 예입니다. 하나는 TESTDLL1 (제한 된 내보내기)를 사용 하는 MFC 확장 DLL의 기본 구조를 보여주고 다른 하나는 TESTDLL2 (전체 클래스 인터페이스)를 내보내는 것을 보여 줍니다.

클라이언트 응용 프로그램과 MFC 확장 Dll은 모두 동일한 버전의 MFCxx.DLL를 사용 해야 합니다. MFC DLL의 규칙을 따르고 MFC 확장 DLL의 디버그 및 소매 (/release) 버전을 모두 제공 해야 합니다. 이렇게 하면 클라이언트 프로그램에서 응용 프로그램의 디버그 버전과 일반 정품 버전을 모두 빌드하고 모든 Dll의 적절 한 디버그 또는 일반 정품 버전으로 연결할 수 있습니다.

> [!NOTE]
> C + + 이름 및 내보내기 문제 때문에 다른 플랫폼에 대 한 dll과 dll의 디버그 및 일반 정품 버전 간에 MFC 확장명 DLL의 내보내기 목록이 다를 수 있습니다. 소매 MFCxx.DLL에는 2000 개의 내보낸 진입점이 있습니다. 디버그 MFCxxD.DLL에는 3000 개의 내보내진 진입점이 있습니다.

### <a name="quick-note-on-memory-management"></a>메모리 관리에 대 한 빠른 노트

이 기술 정보 뒷부분의 "메모리 관리" 섹션에서는 공유 버전의 MFC를 사용 하 여 MFCxx.DLL을 구현 하는 방법을 설명 합니다. MFC 확장 DLL을 구현 하기 위해 알아야 하는 정보는 여기에 설명 되어 있습니다.

클라이언트 응용 프로그램의 주소 공간에 로드 된 모든 MFC 확장 Dll은 같은 응용 프로그램에 있는 것 처럼 동일한 메모리 할당자, 리소스 로드 및 기타 MFC "전역" 상태를 사용 합니다. MFCxx.DLL 이는 mfc에 정적으로 연결 되는 비 MFC DLL 라이브러리와 일반 MFC Dll이 정확히 반대를 수행 하 고 각 DLL에서 자체 메모리 풀을 할당 하는 것 이기 때문에 중요 합니다.

MFC 확장 DLL에서 메모리를 할당 하는 경우 해당 메모리는 다른 응용 프로그램 할당 개체와 자유롭게 섞 수 있습니다. 또한 공유 MFC 라이브러리를 사용 하는 응용 프로그램이 충돌 하는 경우 운영 체제를 보호 하면 DLL을 공유 하는 다른 모든 MFC 응용 프로그램의 무결성이 유지 됩니다.

마찬가지로 리소스를 로드 하는 데 사용할 현재 실행 파일과 같은 다른 "전역" MFC 상태는 클라이언트 응용 프로그램과 모든 MFC 확장명 Dll과 MFCxx.DLL 자체에도 공유 됩니다.

### <a name="building-an-mfc-extension-dll"></a>MFC 확장 DLL 빌드

응용 프로그램 마법사를 사용 하 여 MFC 확장명 DLL 프로젝트를 만들 수 있으며, 적절 한 컴파일러 및 링커 설정이 자동으로 생성 됩니다. 또한 `DllMain` 수정할 수 있는 함수를 생성 했습니다.

기존 프로젝트를 MFC 확장명 DLL로 변환 하는 경우에는 공유 버전의 MFC를 사용 하 여 응용 프로그램을 빌드하기 위한 표준 규칙부터 시작 하 여 다음을 수행 합니다.

- 컴파일러 플래그에 **/D_AFXEXT** 를 추가 합니다. 프로젝트 속성 대화 상자에서 C/c + + 노드를 선택 합니다. 그런 다음 전처리기 범주를 선택 합니다. `_AFXEXT`각 항목을 세미콜론으로 구분 하 여 매크로 정의 필드에를 추가 합니다.

- **/Gy** 컴파일러 스위치를 제거 합니다. 프로젝트 속성 대화 상자에서 C/c + + 노드를 선택 합니다. 그런 다음 코드 생성 범주를 선택 합니다. "함수 수준 링크 사용" 옵션이 사용 하도록 설정 되어 있지 않은지 확인 합니다. 이렇게 하면 링커가 참조 되지 않은 함수를 제거 하지 않으므로 더 쉽게 클래스를 내보낼 수 있습니다. 원본 프로젝트를 사용 하 여 정적으로 MFC에 링크 된 기본 MFC DLL을 빌드하는 경우 **/mt [d]** 컴파일러 옵션을 **/md [d]** 로 변경 합니다.

- 링크를 위한 **/dll** 옵션을 사용 하 여 내보내기 라이브러리를 빌드합니다. 대상 유형으로 Win32 동적 연결 라이브러리를 지정 하 여 새 대상을 만들 때 설정 됩니다.

### <a name="changing-your-header-files"></a>헤더 파일 변경

MFC 확장 DLL의 목표는 일반적으로 해당 기능을 사용할 수 있는 하나 이상의 응용 프로그램에 몇 가지 일반적인 기능을 내보내는 것입니다. 이렇게 하면 클라이언트 응용 프로그램에 사용할 수 있는 클래스 및 전역 함수를 구축 수 있습니다.

이렇게 하려면 각 멤버 함수를 적절 하 게 가져오기 또는 내보내기로 표시 해야 합니다. 특수 선언이 필요 합니다. `__declspec(dllexport)` 및 `__declspec(dllimport)` . 클라이언트 응용 프로그램에서 클래스를 사용 하는 경우 클래스를로 선언 하려고 `__declspec(dllimport)` 합니다. MFC 확장 DLL 자체를 빌드하는 경우에는로 선언 해야 합니다 `__declspec(dllexport)` . 또한 클라이언트 프로그램이 로드 시 바인딩하는 함수는 실제로 내보내야 합니다.

전체 클래스를 내보내려면 `AFX_EXT_CLASS` 클래스 정의에서를 사용 합니다. 이 매크로는 및가 정의 될 때 프레임 워크에서 정의 `__declspec(dllexport)` `_AFXDLL` `_AFXEXT` 되지만 `__declspec(dllimport)` `_AFXEXT` 가 정의 되지 않은 경우로 정의 됩니다. `_AFXEXT`위에서 설명한 것 처럼는 MFC 확장명 DLL을 빌드할 때만 정의 됩니다. 예를 들면 다음과 같습니다.

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않음

클래스의 필요한 개별 멤버만 내보내려는 경우가 있습니다. 예를 들어 `CDialog` 파생 클래스를 내보내는 경우 생성자와 `DoModal` 호출만 내보내야 할 수 있습니다. DLL의를 사용 하 여 이러한 멤버를 내보낼 수 있습니다. .DEF 파일 이지만 내보내야 하는 `AFX_EXT_CLASS` 개별 멤버에 대해 거의 동일한 방법으로를 사용할 수도 있습니다.

예를 들면 다음과 같습니다.

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

이 작업을 수행 하면 클래스의 모든 멤버를 더 이상 내보내지 않으므로 추가 문제가 발생할 수 있습니다. 이 문제는 MFC 매크로의 작동 방식에 있습니다. 여러 MFC 도우미 매크로는 실제로 데이터 멤버를 선언하거나 정의합니다. 따라서 이러한 데이터 멤버는 DLL 에서도 내보내야 합니다.

예를 들어 DECLARE_DYNAMIC 매크로는 MFC 확장명 DLL을 빌드할 때 다음과 같이 정의 됩니다.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"정적"으로 시작 하는 줄은 `AFX_DATA` 클래스 내부에서 정적 개체를 선언 하는 것입니다. 이 클래스를 올바르게 내보내고 클라이언트에서 런타임 정보에 액세스 하는 것을 말합니다. EXE,이 정적 개체를 내보내야 합니다. 정적 개체는 한정자 `AFX_DATA`를 사용하여 선언되므로 `AFX_DATA`를 DLL을 빌드할 때 `__declspec(dllexport)`로 정의하고 클라이언트 실행 파일을 빌드할 때 `__declspec(dllimport)`로 정의하면 됩니다.

위에서 설명한 것 처럼 `AFX_EXT_CLASS` 는 이러한 방식으로 이미 정의 되어 있습니다. `AFX_DATA`클래스 정의와 동일 하 게 다시 정의 하기만 하면 됩니다 `AFX_EXT_CLASS` .

예를 들면 다음과 같습니다.

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

MFC는 항상 `AFX_DATA` 해당 매크로 내에서 정의 하는 데이터 항목에 대해 기호를 사용 하므로이 기술은 이러한 모든 시나리오에 적용 됩니다. 예를 들어 DECLARE_MESSAGE_MAP에 대해 작동 합니다.

> [!NOTE]
> 클래스의 일부 멤버가 아니라 전체 클래스를 내보내는 경우 정적 데이터 멤버가 자동으로 내보내집니다.

동일한 기술을 사용 하 여 `CArchive` DECLARE_SERIAL 및 IMPLEMENT_SERIAL 매크로를 사용 하는 클래스에 대 한 추출 연산자를 자동으로 내보낼 수 있습니다. 클래스 선언 (에 있음)을 bracketing 하 여 archive 연산자를 내보냅니다. H 파일)을 사용 하 여 다음 코드를 사용 합니다.

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT의 제한 사항

Mfc 확장 Dll의 여러 계층이 없는 경우 MFC 확장 Dll에 _**afxext.h** 전처리기 기호를 사용할 수 있습니다. MFC 클래스에서 파생되는 고유한 MFC 확장 DLL의 클래스를 호출하거나 해당 클래스에서 파생되는 MFC 확장 DLL이 있는 경우 모호성을 방지하기 위해 고유한 전처리기 기호를 사용해야 합니다.

문제는 Win32에서 데이터를 DLL에서 내보낸 것 처럼 명시적으로 선언 하 `__declspec(dllexport)` 고 `__declspec(dllimport)` dll에서 가져와야 하는 경우에 해당 합니다. 를 정의할 때 `_AFXEXT` MFC 헤더는 `AFX_EXT_CLASS` 가 올바르게 정의 되었는지 확인 합니다.

여러 계층이 있는 경우와 같은 하나의 기호 `AFX_EXT_CLASS` 는 충분 하지 않습니다. mfc 확장 dll은 새 클래스를 내보내고 다른 mfc 확장 dll에서 다른 클래스를 가져올 수 있기 때문입니다. 이 문제를 해결 하려면 dll 자체를 빌드하고 DLL을 사용 하는 것을 나타내는 특수 전처리기 기호를 사용 합니다. 예를 들어 두 개의 MFC 확장명 Dll, A.DLL 및 B.DLL를 생각해 보겠습니다. 각 클래스는 각각 .H 및 b. .H의 일부 클래스를 내보냅니다. B.DLL A.DLL의 클래스를 사용 합니다. 헤더 파일은 다음과 같습니다.

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

A.DLL 빌드 되 면 **/DA_IMPL** 으로 빌드되고 B.DLL 빌드 될 때 **/DB_IMPL**를 사용 하 여 빌드됩니다. 각 DLL에 대해 별도의 기호를 사용 하 여 CExampleB를 내보내고 B.DLL를 빌드할 때 CExampleA를 가져옵니다. CExampleA은 A.DLL를 빌드하고 B.DLL (또는 다른 클라이언트)에서 사용 될 때 가져올 때 내보내집니다.

기본 제공 `AFX_EXT_CLASS` 및 전처리기 기호를 사용 하는 경우이 유형의 계층화를 수행할 수 없습니다 `_AFXEXT` . 위에서 설명한 기법은 MFC 자체에서 OLE, 데이터베이스 및 네트워크 MFC 확장명 Dll을 빌드할 때 사용 하는 메커니즘과 달리이 문제를 해결 합니다.

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않음

전체 클래스를 내보내지 않는 경우에는 특별히 주의 해야 합니다. MFC 매크로를 통해 만든 필수 데이터 항목을 올바르게 내보낼지 확인 해야 합니다. 이 작업은 `AFX_DATA` 특정 클래스의 매크로에 다시 정의 하 여 수행할 수 있습니다. 전체 클래스를 내보내지 않는 경우에는 항상 이 작업을 수행해야 합니다.

예를 들어:

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

다음은 MFC 확장명 DLL의 기본 소스 파일에 입력 해야 하는 정확한 코드입니다. 이는 표준 포함 뒤에와 야 합니다. 응용 프로그램 마법사를 사용 하 여 MFC 확장명 DLL에 대 한 시작 파일을 만드는 경우에는를 제공 `DllMain` 합니다.

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

에 대 `AfxInitExtensionModule` 한 호출은 모듈 런타임 클래스 (구조체) 뿐만 아니라 개체 `CRuntimeClass` 팩터리 (개체)를 캡처하여 `COleObjectFactory` 나중에 개체를 만들 때 사용 합니다 `CDynLinkLibrary` . (선택 사항)에 대 한 호출을 `AfxTermExtensionModule` 통해 mfc `FreeLibrary` 확장 dll에서 각 프로세스가 분리 될 때 (프로세스가 종료 될 때 또는 호출 결과로 DLL이 언로드될 때 발생) MFC 확장 dll을 정리할 수 있습니다. 대부분의 MFC 확장명 Dll은 동적으로 로드 되지 않으므로 (일반적으로 해당 가져오기 라이브러리를 통해 연결 됨)에 대 한 호출은 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.

응용 프로그램이 MFC 확장명 Dll을 동적으로 로드 하 고 해제 하는 경우 `AfxTermExtensionModule` 위에 표시 된 대로를 호출 해야 합니다. 또한 `AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` 응용 프로그램에서 여러 스레드를 사용 하거나 MFC 확장명 DLL을 동적으로 로드 하는 경우 및 (Win32 함수 대신)를 사용 해야 합니다. `AfxLoadLibrary`및를 사용 하면 `AfxFreeLibrary` MFC 확장 DLL을 로드 하 고 언로드할 때 실행 되는 시작 및 종료 코드가 전역 mfc 상태를 손상 하지 않을 수 있습니다.

헤더 파일 AFXDLLX입니다. H에는 및에 대 한 정의와 같은 MFC 확장명 Dll에 사용 되는 구조에 대 한 특수 정의가 포함 되어 있습니다 `AFX_EXTENSION_MODULE` `CDynLinkLibrary` .

전역 *Extensiondll* 은 표시 된 대로 선언 해야 합니다. 16 비트 버전의 MFC와는 달리이 시간 동안에는 메모리를 할당 하 고 MFC 함수를 호출할 수 있습니다. MFCxx.DLL은가 호출 될 때 완전히 초기화 되기 때문입니다 `DllMain` .

### <a name="sharing-resources-and-classes"></a>리소스 및 클래스 공유

간단한 MFC 확장 Dll은 클라이언트 응용 프로그램에 대 한 저대역폭 함수를 몇 개만 내보내야 하며 더 이상 필요 하지 않습니다. 더 많은 사용자 인터페이스를 많이 사용 하는 Dll은 리소스 및 c + + 클래스를 클라이언트 응용 프로그램으로 내보낼 수 있습니다.

리소스 내보내기는 리소스 목록을 통해 수행됩니다. 각 응용 프로그램은 개체의 단일 연결 목록입니다 `CDynLinkLibrary` . 리소스를 찾을 때 리소스를 로드 하는 대부분의 표준 MFC 구현은 먼저 현재 리소스 모듈 ()에서 확인 `AfxGetResourceHandle` 하 고, 찾을 수 없는 경우 요청 된 리소스를 로드 하려고 시도 하는 개체 목록을 탐색 합니다 `CDynLinkLibrary` .

C + + 클래스 이름이 지정 된 경우에는 c + + 개체를 동적으로 만들 수 있습니다. MFC 개체 deserialization 메커니즘은 `CRuntimeClass` 이전에 저장 된 항목을 기반으로 필요한 형식의 c + + 개체를 동적으로 만들어 다시 생성할 수 있도록 모든 개체를 등록 해야 합니다.

클라이언트 응용 프로그램에서 MFC 확장명 DLL의 클래스를 사용 하도록 하려면 `DECLARE_SERIAL` 클라이언트 응용 프로그램에 표시 되도록 클래스를 내보내야 합니다. 이 작업은 목록을 탐색 하는 경우에도 수행 됩니다 `CDynLinkLibrary` .

MFC 고급 개념 샘플 [DLLHUSK](../overview/visual-cpp-samples.md)의 경우 목록은 다음과 같습니다.

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

일반적으로 MFCxx.DLL는 리소스 및 클래스 목록의 마지막입니다. 모든 표준 명령 Id에 대 한 프롬프트 문자열을 포함 하는 모든 표준 MFC 리소스를 포함 하 MFCxx.DLL입니다. 이를 목록의 끝 부분에 배치 하면 Dll과 클라이언트 응용 프로그램 자체에 고유한 표준 MFC 리소스 복사본이 포함 되지 않지만 MFCxx.DLL의 공유 리소스를 대신 사용 합니다.

모든 Dll의 리소스 및 클래스 이름을 클라이언트 응용 프로그램의 이름 공간에 병합 하는 경우 선택 하는 Id 또는 이름을 신중 하 게 선택 해야 한다는 단점이 있습니다. 물론 리소스 또는 `CDynLinkLibrary` 개체를 클라이언트 응용 프로그램으로 내보내는 것을 제외 하 고이 기능을 사용 하지 않도록 설정할 수 있습니다. [DLLHUSK](../overview/visual-cpp-samples.md) 샘플에서는 여러 헤더 파일을 사용하여 공유 리소스 이름 공간을 관리합니다. 공유 리소스 파일 사용에 대 한 자세한 팁은 [Technical Note 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 을 참조 하세요.

### <a name="initializing-the-dll"></a>DLL 초기화

위에서 설명한 것 처럼 일반적으로 `CDynLinkLibrary` 리소스와 클래스를 클라이언트 응용 프로그램으로 내보내기 위해 개체를 만들려고 합니다. DLL을 초기화 하려면 내보낸 진입점을 제공 해야 합니다. 최소는 인수를 사용 하지 않고 아무 것도 반환 하지 않는 void 루틴 이지만 원하는 모든 것이 될 수 있습니다.

이 방법을 사용 하는 경우 DLL을 사용 하려는 각 클라이언트 응용 프로그램에서이 초기화 루틴을 호출 해야 합니다. 를 `CDynLinkLibrary` 호출한 직후에이 개체를 할당할 수도 있습니다 `DllMain` `AfxInitExtensionModule` .

초기화 루틴은 `CDynLinkLibrary` MFC 확장명 DLL 정보에 연결 된 현재 응용 프로그램 힙에서 개체를 만들어야 합니다. 이 작업은 다음을 수행 하 여 수행할 수 있습니다.

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

이 예제에서 *InitXxxDLL* 루틴 이름은 원하는 모든 이름일 수 있습니다. **Extern "C"** 가 될 필요는 없지만 이렇게 하면 내보내기 목록을 더 쉽게 유지 관리할 수 있습니다.

> [!NOTE]
> 일반 MFC DLL에서 MFC 확장명 DLL을 사용 하는 경우이 초기화 함수를 내보내야 합니다. MFC 확장 DLL 클래스 또는 리소스를 사용 하기 전에 일반 MFC DLL에서이 함수를 호출 해야 합니다.

### <a name="exporting-entries"></a>항목 내보내기

클래스를 내보내는 간단한 방법은 `__declspec(dllimport)` `__declspec(dllexport)` 내보내고 싶은 각 클래스 및 전역 함수에서 및를 사용 하는 것입니다. 이렇게 하면 내보내는 함수를 보다 간단 하 게 제어 하 고 서 수로 함수를 내보낼 수 없기 때문에 각 진입점 (아래 설명 참조)의 이름을 지정 하는 것 보다 훨씬 더 효율적입니다. TESTDLL1 및 TESTDLL2이 메서드를 사용 하 여 해당 항목을 내보냅니다.

보다 효율적인 메서드 (및 MFCxx.DLL에 사용 되는 메서드)는에서 각 항목의 이름을 지정 하 여 각 항목을 직접 내보내는 것입니다. DEF 파일. DLL에서 선택적 내보내기를 내보내기 때문에 (즉, 모든 것이 아님) 내보내려는 특정 인터페이스를 결정 해야 합니다. 의 항목 형식으로 링커에 대 한 이름을 지정 해야 하므로이는 어렵습니다. DEF 파일. C + + 클래스에 대 한 바로 가기 링크를 반드시 포함 해야 하는 경우를 제외 하 고는 내보내지 마세요.

을 사용 하 여 c + + 클래스 내보내기를 시도한 경우 DEF 파일 이전에는이 목록을 자동으로 생성 하는 도구를 개발할 수 있습니다. 2 단계 링크 프로세스를 사용 하 여이 작업을 수행할 수 있습니다. 내보내기를 사용 하지 않고 DLL을 한 번 연결 하 고 링커가를 생성할 수 있도록 허용 합니다. 맵 파일. 여. 맵 파일을 사용 하 여 내보내야 하는 함수 목록을 생성할 수 있습니다. 따라서 일부 다시 정렬에서는에 대 한 내보내기 항목을 생성 하는 데 사용할 수 있습니다. DEF 파일. 이러한 프로세스를 사용 하 여 MFCxx.DLL 및 OLE 및 Database MFC 확장 Dll의 내보내기 목록이 생성 되었습니다 (완전히 자동이 지 않으며 한 번에 한 번의 손을 조정 해야 함).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp 및 그렇지 않으면 cdynlinklibrary

MFC 확장 DLL에는 `CWinApp` 자체의 파생 개체가 없으며 대신 `CWinApp` 클라이언트 응용 프로그램의 파생 개체를 사용 해야 합니다. 이는 클라이언트 응용 프로그램이 주 메시지 펌프, 유휴 루프 등을 소유 하 고 있음을 의미 합니다.

MFC 확장 DLL이 각 응용 프로그램에 대 한 추가 데이터를 유지 해야 하는 경우에서 새 클래스를 파생 하 `CDynLinkLibrary` 고 위의 InitXxxDLL 루틴에 설명 된 대로 만들 수 있습니다. DLL은 실행 하는 동안 현재 응용 프로그램의 개체 목록을 검사 `CDynLinkLibrary` 하 여 특정 MFC 확장명 DLL에 대 한 개체를 찾을 수 있습니다.

### <a name="using-resources-in-your-dll-implementation"></a>DLL 구현에서 리소스 사용

위에서 설명한 것 처럼 기본 리소스 로드는 `CDynLinkLibrary` 요청 된 리소스를 포함 하는 첫 번째 EXE 또는 DLL을 찾는 개체 목록을 살펴봅니다. 모든 MFC Api 뿐만 아니라 모든 내부 코드는를 사용 하 여 리소스 `AfxFindResourceHandle` 를 찾을 수 있는 위치에 관계 없이 리소스 목록을 탐색 합니다.

특정 위치 에서만 리소스를 로드 하려는 경우에는 Api를 사용 하 여 `AfxGetResourceHandle` `AfxSetResourceHandle` 이전 핸들을 저장 하 고 새 핸들을 설정 합니다. 클라이언트 애플리케이션으로 돌아가기 전에 이전 리소스 핸들을 복원해야 합니다. 샘플 TESTDLL2는이 방법을 사용 하 여 명시적으로 메뉴를 로드 합니다.

목록 검색은 약간 느리고 리소스 ID 범위를 관리해야 한다는 단점이 있습니다. 여러 MFC 확장 DLL에 연결하는 클라이언트 애플리케이션이 DLL 인스턴스 핸들을 지정하지 않고도 모든 DLL 제공 리소스를 사용할 수 있다는 장점도 있습니다. `AfxFindResourceHandle`은 리소스 목록을 검색하여 지정된 일치 항목을 찾는 데 사용되는 API입니다. 이 API는 리소스의 이름 및 형식을 사용하고 처음 발견된 리소스 핸들(또는 NULL)을 반환합니다.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL 버전을 사용 하는 응용 프로그램 작성

### <a name="application-requirements"></a>응용 프로그램 요구 사항

공유 버전의 MFC를 사용 하는 응용 프로그램은 몇 가지 간단한 규칙을 따라야 합니다.

- 개체를 포함 하 `CWinApp` 고 메시지 펌프에 대 한 표준 규칙을 따라야 합니다.

- 필요한 컴파일러 플래그 집합을 사용 하 여 컴파일해야 합니다 (아래 참조).

- Mfcxx.dll 가져오기 라이브러리와 연결 해야 합니다. MFC 헤더는 필요한 컴파일러 플래그를 설정 하 여 응용 프로그램을 연결 해야 하는 라이브러리를 링크 타임에 결정 합니다.

- 실행 파일을 실행 하려면 경로 또는 Windows 시스템 디렉터리에 MFCxx.DLL 해야 합니다.

### <a name="building-with-the-development-environment"></a>개발 환경으로 빌드

대부분의 표준 기본값을 사용 하 여 내부 메이크파일을 사용 하는 경우 프로젝트를 쉽게 변경 하 여 DLL 버전을 빌드할 수 있습니다.

다음 단계에서는 NAFXCWD.LIB에 연결 된 MFC 응용 프로그램이 올바르게 작동 하는 것으로 가정 합니다. LIB (디버그의 경우) 및 NAFXCW. LIB (정품)는 MFC 라이브러리의 공유 버전을 사용 하도록 변환 하려고 합니다. Visual C++ 환경을 실행 중 이며 내부 프로젝트 파일이 있습니다.

1. **프로젝트** 메뉴에서 **속성**을 클릭 합니다. **프로젝트 기본값**의 **일반** 페이지에서 공유 DLL (mfcxx.dll (d) .dll) **의 MFC를 사용** 하도록 Microsoft Foundation Classes를 설정 합니다.

### <a name="building-with-nmake"></a>NMAKE를 사용 하 여 빌드

Visual C++의 외부 메이크파일 기능을 사용 하거나 NMAKE를 직접 사용 하는 경우 컴파일러 및 링커 옵션을 지원 하도록 메이크파일을 편집 해야 합니다.

필요한 컴파일러 플래그:

- **/D_AFXDLL/MD** 
   **/D_AFXDLL**

표준 MFC 헤더를 정의 하려면이 기호가 필요 합니다.

- **/Md** 응용 프로그램은 C 런타임 라이브러리의 DLL 버전을 사용 해야 합니다.

다른 모든 컴파일러 플래그는 MFC 기본값 (예: 디버그 _DEBUG)을 따릅니다.

라이브러리의 링커 목록을 편집 합니다. NAFXCWD.LIB를 변경 합니다. LIB를 Mfcxxd.dll로 변경 하 고 NAFXCW를 변경 합니다. LIB Mfcxx.dll. LIBC를 바꿉니다. MSVCRT.LIB를 사용 하는 LIB. LIB. 다른 MFC 라이브러리와 마찬가지로 Mfcxxd.dll는 모든 C 런타임 라이브러리 **앞** 에 배치 해야 합니다.

필요에 따라 일반 정품 및 디버그 리소스 컴파일러 옵션 (실제로는 **/r**을 사용 하 여 리소스를 컴파일하는 옵션)을 추가 **/D_AFXDLL** 합니다. 이렇게 하면 MFC Dll에 있는 리소스를 공유 하 여 최종 실행 파일의 크기를 줄일 수 있습니다.

이러한 변경을 수행한 후에는 전체 다시 작성이 필요 합니다.

### <a name="building-the-samples"></a>예제 빌드

대부분의 MFC 샘플 프로그램은 명령줄에서 Visual C++ 또는 공유 NMAKE 호환 메이크파일의에서 빌드할 수 있습니다.

MFCxx.DLL를 사용 하도록 이러한 샘플을 변환 하려면를 로드 하면 됩니다. MAK 파일을 Visual C++ 하 고 위에서 설명한 대로 프로젝트 옵션을 설정 합니다. NMAKE 빌드를 사용 하는 경우 NMAKE 명령줄에서 "AFXDLL = 1"을 지정 하 고 공유 MFC 라이브러리를 사용 하 여 샘플을 빌드할 수 있습니다.

MFC 고급 개념 샘플 [DLLHUSK](../overview/visual-cpp-samples.md) 는 MFC의 DLL 버전을 사용 하 여 빌드됩니다. 이 샘플에서는 MFCxx.DLL와 연결 된 응용 프로그램을 빌드하는 방법을 보여 주지만이 기술 정보 뒷부분에서 설명 하는 MFC 확장명 Dll과 같은 MFC DLL 패키징 옵션의 다른 기능도 설명 합니다.

### <a name="packaging-notes"></a>패키징 정보

Dll의 일반 정품 버전 (Mfcxx.dll [U])입니다. DLL)을 자유롭게 재배포할 수 있습니다. Dll의 디버그 버전은 자유롭게 재배포할 수 없으며 응용 프로그램을 개발 하는 동안에만 사용 해야 합니다.

디버그 Dll은 디버깅 정보와 함께 제공 됩니다. Visual C++ 디버거를 사용 하 여 DLL 뿐만 아니라 응용 프로그램의 실행을 추적할 수 있습니다. 릴리스 Dll (Mfcxx.dll [U])입니다. DLL)에 디버깅 정보가 포함 되어 있지 않습니다.

Dll을 사용자 지정 하거나 다시 작성 하는 경우에는 MFC SRC 파일 MFCDLL "Mfcxx.dll" 이외의 항목을 호출 해야 합니다. MAK는 빌드 옵션을 설명 하 고 DLL의 이름을 바꾸기 위한 논리를 포함 합니다. 이러한 Dll은 여러 MFC 응용 프로그램에서 공유할 수 있으므로 파일의 이름을 변경 해야 합니다. 사용자 지정 버전의 MFC Dll이 시스템에 설치 된 버전을 바꾸면 공유 MFC Dll을 사용 하 여 다른 MFC 응용 프로그램이 손상 될 수 있습니다.

MFC Dll을 다시 빌드하는 것은 권장 되지 않습니다.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL 구현 방법

다음 섹션에서는 MFC DLL (MFCxx.DLL 및 MFCxxD.DLL)이 구현 되는 방법에 대해 설명 합니다. 여기서 설명 하는 세부 정보는 응용 프로그램에서 MFC DLL을 사용 하는 경우에도 중요 하지 않습니다. 여기에 나와 있는 세부 정보는 MFC 확장명 DLL을 작성 하는 방법을 이해 하는 데 반드시 필요한 것은 아니지만이 구현을 이해 하면 사용자 고유의 DLL을 작성할 수 있습니다.

### <a name="implementation-overview"></a>구현 개요

MFC DLL은 위에서 설명한 대로 MFC 확장명 DLL의 특별 한 경우입니다. 이 클래스에는 다 수의 클래스에 대 한 내보내기가 매우 많습니다. MFC DLL에서 몇 가지 추가 작업을 수행 하 여 일반 MFC 확장명 DLL 보다 훨씬 더 특수 하 게 만들 수 있습니다.

### <a name="win32-does-most-of-the-work"></a>Win32는 대부분의 작업을 수행 합니다.

16 비트 버전의 MFC에는 스택 세그먼트에 앱 별 데이터, 일부 80x86 어셈블리 코드에서 만든 특수 세그먼트, 프로세스별 예외 컨텍스트 및 기타 기법을 비롯 한 다양 한 특수 기술이 필요 합니다. Win32는 DLL에서 프로세스별 데이터를 직접 지원 합니다 .이는 대부분의 시간을 원하는 것입니다. MFCxx.DLL 가장 많은 부분은 단순히 NAFXCW입니다. DLL로 패키지 된 LIB. MFC 소스 코드를 살펴보면 몇 가지 특별 한 사례를 수행 해야 하기 때문에 _AFXDLL #ifdef 매우 적습니다. 특별 한 경우는 Windows 3.1 (Win32s 라고도 함)에서 Win32를 처리 하는 것입니다. Win32s는 프로세스별 DLL 데이터를 직접 지원 하지 않으므로 MFC DLL은 TLS (스레드 로컬 저장소) Win32 Api를 사용 하 여 프로세스 로컬 데이터를 가져와야 합니다.

### <a name="impact-on-library-sources-additional-files"></a>라이브러리 소스에 미치는 영향, 추가 파일

정상적인 MFC 클래스 라이브러리 소스와 헤더에 **_AFXDLL** 버전의 영향은 비교적 적습니다. 특수 버전 파일이 있습니다 (AFXV_DLL. H) 뿐만 아니라 추가 헤더 파일 (AFXDLL_. H)를 제공 합니다. H 헤더입니다. AFXDLL_입니다. H 헤더에는 `CDynLinkLibrary` `_AFXDLL` 응용 프로그램과 MFC 확장 dll의 클래스 및 기타 구현 정보가 포함 됩니다. AFXDLLX입니다. MFC 확장 Dll을 빌드하기 위한 H 헤더가 제공 됩니다 (자세한 내용은 위 참조).

MFC SRC의 MFC 라이브러리에 대 한 일반 소스에는 #ifdef 아래에 몇 가지 추가 조건부 코드가 있습니다 `_AFXDLL` . 추가 소스 파일 (DLLINIT. CPP)에는 MFC의 공유 버전에 대 한 추가 DLL 초기화 코드 및 기타 붙이기가 포함 되어 있습니다.

공유 버전의 MFC를 빌드하기 위해 추가 파일이 제공 됩니다. DLL을 빌드하는 방법에 대 한 자세한 내용은 아래를 참조 하십시오.

- 두. .DEF 파일은 디버그 (Mfcxxd.dll) 및 릴리스 (Mfcxx.dll) 버전의 DLL에 대 한 MFC DLL 진입점을 내보내는 데 사용 됩니다.

- 하면. RC 파일 (MFCDLL. RC)에는 모든 표준 MFC 리소스 및 DLL에 대 한 VERSIONINFO 리소스가 포함 되어 있습니다.

- 은. CLW 파일 (MFCDLL. CLW)를 제공 하 여 클래스 마법사를 사용 하 여 MFC 클래스를 탐색할 수 있습니다. 참고:이 기능은 MFC의 DLL 버전에만 해당 되는 것은 아닙니다.

### <a name="memory-management"></a>메모리 관리

MFCxx.DLL를 사용 하는 응용 프로그램은 공유 C 런타임 DLL MSVCRTxx.DLL에서 제공 하는 공통 메모리 할당자를 사용 합니다. Mfc Dll 뿐만 아니라 응용 프로그램은이 공유 메모리 할당자를 사용 합니다. MFC Dll은 메모리 할당을 위해 공유 DLL을 사용 하 여 나중에 응용 프로그램에서 해제 하거나 그 반대로 메모리를 할당할 수 있습니다. 응용 프로그램과 DLL은 모두 동일한 할당자를 사용 해야 하므로 c + + 전역 **operator new** 또는 **operator delete**를 재정의 하면 안 됩니다. C 런타임 메모리 할당 루틴 (예: **malloc**, **realloc**, **free**및 기타)의 나머지 부분에도 동일한 규칙이 적용 됩니다.

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>서 수가 며 클래스 __declspec (dllexport) 및 DLL 이름 지정

`class` **`__declspec(dllexport)`** C + + 컴파일러의 기능은 사용 하지 않습니다. 대신, 내보내기 목록이 클래스 라이브러리 소스 (Mfcxx.dll 및 Mfcxxd.dll)에 포함 됩니다. 이러한 선택 진입점 (함수 및 데이터) 집합만 내보내집니다. MFC private 구현 함수 또는 클래스와 같은 다른 기호는 내보내지 않습니다. 모든 내보내기 작업은 상주 하거나 상주 하지 않는 이름 테이블에 문자열 이름이 없는 서 수로 수행 됩니다.

`class` **`__declspec(dllexport)`** 는 작은 dll을 빌드하는 데 사용할 수 있는 대안이 될 수 있지만 MFC와 같은 대기업의 경우 기본 내보내기 메커니즘의 효율성과 용량 제한이 있습니다.

즉, 대부분의 실행 이나 로드 속도를 손상 시 키 지 않으면 서 800 KB에 불과합니다. 릴리스 MFCxx.DLL 많은 양의 기능을 패키지할 수 있습니다. 이 기법을 사용 하지 않은 MFCxx.DLL은 10만 더 큽니다. 이를 통해의 끝에 진입점을 더 추가할 수 있습니다. 서 수로 내보내는 속도 및 크기 효율성을 손상 시 키 지 않고 단순한 버전 관리를 허용 하는 DEF 파일입니다. MFC 클래스 라이브러리의 주 버전 수정 버전은 라이브러리 이름을 변경 합니다. 즉, MFC30.DLL는 MFC 클래스 라이브러리 버전 3.0을 포함 하는 재배포 가능 DLL입니다. 이 DLL을 업그레이드 하는 경우 (예를 들어, 가상의 MFC 3.1에서는 대신 DLL의 이름이 MFC31.DLL. Mfc DLL의 사용자 지정 버전을 생성 하도록 MFC 소스 코드를 수정 하는 경우에는 다른 이름 (이름에 "MFC"가 없는 경우)을 사용 합니다.

## <a name="see-also"></a>참고 항목

[번호로 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
