---
title: Dll 및 Visual C++ 런타임 라이브러리 동작
ms.date: 08/19/2019
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
ms.openlocfilehash: 572a0ba70c1ba2d46d2d9fd6d8ac543a77bbbc01
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856776"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll 및 Visual C++ 런타임 라이브러리 동작

Visual Studio를 사용 하 여 DLL (동적 연결 라이브러리)을 빌드하는 경우 기본적으로 링커는 VCRuntime (시각적 C++ 런타임 라이브러리)을 포함 합니다. VCRuntime에는 C/C++ 실행 파일을 초기화 하 고 종료 하는 데 필요한 코드가 포함 되어 있습니다. DLL에 연결 된 경우 VCRuntime 코드는 DLL에 대 한 Windows OS 메시지를 처리 하 여 프로세스나 스레드에 연결 하거나 분리 하는 `_DllMainCRTStartup` 라는 내부 DLL 진입점 함수를 제공 합니다. `_DllMainCRTStartup` 함수는 스택 버퍼 보안 설정, CRT (C 런타임 라이브러리) 초기화 및 종료, 정적 및 전역 개체에 대 한 생성자 및 소멸자 호출과 같은 필수 작업을 수행 합니다. 또한 WinRT, MFC, ATL 등의 다른 라이브러리에 대해 후크 함수를 호출 하 여 자체 초기화 및 종료를 수행 `_DllMainCRTStartup` 합니다. 이 초기화를 사용 하지 않으면 CRT 및 기타 라이브러리와 정적 변수는 초기화 되지 않은 상태로 유지 됩니다. DLL이 정적으로 연결 된 CRT 또는 동적으로 연결 된 CRT DLL을 사용 하는지 여부에 관계 없이 동일한 VCRuntime 내부 초기화 및 종료 루틴이 호출 됩니다.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>기본 DLL 진입점 _DllMainCRTStartup

Windows에서 모든 Dll에는 초기화 및 종료에 대해 호출 되는 선택적 진입점 함수 (일반적으로 `DllMain`이라고 함)가 포함 될 수 있습니다. 이를 통해 필요에 따라 추가 리소스를 할당 하거나 해제할 수 있습니다. Windows에서는 프로세스 연결, 프로세스 분리, 스레드 연결 및 스레드 분리의 네 가지 상황에서 진입점 함수를 호출 합니다. DLL을 사용 하는 응용 프로그램이 로드 될 때 또는 응용 프로그램이 런타임에 DLL을 요청 하는 경우 프로세스 주소 공간에 DLL이 로드 되 면 운영 체제에서 DLL 데이터의 개별 복사본을 만듭니다. 이를 *프로세스 연결*이라고 합니다. *스레드 연결* 은 DLL이 로드 된 프로세스가 새 스레드를 만들 때 발생 합니다. 스레드 *분리* 는 스레드가 종료 될 때 발생 하며, DLL이 더 이상 필요 하지 않고 응용 프로그램에 의해 해제 될 때 *프로세스 분리* 가 발생 합니다. 운영 체제는 이러한 각 이벤트에 대 한 DLL 진입점에 대 한 별도의 호출을 수행 하 여 각 이벤트 유형에 대 한 *reason* 인수를 전달 합니다. 예를 들어 OS는 `DLL_PROCESS_ATTACH`를 신호 프로세스 연결에 대 한 *이유* 인수로 보냅니다.

VCRuntime 라이브러리는 `_DllMainCRTStartup` 이라는 진입점 함수를 제공 하 여 기본 초기화 및 종료 작업을 처리 합니다. 프로세스 연결에서 `_DllMainCRTStartup` 함수는 버퍼 보안 검사를 설정 하 고, CRT 및 기타 라이브러리를 초기화 하 고, 런타임 형식 정보를 초기화 하 고, 정적 및 비로컬 데이터의 생성자를 초기화 하 고 호출 하 고, 스레드 로컬 저장소를 초기화 하 고, 각 연결에 대 한 내부 정적 카운터를 증가 시키고, 사용자 또는 라이브러리에서 제공한 `DllMain`를 호출 합니다. 프로세스 분리 시 함수는 이러한 단계를 역순으로 진행 합니다. `DllMain`를 호출 하 고, 내부 카운터를 감소 시키고, 소멸자를 호출 하 고, CRT 종료 함수 및 등록 된 `atexit` 함수를 호출 하 고, 다른 종료 라이브러리에 게 알립니다. 첨부 파일 카운터가 0으로 이동 하면 함수는 `FALSE` 반환 하 여 DLL이 언로드될 수 있음을 창에 표시 합니다. `_DllMainCRTStartup` 함수는 스레드 연결 및 스레드 분리 중에도 호출 됩니다. 이러한 경우 VCRuntime 코드는 자체에서 추가 초기화 나 종료를 수행 하지 않으며 `DllMain`를 호출 하 여 메시지를 전달 하기만 하면 됩니다. `DllMain`에서 `FALSE`를 반환 하 고, 신호를 보내고, 실패 하는 경우 `_DllMainCRTStartup` `DllMain` 호출 하 고, *이유* 인수로 `DLL_PROCESS_DETACH`을 전달한 다음, 나머지 종료 프로세스를 진행 합니다.

