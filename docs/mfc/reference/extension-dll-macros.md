---
title: Dll을 관리 하기 위한 매크로 및 함수
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: e4170ba95775fd3380837673a76a8adafc8ad011
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837183"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll을 관리 하기 위한 매크로 및 함수

|Name|설명|
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|클래스를 내보냅니다.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL에서 내보낸 함수를 보호 합니다.|
|[AfxOleInitModule](#afxoleinitmodule)|MFC에 동적으로 연결 되는 일반 MFC DLL에서 OLE를 지원 합니다.|
|[AfxNetInitModule](#afxnetinitmodule)|MFC에 동적으로 연결 되는 일반 MFC DLL의 MFC 소켓 지원을 제공 합니다.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|모듈별 상태 플래그의 현재 상태를 가져옵니다.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|초기화 하기 전에 모듈 상태를 설정 하 고 정리 후에 이전 모듈 상태를 복원 합니다.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL을 초기화 합니다.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그를 설정 합니다.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|각 프로세스가 DLL에서 분리 될 때 MFC가 mfc 확장명 DLL을 정리할 수 있도록 합니다.|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> AFX_EXT_CLASS

[MFC 확장 DLL](../../build/extension-dlls.md)은 AFX_EXT_CLASS 매크로를 사용하여 클래스를 내보냅니다. MFC 확장 DLL에 연결되는 실행 파일은 이 매크로를 사용하여 클래스를 가져옵니다.

### <a name="remarks"></a>설명

AFX_EXT_CLASS 매크로를 사용 하 여 MFC 확장명 DLL을 빌드하는 데 사용 되는 것과 동일한 헤더 파일을 DLL로 연결 되는 실행 파일과 함께 사용할 수 있습니다.

DLL에 대한 헤더 파일에서 다음과 같이 AFX_EXT_CLASS 키워드를 클래스 선언에 추가합니다.

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

자세한 내용은 [AFX_EXT_CLASS를 사용 하 여 내보내기 및 가져오기](../../build/exporting-and-importing-using-afx-ext-class.md)를 참조 하세요.

### <a name="requirements"></a>요구 사항

**헤더:** afxv_dll. h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> AFX_MANAGE_STATE

DLL에서 내보낸 함수를 보호 하려면이 매크로를 호출 합니다.

### <a name="syntax"></a>구문

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>매개 변수

*pModuleState*<br/>
구조체에 대 한 포인터 `AFX_MODULE_STATE` 입니다.

### <a name="remarks"></a>설명

이 매크로가 호출 되 면 즉시 포함 하는 범위의 나머지 부분에 대 한 유효한 모듈 *상태가 됩니다.* 범위를 벗어나면 이전 유효 모듈 상태가 자동으로 복원 됩니다.
구조체에는 모듈 `AFX_MODULE_STATE` 에 대 한 전역 데이터 즉, 푸시되 나 팝 된 모듈 상태의 일부가 포함 되어 있습니다.

기본적으로 MFC는 주 응용 프로그램의 리소스 핸들을 사용 하 여 리소스 템플릿을 로드 합니다. Dll에서 dll의 대화 상자를 시작 하는 함수와 같은 내보낸 함수가 있는 경우이 템플릿은 실제로 DLL 모듈에 저장 됩니다. 사용할 올바른 핸들의 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 작업을 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

현재 범위 끝까지 [AfxGetStaticModuleState](#afxgetstaticmodulestate) 에서 반환 된 상태로 현재 모듈 상태를 바꿉니다.

모듈 상태 및 MFC에 대 한 자세한 내용은 [새 문서, 창 및 뷰 만들기](../creating-new-documents-windows-and-views.md) 의 "MFC 모듈의 상태 데이터 관리" 및 [Technical Note 58](../tn058-mfc-module-state-implementation.md)을 참조 하세요.

> [!NOTE]
> MFC는 어셈블리에 대 한 활성화 컨텍스트를 만들 때 [AfxWinInit](application-information-and-management.md#afxwininit) 를 사용 하 여 컨텍스트를 만들고 `AFX_MANAGE_STATE` 활성화 하 고 비활성화 합니다. 또한 mfc `AFX_MANAGE_STATE` 코드를 사용자 DLL에서 선택한 적절 한 활성화 컨텍스트에서 실행할 수 있도록 Mfc dll 뿐만 아니라 정적 mfc 라이브러리에도이 기능을 사용할 수 있습니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원](../support-for-activation-contexts-in-the-mfc-module-state.md)을 참조 하세요.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_. h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

동적으로 MFC에 링크 된 일반 MFC DLL에서 OLE를 지원 하려면 일반 MFC DLL의 함수에서이 함수를 호출 `CWinApp::InitInstance` 하 여 MFC OLE dll을 초기화 합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>설명

MFC OLE DLL은 MFC 확장명 DLL입니다. MFC 확장 DLL이 체인에 유선으로 연결 되도록 하려면 해당 DLL을 사용 하는 `CDynLinkLibrary` `CDynLinkLibrary` 모든 모듈의 컨텍스트에서 개체를 만들어야 합니다. `AfxOleInitModule` 일반 mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 의 개체 체인에 유선으로 연결 되도록 일반 mfc dll의 컨텍스트에서 개체를 만듭니다.

OLE 컨트롤을 빌드하고를 사용 하는 경우 `COleControlModule` `AfxOleInitModule` `InitInstance` 에 대 한 멤버 함수는를 호출 하면 안 됩니다 `COleControlModule` `AfxOleInitModule` .

### <a name="requirements"></a>요구 사항

**헤더**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> AfxNetInitModule

Mfc에 동적으로 연결 되는 일반 MFC DLL의 MFC 소켓과 지원에 대 한 일반적인 mfc DLL의 함수에이 함수에 대 한 호출을 추가 `CWinApp::InitInstance` 하 여 Mfc 소켓 dll을 초기화 합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>설명

MFC 소켓 DLL은 MFC 확장명 DLL입니다. MFC 확장 DLL이 체인에 유선으로 연결 되도록 하려면 해당 DLL을 사용 하는 `CDynLinkLibrary` `CDynLinkLibrary` 모든 모듈의 컨텍스트에서 개체를 만들어야 합니다. `AfxNetInitModule` 일반 mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 의 개체 체인에 유선으로 연결 되도록 일반 mfc dll의 컨텍스트에서 개체를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> AfxGetAmbientActCtx

이 함수를 사용 하 여 MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그의 현재 상태를 가져옵니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Return Value

모듈 상태 플래그 현재 값입니다.

### <a name="remarks"></a>설명

플래그가 설정 되 고 (기본값) 스레드가 MFC 모듈로 들어가면 ( [AFX_MANAGE_STATE](#afx_manage_state)참조) 모듈의 컨텍스트가 활성화 됩니다.

플래그를 설정 하지 않으면 모듈의 컨텍스트가 항목에서 활성화 되지 않습니다.

모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함 된 매니페스트에서 결정 됩니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState

초기화 전에 모듈 상태를 설정 하거나 정리 후 이전 모듈 상태를 복원 하려면이 함수를 호출 합니다.

### <a name="syntax"></a>구문

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Return Value

구조체에 대 한 포인터 `AFX_MODULE_STATE` 입니다.

### <a name="remarks"></a>설명

구조체에는 모듈 `AFX_MODULE_STATE` 에 대 한 전역 데이터 즉, 푸시되 나 팝 된 모듈 상태의 일부가 포함 되어 있습니다.

기본적으로 MFC는 주 응용 프로그램의 리소스 핸들을 사용 하 여 리소스 템플릿을 로드 합니다. Dll에서 dll의 대화 상자를 시작 하는 함수와 같은 내보낸 함수가 있는 경우이 템플릿은 실제로 DLL 모듈에 저장 됩니다. 사용할 올바른 핸들의 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 작업을 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

현재 범위의 끝까지 현재 모듈 상태를에서 반환 된 상태로 바꿉니다 `AfxGetStaticModuleState` .

모듈 상태 및 MFC에 대 한 자세한 내용은 [새 문서, 창 및 뷰 만들기](../creating-new-documents-windows-and-views.md) 의 "MFC 모듈의 상태 데이터 관리" 및 [Technical Note 58](../tn058-mfc-module-state-implementation.md)을 참조 하세요.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_. h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

MFC 확장 DLL에서이 함수 `DllMain` 를 호출 하 여 dll을 초기화 합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
초기화 후 MFC 확장 DLL 모듈의 상태를 포함 하는 [AFX_EXTENSION_MODULE structure](afx-extension-module-structure.md) 구조체에 대 한 참조입니다. 상태에는를 입력 하기 전에 실행 되는 일반 정적 개체 생성의 일부로 MFC 확장 DLL에 의해 초기화 된 런타임 클래스 개체의 복사본이 포함 됩니다 `DllMain` .

*hModule*<br/>
MFC 확장 DLL 모듈의 핸들입니다.

### <a name="return-value"></a>반환 값

MFC 확장 DLL이 성공적으로 초기화 되었으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

예를 들어:

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

`AfxInitExtensionModule` DLL의 HMODULE 복사본을 만들고 DLL의 런타임 클래스 (구조체) 뿐만 아니라 개체를 `CRuntimeClass` `COleObjectFactory` 만들 때 나중에 사용할 수 있도록 해당 개체 팩터리 (개체)를 캡처합니다 `CDynLinkLibrary` .
MFC 확장 Dll은 함수에서 다음 두 가지 작업을 수행 해야 합니다 `DllMain` .

- [AfxInitExtensionModule](#afxinitextensionmodule) 을 호출 하 고 반환 값을 확인 합니다.

- DLL이 `CDynLinkLibrary` [CRuntimeClass Structure](cruntimeclass-structure.md) 개체를 내보내거나 고유한 사용자 지정 리소스를 포함 하는 경우 개체를 만듭니다.

`AfxTermExtensionModule`를 호출 하 여 각 프로세스가 mfc 확장명 dll에서 분리 될 때 (프로세스가 종료 될 때 또는 호출의 결과로 DLL이 언로드될 때 발생) mfc 확장명 dll을 정리할 수 있습니다 `AfxFreeLibrary` .

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_. h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> AfxSetAmbientActCtx

이 함수를 사용 하 여 MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그를 설정 합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
모듈 상태 플래그의 새 값입니다.

### <a name="remarks"></a>설명

플래그가 설정 되 고 (기본값) 스레드가 MFC 모듈로 들어가면 ( [AFX_MANAGE_STATE](#afx_manage_state)참조) 모듈의 컨텍스트가 활성화 됩니다.
플래그를 설정 하지 않으면 모듈의 컨텍스트가 항목에서 활성화 되지 않습니다.
모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함 된 매니페스트에서 결정 됩니다.

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

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> AfxTermExtensionModule

각 프로세스가 DLL에서 분리 될 때 (프로세스가 종료 될 때, 또는 호출 결과로 DLL이 언로드될 때) MFC가 MFC 확장명 DLL을 정리할 수 있도록 하려면이 함수를 호출 `AfxFreeLibrary` 합니다.

### <a name="syntax"></a>구문

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
MFC 확장 DLL 모듈의 상태를 포함 하는 [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) 구조체에 대 한 참조입니다.

*공을*<br/>
TRUE 이면 모든 MFC 확장 DLL 모듈을 정리 합니다. 그렇지 않으면 현재 DLL 모듈만 정리 합니다.

### <a name="remarks"></a>설명

`AfxTermExtensionModule` 는 모듈에 연결 된 모든 로컬 저장소를 삭제 하 고 메시지 맵 캐시에서 모든 항목을 제거 합니다. 예를 들어:

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

응용 프로그램이 MFC 확장명 Dll을 동적으로 로드 하 고 해제 하는 경우를 호출 해야 `AfxTermExtensionModule` 합니다. 대부분의 MFC 확장명 Dll은 동적으로 로드 되지 않으므로 (일반적으로 해당 가져오기 라이브러리를 통해 연결 됨)에 대 한 호출은 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.

MFC 확장 Dll은에서 [AfxInitExtensionModule](#afxinitextensionmodule) 를 호출 해야 `DllMain` 합니다. DLL이 [CRuntimeClass](cruntimeclass-structure.md) 개체를 내보내거나 자체 사용자 지정 리소스가 있는 경우 `CDynLinkLibrary` 에도에서 개체를 만들어야 `DllMain` 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_. h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC 모듈의 상태 데이터 관리](../managing-the-state-data-of-mfc-modules.md)<br/>
