---
title: CAtlComModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
ms.openlocfilehash: 68fdb48edc9304d9d74df6f36bd208cfd35ff307
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321479"
---
# <a name="catlcommodule-class"></a>CAtlComModule 클래스

이 클래스는 COM 서버 모듈을 구현합니다.

## <a name="syntax"></a>구문

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtlCom모듈::CAtlCom모듈](#catlcommodule)|생성자입니다.|
|[CAtlCom모듈::~카틀컴모듈](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlComModule::레지스터 서버](#registerserver)|이 메서드를 호출하여 개체 맵의 각 개체에 대한 시스템 레지스트리를 업데이트합니다.|
|[CAtlComModule::레지스터타이핑리브](#registertypelib)|형식 라이브러리를 등록하려면 이 메서드를 호출합니다.|
|[CAtlComModule::레지스터 서버 취소](#unregisterserver)|이 메서드를 호출하여 개체 맵의 각 개체를 등록 취소합니다.|
|[CAtlComModule::등록 취소TypeLib](#unregistertypelib)|형식 라이브러리를 등록 취소하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CAtlComModule`COM 서버 모듈을 구현하여 클라이언트가 모듈의 구성 요소에 액세스할 수 있도록 합니다.

이 클래스는 이전 버전의 ATL에서 사용된 사용되지 않는 [CComModule](../../atl/reference/ccommodule-class.md) 클래스를 대체합니다. 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>CAtlCom모듈::CAtlCom모듈

생성자입니다.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>설명

모듈을 초기화합니다.

## <a name="catlcommodulecatlcommodule"></a><a name="dtor"></a>CAtlCom모듈::~카틀컴모듈

소멸자입니다.

```
~CAtlComModule();
```

### <a name="remarks"></a>설명

모든 클래스 공장을 해제합니다.

## <a name="catlcommoduleregisterserver"></a><a name="registerserver"></a>CAtlComModule::레지스터 서버

이 메서드를 호출하여 개체 맵의 각 개체에 대한 시스템 레지스트리를 업데이트합니다.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록할 경우 기본값은 FALSE입니다.

*pCLSID*<br/>
등록할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

글로벌 함수 [AtlComModuleRegisterServer를](server-registration-global-functions.md#atlcommoduleregisterserver)호출합니다.

## <a name="catlcommoduleregistertypelib"></a><a name="registertypelib"></a>CAtlComModule::레지스터타이핑리브

형식 라이브러리를 등록하려면 이 메서드를 호출합니다.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
N이 TYPELIB\\리소스의 정수 인덱스인 형식 "\N"의 문자열입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

유형 라이브러리에 대한 정보를 시스템 레지스트리에 추가합니다. 모듈 인스턴스에 여러 형식 라이브러리가 포함된 경우 이 메서드의 첫 번째 버전을 사용하여 사용할 형식 라이브러리를 지정합니다.

## <a name="catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>CAtlComModule::레지스터 서버 취소

이 메서드를 호출하여 개체 맵의 각 개체를 등록 취소합니다.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록 취소할 경우 기본값은 FALSE입니다.

*pCLSID*<br/>
등록취소할 개체의 CLSID를 가리킵니다. NULL(기본값)이 면 개체 맵의 모든 오브젝트가 등록취소됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

글로벌 함수 [AtlComModuleUnregisterServer를](server-registration-global-functions.md#atlcommoduleunregisterserver)호출합니다.

## <a name="catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>CAtlComModule::등록 취소TypeLib

형식 라이브러리를 등록 취소하려면 이 메서드를 호출합니다.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
N이 TYPELIB\\리소스의 정수 인덱스인 형식 "\N"의 문자열입니다.

### <a name="remarks"></a>설명

시스템 레지스트리에서 형식 라이브러리에 대한 정보를 제거합니다. 모듈 인스턴스에 여러 형식 라이브러리가 포함된 경우 이 메서드의 첫 번째 버전을 사용하여 사용할 형식 라이브러리를 지정합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="see-also"></a>참고 항목

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