Visual Studio에서 Dll을 빌드할 때 VCRuntime에서 제공 하는 기본 진입점 `_DllMainCRTStartup` 자동으로 연결 됩니다. [/Entry (진입점 기호)](reference/entry-entry-point-symbol.md) 링커 옵션을 사용 하 여 DLL에 대 한 진입점 함수를 지정할 필요가 없습니다.

> [!NOTE]
> /ENTRY: 링커 옵션을 사용 하 여 DLL에 대 한 다른 진입점 함수를 지정할 수 있지만 진입점 함수는 `_DllMainCRTStartup` 하는 모든 것을 동일한 순서로 복제 해야 하기 때문에 권장 하지 않습니다. VCRuntime은 동작을 복제할 수 있는 함수를 제공 합니다. 예를 들어 [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)를 [/gs (buffer security check)](reference/gs-buffer-security-check.md) 버퍼 검사 옵션을 지원 하기 위해 프로세스 연결에서 즉시 호출할 수 있습니다. 진입점 함수와 동일한 매개 변수를 전달 하 여 `_CRT_INIT` 함수를 호출 하 여 나머지 DLL 초기화 또는 종료 함수를 수행할 수 있습니다.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 초기화

Dll은 DLL이 로드 될 때 실행 되어야 하는 초기화 코드를 포함할 수 있습니다. 사용자 고유의 DLL 초기화 및 종료 함수를 수행 하기 위해 `_DllMainCRTStartup`는 사용자가 제공할 수 있는 `DllMain` 라는 함수를 호출 합니다. `DllMain`에는 DLL 진입점에 필요한 서명이 있어야 합니다. 기본 진입점 함수는 Windows에서 전달 하는 것과 동일한 매개 변수를 사용 하 여 `DllMain`를 호출 `_DllMainCRTStartup` 합니다. 기본적으로 `DllMain` 함수를 제공 하지 않는 경우 Visual Studio에서 사용자에 게 해당 함수를 제공 하 고 `_DllMainCRTStartup`에서 호출할 항목이 항상 포함 되도록 연결 합니다. 즉, DLL을 초기화할 필요가 없는 경우 DLL을 빌드할 때 특별 한 작업을 수행할 필요가 없습니다.

`DllMain`에 사용 되는 서명입니다.

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

