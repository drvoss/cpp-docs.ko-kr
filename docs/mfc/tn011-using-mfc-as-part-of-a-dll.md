---
title: 'TN011: DLL의 일부로 MFC 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 0f4d4e2ed76a0fa5f8f775345fc672a1df055a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370433"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: DLL의 일부로 MFC 사용

이 노트에서는 MFC 라이브러리를 Windows 동적 링크 라이브러리(DLL)의 일부로 사용할 수 있는 일반 MFC DLL에 대해 설명합니다. Windows DLL과 Windows DLL을 빌드하는 방법에 대해 잘 알고 있다고 가정합니다. MFC 라이브러리에 대한 확장을 만들 수 있는 MFC 확장 DLL에 대한 자세한 내용은 [MFC의 DLL 버전을](../mfc/tn033-dll-version-of-mfc.md)참조하십시오.

## <a name="dll-interfaces"></a>DLL 인터페이스

일반 MFC DLL은 응용 프로그램과 DLL 간의 인터페이스가 C와 유사한 함수 또는 명시적으로 내보낸 클래스에 지정된다고 가정합니다. MFC 클래스 인터페이스를 내보낼 수 없습니다.

DLL과 응용 프로그램 모두 MFC를 사용하려는 경우 둘 다 MFC 라이브러리의 공유 버전을 사용하거나 라이브러리의 복사본에 정적으로 연결할 수 있습니다. 응용 프로그램과 DLL은 모두 MFC 라이브러리의 표준 버전 중 하나를 사용할 수 있습니다.

일반 MFC DLL에는 다음과 같은 몇 가지 장점이 있습니다.

- DLL을 사용하는 응용 프로그램은 MFC를 사용할 필요가 없으며 Visual C++ 응용 프로그램일 필요는 없습니다.

- MFC에 정적으로 연결되는 일반 MFC DLL의 경우 DLL의 크기는 사용 및 연결된 MFC 및 C 런타임 루틴에만 따라 달라집니다.

- MFC에 동적으로 연결되는 일반 MFC DLL을 사용하면 공유 버전의 MFC를 사용하여 메모리를 절약하는 것이 중요할 수 있습니다. 그러나 공유\<DLL, Mfc*버전*>.dll 및 Msvvcrt\<*버전*> DLL을 DLL과 배포해야 합니다.

- DLL 디자인은 클래스가 구현되는 방식과 는 독립적입니다. DLL 설계는 원하는 API에만 내보전됩니다. 따라서 구현이 변경되는 경우 일반 MFC DLL은 여전히 유효합니다.

- MFC에 정적으로 연결되는 일반 MFC DLL을 사용하면 DLL과 응용 프로그램 모두 MFC를 사용하는 경우 DLL과 다른 버전의 MFC를 원하는 응용 프로그램에 문제가 없습니다. MFC 라이브러리는 각 DLL 또는 EXE에 정적으로 연결되어 있으므로 어떤 버전이 있는지에 대한 의문이 없습니다.

## <a name="api-limitations"></a>API 제한 사항

일부 MFC 기능은 기술적 제한또는 일반적으로 응용 프로그램에서 제공되기 때문에 DLL 버전에는 적용되지 않습니다. 현재 버전의 MFC에서는 적용할 수 없는 유일한 `CWinApp::SetDialogBkColor`함수가 있습니다.

## <a name="building-your-dll"></a>DLL 구축

MFC에 정적으로 연결되는 일반 MFC DLL을 컴파일할 `_USRDLL` `_WINDLL` 때는 기호를 정의해야 합니다. DLL 코드도 다음 컴파일러 스위치로 컴파일해야 합니다.

- **/D_WINDLL** 컴파일이 DLL에 대한 임을 의미합니다.

- **/D_USRDLL** 일반 MFC DLL을 구축하고 있음을 명시합니다.

또한 이러한 기호를 정의하고 MFC에 동적으로 연결되는 일반 MFC DLL을 컴파일할 때 이러한 컴파일러 스위치를 사용해야 합니다. 또한 기호를 `_AFXDLL` 정의해야 하며 DLL 코드를 다음과 같이 컴파일해야 합니다.

- **/D_AFXDLL** 동적으로 MFC에 연결되는 일반 MFC DLL을 빌드하고 있음을 지정합니다.

응용 프로그램과 DLL 사이의 인터페이스(API)를 명시적으로 내보내야 합니다. 인터페이스를 낮은 대역폭으로 정의하고 할 수 있는 경우 C 인터페이스만 사용하는 것이 좋습니다. 직접 C 인터페이스는 보다 복잡한 C++ 클래스보다 유지 관리가 더 쉽습니다.

