---
title: CAtlDllModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: 7a5f8e7e489c8e0d573569ac7c4a8fb63f652732
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319009"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT 클래스

이 클래스는 DLL에 대한 모듈을 나타냅니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 `CAtlDllModuleT`클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀들 모듈: :CAtlDll모듈](#catldllmodulet)|생성자입니다.|
|[카틀들 모듈 : :~카틀델 모듈](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL을 언로드할 수 있는지 테스트합니다.|
|[CAtlDllModuleT::DllGetClass개체](#dllgetclassobject)|클래스 팩터리를 반환합니다.|
|[카틀들모듈T::D메인](#dllmain)|동적 링크 라이브러리(DLL)에 대한 선택적 진입점입니다.|
|[CAtlDllModuleT::Dll레지스터 서버](#dllregisterserver)|DLL의 개체에 대한 시스템 레지스트리에 항목을 추가합니다.|
|[CAtlDllModuleT::DllunregisterServer](#dllunregisterserver)|DLL의 개체에 대한 시스템 레지스트리의 항목을 제거합니다.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|클래스 팩터리를 반환합니다. [DllGetClassObject에](#dllgetclassobject)의해 호출됩니다.|

## <a name="remarks"></a>설명

`CAtlDllModuleT`은 동적 링크 라이브러리(DLL)에 대한 모듈을 나타내며 모든 DLL 프로젝트에서 사용되는 함수를 제공합니다. [CAtlModuleT](../../atl/reference/catlmodulet-class.md) 클래스의 이 전문화에는 등록 지원이 포함됩니다.

ATL 모듈에 대한 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a>카틀들 모듈: :CAtlDll모듈

생성자입니다.

```
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a>카틀들 모듈 : :~카틀델 모듈

소멸자입니다.

```
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow

DLL을 언로드할 수 있는지 테스트합니다.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Return Value

DLL을 언로드할 수 있는 경우 S_OK 반환하거나 S_FALSE 수 없는 경우 반환합니다.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClass개체

클래스 팩터리를 반환합니다.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
만들 개체의 CLSID입니다.

*riid*<br/>
요청된 인터페이스의 IID입니다.

*ppv*<br/>
*riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppv가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a>카틀들모듈T::D메인

동적 링크 라이브러리(DLL)에 대한 선택적 진입점입니다.

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>매개 변수

*dwReason*<br/>
DLL_PROCESS_ATTACH 설정하면 DLL_THREAD_ATTACH 및 DLL_THREAD_DETACH 알림 호출이 비활성화됩니다.

*lpreserved*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

DLL_THREAD_ATTACH 및 DLL_THREAD_DETACH 알림 호출을 사용하지 않도록 설정하는 것은 많은 DLL이 있고, 스레드를 자주 만들고 삭제하며, DLL이 이러한 스레드 수준 첨부/분리 알림이 필요하지 않은 다중 스레드 응용 프로그램에 유용한 최적화가 될 수 있습니다.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a>CAtlDllModuleT::Dll레지스터 서버

DLL의 개체에 대한 시스템 레지스트리에 항목을 추가합니다.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록할 경우 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a>CAtlDllModuleT::DllunregisterServer

DLL의 개체에 대한 시스템 레지스트리의 항목을 제거합니다.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
TRUE 형식 라이브러리를 레지스트리에서 제거할 경우 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a>CAtlDllModuleT::GetClassObject

지정된 CLSID의 개체를 만듭니다.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
만들 개체의 CLSID입니다.

*riid*<br/>
요청된 인터페이스의 IID입니다.

*ppv*<br/>
*riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppv가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlDllModuleT::DllGetClassObject에](#dllgetclassobject) 의해 호출 되며 이전 버전과의 호환성을 위해 포함 됩니다.

## <a name="see-also"></a>참고 항목

[CAtlModuleT 클래스](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
