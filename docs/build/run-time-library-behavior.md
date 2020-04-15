---
title: DLL 및 Visual C++ 런타임 라이브러리 동작
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
ms.openlocfilehash: 2f2ffb13e6a80b144298bbf8cd76b5666a10b4dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335657"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL 및 Visual C++ 런타임 라이브러리 동작

Visual Studio를 사용하여 DLL(동적 링크 라이브러리)을 빌드하는 경우 기본적으로 링커에는 Visual C++ 런타임 라이브러리(VCRuntime)가 포함됩니다. VCRuntime에는 C/C++ 실행 자를 초기화하고 종료하는 데 필요한 코드가 포함되어 있습니다. DLL에 연결하면 VCRuntime 코드는 프로세스 또는 스레드에 연결하거나 분리할 DLL에 Windows OS 메시지를 처리하는 내부 DLL 진입점 함수를 `_DllMainCRTStartup` 제공합니다. 이 `_DllMainCRTStartup` 함수는 스택 버퍼 보안 설정, CRT(C 런타임 라이브러리) 초기화 및 종료, 정적 및 전역 개체에 대한 생성자 및 소멸자 호출과 같은 필수 작업을 수행합니다. `_DllMainCRTStartup`또한 WinRT, MFC 및 ATL과 같은 다른 라이브러리에 대한 후크 함수를 호출하여 자체 초기화 및 종료를 수행합니다. 이 초기화가 없으면 CRT 및 기타 라이브러리와 정적 변수가 초기화되지 않은 상태로 유지됩니다. DLL이 정적으로 연결된 CRT 또는 동적으로 연결된 CRT DLL을 사용하는지 여부에 관계없이 동일한 VCRuntime 내부 초기화 및 종료 루틴이 호출됩니다.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>기본 DLL 진입점 _DllMainCRTStartup

Windows에서 모든 DLL에는 초기화 및 종료 모두에 `DllMain`대해 호출되는 선택적 진입점 함수(일반적으로 라고 함)가 포함될 수 있습니다. 이렇게 하면 필요에 따라 추가 리소스를 할당하거나 해제할 수 있습니다. Windows는 프로세스 연결, 프로세스 분리, 스레드 연결 및 스레드 분리의 네 가지 상황에서 진입점 함수를 호출합니다. DLL을 프로세스 주소 공간에 로드하는 경우( DLL을 사용하는 응용 프로그램이 로드되거나 응용 프로그램이 런타임에 DLL을 요청할 때) 운영 체제는 DLL 데이터의 별도의 복사본을 만듭니다. 이를 *프로세스 첨부라고*합니다. *스레드 연결은* DLL이 로드된 프로세스가 새 스레드를 만들 때 발생합니다. *스레드 분리는* 스레드가 종료될 때 발생하며 *프로세스 분리는* DLL이 더 이상 필요하지 않고 응용 프로그램에서 해제되는 경우입니다. 운영 체제는 이러한 각 이벤트에 대해 DLL 진입점을 별도로 호출하여 각 이벤트 유형에 대한 *이유* 인수를 전달합니다. 예를 들어 OS는 `DLL_PROCESS_ATTACH` 프로세스 연결 신호에 *대한 이유* 인수로 보냅니다.

VCRuntime 라이브러리는 기본 초기화 `_DllMainCRTStartup` 및 종료 작업을 처리하기 위해 호출된 진입점 함수를 제공합니다. 프로세스 연결시 `_DllMainCRTStartup` 함수는 버퍼 보안 검사를 설정하고 CRT 및 기타 라이브러리를 초기화하고, 런타임 형식 정보를 초기화하고, 정적 및 비로컬 데이터에 대한 생성자를 초기화하고, 스레드 로컬 저장소를 초기화하고, 각 첨부에 대해 내부 정적 카운터를 증분한 다음 사용자 또는 라이브러리 제공을 `DllMain`호출합니다. 프로세스 분리시 함수는 역으로 이러한 단계를 거칩니다. 내부 `DllMain`카운터를 호출하고, 소멸자 호출하고, CRT 종료 함수 및 등록된 `atexit` 함수를 호출하고, 다른 종료 라이브러리에 알린다. 첨부 파일 카운터가 0으로 이동하면 함수가 반환되어 `FALSE` DLL을 언로드할 수 있음을 Windows에 나타냅니다. 이 `_DllMainCRTStartup` 함수는 스레드 연결 및 스레드 분리 중에도 호출됩니다. 이러한 경우 VCRuntime 코드는 자체적으로 추가 초기화 또는 종료를 `DllMain` 수행하지 않으며 메시지를 전달하기 위해 호출만 수행합니다. 프로세스 `DllMain` `FALSE` 연결, 신호 실패에서 `_DllMainCRTStartup` 반환하는 경우 다시 호출하고 `DllMain` `DLL_PROCESS_DETACH` *이유* 인수로 전달하면 종료 프로세스의 나머지 부분을 거칩니다.