C 및 C++ 파일 모두에서 포함할 수 있는 별도의 헤더에 API를 배치합니다. MFC 고급 개념 샘플 [DLLScreenCap의](../overview/visual-cpp-samples.md) 헤더 ScreenCap.h를 참조하십시오. 함수를 내보내려면 모듈 정의 `EXPORTS` 파일의 섹션에 함수를 입력합니다( DEF) 또는 `__declspec(dllexport)` 함수 정의에 포함할 수 있습니다. 이러한 `__declspec(dllimport)` 함수를 클라이언트 실행 기능으로 가져오는 데 사용합니다.

MFC에 동적으로 연결되는 일반 MFC DLL에서 내보낸 모든 함수의 시작 부분에 AFX_MANAGE_STATE 매크로를 추가해야 합니다. 이 매크로는 현재 모듈 상태를 DLL의 모듈 상태로 설정합니다. 이 매크로를 사용하려면 DLL에서 내보낸 함수의 시작 부분에 다음 코드 줄을 추가합니다.

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>윈메인 -> dllMain

MFC 라이브러리는 일반적인 MFC `DllMain` 응용 프로그램에서와 같이 [CWinApp](../mfc/reference/cwinapp-class.md) 파생 개체를 초기화하는 표준 Win32 진입점을 정의합니다. 일반적인 MFC 응용 프로그램에서와 같이 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 메서드에 모든 DLL 관련 초기화를 배치합니다.

응용 프로그램이 주 메시지 펌프를 소유하므로 [CWinApp::실행](../mfc/reference/cwinapp-class.md#run) 메커니즘은 DLL에 적용되지 않습니다. DLL이 모덜리스 대화 상자를 표시하거나 자체 의 주 프레임 창이 있는 경우 응용 프로그램의 주 메시지 펌프는 [CWinApp::PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage)를 호출하는 DLL 내보낸 루틴을 호출해야 합니다.

이 기능을 사용하려면 DLLScreenCap 샘플을 참조하십시오.

MFC가 제공하는 함수는 `DllMain` DLL이 언로드되기 `CWinApp` 전에 파생된 클래스의 [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 메서드를 호출합니다.

## <a name="linking-your-dll"></a>DLL 연결

MFC에 정적으로 연결되는 일반 MFC DLL을 사용하면 DLL을 Nafxcwd.lib 또는 Nafxcw.lib와 Libcmt.lib라는 C 런타임 버전과 연결해야 합니다. 이러한 라이브러리는 미리 빌드되며 Visual C++ 설정을 실행할 때 라이브러리를 지정하여 설치할 수 있습니다.

## <a name="sample-code"></a>샘플 코드

전체 샘플은 MFC 고급 개념 샘플 프로그램 DLLScreenCap을 참조하십시오. 이 샘플에서 주의해야 할 몇 가지 흥미로운 사항은 다음과 같습니다.

- DLL의 컴파일러 플래그와 응용 프로그램의 플래그는 다릅니다.

- 링크 선 및 . DLL및 응용 프로그램에 대한 DEF 파일은 다릅니다.

- DLL을 사용하는 응용 프로그램은 C++에 있을 필요가 없습니다.

- 응용 프로그램과 DLL 사이의 인터페이스는 C 또는 C++에서 사용할 수 있으며 DLLScreenCap.def로 내보내는 API입니다.

다음 예제에서는 MFC에 정적으로 연결되는 일반 MFC DLL에 정의된 API를 보여 줍니다. 이 예제에서는 C++ 사용자를 `extern "C" { }` 위한 블록에 선언이 동봉됩니다. 이 에는 몇 가지 장점이 있습니다. 첫째, C++ 이외의 클라이언트 응용 프로그램에서 DLL API를 사용할 수 있습니다. 둘째, C++ 이름 mangling내보낸 이름에 적용 되지 않습니다 때문에 DLL 오버 헤드를 줄일 수 있습니다. 마지막으로 에 명시적으로 추가하는 것이 더 쉬워집니다. 이름 문글살에 대해 걱정할 필요 없이 DEF 파일(서수 내보내기용).

```cpp
#ifdef __cplusplus
extern "C" {
#endif  /* __cplusplus */

struct TracerData
{
    BOOL bEnabled;
    UINT flags;
};

BOOL PromptTraceFlags(TracerData FAR* lpData);

#ifdef __cplusplus
}
#endif
```

API에서 사용되는 구조는 MFC 클래스에서 파생되지 않으며 API 헤더에 정의됩니다. 이렇게 하면 DLL과 응용 프로그램 간의 인터페이스가 복잡해지고 C 프로그램에서 DLL을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
