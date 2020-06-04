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
ms.openlocfilehash: ad4cb883cfe7e397cf599d659afb02b23501dc5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370321"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC의 DLL 버전

이 참고에서는 MFC 응용 프로그램 및 MFC 확장 DLL과 공유 동적 링크 라이브러리를 사용하는 MFCxx.DLL 및 MFCxxD.DLL(x는 MFC 버전 번호)을 사용하는 방법에 대해 설명합니다. 일반 MFC DLL에 대한 자세한 내용은 [MFC를 DLL의 일부로 사용하여](../mfc/tn011-using-mfc-as-part-of-a-dll.md)참조하세요.

이 기술 노트에서는 DLL의 세 가지 측면을 다룹니다. 마지막 두 고급 사용자를 위한 것입니다.

- [MFC 확장 DLL을 빌드하는 방법](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC의 DLL 버전을 사용하는 MFC 응용 프로그램을 빌드하는 방법](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC 공유 동적 링크 라이브러리 구현 방법](#_mfcnotes_how_the_mfc30.dll_is_implemented)

MFC가 아닌 응용 프로그램과 함께 사용할 수 있는 MFC를 사용하여 DLL을 빌드하려는 경우 기술 [참고 11을](../mfc/tn011-using-mfc-as-part-of-a-dll.md)참조하십시오.

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL 지원 개요: 용어 및 파일

**일반 MFC DLL**: 일반 MFC DLL을 사용하여 일부 MFC 클래스를 사용하여 독립 실행형 DLL을 빌드합니다. 앱/DLL 경계를 가로지르는 인터페이스는 "C" 인터페이스이며 클라이언트 응용 프로그램이 MFC 응용 프로그램일 필요는 없습니다.

MFC 1.0에서 지원되는 DLL 지원 버전입니다. 기술 노트 [11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 및 MFC 고급 개념 샘플 [DLLScreenCap에](../overview/visual-cpp-samples.md)설명되어 있습니다.

> [!NOTE]
> Visual C++ 버전 4.0에서 **USRDLL이라는** 용어는 더 이상 사용되지 않으며 MFC에 정적으로 연결되는 일반 MFC DLL로 대체되었습니다. MFC에 동적으로 연결되는 일반 MFC DLL을 빌드할 수도 있습니다.

MFC 3.0 이상은 OLE 및 데이터베이스 클래스를 포함한 모든 새로운 기능을 갖춘 일반 MFC DLL을 지원합니다.

**AFXDLL**: MFC 라이브러리의 공유 버전이라고도 합니다. MFC 2.0에 추가된 새로운 DLL 지원입니다. MFC 라이브러리 자체는 여러 DLL(아래에 설명)에 있으며 클라이언트 응용 프로그램 또는 DLL은 필요한 DLL을 동적으로 연결합니다. 응용 프로그램/DLL 경계를 가로지르는 인터페이스는 C++/MFC 클래스 인터페이스입니다. 클라이언트 응용 프로그램은 MFC 응용 프로그램이어야 합니다. 이는 모든 MFC 3.0 기능을 지원합니다(예외: UNICODE는 데이터베이스 클래스에 대해 지원되지 않음).

> [!NOTE]
> Visual C++ 버전 4.0에서 이러한 유형의 DLL을 "확장 DLL"이라고 합니다.

이 참고는 MFCxx.DLL을 사용하여 다음을 포함하는 전체 MFC DLL 집합을 참조합니다.

- 디버그: MFCxxD.DLL(결합) 및 MFCSxxD.LIB(정적).

- 릴리스: MFCxx.DLL(결합) 및 MFCSxx.LIB(정적).

- 유니코드 디버그: MFCxxUD.DLL(결합) 및 MFCSxxD.LIB(정적).

- 유니코드 릴리스: MFcCxxU.DLL(결합) 및 MFCSxxU.LIB(정적).

> [!NOTE]
> The MFCSxx[U][D]. LIB 라이브러리는 MFC 공유 DLL과 함께 사용됩니다. 이러한 라이브러리에는 응용 프로그램 또는 DLL에 정적으로 연결해야 하는 코드가 포함되어 있습니다.

응용 프로그램은 해당 가져오기 라이브러리에 연결됩니다.

- 디버그: MFCxxD.LIB

- 릴리스: MFCxx.LIB

- 유니코드 디버그: MFCxxUD.LIB

- 유니코드 릴리스: MFCxxU.LIB

"MFC 확장 DLL"은 MFCxx.DLL(및/또는 다른 MFC 공유 DLL)에 구축된 DLL입니다. 여기서 MFC 구성 요소 아키텍처가 시작됩니다. MFC 클래스에서 유용한 클래스를 파생하거나 다른 MFC와 같은 도구 키트를 빌드하는 경우 DLL에 배치할 수 있습니다. 이 DLL은 궁극적인 클라이언트 응용 프로그램과 마찬가지로 MFCxx.DLL을 사용합니다. 이렇게 하면 재사용 가능한 리프 클래스, 재사용 가능한 기본 클래스 및 재사용 가능한 보기/문서 클래스가 허용됩니다.

## <a name="pros-and-cons"></a>장점과 단점

MFC의 공유 버전을 사용해야 하는 이유

- 공유 라이브러리를 사용하면 응용 프로그램이 작아질 수 있습니다(대부분의 MFC 라이브러리를 사용하는 최소 응용 프로그램은 10K 미만임).

- MFC의 공유 버전은 MFC 확장 DLL 및 일반 MFC DLL을 지원합니다.

- 공유 MFC 라이브러리를 사용하는 응용 프로그램을 빌드하는 것은 MFC 자체를 연결할 필요가 없기 때문에 정적으로 연결된 MFC 응용 프로그램을 빌드하는 것보다 빠릅니다. 이는 링커가 디버그 정보를 압축해야 하는 **DEBUG** 빌드에서 특히 그렇습니다 .

MFC의 공유 버전을 사용하지 않아야 하는 이유는 다음과 같은 것입니다.

- 공유 라이브러리를 사용하는 응용 프로그램을 배송하려면 프로그램과 함께 MFCxx.DLL(및 기타) 라이브러리를 배송해야 합니다. MFCxx.DLL은 많은 DLL처럼 자유롭게 재배포할 수 있지만 설치 프로그램에 DLL을 설치해야 합니다. 또한 프로그램 및 MFC DLL 자체에서 모두 사용되는 C 런타임 라이브러리가 포함된 MSVCRTxx.DLL을 제공해야 합니다.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC 확장 DLL을 작성하는 방법

MFC 확장 DLL은 MFC 클래스의 기능을 꾸미기 위해 작성된 클래스와 함수를 포함하는 DLL입니다. MFC 확장 DLL은 몇 가지 추가 고려 사항과 함께 응용 프로그램에서 사용하는 것과 동일한 방식으로 공유 MFC DLL을 사용합니다.

- 빌드 프로세스는 몇 가지 추가 컴파일러 및 링커 옵션을 사용하여 공유 MFC 라이브러리를 사용하는 응용 프로그램을 빌드하는 것과 유사합니다.

- MFC 확장 DLL에는 -derived 클래스가 `CWinApp`없습니다.

- MFC 확장 DLL은 특별한 `DllMain`을 제공해야 합니다. AppWizard는 `DllMain` 수정할 수 있는 함수를 제공합니다.

- MFC 확장 DLL은 일반적으로 MFC 확장 `CDynLinkLibrary` DLL이 응용 프로그램에 es `CRuntimeClass`또는 리소스를 내보내려는 경우 를 만드는 초기화 루틴을 제공합니다. MFC 확장 `CDynLinkLibrary` DLL에 의해 애플리케이션별 데이터를 유지 관리해야 하는 경우 파생클래스가 사용될 수 있다.

이러한 고려 사항은 아래에 자세히 설명되어 있습니다. MFC 고급 개념 샘플 [DLLHUSK는](../overview/visual-cpp-samples.md) 다음을 보여 주므로 참조해야 합니다.

- 공유 라이브러리를 사용하여 응용 프로그램을 빌드합니다. (DLLHUSK. EXE는 MFC 라이브러리및 다른 DLL에 동적으로 연결되는 MFC 응용 프로그램입니다.

- MFC 확장 DLL 구축. (MFC 확장 DLL을 빌드하는 데 사용되는 특수 `_AFXEXT` 플래그를 참고하십시오.)

- MFC 확장 DLL의 두 가지 예입니다. 하나는 제한된 내보내기(TESTDLL1)가 있는 MFC 확장 DLL의 기본 구조를 보여주고 다른 하나는 전체 클래스 인터페이스(TESTDLL2)를 내보내는 것을 보여줍니다.

클라이언트 응용 프로그램과 MFC 확장 DLL 은 모두 동일한 버전의 MFCxx.DLL을 사용해야 합니다. MFC DLL의 규칙을 따르고 MFC 확장 DLL의 디버그 및 정품(/release) 버전을 모두 제공해야 합니다. 이를 통해 클라이언트 프로그램은 응용 프로그램의 디버그 및 소매 버전을 모두 빌드하고 모든 DLL의 적절한 디버그 또는 소매 버전과 연결할 수 있습니다.

> [!NOTE]
> C++ 이름 mangling 및 내보내기 문제 때문에 MFC 확장 DLL의 내보내기 목록은 다른 플랫폼에 대해 동일한 DLL 및 DLL의 디버그 버전과 소매 버전 간에 다를 수 있습니다. 소매 MFCxx.DLL에는 약 2000 개의 수출 진입점이 있습니다. 디버그 MFCxxD.DLL에는 약 3,000개의 내보낸 진입점이 있습니다.

### <a name="quick-note-on-memory-management"></a>메모리 관리에 대한 간략한 참고 사항

이 기술 노트의 끝 부분에 있는 "메모리 관리" 섹션에서는 MFC의 공유 버전으로 MFCxx.DLL의 구현에 대해 설명합니다. MFC 확장 DLL만 구현하는 데 필요한 정보는 여기에 설명되어 있습니다.

MFCxx.DLL 및 클라이언트 응용 프로그램의 주소 공간에 로드된 모든 MFC 확장 DLL은 동일한 응용 프로그램에 있는 것처럼 동일한 메모리 할당자, 리소스 로드 및 기타 MFC "전역" 상태를 사용합니다. MFC에 정적으로 연결되는 비 MFC DLL 라이브러리와 일반 MFC DLL은 정반대를 수행하며 각 DLL이 자체 메모리 풀에서 할당되기 때문에 중요합니다.

MFC 확장 DLL이 메모리를 할당하는 경우 해당 메모리는 다른 응용 프로그램에서 할당된 개체와 자유롭게 혼합할 수 있습니다. 또한 공유 MFC 라이브러리를 사용하는 응용 프로그램이 충돌하는 경우 운영 체제의 보호는 DLL을 공유하는 다른 MFC 응용 프로그램의 무결성을 유지합니다.

마찬가지로 리소스를 로드하는 현재 실행 파일과 같은 다른 "전역" MFC 상태도 클라이언트 응용 프로그램과 모든 MFC 확장자 DLL 및 MFCxx.DLL 자체 간에 공유됩니다.

### <a name="building-an-mfc-extension-dll"></a>MFC 확장 DLL 구축

AppWizard를 사용하여 MFC 확장 DLL 프로젝트를 만들 수 있으며 적절한 컴파일러 및 링커 설정을 자동으로 생성합니다. 또한 수정할 `DllMain` 수 있는 함수를 생성했습니다.

기존 프로젝트를 MFC 확장 DLL로 변환하는 경우 MFC의 공유 버전을 사용하여 응용 프로그램을 빌드하기 위한 표준 규칙으로 시작한 다음 수행합니다.

- 컴파일러 플래그에 **/D_AFXEXT** 추가합니다. 프로젝트 속성 대화 상자에서 C/C++ 노드를 선택합니다. 그런 다음 프리프로세서 범주를 선택합니다. 매크로 `_AFXEXT` 정의 필드에 추가하여 각 항목을 세미콜론으로 구분합니다.

- **/Gy** 컴파일러 스위치를 제거합니다. 프로젝트 속성 대화 상자에서 C/C++ 노드를 선택합니다. 그런 다음 코드 생성 범주를 선택합니다. "기능 수준 연결 사용" 옵션을 사용할 수 없습니다. 이렇게 하면 링커가 참조되지 않은 함수를 제거하지 않으므로 클래스를 더 쉽게 내보낼 수 있습니다. 원래 프로젝트가 MFC에 정적으로 연결된 일반 MFC DLL을 빌드하는 데 사용되는 경우 **/MT[d]** 컴파일러 옵션을 **/MD[d]로**변경합니다.

- **LINK에 /DLL** 옵션을 사용하여 내보내기 라이브러리를 빌드합니다. Win32 동적 링크 라이브러리를 대상 유형으로 지정하여 새 대상을 만들 때 이 설정이 설정됩니다.

### <a name="changing-your-header-files"></a>헤더 파일 변경

MFC 확장 DLL의 목표는 일반적으로 해당 기능을 사용할 수 있는 하나 이상의 응용 프로그램에 몇 가지 일반적인 기능을 내보내는 것입니다. 이는 클라이언트 응용 프로그램에 사용할 수 있는 클래스 및 전역 함수내보내기로 요약됩니다.

이렇게 하려면 각 멤버 함수가 가져오기 또는 내보내기로 적절하게 표시되어 있는지 확인해야 합니다. 이렇게 하려면 특별한 `__declspec(dllexport)` 선언이 `__declspec(dllimport)`필요합니다. 클라이언트 응용 프로그램에서 클래스를 사용하는 경우 클래스를 로 `__declspec(dllimport)`선언하려고 합니다. MFC 확장 DLL 자체가 빌드될 때 는 `__declspec(dllexport)`로 선언되어야 합니다. 또한 클라이언트 프로그램이 로드 시 바인딩되도록 함수를 실제로 내보내야 합니다.

전체 클래스를 내보내려면 클래스 정의에서 사용합니다. `AFX_EXT_CLASS` 이 매크로는 프레임워크에 `__declspec(dllexport)` 의해 `_AFXDLL` `_AFXEXT` 정의될 때와 `__declspec(dllimport)` 정의되지만 정의되지 않은 경우로 `_AFXEXT` 정의됩니다. `_AFXEXT`위에서 설명한 대로 MFC 확장 DLL을 빌드할 때만 정의됩니다. 다음은 그 예입니다.

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않음

경우에 따라 클래스의 필요한 개별 멤버만 내보낼 수 있습니다. 예를 들어 -derived 클래스를 `CDialog`내보내는 경우 생성자와 `DoModal` 호출만 내보내야 할 수 있습니다. DLL의 을 사용하여 이러한 멤버를 내보낼 수 있습니다. DEF 파일이지만 내보내야 `AFX_EXT_CLASS` 하는 개별 멤버에서 거의 동일한 방식으로 사용할 수도 있습니다.

다음은 그 예입니다.

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

이렇게 하면 더 이상 클래스의 모든 멤버를 내보내지 않기 때문에 추가 문제가 발생할 수 있습니다. 문제는 MFC 매크로가 작동하는 방식입니다. MFC의 도우미 매크로 중 일부는 실제로 데이터 멤버를 선언하거나 정의합니다. 따라서 이러한 데이터 멤버는 DLL에서 내보내야 합니다.

예를 들어 mFC 확장 DLL을 빌드할 때 DECLARE_DYNAMIC 매크로는 다음과 같이 정의됩니다.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"정적"으로 `AFX_DATA`시작하는 줄은 클래스 내부의 정적 개체를 선언하는 것입니다. 이 클래스를 올바르게 내보내고 클라이언트의 런타임 정보에 액세스하려면 . EXE에서는 이 정적 개체를 내보내야 합니다. 정적 `AFX_DATA`개체는 수정자와 함께 선언되므로 `AFX_DATA` DLL을 작성할 `__declspec(dllexport)` 때 정의하고 클라이언트 실행 `__declspec(dllimport)` 파일을 작성할 때로 정의하기만 하면 됩니다.

위에서 설명한 `AFX_EXT_CLASS` 바와 같이, 이미 이런 식으로 정의되어 있다. 클래스 정의와 동일하게 `AFX_DATA` `AFX_EXT_CLASS` 다시 정의하기만 하면 됩니다.

다음은 그 예입니다.

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

MFC는 `AFX_DATA` 항상 매크로 내에서 정의하는 데이터 항목에 기호를 사용하므로 이 기술은 이러한 모든 시나리오에서 작동합니다. 예를 들어, 그것은 DECLARE_MESSAGE_MAP 위해 작동합니다.

> [!NOTE]
> 클래스의 선택된 멤버가 아닌 전체 클래스를 내보내는 경우 정적 데이터 멤버가 자동으로 내보내됩니다.

동일한 기술을 사용하여 DECLARE_SERIAL 및 IMPLEMENT_SERIAL `CArchive` 매크로를 사용하는 클래스에 대해 추출 연산자내보내기를 자동으로 내보낼 수 있습니다. 클래스 선언을 괄호로 묶고 아카이브 연산자 내보내기(에 있는) H 파일)과 다음 코드:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT 제한 사항

MFC 확장 DLL의 여러 계층이 없는 한 MFC 확장 DLL에 **_AFXEXT** 사전 프로세서 기호를 사용할 수 있습니다. MFC 클래스에서 파생된 고유한 MFC 확장 DLL의 클래스에서 호출하거나 파생되는 MFC 확장 DLL이 있는 경우 모호성을 피하기 위해 자체 프로세서 기호를 사용해야 합니다.

문제는 Win32에서 DLL에서 내보낼 `__declspec(dllexport)` 것처럼 모든 데이터를 명시적으로 선언해야 하며 `__declspec(dllimport)` DLL에서 가져올 경우 명시적으로 선언해야 한다는 것입니다. 를 정의할 `_AFXEXT`때 MFC `AFX_EXT_CLASS` 헤더는 올바르게 정의되었는지 확인합니다.

여러 레이어가 있는 경우 MFC 확장 `AFX_EXT_CLASS` DLL이 새 클래스를 내보내고 다른 MFC 확장 DLL에서 다른 클래스를 가져올 수 있으므로 한 기호가 충분하지 않습니다. 이 문제를 해결하려면 DLL 자체를 빌드하는 것과 DLL을 사용하는 것을 나타내는 특수 전처리기 기호를 사용합니다. 예를 들어 두 개의 MFC 확장 DLL, A.DLL 및 B.DLL을 가정해 보겠습니다. 각각 A.H와 B.H의 일부 클래스를 내보냅니다. B.DLL은 A.DLL의 클래스를 사용합니다. 헤더 파일은 다음과 같습니다.

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

A.DLL이 구축되면 **/DA_IMPL** 내장되고 B.DLL이 구축되면 **/DB_IMPL.** 각 DLL에 대해 별도의 기호를 사용하여 CExampleB를 내보내고 B.DLL을 작성할 때 CExampleA를 가져옵니다. CExampleA는 A.DLL을 빌드할 때 내보내고 B.DLL(또는 다른 클라이언트)에서 사용할 때 가져옵니다.

기본 제공 `AFX_EXT_CLASS` 및 `_AFXEXT` 전처리자 기호를 사용할 때는 이러한 유형의 계층화를 수행할 수 없습니다. 위에서 설명한 기술은 OLE, 데이터베이스 및 네트워크 MFC 확장 DLL을 빌드할 때 MFC 자체가 사용하는 메커니즘과 달리 이 문제를 해결합니다.

### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않음

다시 말하지만, 전체 클래스를 내보내지 않을 때는 특별한주의를 기울여야합니다. MFC 매크로에서 만든 필요한 데이터 항목을 올바르게 내보내야 합니다. 이 작업은 특정 클래스의 `AFX_DATA` 매크로를 다시 정의하여 수행할 수 있습니다. 이 작업은 전체 클래스를 내보내지 않을 때마다 수행해야 합니다.

다음은 그 예입니다.

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

다음은 MFC 확장 DLL의 주 소스 파일에 배치해야 하는 정확한 코드입니다. 그것은 표준이 포함 된 후에 와야한다. AppWizard를 사용하여 MFC 확장자 DLL에 대한 시작 파일을 `DllMain` 만들 면 A가 제공됩니다.

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

`AfxInitExtensionModule` 모듈 런타임 클래스(구조체)와`CRuntimeClass` 개체를 나중에 사용할`COleObjectFactory` `CDynLinkLibrary` 개체 팩터리(개체)를 캡처하는 호출입니다. MFC 확장 DLL에서 각 프로세스가 분리될 때(프로세스가 종료될 때 또는 `AfxTermExtensionModule` `FreeLibrary` 호출로 인해 DLL이 언로드될 때 발생하는) MFC 확장 DLL을 정리할 수 있는 (선택 사항) 호출을 허용합니다. 대부분의 MFC 확장 DLL은 동적으로 로드되지 않으므로(일반적으로 가져오기 라이브러리를 `AfxTermExtensionModule` 통해 연결됨) 호출은 일반적으로 필요하지 않습니다.

응용 프로그램이 MFC 확장 DLL을 동적으로 로드하고 `AfxTermExtensionModule` 해제하는 경우 위와 같이 호출해야 합니다. 또한 응용 프로그램이 `AfxLoadLibrary` `AfxFreeLibrary` 여러 스레드를 `LoadLibrary` 사용하거나 MFC 확장 DLL을 동적으로 로드하는 경우 Win32 함수 및 (Win32 함수 대신)을 `FreeLibrary`사용해야 합니다. MFC `AfxFreeLibrary` 확장 DLL을 로드하고 언로드할 때 실행되는 시작 및 종료 코드가 전역 MFC 상태를 손상시키지 않도록 합니다. `AfxLoadLibrary`

헤더 파일 AFXDLLX. H에는 에 대한 정의와 `AFX_EXTENSION_MODULE` `CDynLinkLibrary`같은 MFC 확장 DLL에 사용되는 구조에 대한 특수 정의가 포함되어 있습니다.

전역 *확장DLL은* 그림과 같이 선언되어야 합니다. MFC의 16비트 버전과 달리 MFCxx.DLL이 호출될 때까지 완전히 초기화되므로 이 시간 동안 메모리를 할당하고 MFC 함수를 호출할 수 있습니다. `DllMain`

### <a name="sharing-resources-and-classes"></a>리소스 및 수업 공유

간단한 MFC 확장 DLL은 클라이언트 응용 프로그램에 몇 가지 저대역폭 함수만 내보낼 필요가 있습니다. 더 많은 사용자 인터페이스 집약적인 DLL은 리소스 및 C++ 클래스를 클라이언트 응용 프로그램으로 내보낼 수 있습니다.

리소스 내보내기는 리소스 목록을 통해 수행됩니다. 각 응용 프로그램에서 개체의 개별적으로 `CDynLinkLibrary` 연결된 목록입니다. 리소스를 찾을 때 리소스를 로드하는 대부분의 표준 MFC 구현은 현재`AfxGetResourceHandle`리소스 모듈()을 먼저 `CDynLinkLibrary` 살펴보고 찾지 못하면 요청된 리소스를 로드하려는 개체 목록을 살펴봅니다.

C++ 클래스 이름이 지정된 C++ 개체의 동적 생성은 비슷합니다. MFC 개체 직렬화 메커니즘은 이전에 `CRuntimeClass` 저장된 내용에 따라 필요한 형식의 C++ 개체를 동적으로 만들어 재구성할 수 있도록 모든 개체를 등록해야 합니다.

클라이언트 응용 프로그램이 MFC 확장 DLL의 `DECLARE_SERIAL`클래스를 사용하도록 하려면 클래스를 클라이언트 응용 프로그램에 표시하려면 클래스를 내보내야 합니다. 이것은 또한 목록을 걷는 `CDynLinkLibrary` 것으로 수행됩니다.

MFC 고급 개념 샘플 [DLLHUSK의](../overview/visual-cpp-samples.md)경우 목록은 다음과 같습니다.

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

MFCxx.DLL은 일반적으로 리소스 및 클래스 목록에서 마지막입니다. MFCxx.DLL에는 모든 표준 명령 IS에 대한 프롬프트 문자열을 포함하여 모든 표준 MFC 리소스가 포함됩니다. 목록의 꼬리에 배치하면 DLL과 클라이언트 응용 프로그램 자체가 표준 MFC 리소스의 자체 복사본을 갖지 않고 대신 MFCxx.DLL의 공유 리소스에 의존할 수 있습니다.

모든 DLL의 리소스와 클래스 이름을 클라이언트 응용 프로그램의 이름 공간에 병합하면 선택한 ID나 이름을 주의해야 하는 단점이 있습니다. 물론 리소스 또는 개체를 `CDynLinkLibrary` 클라이언트 응용 프로그램에 내보내지 않음으로써 이 기능을 비활성화할 수 있습니다. [DLLHUSK](../overview/visual-cpp-samples.md) 샘플은 여러 헤더 파일을 사용하여 공유 리소스 이름 공간을 관리합니다. 공유 리소스 파일 사용에 대한 자세한 내용은 [기술 참고 35를](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 참조하십시오.

### <a name="initializing-the-dll"></a>DLL 초기화

위에서 언급했듯이 일반적으로 리소스 및 `CDynLinkLibrary` 클래스를 클라이언트 응용 프로그램으로 내보내기 위해 개체를 만들려고 합니다. DLL을 초기화하려면 내보낸 진입점을 제공해야 합니다. 최소한, 이것은 인수를 취하지 않고 아무 것도 반환하지 않는 void 루틴이지만 원하는 것이 될 수 있습니다.

DLL을 사용하려는 각 클라이언트 응용 프로그램은 이 방법을 사용하는 경우 이 초기화 루틴을 호출해야 합니다. 호출 `AfxInitExtensionModule`직후에 이 `CDynLinkLibrary` 개체를 `DllMain` 할당할 수도 있습니다.

초기화 루틴은 MFC 확장 DLL 정보에 연결된 현재 응용 프로그램의 힙에 `CDynLinkLibrary` 개체를 만들어야 합니다. 이 작업은 다음과 같은 작업을 수행할 수 있습니다.

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

이 예제의 루틴 *이름InitXxxDLL은* 원하는 모든 이름일 수 있습니다. **외종 "C"일**필요는 없지만 이렇게 하면 내보내기 목록을 쉽게 유지 관리할 수 있습니다.

> [!NOTE]
> 일반 MFC DLL에서 MFC 확장 DLL을 사용하는 경우 이 초기화 함수를 내보내야 합니다. 이 함수는 MFC 확장 DLL 클래스 또는 리소스를 사용하기 전에 일반 MFC DLL에서 호출해야 합니다.

### <a name="exporting-entries"></a>항목 내보내기

클래스를 내보내는 간단한 방법은 `__declspec(dllimport)` 내보낼 각 클래스 및 `__declspec(dllexport)` 글로벌 함수를 사용하는 것입니다. 이렇게 하면 훨씬 쉬워지지만 내보낼 함수를 덜 제어할 수 있고 서수로 함수를 내보낼 수 없으므로 각 진입점(아래에 설명)의 이름을 지정하는 것보다 효율이 떨어집니다. TESTDLL1 및 TESTDLL2는 이 메서드를 사용하여 항목을 내보냅니다.

보다 효율적인 방법(및 MFCxx.DLL에서 사용하는 방법)은 의 각 항목에 이름을 지정하여 각 항목을 직접 내보내는 것입니다. DEF 파일. 우리는 우리의 DLL에서 선택적 수출을 수출하기 때문에 (즉, 모든 것이 아닙니다), 우리는 우리가 내보낼 특정 인터페이스를 결정해야합니다. 의 항목 형식으로 링커에 손상된 이름을 지정해야 하므로 이 방법은 어렵습니다. DEF 파일. C++ 클래스에 대한 기호 링크가 있어야 하지 않는 한 내보내지 마십시오.

을 사용 해 경우 C++ 클래스를 내보내기를 시도했습니다. 이전에 DEF 파일을 사용하여 이 목록을 자동으로 생성하는 도구를 개발할 수 있습니다. 이 작업은 2단계 링크 프로세스를 사용하여 수행할 수 있습니다. 내보내기 없이 DLL을 한 번 연결하고 링커가 을 생성하도록 허용합니다. MAP 파일. Tthe. MAP 파일을 사용하여 내보내야 하는 함수 목록을 생성할 수 있으므로 일부 재배열을 사용하면 에 대한 EXPORT 항목을 생성하는 데 사용할 수 있습니다. DEF 파일. MFCxx.DLL 및 OLE 및 데이터베이스 MFC 확장 DLL에 대한 내보내기 목록은 수천 개의 수의 DLL을 사용하여 생성되었습니다(완전히 자동이 아니며 가끔씩 일부 수동 조정이 필요하지만).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs. CDynLink라이브러리

MFC 확장 DLL에는 자체 `CWinApp`-파생 개체가 없습니다. 대신 클라이언트 응용 `CWinApp`프로그램의 -derived 개체와 함께 작동 해야 합니다. 즉, 클라이언트 응용 프로그램이 주 메시지 펌프, 유휴 루프 등을 소유합니다.

MFC 확장 DLL각 응용 프로그램에 대 한 추가 데이터를 유지 `CDynLinkLibrary` 관리 해야 하는 경우 에서 새 클래스를 파생 하 고 위에서 설명하는 InitXxxDLL 루틴에서 만들 수 있습니다. 실행 중인 경우 DLL은 현재 응용 프로그램의 `CDynLinkLibrary` 개체 목록을 확인하여 특정 MFC 확장 DLL에 대한 개체목록을 찾을 수 있습니다.

### <a name="using-resources-in-your-dll-implementation"></a>DLL 구현에서 리소스 사용

위에서 언급했듯이 기본 리소스 로드는 요청된 리소스가 있는 첫 번째 EXE 또는 DLL을 찾는 `CDynLinkLibrary` 개체 목록을 안내합니다. 모든 MFC API와 모든 내부 코드는 `AfxFindResourceHandle` 리소스 목록을 걸어서 리소스가 어디에 있든 상관없이 리소스를 찾습니다.

특정 위치에서만 리소스를 로드하려면 API를 `AfxGetResourceHandle` 사용하고 이전 `AfxSetResourceHandle` 핸들을 저장하고 새 핸들을 설정합니다. 클라이언트 응용 프로그램으로 돌아가기 전에 이전 리소스 핸들을 복원해야 합니다. 샘플 TESTDLL2는 메뉴를 명시적으로 로드하기 위해 이 방법을 사용합니다.

목록을 걷는 것은 약간 느리고 리소스 ID 범위를 관리해야 한다는 단점이 있습니다. 여러 MFC 확장 DLL에 연결하는 클라이언트 응용 프로그램은 DLL 인스턴스 핸들을 지정하지 않고도 DLL에서 제공한 리소스를 사용할 수 있다는 장점이 있습니다. `AfxFindResourceHandle`는 리소스 목록을 보행하여 지정된 일치 를 찾는 데 사용되는 API입니다. 리소스의 이름과 형식을 가져와 처음 찾은 리소스 핸들(또는 NULL)을 반환합니다.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL 버전을 사용하는 응용 프로그램 작성

### <a name="application-requirements"></a>응용 프로그램 요구 사항

MFC의 공유 버전을 사용하는 응용 프로그램은 몇 가지 간단한 규칙을 따라야 합니다.

- 개체가 `CWinApp` 있어야 하며 메시지 펌프의 표준 규칙을 따라야 합니다.

- 필요한 컴파일러 플래그 집합으로 컴파일해야 합니다(아래 참조).

- MFCxx 가져오기 라이브러리와 연결해야 합니다. 필요한 컴파일러 플래그를 설정하여 MFC 헤더는 링크 시 응용 프로그램이 연결해야 하는 라이브러리를 결정합니다.

- 실행 을 실행하려면 MFCxx.DLL이 경로 또는 Windows 시스템 디렉터리에 있어야 합니다.

### <a name="building-with-the-development-environment"></a>개발 환경구축

대부분의 표준 기본값으로 내부 메이크파일을 사용하는 경우 프로젝트를 쉽게 변경하여 DLL 버전을 빌드할 수 있습니다.

다음 단계에서는 NAFXCWD에 연결된 올바르게 작동하는 MFC 응용 프로그램이 있다고 가정합니다. LIB(디버그용) 및 NAFXCW. LIB(소매용)를 변환하여 MFC 라이브러리의 공유 버전을 사용하도록 변환하려고 합니다. Visual C++ 환경을 실행하고 있으며 내부 프로젝트 파일이 있습니다.

1. **프로젝트** 메뉴에서 **속성**을 클릭합니다. 프로젝트 기본값 아래의 **일반** 페이지에서 공유 DLL(MFCxx(d).dll)에서 **MFC를 사용하도록** Microsoft 기초 클래스를 **설정합니다.**

### <a name="building-with-nmake"></a>NMAKE와 건물

Visual C++의 외부 메이크파일 기능을 사용하거나 NMAKE를 직접 사용하는 경우 컴파일러 및 링커 옵션을 지원하도록 makefile파일을 편집해야 합니다.

필수 컴파일러 플래그:

- **/D_AFXDLL/MD/D_AFXDLL**
   **/D_AFXDLL**

표준 MFC 헤더를 정의하려면 이 기호가 필요합니다.

- **/MD** 응용 프로그램은 C 런타임 라이브러리의 DLL 버전을 사용해야 합니다.

다른 모든 컴파일러 플래그는 MFC 기본값(예: 디버그의 경우 _DEBUG)을 따릅니다.

라이브러리의 링커 목록을 편집합니다. NAFXCWD를 변경합니다. LIB에서 MFCxxD.LIB로 전환하고 NAFXCW를 변경합니다. Lib에서 MFCxx.LIB로 이동합니다. LIBC를 교체합니다. MSVCRT와 LIB. Lib. 다른 MFC 라이브러리와 마찬가지로 MFCxxD.LIB는 C 런타임 라이브러리 **앞에** 배치하는 것이 중요합니다.

선택적으로 소매 및 디버그 리소스 컴파일러 **옵션(/R로**리소스를 실제로 컴파일하는 옵션)에 **/D_AFXDLL** 추가합니다. 이렇게 하면 MFC DLL에 있는 리소스를 공유하여 최종 실행 파일이 작아집니다.

이러한 변경 이 후에는 전체 재생성이 필요합니다.

### <a name="building-the-samples"></a>예제 빌드

대부분의 MFC 샘플 프로그램은 Visual C++또는 명령줄에서 공유NMAKE 호환 MAKEFILE에서 빌드할 수 있습니다.

이러한 샘플을 MFCxx.DLL을 사용하도록 변환하려면 을 로드할 수 있습니다. MAK 파일을 시각적 C++에 넣고 위에서 설명한 대로 프로젝트 옵션을 설정합니다. NMAKE 빌드를 사용하는 경우 NMAKE 명령줄에 "AFXDLL=1"을 지정하고 공유 MFC 라이브러리를 사용하여 샘플을 빌드할 수 있습니다.

MFC 고급 개념 샘플 [DLLHUSK는](../overview/visual-cpp-samples.md) MFC의 DLL 버전으로 구축되었습니다. 이 샘플에서는 MFCxx.DLL과 연결된 응용 프로그램을 빌드하는 방법을 보여 줄 뿐만 아니라 이 기술 노트의 후반부에서 설명하는 MFC 확장 DLL DLL과 같은 MFC DLL 패키징 옵션의 다른 기능도 보여 줍니다.

### <a name="packaging-notes"></a>패키징 노트

DLL(MFCxx[U]의 정품 버전입니다. DLL)은 자유롭게 재배포할 수 있습니다. DLL의 디버그 버전은 자유롭게 재배포할 수 없으며 응용 프로그램을 개발하는 동안에만 사용해야 합니다.

디버그 DLL에는 디버깅 정보가 제공됩니다. Visual C++ 디버거를 사용하면 DLL뿐만 아니라 응용 프로그램의 실행을 추적할 수 있습니다. 릴리즈 DLL(MFCxx[U]) DLL) 디버깅 정보가 포함되어 있지 않습니다.

DLL을 사용자 지정하거나 다시 빌드하는 경우 MFC SRC 파일 MFCDLL "MFCxx" 이외의 것을 호출해야 합니다. MAK는 빌드 옵션을 설명하고 DLL 이름을 바꾸기 위한 논리를 포함합니다. 이러한 DLL은 잠재적으로 많은 MFC 응용 프로그램에서 공유되므로 파일 이름을 변경해야 합니다. 사용자 지정 버전의 MFC DLL을 시스템에 설치한 MFC DLL을 대체하면 공유 MFC DLL을 사용하여 다른 MFC 응용 프로그램이 중단될 수 있습니다.

MFC DLL을 다시 빌드하는 것은 권장되지 않습니다.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL 구현 방법

다음 섹션에서는 MFC DLL(MFCxx.DLL 및 MFCxxD.DLL)이 구현되는 방법에 대해 설명합니다. 응용 프로그램과 함께 MFC DLL을 사용하는 것만 하면 여기에 대한 세부 정보를 이해하는 것도 중요하지 않습니다. 여기서 세부 정보는 MFC 확장 DLL을 작성하는 방법을 이해하는 데 필수적이지는 않지만 이 구현을 이해하면 사용자 고유의 DLL을 작성하는 데 도움이 될 수 있습니다.

### <a name="implementation-overview"></a>구현 개요

MFC DLL은 위에서 설명한 대로 MFC 확장 DLL의 특별한 경우입니다. 그것은 클래스의 큰 숫자에 대한 수출의 매우 큰 숫자를 가지고있다. MFC DLL에는 일반 MFC 확장 DLL보다 훨씬 더 특별하게 만드는 몇 가지 추가 사항이 있습니다.

### <a name="win32-does-most-of-the-work"></a>Win32는 대부분의 작업을 수행합니다.

MFC의 16비트 버전에는 스택 세그먼트의 앱당 데이터, 일부 80x86 어셈블리 코드에서 만든 특수 세그먼트, 프로세스별 예외 컨텍스트 및 기타 기술을 비롯한 여러 가지 특수 기술이 필요했습니다. Win32는 DLL에서 프로세스별 데이터를 직접 지원하므로 대부분의 시간을 원하는 것입니다. 대부분의 경우 MFCxx.DLL은 NAFXCW입니다. Lib는 DLL에 포장됩니다. MFC 소스 코드를 보면 특별한 경우는 거의 없기 때문에 _AFXDLL #ifdef 거의 없습니다. 특히 Windows 3.1에서 Win32를 처리하는 특수 한 경우 (그렇지 않으면 Win32s라고함). Win32s는 프로세스당 DLL 데이터를 직접 지원하지 않으므로 MFC DLL은 TLS(스레드 로컬 저장소) Win32 API를 사용하여 프로세스 로컬 데이터를 가져와야 합니다.

### <a name="impact-on-library-sources-additional-files"></a>라이브러리 소스, 추가 파일에 미치는 영향

**_AFXDLL** 버전이 일반 MFC 클래스 라이브러리 원본 및 헤더에 미치는 영향은 비교적 미미합니다. 특수 버전 파일(AFXV_DLL 있습니다. H) 뿐만 아니라 추가 헤더 파일 (AFXDLL_. H) 메인 AFXWIN에 의해 포함되어 있습니다. H 헤더. The AFXDLL_. H 헤더에는 `CDynLinkLibrary` `_AFXDLL` 응용 프로그램과 MFC 확장 DLL의 클래스 및 기타 구현 세부 정보가 포함됩니다. The AFXDLLX. H 헤더는 MFC 확장 DLL을 구축하기 위해 제공됩니다 (자세한 내용은 위 참조).

MFC SRC의 MFC 라이브러리에 대한 일반 소스에는 `_AFXDLL` #ifdef 따라 몇 가지 추가 조건부 코드가 있습니다. 추가 소스 파일(DLLINIT. CPP)에는 MFC의 공유 버전에 대한 추가 DLL 초기화 코드 및 기타 접착제가 포함되어 있습니다.

MFC의 공유 버전을 빌드하기 위해 추가 파일이 제공됩니다. DLL을 빌드하는 방법에 대한 자세한 내용은 아래를 참조하십시오.

- 두. DEF 파일은 DLL의 디버그(MFCxxD.DEF) 및 릴리스(MFCxx.DEF) 버전에 대한 MFC DLL 진입점을 내보내는 데 사용됩니다.

- . RC 파일(MFCDLL) RC)에는 DLL에 대한 모든 표준 MFC 리소스와 VERSIONINFO 리소스가 포함되어 있습니다.

- . CLW 파일(MFCDLL) CLW)는 클래스 위저드를 사용하여 MFC 클래스를 탐색할 수 있도록 제공됩니다. 참고: 이 기능은 MFC의 DLL 버전에만 해당되지 않습니다.