일부 라이브러리는 `DllMain` 함수를 래핑합니다. 예를 들어 일반 MFC DLL에서 `CWinApp` 개체의 `InitInstance` 및 `ExitInstance` 멤버 함수를 구현 하 여 DLL에서 요구 하는 초기화 및 종료를 수행 합니다. 자세한 내용은 [일반 MFC Dll 초기화](#initializing-regular-dlls) 섹션을 참조 하세요.

> [!WARNING]
> DLL 진입점에서 안전 하 게 수행할 수 있는 작업에는 상당한 제한이 있습니다. `DllMain`에서 호출 하기에 안전 하지 않은 특정 Windows Api에 대 한 [일반적인 모범 사례](/windows/win32/Dlls/dynamic-link-library-best-practices) 를 참조 하세요. 필요한 항목이 있지만 가장 간단한 초기화는 DLL에 대 한 초기화 함수에서 수행 합니다. `DllMain` 실행 되 고 DLL의 다른 함수를 호출 하기 전에 응용 프로그램에서 초기화 함수를 호출 하도록 요구할 수 있습니다.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>일반 (비 MFC) Dll 초기화

VCRuntime에서 제공 하는 `_DllMainCRTStartup` 진입점을 사용 하는 일반 (비 MFC) Dll에서 초기화를 수행 하려면 DLL 소스 코드에 `DllMain`라는 함수가 포함 되어 있어야 합니다. 다음 코드는 `DllMain` 정의가 어떻게 표시 되는지 보여 주는 기본적인 기본 구조를 제공 합니다.

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason)
    {
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```

> [!NOTE]
> 이전 Windows SDK 설명서에서는 링커 명령줄에서/ENTRY 옵션과 함께 DLL 진입점 함수의 실제 이름을 지정 해야 한다고 설명 했습니다. Visual Studio에서는 진입점 함수의 이름이 `DllMain`경우/ENTRY 옵션을 사용할 필요가 없습니다. 실제로는/ENTRY 옵션을 사용 하 여 진입점 함수 이름을 `DllMain`이외의 이름으로 지정 하는 경우 진입점 함수에서 `_DllMainCRTStartup` 하는 것과 동일한 초기화 호출을 수행 하지 않으면 CRT가 제대로 초기화 되지 않습니다.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>일반 MFC Dll 초기화

일반 MFC Dll에는 `CWinApp` 개체가 있으므로 MFC 응용 프로그램과 동일한 위치에서 초기화 및 종료 작업을 수행 해야 합니다. DLL의 `CWinApp`파생 클래스에 대 한 `InitInstance` 및 `ExitInstance` 멤버 함수에서 이러한 작업을 수행 해야 합니다. MFC는 `DLL_PROCESS_ATTACH` 및 `DLL_PROCESS_DETACH`에 대해 `_DllMainCRTStartup`에 의해 호출 되는 `DllMain` 함수를 제공 하므로 고유한 `DllMain` 함수를 작성 하면 안 됩니다. MFC 제공 `DllMain` 함수는 DLL이 로드 될 때 `InitInstance`를 호출 하 고 DLL이 언로드되기 전에 `ExitInstance`를 호출 합니다.

일반 MFC DLL은 `InitInstance` 함수에서 [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 및 [tlsgetvalue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) 를 호출 하 여 여러 스레드를 추적할 수 있습니다. 이러한 함수를 사용 하면 DLL에서 스레드별 데이터를 추적할 수 있습니다.

Mfc에 동적으로 연결 되는 일반 MFC DLL에서 MFC OLE, MFC 데이터베이스 (또는 DAO) 또는 MFC 소켓 지원을 각각 사용 하는 경우 디버그 MFC 확장 Dll MFCO*버전*d .DLL, MFCD*버전*d .Dll 및 MFCN*버전*d .dll (여기서 *버전* 은 버전 번호)이 자동으로 연결 됩니다. 일반 MFC DLL의 `CWinApp::InitInstance`에서 사용 하는 각 Dll에 대해 다음과 같은 미리 정의 된 초기화 함수 중 하나를 호출 해야 합니다.

|MFC 지원 형식|호출할 초기화 함수|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*버전*D .dll)|`AfxOleInitModule`|
|MFC 데이터베이스 (MFCD*버전*D .dll)|`AfxDbInitModule`|
|MFC 소켓 (MFCN*버전*D .dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 확장 Dll 초기화

MFC 확장 Dll에는 일반 MFC Dll과 같은 `CWinApp`파생 개체가 없으므로 MFC DLL 마법사가 생성 하는 `DllMain` 함수에 초기화 및 종료 코드를 추가 해야 합니다.

이 마법사는 MFC 확장명 Dll에 대해 다음 코드를 제공 합니다. 코드에서 `PROJNAME`은 프로젝트 이름에 대 한 자리 표시자입니다.

```cpp
#include "pch.h" // For Visual Studio 2017 and earlier, use "stdafx.h"
#include <afxdllx.h>

#ifdef _DEBUG
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      TRACE0("PROJNAME.DLL Initializing!\n");

      // MFC extension DLL one-time initialization
      AfxInitExtensionModule(PROJNAMEDLL,
                                 hInstance);

      // Insert this DLL into the resource chain
      new CDynLinkLibrary(Dll3DLL);
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      TRACE0("PROJNAME.DLL Terminating!\n");
   }
   return 1;   // ok
}
```

초기화 중에 새 `CDynLinkLibrary` 개체를 만들면 MFC 확장 DLL에서 `CRuntimeClass` 개체 또는 리소스를 클라이언트 응용 프로그램으로 내보낼 수 있습니다.

하나 이상의 일반 MFC Dll에서 MFC 확장명 DLL을 사용 하려는 경우 `CDynLinkLibrary` 개체를 만드는 초기화 함수를 내보내야 합니다. 이 함수는 MFC 확장명 DLL을 사용 하는 각 일반 MFC Dll에서 호출 해야 합니다. 이 초기화 함수를 호출 하는 적절 한 위치가 MFC 확장 DLL의 내보낸 클래스 또는 함수를 사용 하기 전에 일반 MFC DLL의 `CWinApp`파생 개체의 `InitInstance` 멤버 함수에 있습니다.

MFC DLL 마법사가 생성 하는 `DllMain`에서 `AfxInitExtensionModule`를 호출 하면 모듈의 런타임 클래스 (`CRuntimeClass` 구조체) 뿐만 아니라 개체 팩터리 (`COleObjectFactory` 개체)가 `CDynLinkLibrary` 개체가 만들어질 때 사용할 수 있도록 캡처됩니다. `AfxInitExtensionModule`의 반환 값을 확인 해야 합니다. `AfxInitExtensionModule`에서 0 값을 반환 하는 경우 `DllMain` 함수에서 0을 반환 합니다.

MFC 확장 DLL이 실행 파일에 명시적으로 연결 된 경우 (실행 파일 호출 `AfxLoadLibrary` DLL로 연결 됨) `DLL_PROCESS_DETACH`의 `AfxTermExtensionModule`에 대 한 호출을 추가 해야 합니다. 이 함수를 사용 하면 각 프로세스가 MFC 확장명 DLL에서 분리 될 때 (프로세스가 종료 되거나 DLL이 `AfxFreeLibrary` 호출로 인해 발생 하는 경우에 발생) mfc 확장명 DLL을 정리할 수 있습니다. MFC 확장 DLL이 응용 프로그램에 암시적으로 연결 되는 경우 `AfxTermExtensionModule`에 대 한 호출이 필요 하지 않습니다.

MFC 확장 Dll에 명시적으로 연결 하는 응용 프로그램은 DLL을 해제할 때 `AfxTermExtensionModule`를 호출 해야 합니다. 또한 응용 프로그램에서 여러 스레드를 사용 하는 경우 Win32 함수 `LoadLibrary` 및 `FreeLibrary`대신 `AfxLoadLibrary` 및 `AfxFreeLibrary`를 사용 해야 합니다. `AfxLoadLibrary` 및 `AfxFreeLibrary`를 사용 하면 MFC 확장 DLL이 로드 및 언로드될 때 실행 되는 시작 및 종료 코드가 전역 MFC 상태를 손상 하지 않습니다.

MFCx0는 `DllMain`가 호출 된 시간에 완전히 초기화 되기 때문에 `DllMain` 내에서 메모리를 할당 하 고 MFC 함수를 호출할 수 있습니다 (16 비트 버전의 MFC와 달리).

확장 Dll은 `DLL_THREAD_ATTACH`를 처리 하 고 `DllMain` 함수의 `DLL_THREAD_DETACH` 사례를 처리 하 여 다중 스레딩을 처리할 수 있습니다. 이러한 경우는 스레드가 DLL에서 연결 및 분리 될 때 `DllMain`에 전달 됩니다. DLL이 연결 될 때 [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 를 호출 하면 DLL이 dll에 연결 된 모든 스레드에 대해 TLS (스레드 로컬 저장소) 인덱스를 유지 관리할 수 있습니다.

헤더 파일 Afxdllx에는 `AFX_EXTENSION_MODULE` 및 `CDynLinkLibrary`에 대 한 정의와 같은 MFC 확장명 Dll에서 사용 되는 구조에 대 한 특수 정의가 포함 되어 있습니다. MFC 확장 DLL에이 헤더 파일을 포함 해야 합니다.

> [!NOTE]
>  *.Pch. h* (Visual Studio 2017 및 이전 버전의*stdafx.h* )에서 `_AFX_NO_XXX` 매크로를 정의 하거나 정의 해제 하지 않는 것이 중요 합니다. 이러한 매크로는 특정 대상 플랫폼이 해당 기능을 지원 하는지 여부를 확인 하기 위한 목적 으로만 존재 합니다. 프로그램을 작성 하 여 이러한 매크로를 확인할 수 있지만 (예: `#ifndef _AFX_NO_OLE_SUPPORT`) 프로그램에서 이러한 매크로를 정의 하거나 정의 해제 해서는 안 됩니다.

다중 스레딩을 처리 하는 샘플 초기화 함수는 Windows SDK의 [동적 연결 라이브러리에서 스레드 로컬 저장소를 사용 하](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) 는 경우에 포함 됩니다. 샘플은 `LibMain`라는 진입점 함수를 포함 하지만 MFC 및 C 런타임 라이브러리와 함께 작동 하도록이 함수의 이름을 `DllMain` 합니다.

## <a name="see-also"></a>참고 항목

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)<br/>
[DllMain 진입점](/windows/win32/Dlls/dllmain)<br/>
[동적 연결 라이브러리 모범 사례](/windows/win32/Dlls/dynamic-link-library-best-practices)
