---
title: CComModule 클래스
ms.date: 08/19/2019
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: 5e30f847ff99a80ab19b880728472a339fd4cbe5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747935"
---
# <a name="ccommodule-class"></a>CComModule 클래스

ATL 7.0을 `CComModule` [참조하면](../../atl/atl-module-classes.md) 더 이상 사용되지 않습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComModule::GetClassObject](#getclassobject)|지정된 CLSID의 개체를 만듭니다. DLL에만 적합합니다.|
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst`를 반환합니다.|
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource`를 반환합니다.|
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib`를 반환합니다.|
|[CComModule::Init](#init)|데이터 멤버를 초기화합니다.|
|[CComModule::RegisterClassHelper](#registerclasshelper)|시스템 레지스트리에 개체의 표준 클래스 등록을 입력합니다.|
|[CComModule::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다. EXEs전용.|
|[CComModule::RegisterServer](#registerserver)|개체 맵의 각 개체에 대한 시스템 레지스트리를 업데이트합니다.|
|[CComModule::RegisterTypeLib](#registertypelib)|형식 라이브러리를 등록합니다.|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 해지합니다. EXEs전용.|
|[CComModule::Term](#term)|데이터 멤버를 해제합니다.|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.|
|[CComModule::UnregisterServer](#unregisterserver)|개체 맵의 각 개체를 등록 취소합니다.|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|개체의 표준 클래스 등록을 등록하거나 등록 취소합니다.|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다.|
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL 레지스트리 구성 요소에 정적으로 연결됩니다. 지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComModule::m_csObjMap](#m_csobjmap)|개체 맵 정보에 대한 동기화된 액세스를 보장합니다.|
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|형식 라이브러리 정보에 대한 동기화된 액세스를 보장합니다.|
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|창 을 만드는 동안 사용 되는 창 클래스 정보 및 정적 데이터에 대 한 동기화 된 액세스를 보장 합니다.|
|[CComModule::m_hInst](#m_hinst)|모듈 인스턴스에 대한 핸들을 포함합니다.|
|[CComModule::m_hInstResource](#m_hinstresource)|기본적으로 모듈 인스턴스에 대한 핸들이 포함됩니다.|
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|기본적으로 모듈 인스턴스에 대한 핸들이 포함됩니다.|
|[CComModule::m_pObjMap](#m_pobjmap)|모듈 인스턴스에서 유지 관리하는 개체 맵을 가리킵니다.|

## <a name="remarks"></a>설명

> [!NOTE]
> 이 클래스는 더 이상 사용되지 않으며 ATL 코드 생성 마법사는 이제 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및 [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스를 사용합니다. 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오. 다음 정보는 ATL의 이전 릴리스로 만든 응용 프로그램과 함께 사용할 수 있습니다. `CComModule`은 여전히 역방향 기능에 대한 ATL의 일부입니다.

`CComModule`COM 서버 모듈을 구현하여 클라이언트가 모듈의 구성 요소에 액세스할 수 있도록 합니다. `CComModule`DLL(프로세스 중) 및 EXE(로컬) 모듈을 모두 지원합니다.

인스턴스는 `CComModule` 개체 맵을 사용하여 클래스 개체 정의 집합을 유지 관리합니다. 이 개체 맵은 구조의 `_ATL_OBJMAP_ENTRY` 배열로 구현되며 다음에 대한 정보를 포함합니다.

- 시스템 레지스트리에 개체 설명을 입력하고 제거합니다.

- 클래스 팩터리에서 개체를 인스턴스화합니다.

- 구성 요소의 클라이언트와 루트 개체 간의 통신을 설정합니다.

- 클래스 개체의 수명 관리 수행

ATL COM AppWizard를 실행하면 마법사가 자동으로 `_Module`생성됩니다. `CComModule` ATL 프로젝트 마법사에 대한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)문서를 참조하십시오.

또한 `CComModule`ATL은 EXEs 및 Windows 서비스에 대한 아파트 모델 모듈을 구현하는 [CComAutoThreadModule을](../../atl/reference/ccomautothreadmodule-class.md)제공합니다. 여러 아파트에서 `CComAutoThreadModule` 객체를 만들려는 경우모듈을 파생시.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a>CComModule::GetClassObject

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
【인】 만들 개체의 CLSID입니다.

*riid*<br/>
【인】 요청된 인터페이스의 IID입니다.

*ppv*<br/>
【아웃】 *riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppv가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

지정된 CLSID의 개체를 만들고 이 개체에 대한 인터페이스 포인터를 검색합니다.

`GetClassObject`DLL에서만 사용할 수 있습니다.

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CComModule::getmoduleInstance

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Return Value

이 모듈을 식별하는 HINSTANCE입니다.

### <a name="remarks"></a>설명

[m_hInst](#m_hinst) 데이터 멤버를 반환합니다.

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CComModule:::GetResource인스턴스

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Return Value

An HINSTANCE.

### <a name="remarks"></a>설명

[m_hInstResource](#m_hinstresource) 데이터 멤버를 반환합니다.

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>Return Value

An HINSTANCE.

### <a name="remarks"></a>설명

[m_hInstTypeLib](#m_hinsttypelib) 데이터 멤버를 반환합니다.

## <a name="ccommoduleinit"></a><a name="init"></a>CCom모듈::이니트

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 개체 맵 항목의 배열에 대한 포인터입니다.

*H*<br/>
【인】 HINSTANCE또는에 `DLLMain` `WinMain`전달되었습니다.

*plibid*<br/>
【인】 프로젝트와 연결된 형식 라이브러리의 LIBID에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

모든 데이터 멤버를 초기화합니다.

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a>CComModule::m_csObjMap

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>설명

개체 맵에 대한 동기화된 액세스를 보장합니다.

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>설명

형식 라이브러리에 대한 동기화된 액세스를 보장합니다.

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a>CCom모듈::m_csWindowCreate

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>설명

창 클래스 정보와 창 생성 중에 사용되는 정적 데이터에 대한 동기화된 액세스를 보장합니다.

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a>CCom모듈::m_hInst

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>설명

모듈 인스턴스에 대한 핸들을 포함합니다.

[Init](#init) 메서드는 `m_hInst` 또는 `WinMain`에 `DLLMain` 전달된 핸들로 설정합니다.

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a>CComModule::m_hInstResource

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>설명

기본적으로 모듈 인스턴스에 대한 핸들이 포함됩니다.

[Init](#init) 메서드는 `m_hInstResource` 또는 `WinMain`에 `DLLMain` 전달된 핸들로 설정합니다. 리소스에 대한 `m_hInstResource` 핸들로 명시적으로 설정할 수 있습니다.

[GetResourceInstance](#getresourceinstance) 메서드는 에 저장된 `m_hInstResource`핸들을 반환합니다.

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>설명

기본적으로 모듈 인스턴스에 대한 핸들이 포함됩니다.

[Init](#init) 메서드는 `m_hInstTypeLib` 또는 `WinMain`에 `DLLMain` 전달된 핸들로 설정합니다. 핸들을 형식 `m_hInstTypeLib` 라이브러리로 명시적으로 설정할 수 있습니다.

[GetTypeLibInstance](#gettypelibinstance) 메서드는 에 저장된 `m_hInstTypeLib`핸들을 반환합니다.

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a>CComModule::m_pObjMap

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>설명

모듈 인스턴스에서 유지 관리하는 개체 맵을 가리킵니다.

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule::레지스터클래스도우미

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 등록할 개체의 CLSID입니다.

*lpszProgID*<br/>
【인】 개체와 연결된 ProgID입니다.

*lpszVerIndProgID*<br/>
【인】 개체와 연결된 버전 독립적인 ProgID입니다.

*nDescID*<br/>
【인】 개체 설명에 대 한 문자열 리소스의 식별자입니다.

*dwFlags*<br/>
【인】 레지스트리에 입력할 스레딩 모델을 지정합니다. 가능한 값은 THREADFLAGS_APARTMENT, THREADFLAGS_BOTH 또는 AUTPRXFLAG입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

시스템 레지스트리에 개체의 표준 클래스 등록을 입력합니다.

[UpdateRegistryClass](#updateregistryclass) 메서드는 `RegisterClassHelper`을 호출합니다.

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::레지스터클래스개체

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>매개 변수

*dwClsContext*<br/>
【인】 클래스 개체를 실행할 컨텍스트를 지정합니다. 가능한 값은 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER 또는 CLSCTX_LOCAL_SERVER. 이러한 값에 대한 설명은 Windows SDK의 [CLSCTX를](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) 참조하십시오.

*dwFlags*<br/>
【인】 클래스 개체에 대한 연결 유형을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE 또는 REGCLS_MULTI_SEPARATE. 이러한 값에 대한 설명은 Windows SDK의 [REGCLS를](/windows/win32/api/combaseapi/ne-combaseapi-regcls) 참조하십시오.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

다른 응용 프로그램이 연결할 수 있도록 OLE에 EXE 클래스 개체를 등록합니다. 이 메서드는 EXEs에서만 사용할 수 있습니다.

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a>CComModule::레지스터 서버

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
【인】 형식 라이브러리가 등록될지 여부를 나타냅니다. 기본값은 FALSE입니다.

*pCLSID*<br/>
【인】 등록할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*pCLSID* 매개 변수에 따라 단일 클래스 개체 또는 개체 맵의 모든 개체에 대한 시스템 레지스트리를 업데이트합니다.

*bRegTypeLib이* TRUE이면 형식 라이브러리 정보도 업데이트됩니다.

개체 맵에 항목을 추가하는 방법에 대한 자세한 내용은 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 를 참조하십시오.

`RegisterServer`명령줄 옵션으로 EXE 실행을 `DLLRegisterServer` 위해 `WinMain` DLL또는 에 의해 자동으로 호출됩니다. `/RegServer`

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a>CComModule::레지스터TypeLib

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
【인】 형식의 `"\\N"` `N` 문자열은 TYPELIB 리소스의 정수 인덱스입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

유형 라이브러리에 대한 정보를 시스템 레지스트리에 추가합니다.

모듈 인스턴스에 여러 형식 라이브러리가 포함된 경우 이 메서드의 두 번째 버전을 사용하여 사용할 형식 라이브러리를 지정합니다.

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule:::클래스 객체 취소

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

클래스 개체를 제거합니다. 이 메서드는 EXEs에서만 사용할 수 있습니다.

## <a name="ccommoduleterm"></a><a name="term"></a>CCom모듈:::기간

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```cpp
void Term() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다.

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::레지스터 해제클래스 도우미

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 등록취소할 개체의 CLSID입니다.

*lpszProgID*<br/>
【인】 개체와 연결된 ProgID입니다.

*lpszVerIndProgID*<br/>
【인】 개체와 연결된 버전 독립적인 ProgID입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.

[UpdateRegistryClass](#updateregistryclass) 메서드는 `UnregisterClassHelper`을 호출합니다.

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::레지스터 서버 취소

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
TRUE인 경우 형식 라이브러리도 등록취소됩니다.

*pCLSID*<br/>
등록취소할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록취소됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*pCLSID* 매개 변수에 따라 단일 클래스 개체 또는 개체 맵의 모든 개체를 등록 취소합니다.

`UnregisterServer`명령줄 옵션으로 EXE 실행을 `DLLUnregisterServer` 위해 `WinMain` DLL또는 에 의해 자동으로 호출됩니다. `/UnregServer`

개체 맵에 항목을 추가하는 방법에 대한 자세한 내용은 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 를 참조하십시오.

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CCom모듈::업데이트레지스트리클래스

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
등록되거나 등록취소할 개체의 CLSID입니다.

*lpszProgID*<br/>
개체와 연결된 ProgID입니다.

*lpszVerIndProgID*<br/>
개체와 연결된 버전 독립적인 ProgID입니다.

*nDescID*<br/>
개체 설명에 대 한 문자열 리소스의 식별자입니다.

*szDesc*<br/>
개체의 설명이 포함된 문자열입니다.

*dwFlags*<br/>
레지스트리에 입력할 스레딩 모델을 지정합니다. 가능한 값은 THREADFLAGS_APARTMENT, THREADFLAGS_BOTH 또는 AUTPRXFLAG입니다.

*bRegister*<br/>
개체를 등록할지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*bRegister가* TRUE이면 이 메서드는 시스템 레지스트리에 개체의 표준 클래스 등록을 입력합니다.

*bRegister가* FALSE이면 개체의 등록이 제거됩니다.

*bRegister의*값에 따라 `UpdateRegistryClass` [RegisterClassHelper](#registerclasshelper) 또는 [레지스터 클래스 도우미](#unregisterclasshelper)를 호출합니다.

[DECLARE_REGISTRY](registry-macros.md#declare_registry) 매크로를 지정하면 `UpdateRegistryClass` 개체 맵이 처리될 때 자동으로 호출됩니다.

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule::업데이트레지스트리로부터자원

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
【인】 리소스 이름입니다.

*nResID*<br/>
【인】 리소스 ID입니다.

*bRegister*<br/>
【인】 개체를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
【인】 스크립트의 대체 가능한 매개 변수와 연결된 값을 저장하는 대체 맵에 대한 포인터입니다. ATL은 자동으로 `%MODULE%`을 사용합니다. 추가 대체 가능한 매개 변수를 사용하려면 설명에서 자세한 내용을 참조하세요. 그렇지 않으면 NULL 기본값을 사용합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*lpszRes* 또는 *nResID에*의해 지정 된 리소스에 포함 된 스크립트를 실행 합니다.

*bRegister가* TRUE이면 이 메서드는 시스템 레지스트리에 개체를 등록합니다. 그렇지 않으면 개체를 등록 취소합니다.

[DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) 또는 [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) 매크로를 `UpdateRegistryFromResourceD` 지정하면 개체 맵이 처리될 때 자동으로 호출됩니다.

> [!NOTE]
> 런타임에 대체 값을 대체하려면 DECLARE_REGISTRY_RESOURCE 지정하거나 매크로를 DECLARE_REGISTRY_RESOURCEID 마십시오. 대신 각 항목에 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자를 대체할 값과 쌍을 이루는 변수 자리 표시자가 포함된 구조의 배열을 만듭니다. 그런 `UpdateRegistryFromResourceD`다음 *호출하여 pMapEntry* 매개 변수에 대한 배열을 전달합니다. 이렇게 하면 구조의 `_ATL_REGMAP_ENTRIES` 모든 대체 값이 등록기관의 대체 맵에 추가됩니다.

> [!NOTE]
> ATL 레지스트리 구성 요소(레지스트라)에 정적으로 연결하려면 [UpdateRegistryFromResourceS](#updateregistryfromresources)을 참조하십시오.

대체 가능한 매개 변수 및 스크립팅에 대한 자세한 내용은 [ATL 레지스트리 구성 요소(등록기관)](../../atl/atl-registry-component-registrar.md)문서를 참조하십시오.

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule::업데이트레지스트리From리소스

ATL 7.0은 `CComModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
【인】 리소스 이름입니다.

*nResID*<br/>
【인】 리소스 ID입니다.

*bRegister*<br/>
【인】 리소스 스크립트를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
【인】 스크립트의 대체 가능한 매개 변수와 연결된 값을 저장하는 대체 맵에 대한 포인터입니다. ATL은 자동으로 `%MODULE%`을 사용합니다. 추가 대체 가능한 매개 변수를 사용하려면 설명에서 자세한 내용을 참조하세요. 그렇지 않으면 NULL 기본값을 사용합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

[UpdateRegistryFromResourceD](#updateregistryfromresourced)와 유사하게 `UpdateRegistryFromResourceS`를 제외한 ATL 레지스트리 구성 요소 (등록자)에 대한 정적 링크를 만듭니다.

`UpdateRegistryFromResourceS`*pch.h* *(Visual* Studio 2017 및 `#define _ATL_STATIC_REGISTRY` 이전)에 추가하면 개체 맵이 처리될 때 자동으로 호출됩니다.

> [!NOTE]
> 런타임에 대체 값을 대체하려면 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) [지정하거나](registry-macros.md#declare_registry_resourceid) DECLARE_REGISTRY_RESOURCEID 매크로를 지정하지 마십시오. 대신 각 항목에 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자를 대체할 값과 쌍을 이루는 변수 자리 표시자가 포함된 구조의 배열을 만듭니다. 그런 `UpdateRegistryFromResourceS`다음 *호출하여 pMapEntry* 매개 변수에 대한 배열을 전달합니다. 이렇게 하면 구조의 `_ATL_REGMAP_ENTRIES` 모든 대체 값이 등록기관의 대체 맵에 추가됩니다.

대체 가능한 매개 변수 및 스크립팅에 대한 자세한 내용은 [ATL 레지스트리 구성 요소(등록기관)](../../atl/atl-registry-component-registrar.md)문서를 참조하십시오.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