### <a name="memory-management"></a>메모리 관리

MFCxx.DLL을 사용하는 응용 프로그램은 공유 C 런타임 DLL인 MSVCRTxx.DLL에서 제공하는 공통 메모리 할당을 사용합니다. 응용 프로그램, 모든 MFC 확장 DLL 및 MFC DLL 자체는 이 공유 메모리 할당을 사용합니다. 메모리 할당에 공유 DLL을 사용하면 MFC DLL은 나중에 응용 프로그램에서 해제된 메모리를 할당하거나 그 반대의 경우도 마찬가지입니다. 응용 프로그램과 DLL 모두 동일한 할당을 사용해야 하므로 C++ 전역 **연산자 new** 또는 **연산자 delete를**재정의해서는 안 됩니다. C 런타임 메모리 할당 루틴의 나머지 부분에도 동일한 규칙이 적용됩니다(예: **malloc,** **realloc,** **free**및 기타).

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>서수 및 클래스 __declspec(dllexport) 및 DLL 이름 지정

C++ 컴파일러의 `class` **__declspec(dllexport)** 기능은 사용하지 않습니다. 대신 내보내기 목록이 클래스 라이브러리 원본(MFCxx.DEF 및 MFCxxD.DEF)에 포함됩니다. 이러한 선택된 진입점 집합(함수 및 데이터)만 내보내됩니다. MFC 개인 구현 함수 또는 클래스와 같은 다른 기호는 내보내기되지 않습니다 모든 내보내기는 상주 또는 비상주 이름 테이블에 문자열 이름없이 서수로 수행됩니다.