Visual Studio에서 DLL을 빌드할 `_DllMainCRTStartup` 때 VCRuntime에서 제공하는 기본 진입점이 자동으로 연결됩니다. [/ENTRY(진입점 기호)](reference/entry-entry-point-symbol.md) 링커 옵션을 사용하여 DLL에 대한 진입점 함수를 지정할 필요가 없습니다.

> [!NOTE]
> /ENTRY: 링커 옵션을 사용하여 DLL에 대한 다른 진입점 함수를 지정할 수 있지만 진입점 함수가 `_DllMainCRTStartup` 수행하는 모든 작업을 동일한 순서로 복제해야 하므로 사용하지 않는 것이 좋습니다. VCRuntime은 해당 동작을 복제할 수 있는 함수를 제공합니다. 예를 들어 [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)를 [/gs (buffer security check)](reference/gs-buffer-security-check.md) 버퍼 검사 옵션을 지원 하기 위해 프로세스 연결에서 즉시 호출할 수 있습니다. 진입점 함수와 동일한 매개 변수를 전달하여 나머지 DLL 초기화 또는 종료 함수를 수행하기 위해 `_CRT_INIT` 함수를 호출할 수 있습니다.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 초기화

DLL에는 DLL이 로드될 때 실행해야 하는 초기화 코드가 있을 수 있습니다. 사용자 고유의 DLL 초기화 및 종료 함수를 `_DllMainCRTStartup` 수행하려면 `DllMain` 제공할 수 있는 함수를 호출합니다. DLL 진입점에 필요한 서명이 `DllMain` 있어야 합니다. 기본 진입점 `_DllMainCRTStartup` 함수는 Windows에서 전달한 동일한 매개 변수를 사용하여 호출합니다. `DllMain` 기본적으로 함수를 `DllMain` 제공하지 않는 경우 Visual Studio는 함수를 제공하고 항상 `_DllMainCRTStartup` 호출할 항목이 없도록 연결합니다. 즉, DLL을 초기화할 필요가 없는 경우 DLL을 빌드할 때 해야 할 특별한 일은 없습니다.

이 서명은 다음과 `DllMain`같은 경우 사용됩니다.

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

