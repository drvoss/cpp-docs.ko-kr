---
title: CAtlBaseModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: a55412eff18fd04ac4e41c0f001991c1cf725b9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321503"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule 클래스

이 클래스는 모든 ATL 프로젝트에서 인스턴스화됩니다.

## <a name="syntax"></a>구문

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀베이스 모듈::CAtlBaseModule](#catlbasemodule)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlBaseModule::추가 리소스 인스턴스](#addresourceinstance)|저장된 핸들 목록에 리소스 인스턴스를 추가합니다.|
|[카틀베이스 모듈::GetHInstanceAt](#gethinstanceat)|지정된 리소스 인스턴스에 핸들을 반환합니다.|
|[CAtlBase모듈::겟모듈인스턴스](#getmoduleinstance)|개체에서 모듈 인스턴스를 반환합니다. `CAtlBaseModule`|
|[CAtlBaseModule::GetResource인스턴스](#getresourceinstance)|개체에서 리소스 인스턴스를 반환합니다. `CAtlBaseModule`|
|[CAtlBaseModule::제거리소스 인스턴스](#removeresourceinstance)|저장된 핸들 목록에서 리소스 인스턴스를 제거합니다.|
|[CAtlBaseModule::SetResource인스턴스](#setresourceinstance)|개체의 리소스 인스턴스를 설정합니다. `CAtlBaseModule`|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[카틀베이스 모듈::m_bInitFailed](#m_binitfailed)|모듈 초기화가 실패했는지 를 나타내는 변수입니다.|

## <a name="remarks"></a>설명

`CAtlBaseModule` 명명된 _AtlBaseModule 인스턴스는 모든 ATL 프로젝트에 존재하며, 여기에는 모듈 인스턴스에 대한 핸들, 리소스가 포함된 모듈에 대한 핸들(기본적으로 하나와 동일) 및 기본 리소스를 제공하는 모듈에 대한 핸들 배열이 포함됩니다. `CAtlBaseModule`여러 스레드에서 안전하게 액세스할 수 있습니다.

이 클래스는 이전 버전의 ATL에서 사용된 사용되지 않는 [CComModule](../../atl/reference/ccommodule-class.md) 클래스를 대체합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule::추가 리소스 인스턴스

저장된 핸들 목록에 리소스 인스턴스를 추가합니다.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*힌스트 (약)*<br/>
추가할 리소스 인스턴스입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 리소스가 성공적으로 추가된 경우 true를 반환합니다.

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>카틀베이스 모듈::CAtlBaseModule

생성자입니다.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>설명

`CAtlBaseModule`를 만듭니다.

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>카틀베이스 모듈::GetHInstanceAt

지정된 리소스 인스턴스에 핸들을 반환합니다.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
리소스 인스턴스의 수입니다.

### <a name="return-value"></a>Return Value

해당 리소스 인스턴스가 없는 경우 핸들을 리소스 인스턴스 또는 NULL로 반환합니다.

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBase모듈::겟모듈인스턴스

개체에서 모듈 인스턴스를 반환합니다. `CAtlBaseModule`

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Return Value

모듈 인스턴스를 반환합니다.

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule::GetResource인스턴스

리소스 인스턴스를 반환합니다.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Return Value

리소스 인스턴스를 반환합니다.

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a>카틀베이스 모듈::m_bInitFailed

모듈 초기화가 실패했는지 를 나타내는 변수입니다.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>설명

모듈이 초기화된 경우 true, 초기화에 실패한 경우 false입니다.

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule::제거리소스 인스턴스

저장된 핸들 목록에서 리소스 인스턴스를 제거합니다.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*힌스트 (약)*<br/>
제거할 리소스 인스턴스입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 리소스가 성공적으로 제거된 경우 true를 반환합니다.

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule::SetResource인스턴스

개체의 리소스 인스턴스를 설정합니다. `CAtlBaseModule`

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*힌스트 (약)*<br/>
새 리소스 인스턴스입니다.

### <a name="return-value"></a>Return Value

업데이트된 리소스 인스턴스를 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
