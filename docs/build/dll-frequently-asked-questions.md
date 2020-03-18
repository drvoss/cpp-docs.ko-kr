---
title: MFC DLL faq (질문과 대답)
ms.date: 05/06/2019
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 9108aaf3fcface847b0391455a2aecd4d45658c4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422825"
---
# <a name="dll-frequently-asked-questions"></a>DLL 관련 질문과 대답

다음은 DLL에 대한 몇 가지 질문과 대답(FAQ)입니다.

- [MFC DLL에서 여러 스레드를 만들 수 있나요?](#mfc_multithreaded_1)

- [다중 스레드 응용 프로그램이 다른 스레드의 MFC DLL에 액세스할 수 있나요?](#mfc_multithreaded_2)

- [Mfc DLL에서 사용할 수 없는 MFC 클래스 또는 함수가 있나요?](#mfc_prohibited_classes)

- [로드할 때 클라이언트 응용 프로그램의 성능을 개선 하기 위해 사용 해야 하는 최적화 기술](#mfc_optimization)

- [일반 MFC DLL에는 메모리 누수가 있지만 코드는 정상적으로 보입니다. 메모리 누수를 어떻게 찾을 수 있나요?](#memory_leak)

## <a name="mfc_multithreaded_1"></a>MFC DLL에서 여러 스레드를 만들 수 있나요?

초기화 하는 동안을 제외 하 고, MFC DLL은 **TlsAlloc** 와 같은 Win32 TLS (스레드 로컬 저장소) 함수를 사용 하 여 스레드 로컬 저장소를 할당 하는 동안 여러 스레드를 안전 하 게 만들 수 있습니다. 그러나 MFC DLL이 **__declspec (thread)** 를 사용 하 여 스레드 로컬 저장소를 할당 하는 경우 클라이언트 응용 프로그램은 DLL에 암시적으로 연결 되어야 합니다. 클라이언트 응용 프로그램이 DLL에 명시적으로 링크 하는 경우 **LoadLibrary** 를 호출 하면 dll이 로드 되지 않습니다. Dll의 스레드 지역 변수에 대 한 자세한 내용은 [thread](../cpp/thread.md)를 참조 하십시오.

시작하는 동안 새 MFC 스레드를 만드는 MFC DLL은 응용 프로그램에서 로드할 때 응답을 중지합니다. 여기에는 `AfxBeginThread`를 호출 하거나 내부에서 `CWinThread::CreateThread` 하 여 스레드를 만들 때마다이 포함 됩니다.

- 일반 MFC DLL에서 `CWinApp`파생 개체의 `InitInstance`입니다.

- 일반 MFC DLL에서 제공 된 `DllMain` 또는 **RawDllMain** 함수입니다.

- MFC 확장 DLL에서 제공 된 `DllMain` 또는 **RawDllMain** 함수입니다.

## <a name="mfc_multithreaded_2"></a>다중 스레드 응용 프로그램이 다른 스레드의 MFC DLL에 액세스할 수 있나요?

다중 스레드 응용 프로그램은 여러 스레드에서 MFC 및 MFC 확장명 Dll에 동적으로 연결 하는 일반 MFC Dll에 액세스할 수 있습니다. 응용 프로그램은 응용 프로그램에서 만든 여러 스레드에서 정적으로 MFC에 링크 하는 일반 MFC Dll에 액세스할 수 있습니다.

## <a name="mfc_prohibited_classes"></a>Mfc DLL에서 사용할 수 없는 MFC 클래스 또는 함수가 있나요?

확장 Dll은 클라이언트 응용 프로그램의 `CWinApp`파생 클래스를 사용 합니다. 자체 `CWinApp`파생 클래스가 없어야 합니다.

기본 MFC Dll에는 MFC 응용 프로그램과 마찬가지로 `CWinApp`파생 클래스와 해당 응용 프로그램 클래스의 단일 개체가 있어야 합니다. 응용 프로그램의 `CWinApp` 개체와 달리 DLL의 `CWinApp` 개체에는 주 메시지 펌프가 없습니다.

`CWinApp::Run` 메커니즘이 DLL에 적용 되지 않기 때문에 응용 프로그램은 주 메시지 펌프를 소유 합니다. DLL이 모덜리스 대화 상자를 열거나 자체의 주 프레임 창이 있는 경우 응용 프로그램의 기본 메시지 펌프는 DLL에서 내보낸 루틴을 호출 하 여 dll의 응용 프로그램 개체에 대 한 `CWinApp::PreTranslateMessage` 멤버 함수를 호출 해야 합니다.

## <a name="mfc_optimization"></a>로드할 때 클라이언트 응용 프로그램&#39;의 성능을 개선 하기 위해 사용 해야 하는 최적화 기술

DLL이 정적으로 MFC에 링크 된 기본 MFC DLL 인 경우 동적으로 MFC에 링크 된 기본 mfc dll로 변경 하면 파일 크기가 줄어듭니다.

DLL에 많은 수의 내보낸 함수가 있는 경우 .def 파일을 사용 하 여 함수를 내보내고 ( **dllexport)** 를 사용 하는 __declspec 대신 .def 파일을 사용 하 여 내보낸 각 함수에서 .Def 파일 [NONAME 특성](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) 을 사용 합니다. NONAME 특성은 함수 이름이 아닌 서 수 값만을 발생 시켜 DLL의 내보내기 테이블에 저장 되므로 파일 크기를 줄입니다.

응용 프로그램에 암시적으로 링크된 DLL은 응용 프로그램이 로드될 때 로드됩니다. 로드 시 성능을 향상시키려면 DLL을 다른 DLL로 나누어 보세요. 로드한 후 즉시 호출 응용 프로그램에 필요한 모든 함수 및 호출 응용 프로그램을 하나의 DLL에 넣고 호출 응용 프로그램을 암시적으로 해당 DLL에 링크합니다. 호출 응용 프로그램에 즉시 필요하지 않는 다른 함수는 다른 DLL에 넣고 응용 프로그램이 해당 DLL에 명시적으로 연결되도록 합니다. 자세한 내용은 [DLL에 실행 파일 연결](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)을 참조 하세요.

## <a name="memory_leak"></a>&#39;일반 MFC DLL에는 메모리 누수가 있지만 코드는 정상적으로 보입니다. 메모리 누수를 어떻게 찾을 수 있나요?

메모리 누수의 한 가지 가능한 원인은 MFC가 메시지 처리기 함수 내에서 사용 되는 임시 개체를 만들기 때문입니다. MFC 응용 프로그램에서 이러한 임시 개체는 처리 메시지 사이에서 호출 되는 `CWinApp::OnIdle()` 함수에서 자동으로 정리 됩니다. 그러나 MFC Dll (동적 연결 라이브러리)에서는 `OnIdle()` 함수가 자동으로 호출 되지 않습니다. 따라서 임시 개체가 자동으로 정리 되지 않습니다. 임시 개체를 정리 하려면 DLL에서 정기적으로 `OnIdle(1)`를 명시적으로 호출 해야 합니다.

## <a name="see-also"></a>참고 항목

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
