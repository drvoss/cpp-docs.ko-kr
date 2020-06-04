---
title: DLL 관리를 위한 매크로 및 기능
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: 42a08ff2e806acae6713c9df3fe170f7e89f05af
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751592"
---
# <a name="macros-and-functions-for-managing-dlls"></a>DLL 관리를 위한 매크로 및 기능

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|클래스를 내보전합니다.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL에서 내보낸 함수를 보호합니다.|
|[AfxOleInitModule](#afxoleinitmodule)|MFC에 동적으로 연결된 일반 MFC DLL에서 OLE 지원을 제공합니다.|
|[AfxNetInitModule](#afxnetinitmodule)|MFC에 동적으로 연결된 일반 MFC DLL에서 MFC 소켓 지원을 제공합니다.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|모듈별 상태 플래그의 현재 상태를 가져옵니다.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|초기화 하기 전에 모듈 상태를 설정 하 고/또는 정리 후 이전 모듈 상태를 복원 합니다.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL을 초기화합니다.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|모듈별 상태 플래그를 설정하여 MFC의 WinSxS 동작에 영향을 줍니다.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|MFC는 각 프로세스가 DLL에서 분리될 때 MFC 확장 DLL을 정리할 수 있습니다.|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a>AFX_EXT_CLASS

[MFC 확장 DLL은](../../build/extension-dlls.md) 매크로 AFX_EXT_CLASS 사용하여 클래스를 내보냅니다. MFC 확장 DLL에 링크하는 실행 프로그램은 매크로를 사용하여 클래스를 가져옵니다.

### <a name="remarks"></a>설명

AFX_EXT_CLASS 매크로를 사용하면 MFC 확장DLL을 빌드하는 데 사용되는 동일한 헤더 파일을 DLL에 연결하는 실행 파일과 함께 사용할 수 있습니다.

DLL의 헤더 파일에서 클래스 선언에 AFX_EXT_CLASS 키워드를 다음과 같이 추가합니다.

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

자세한 내용은 [AFX_EXT_CLASS 사용하여 내보내기 및 가져오기](../../build/exporting-and-importing-using-afx-ext-class.md)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxv_dll.h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a>AFX_MANAGE_STATE

DLL에서 내보낸 함수를 보호하려면 이 매크로를 호출합니다.

### <a name="syntax"></a>구문

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>매개 변수

*p모듈 상태*<br/>
구조에 대한 `AFX_MODULE_STATE` 포인터입니다.

### <a name="remarks"></a>설명

이 매크로가 호출되면 *pModuleState는* 즉시 포함된 범위의 나머지 부분에 대한 유효 모듈 상태입니다. 범위를 벗어나면 이전 유효 모듈 상태가 자동으로 복원됩니다.
구조에는 `AFX_MODULE_STATE` 모듈, 즉 푸시또는 팝된 모듈 상태의 일부에 대한 전역 데이터가 포함됩니다.

기본적으로 MFC는 주 응용 프로그램의 리소스 핸들을 사용하여 리소스 템플릿을 로드합니다. DLL에서 대화 상자를 실행 하는 것과 같은 DLL에 내보낸 함수가 있는 경우이 템플릿은 실제로 DLL 모듈에 저장 됩니다. 올바른 핸들을 사용하려면 모듈 상태를 전환해야 합니다. 함수의 시작 부분에 다음 코드를 추가하여 이 작업을 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

이렇게 하면 현재 모듈 상태가 [AfxGetStaticModuleState에서](#afxgetstaticmodulestate) 현재 범위가 끝날 때까지 반환된 상태로 바꿉니다.

모듈 상태 및 MFC에 대한 자세한 내용은 새 문서, Windows 및 보기 및 [기술 참고 58](../tn058-mfc-module-state-implementation.md) [만들기에서](../creating-new-documents-windows-and-views.md) "MFC 모듈의 상태 데이터 관리"를 참조하십시오.

> [!NOTE]
> MFC가 어셈블리에 대한 활성화 컨텍스트를 만들 때 [AfxWinInit을](application-information-and-management.md#afxwininit) 사용하여 컨텍스트를 `AFX_MANAGE_STATE` 만들고 활성화 및 비활성화합니다. 또한 사용자 `AFX_MANAGE_STATE` DLL에서 선택한 적절한 활성화 컨텍스트에서 MFC 코드를 실행할 수 있도록 하려면 정적 MFC 라이브러리와 MFC DLL에 대해서도 활성화됩니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원을](../support-for-activation-contexts-in-the-mfc-module-state.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_.h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>아프올레니트 모듈

MFC에 동적으로 연결된 일반 MFC DLL의 `CWinApp::InitInstance` OLE 지원의 경우 일반 MFC DLL 함수에서 이 함수를 호출하여 MFC OLE DLL을 초기화합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>설명

MFC OLE DLL은 MFC 확장 DLL입니다. MFC 확장 DLL이 `CDynLinkLibrary` 체인에 연결되려면 이를 사용할 모든 `CDynLinkLibrary` 모듈의 컨텍스트에서 개체를 만들어야 합니다. `AfxOleInitModule``CDynLinkLibrary` 을 사용하면 일반 MFC DLL의 컨텍스트에서 `CDynLinkLibrary` 개체를 만듭니다.

OLE 컨트롤을 빌드하는 중이고 `COleControlModule`을 사용하는 `AfxOleInitModule` 경우 `InitInstance` 호출에 `COleControlModule` 대한 `AfxOleInitModule`멤버 함수이므로 호출해서는 안 됩니다.

### <a name="requirements"></a>요구 사항

**헤더** \<: afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a>아프넷니트모듈

MFC에 동적으로 연결된 일반 MFC DLL의 MFC 소켓 지원의 경우 일반 MFC DLL `CWinApp::InitInstance` 함수에서 이 함수에 대한 호출을 추가하여 MFC 소켓 DLL을 초기화합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>설명

MFC 소켓 DLL은 MFC 확장 DLL입니다. MFC 확장 DLL이 `CDynLinkLibrary` 체인에 연결되려면 이를 사용할 모든 `CDynLinkLibrary` 모듈의 컨텍스트에서 개체를 만들어야 합니다. `AfxNetInitModule``CDynLinkLibrary` 을 사용하면 일반 MFC DLL의 컨텍스트에서 `CDynLinkLibrary` 개체를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:** \<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a>아fxGet앰비언트액트

이 함수를 사용하여 MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그의 현재 상태를 가져옵니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Return Value

모듈 상태 플래그 현재 값입니다.

### <a name="remarks"></a>설명

플래그가 설정되어 있고 스레드가 MFC [모듈(AFX_MANAGE_STATE](#afx_manage_state)참조)에 들어가면 모듈의 컨텍스트가 활성화됩니다.

플래그가 설정되지 않은 경우 모듈의 컨텍스트가 항목에서 활성화되지 않습니다.

모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함된 매니페스트에서 결정됩니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a>AfxGet정적 모듈 상태

이 함수를 호출하여 초기화 전에 모듈 상태를 설정하고 정리 후 이전 모듈 상태를 복원합니다.

### <a name="syntax"></a>구문

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Return Value

구조에 대한 `AFX_MODULE_STATE` 포인터입니다.

### <a name="remarks"></a>설명

구조에는 `AFX_MODULE_STATE` 모듈, 즉 푸시또는 팝된 모듈 상태의 일부에 대한 전역 데이터가 포함됩니다.

기본적으로 MFC는 주 응용 프로그램의 리소스 핸들을 사용하여 리소스 템플릿을 로드합니다. DLL에서 대화 상자를 실행 하는 것과 같은 DLL에 내보낸 함수가 있는 경우이 템플릿은 실제로 DLL 모듈에 저장 됩니다. 올바른 핸들을 사용하려면 모듈 상태를 전환해야 합니다. 함수의 시작 부분에 다음 코드를 추가하여 이 작업을 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

이렇게 하면 현재 모듈 상태가 현재 `AfxGetStaticModuleState` 범위가 끝날 때까지 반환된 상태로 바꿉니다.

모듈 상태 및 MFC에 대한 자세한 내용은 새 문서, Windows 및 보기 및 [기술 참고 58](../tn058-mfc-module-state-implementation.md) [만들기에서](../creating-new-documents-windows-and-views.md) "MFC 모듈의 상태 데이터 관리"를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

MFC 확장 DLL에서 `DllMain` 이 함수를 호출하여 DLL을 초기화합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
초기화 후 MFC 확장 DLL 모듈의 상태를 포함하는 [AFX_EXTENSION_MODULE 구조구조에](afx-extension-module-structure.md) 대한 참조이다. 상태에는 입력하기 전에 `DllMain` 실행된 일반 정적 개체 생성의 일부로 MFC 확장 DLL에 의해 초기화된 런타임 클래스 개체의 복사본이 포함됩니다.

*h모듈*<br/>
MFC 확장 DLL 모듈의 핸들입니다.

### <a name="return-value"></a>Return Value

MFC 확장 DLL이 성공적으로 초기화되면 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

다음은 그 예입니다.

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule`DLL의 HMODULE의 복사본을 만들고 나중에 개체를 만들 때 사용할`CRuntimeClass` DLL의 런타임 클래스(구조체)와 해당 `CDynLinkLibrary` 개체 팩터리(개체)를`COleObjectFactory` 캡처합니다.
MFC 확장 DLL은 함수에서 `DllMain` 두 가지 작업을 수행해야 합니다.

- [AfxInitExtensionModule을](#afxinitextensionmodule) 호출하고 반환 값을 확인합니다.

- DLL이 `CDynLinkLibrary` [CRuntimeClass 구조 객체를](cruntimeclass-structure.md) 내보내거나 고유한 사용자 지정 리소스가 있는 경우 개체를 만듭니다.

각 프로세스가 `AfxTermExtensionModule` MFC 확장 DLL에서 분리될 때(프로세스가 종료될 때 또는 호출로 인해 DLL이 언로드될 때) MFC 확장 `AfxFreeLibrary` DLL을 정리하도록 호출할 수 있습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_.h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a>아fx셋앰비언트액트

이 함수를 사용하여 MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그를 설정합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
모듈 상태 플래그의 새 값입니다.

### <a name="remarks"></a>설명

플래그가 설정되어 있고 스레드가 MFC [모듈(AFX_MANAGE_STATE](#afx_manage_state)참조)에 들어가면 모듈의 컨텍스트가 활성화됩니다.
플래그가 설정되지 않은 경우 모듈의 컨텍스트가 항목에서 활성화되지 않습니다.
모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함된 매니페스트에서 결정됩니다.

### <a name="example"></a>예제

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a>AfxTerm확장모듈

각 프로세스가 DLL에서 분리될 때 MFC 확장 DLL을 정리할 수 있도록 이 함수를 호출합니다(프로세스가 종료될 때 또는 `AfxFreeLibrary` 호출의 결과로 DLL이 언로드될 때 발생).

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
MFC 확장 DLL 모듈의 상태를 포함하는 [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) 구조에 대한 참조입니다.

*볼*<br/>
TRUE인 경우 모든 MFC 확장 DLL 모듈을 정리합니다. 그렇지 않으면 현재 DLL 모듈만 정리합니다.

### <a name="remarks"></a>설명

`AfxTermExtensionModule`모듈에 연결된 로컬 저장소를 삭제하고 메시지 맵 캐시에서 항목을 제거합니다. 다음은 그 예입니다.

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

응용 프로그램이 MFC 확장 DLL을 동적으로 로드하고 `AfxTermExtensionModule`해제하는 경우 을 호출해야 합니다. 대부분의 MFC 확장 DLL은 동적으로 로드되지 않으므로(일반적으로 가져오기 라이브러리를 `AfxTermExtensionModule` 통해 연결됨) 호출은 일반적으로 필요하지 않습니다.

MFC 확장 DLL은 [에서 AfxInitExtensionModule을](#afxinitextensionmodule) 호출해야 합니다. `DllMain` DLL이 [CRuntimeClass](cruntimeclass-structure.md) 개체를 내보내거나 고유한 사용자 지정 리소스가 있는 `CDynLinkLibrary` 경우 `DllMain`에서 개체를 만들어야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_.h

## <a name="see-also"></a>참조

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC 모듈의 상태 데이터 관리](../managing-the-state-data-of-mfc-modules.md)<br/>