일부 라이브러리는 `DllMain` 함수를 래핑합니다. 예를 들어 일반 MFC DLL에서 `CWinApp` 개체 `InitInstance` 및 `ExitInstance` 멤버 함수를 구현하여 DLL에 필요한 초기화 및 종료를 수행합니다. 자세한 내용은 일반 [MFC DLL 초기화](#initializing-regular-dlls) 섹션을 참조하십시오.

> [!WARNING]
> DLL 진입점에서 안전하게 수행할 수 있는 작업에는 상당한 제한이 있습니다. 에서 호출하기에 안전하지 않은 특정 Windows API에 대한 [일반 권장 사항을](/windows/win32/Dlls/dynamic-link-library-best-practices) 참조하십시오. `DllMain` 가장 간단한 초기화 외에는 아무것도 필요한 경우 DLL의 초기화 함수에서 이 작업을 수행합니다. 응용 프로그램이 실행된 후 `DllMain` DLL의 다른 함수를 호출하기 전에 초기화 함수를 호출하도록 요구할 수 있습니다.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>일반(MFC가 아닌) DLL 초기화

VCRuntime 에서 제공된 `_DllMainCRTStartup` 진입점을 사용하는 일반(MFC가 아닌) DLL에서 사용자 고유의 초기화를 수행하려면 `DllMain`DLL 소스 코드에 라는 함수가 포함되어야 합니다. 다음 코드는 정의의 정의모양을 `DllMain` 보여 주며 기본 골격을 제공합니다.

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
> 이전 Windows SDK 설명서에 따르면 DLL 진입점 함수의 실제 이름은 /ENTRY 옵션을 사용 하 고 링커 명령줄에 지정 해야 합니다. Visual Studio에서는 진입점 함수의 이름이 있는 경우 /ENTRY 옵션을 사용할 `DllMain`필요가 없습니다. 실제로 /ENTRY 옵션을 사용하고 진입점 함수의 이름을 지정하는 `DllMain`경우 진입점 함수가 동일한 초기화 호출을 `_DllMainCRTStartup` 하지 않는 한 CRT가 제대로 초기화되지 않습니다.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>일반 MFC DLL 초기화

일반 MFC DLL에는 `CWinApp` 개체가 있으므로 `InitInstance` `CWinApp`DLL의 -derived 클래스의 멤버 함수에서 MFC `ExitInstance` 응용 프로그램과 동일한 위치에서 초기화 및 종료 작업을 수행해야 합니다. MFC는 `DllMain` `_DllMainCRTStartup` 에 의해 `DLL_PROCESS_ATTACH` 호출 되는 `DLL_PROCESS_DETACH`함수를 제공 하 `DllMain` 고 고유의 함수를 작성 하지 않아야 합니다. MFC에서 제공하는 `DllMain` 함수는 DLL이 로드되고 DLL이 언로드되기 전에 호출될 `InitInstance` 때 호출됩니다. `ExitInstance`

일반 MFC DLL은 함수에서 [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 및 [TlsGetValue를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) 호출하여 여러 스레드를 추적할 수 있습니다. `InitInstance` 이러한 기능을 통해 DLL은 스레드별 데이터를 추적할 수 있습니다.

MFC에 동적으로 연결되는 일반 MFC DLL에서 MFC OLE, MFC 데이터베이스(또는 DAO) 또는 MFC 소켓 지원을 각각 사용하는 경우 디버그 MFC 확장 DFCO*버전*D.dll, MFCD*버전*D.dll 및 MFCN*버전*D.dll(버전이 버전이 버전인 경우 버전이 있는 경우)이 자동으로 연결됩니다. *version* 일반 MFC DLL에서 사용 중인 각 DLL에 대해 미리 정의된 다음 초기화 함수 `CWinApp::InitInstance`중 하나를 호출해야 합니다.

|MFC 지원 유형|호출할 초기화 함수|
|-------------------------|-------------------------------------|
|MFC 올레 (MFCO*버전*D.dll)|`AfxOleInitModule`|
|MFC 데이터베이스(MFCD*버전*D.dll)|`AfxDbInitModule`|
|MFC 소켓(MFCN*버전*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 확장 DLL 초기화

MFC 확장 DLL에는 `CWinApp`-derived 개체가 없으므로(일반 MFC DLL과 마찬가지로) MFC DLL 마법사가 생성하는 함수에 `DllMain` 초기화 및 종료 코드를 추가해야 합니다.

마법사는 MFC 확장 DLL에 대한 다음 코드를 제공합니다. 코드에서 프로젝트 `PROJNAME` 이름에 대한 자리 표시자입니다.

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

초기화 `CDynLinkLibrary` 하는 동안 새 개체를 만들면 MFC 확장 DLL 클라이언트 응용 프로그램에 개체 또는 리소스를 내보낼 `CRuntimeClass` 수 있습니다.

하나 이상의 일반 MFC DLL에서 MFC 확장 DLL을 사용하려면 개체를 만드는 초기화 `CDynLinkLibrary` 함수를 내보내야 합니다. 해당 함수는 MFC 확장 DLL을 사용하는 각 일반 MFC DLL에서 호출되어야 합니다. 이 초기화 함수를 호출하는 적절한 `InitInstance` 장소는 MFC 확장 DLL의 `CWinApp`내보낸 클래스 또는 함수를 사용하기 전에 일반 MFC DLL의 -파생 개체의 멤버 함수에 있습니다.

MFC `DllMain` DLL 마법사가 생성하는 `AfxInitExtensionModule` 경우`CRuntimeClass` `COleObjectFactory` `CDynLinkLibrary` 개체를 만들 때 사용할 모듈의 런타임 클래스(구조체)와 해당 개체 팩터리(개체)를 캡처하는 호출입니다. 의 `AfxInitExtensionModule`반환 값을 확인해야 합니다. 에서 0 값이 반환 `AfxInitExtensionModule`되는 경우 `DllMain` 0 함수에서 0을 반환 합니다.

MFC 확장 DLL이 실행 컴퓨터에 명시적으로 연결되는 경우(즉, `AfxLoadLibrary` DLL에 연결하는 실행 호출을 의미) 에 `AfxTermExtensionModule` `DLL_PROCESS_DETACH`대한 호출을 추가해야 합니다. 이 기능을 사용하면 각 프로세스가 MFC 확장 DLL에서 분리될 때 MFC 확장 DLL을 정리할 수 있습니다(프로세스가 종료되거나 `AfxFreeLibrary` 호출로 인해 DLL이 언로드될 때 발생). MFC 확장 DLL이 응용 프로그램에 암시적으로 연결되는 `AfxTermExtensionModule` 경우 호출이 필요하지 않습니다.

MFC 확장 DLL에 명시적으로 연결되는 `AfxTermExtensionModule` 응용 프로그램은 DLL을 해제할 때 호출해야 합니다. 또한 `AfxLoadLibrary` 응용 프로그램에서 `AfxFreeLibrary` 여러 스레드를 `LoadLibrary` 사용하는 경우 `FreeLibrary`Win32 함수 및 (Win32 함수 대신)을 사용해야 합니다. MFC 확장 DLL을 로드하고 언로드할 때 실행되는 시작 및 종료 코드가 전역 MFC 상태를 손상시키지 않도록 합니다. `AfxLoadLibrary` `AfxFreeLibrary`

MFCx0.dll은 호출된 시간에 `DllMain` 의해 완전히 초기화되므로 16비트 버전의 MFC와 달리 메모리를 `DllMain` 할당하고 MFC 함수를 호출할 수 있습니다.

확장 DLL은 함수의 `DLL_THREAD_ATTACH` 사례와 `DLL_THREAD_DETACH` 사례를 처리하여 `DllMain` 다중 스레딩을 처리할 수 있습니다. 이러한 경우는 `DllMain` 스레드가 DLL에서 연결되고 분리될 때 전달됩니다. DLL이 연결될 때 [TlsAlloc을](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 호출하면 DLL이 DLL에 연결된 모든 스레드에 대해 스레드 로컬 저장소(TLS) 인덱스를 유지할 수 있습니다.

헤더 파일 Afxdllx.h에는 에 대한 정의와 `AFX_EXTENSION_MODULE` `CDynLinkLibrary`같은 MFC 확장자 DLL에 사용되는 구조에 대한 특수 정의가 포함되어 있습니다. 이 헤더 파일을 MFC 확장 DLL에 포함해야 합니다.

> [!NOTE]
> *pch.h(Visual* Studio 2017 `_AFX_NO_XXX` 및 이전)의 매크로를 정의하거나 정의하지 않는 것이 중요합니다.*stdafx.h* 이러한 매크로는 특정 대상 플랫폼이 해당 기능을 지원하는지 여부를 확인하기 위한 목적으로만 존재합니다. 이러한 매크로를 확인하기 위해 프로그램을 작성할 `#ifndef _AFX_NO_OLE_SUPPORT`수 있지만 프로그램에서 이러한 매크로를 정의하거나 정의해제해서는 안 됩니다.

다중 스레딩을 처리하는 샘플 초기화 함수는 Windows SDK의 [동적 링크 라이브러리에서 스레드 로컬 저장소 사용에](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) 포함됩니다. 샘플에는 는 진입점 함수가 `LibMain`포함되어 있지만 MFC `DllMain` 및 C 런타임 라이브러리에서 작동되도록 이 함수의 이름을 지정해야 합니다.

## <a name="see-also"></a>참고 항목

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)<br/>
[DllMain 진입점](/windows/win32/Dlls/dllmain)<br/>
[동적 링크 라이브러리 모범 사례](/windows/win32/Dlls/dynamic-link-library-best-practices)
