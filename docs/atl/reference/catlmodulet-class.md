---
title: CAtlModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: bf64c073249b7426fafb430a708573d9d06d11fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321418"
---
# <a name="catlmodulet-class"></a>CAtlModuleT 클래스

이 클래스는 ATL 모듈을 구현합니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 `CAtlModuleT`클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀 모듈: :CAtlModuleT](#catlmodulet)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[카틀 모듈: :이니리리브](#initlibid)|현재 모듈의 GUID를 포함하는 데이터 멤버를 초기화합니다.|
|[카틀 모듈T::레지스터앱Id](#registerappid)|레지스트리에 EXE를 추가합니다.|
|[CAtlModuleT::레지스터 서버](#registerserver)|레지스트리에 서비스를 추가합니다.|
|[CAtlModuleT::등록 해제](#unregisterappid)|레지스트리에서 EXE를 제거합니다.|
|[CAtlModuleT::레지스터 서버 취소](#unregisterserver)|레지스트리에서 서비스를 제거합니다.|
|[CAtlModuleT::업데이트레지스트리앱피드](#updateregistryappid)|레지스트리의 EXE 정보를 업데이트합니다.|

## <a name="remarks"></a>설명

`CAtlModuleT`, [CAtlModule에서](../../atl/reference/catlmodule-class.md)파생된 실행(EXE) 또는 서비스(EXE) ATL 모듈을 구현합니다. 실행 모듈은 로컬, 프로세스 외 서버, 서비스 모듈은 Windows 시작 시 백그라운드에서 실행 되는 Windows 응용 프로그램입니다.

`CAtlModuleT`모듈의 초기화, 등록 및 등록 취소에 대한 지원을 제공합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a>카틀 모듈: :CAtlModuleT

생성자입니다.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>설명

[CAtlModuleT를 호출 ::InitLibId](#initlibid).

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a>카틀 모듈: :이니리리브

현재 모듈의 GUID를 포함하는 데이터 멤버를 초기화합니다.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>설명

생성자 [CAtlModuleT에 의해 호출::CAtlModuleT](#catlmodulet).

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a>카틀 모듈T::레지스터앱Id

레지스트리에 EXE를 추가합니다.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a>CAtlModuleT::레지스터 서버

레지스트리에 서비스를 추가합니다.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록할 경우 기본값은 FALSE입니다.

*pCLSID*<br/>
등록할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlModuleT::등록 해제

레지스트리에서 EXE를 제거합니다.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a>CAtlModuleT::레지스터 서버 취소

레지스트리에서 서비스를 제거합니다.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
TRUE 형식 라이브러리도 등록 취소할 수 있는 경우

*pCLSID*<br/>
등록취소할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록취소됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a>CAtlModuleT::업데이트레지스트리앱피드

레지스트리의 EXE 정보를 업데이트합니다.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>매개 변수

*bRegister*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="see-also"></a>참고 항목

[카틀 모듈 클래스](../../atl/reference/catlmodule-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