`class` **__declspec(dllexport)를** 사용하는 것은 더 작은 DLL을 구축하는 데 사용할 수 있는 대안일 수 있지만 MFC와 같은 대규모 DLL의 경우 기본 내보내기 메커니즘에는 효율성 과 용량 제한이 있습니다.

이 모든 것이 의미하는 바는 많은 실행이나 로딩 속도를 저하시키지 않으면서 약 800KB에 불과한 MFCxx.DLL 릴리스에서 많은 양의 기능을 패키징할 수 있다는 것입니다. 이 기술을 사용하지 않았다면 MFCxx.DLL은 100K 더 커졌을 것입니다. 이렇게 하면 의 끝에 추가 진입점을 추가할 수도 있습니다. DEF 파일은 서수에 의해 내보내기의 속도와 크기 효율성을 손상시키지 않고 간단한 버전 관리할 수 있습니다. MFC 클래스 라이브러리의 주 버전 개정은 라이브러리 이름을 변경합니다. 즉, MFC30입니다. DLL은 MFC 클래스 라이브러리의 버전 3.0을 포함하는 재배포 가능한 DLL입니다. 이 DLL의 업그레이드는 가상의 MFC 3.1에서 DLL의 이름이 MFC31이라고 합니다. 대신 DLL. 다시 말하지만 MFC 소스 코드를 수정하여 MFC DLL의 사용자 지정 버전을 생성하는 경우 다른 이름(이름에 "MFC"가 없는 경우)을 사용합니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
