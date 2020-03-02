---
title: MFC DLL에 대 한 질문과 대답
ms.date: 05/06/2019
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 9108aaf3fcface847b0391455a2aecd4d45658c4
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220942"
---
# <a name="dll-frequently-asked-questions"></a>DLL 관련 질문과 대답

다음은 DLL에 대한 몇 가지 질문과 대답(FAQ)입니다.

- [MFC DLL이 여러 스레드를 만들 수 있습니까?](#mfc_multithreaded_1)

- [다중 스레드 응용 프로그램을 서로 다른 스레드에서 MFC DLL에 액세스할 수 있습니까?](#mfc_multithreaded_2)

- [MFC DLL에서 사용할 수 없는 MFC 클래스 또는 함수가 있습니까?](#mfc_prohibited_classes)

- [로드 시 클라이언트 응용 프로그램의 성능을 향상 시키려면 어떤 최적화 기술을 사용 해야 합니까?](#mfc_optimization)

- [기본 MFC DLL에 메모리 누수 있지만 내 코드에 문제가 있습니다. 메모리 누수는 어떻게 찾을 수 있습니까?](#memory_leak)

## <a name="mfc_multithreaded_1"></a> MFC DLL이 여러 스레드를 만들 수 있습니까?

초기화하는 동안을 제외하고 MFC DLL은 **TlsAlloc**과 같은 Win32 스레드 로컬 저장소(TLS) 기능을 사용하여 스레드 로컬 저장소를 할당하는 한 여러 스레드를 안전하게 만들 수 있습니다. 그러나 MFC DLL이 **__declspec (thread)** 를 사용하여 스레드 로컬 저장소를 할당하는 경우 클라이언트 응용 프로그램은 DLL에 암시적으로 연결되어야 합니다. 클라이언트 응용 프로그램이 명시적으로 DLL에 연결하면 **LoadLibrary**에 대한 호출이 DLL을 성공적으로 로드하지 못합니다. DLL의 스레드 로컬 변수에 대한 자세한 내용은 [스레드](../cpp/thread.md)를 참조하세요.

시작하는 동안 새 MFC 스레드를 만드는 MFC DLL은 응용 프로그램에서 로드할 때 응답을 중지합니다. 여기에는 다음의 내부에서 `AfxBeginThread` 또는 `CWinThread::CreateThread`를 호출하여 스레드가 생성될 때마다가 포함됩니다.

- 합니다 `InitInstance` 의 `CWinApp`-파생 된 기본 MFC DLL에는 개체입니다.

- 제공 된 `DllMain` 나 **RawDllMain** 기본 MFC DLL의 함수입니다.

- 제공 된 `DllMain` 나 **RawDllMain** MFC 확장 DLL의에서 함수입니다.

## <a name="mfc_multithreaded_2"></a> 다중 스레드 응용 프로그램을 서로 다른 스레드에서 MFC DLL에 액세스할 수 있습니까?

다중 스레드 응용 프로그램에는 서로 다른 여러 스레드에서 MFC에 동적으로 연결 된 기본 MFC Dll 및 MFC 확장명 Dll 액세스할 수 있습니다. 응용 프로그램에는 응용 프로그램에서 생성 하는 여러 스레드에서 정적으로 MFC에 링크는 기본 MFC Dll에 액세스할 수 있습니다.

## <a name="mfc_prohibited_classes"></a> ? 모든 MFC 클래스 또는 MFC DLL에서 사용할 수 없는 함수

확장 Dll 사용의 `CWinApp`-클라이언트 응용 프로그램의 클래스를 파생 합니다. 포함 하지 않아야 자신의 `CWinApp`-클래스를 파생 합니다.

기본 MFC Dll 있어야를 `CWinApp`-파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체 처럼 MFC 응용 프로그램입니다. 와 달리 합니다 `CWinApp` 응용 프로그램의 개체는 `CWinApp` DLL의 개체는 기본 메시지 펌프가 없습니다.

`CWinApp::Run` 메커니즘은 DLL에 적용되지 않으므로 응용 프로그램은 기본 메시지 펌프를 소유합니다. DLL이 모덜리스 대화 상자를 열거나 자체의 메인 프레임 창이 있는 경우 응용 프로그램의 기본 메시지 펌프는 DLL에서 내보낸 루틴을 호출해야 하며, 이 루틴은 DLL 응용 프로그램 개체의 `CWinApp::PreTranslateMessage` 멤버 함수를 호출합니다.

## <a name="mfc_optimization"></a> 어떤 최적화 기술을 사용 해야 하는 클라이언트 응용 프로그램을 개선 하기 위해&#39;를 로드할 때 s 성능이?

DLL이 MFC 일반 변경에 정적으로 연결 된 기본 MFC DLL을 MFC에 동적으로 연결 되는 MFC DLL 파일 크기를 줄입니다.

DLL에 내보내기 함수가 많은 경우 함수를 내보내려면.def 파일을 사용 (사용 하는 대신 **__declspec (dllexport)** ).def 파일을 사용 하 여 [NONAME 특성](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) 각 함수를 내보냅니다. NONAME 특성 파일 크기를 줄일 수 있는 DLL의 내보내기 테이블에 저장할 함수 이름이 아닌 서 수 값을 사용 하면 됩니다.

응용 프로그램에 암시적으로 링크된 DLL은 응용 프로그램이 로드될 때 로드됩니다. 로드 시 성능을 향상시키려면 DLL을 다른 DLL로 나누어 보세요. 로드한 후 즉시 호출 응용 프로그램에 필요한 모든 함수 및 호출 응용 프로그램을 하나의 DLL에 넣고 호출 응용 프로그램을 암시적으로 해당 DLL에 링크합니다. 호출 응용 프로그램에 즉시 필요하지 않는 다른 함수는 다른 DLL에 넣고 응용 프로그램이 해당 DLL에 명시적으로 연결되도록 합니다. 자세한 내용은 [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)를 참조하세요.

## <a name="memory_leak"></a> 있습니다&#39;가 기본 MFC DLL 하지만 코드에서 메모리 누수 문제가 있습니다. 메모리 누수는 어떻게 찾을 수 있습니까?

한 가지 가능한 메모리 누수 원인은 MFC 메시지 처리기 함수 내에서 사용 되는 임시 개체를 만듭니다. MFC 응용 프로그램에서 이러한 임시 개체는 자동으로 정리에 `CWinApp::OnIdle()` 메시지를 처리 하는 사이 호출 되는 함수입니다. 그러나 MFC 동적 연결 라이브러리 (Dll)에 `OnIdle()` 함수 자동으로 호출 되지 않습니다. 결과적으로, 임시 개체는 자동으로 정리 되지 합니다. 명시적으로 호출 해야 DLL 임시 개체를 정리 하려면 `OnIdle(1)` 주기적으로 합니다.

## <a name="see-also"></a>참고자료

[C를 만들기 /C++ Visual Studio에서 Dll](dlls-in-visual-cpp.md)
