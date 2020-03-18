---
title: CAtlWinModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423407"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule 클래스

이 클래스는 ATL 창 구성 요소에 대 한 지원을 제공 합니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtlWinModule:: CAtlWinModule](#catlwinmodule)|생성자입니다.|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlWinModule:: AddCreateWndData](#addcreatewnddata)|데이터 개체를 추가 합니다.|
|[CAtlWinModule:: ExtractCreateWndData](#extractcreatewnddata)|창 모듈 데이터 개체에 대 한 포인터를 반환 합니다.|

## <a name="remarks"></a>설명

이 클래스는 창 고 기능을 필요로 하는 모든 ATL 클래스를 지원 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="addcreatewnddata"></a>CAtlWinModule:: AddCreateWndData

이 메서드는 `_AtlCreateWndData` 구조체를 초기화 하 고 추가 합니다.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>매개 변수

*pData*<br/>
초기화 되어 현재 모듈에 추가 되는 `_AtlCreateWndData` 구조체에 대 한 포인터입니다.

*pObject*<br/>
개체의 **this** 포인터에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조체를 초기화 하는 [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) 를 호출 합니다. 이 구조체는 창 프로시저에서 클래스 인스턴스를 가져오는 데 사용 되는 **this** 포인터를 저장 합니다.

##  <a name="catlwinmodule"></a>CAtlWinModule:: CAtlWinModule

생성자입니다.

```
CAtlWinModule();
```

### <a name="remarks"></a>설명

초기화에 실패 하면 **EXCEPTION_NONCONTINUABLE** 예외가 발생 합니다.

##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule

소멸자입니다.

```
~CAtlWinModule();
```

### <a name="remarks"></a>설명

할당 된 리소스를 모두 해제 합니다.

##  <a name="extractcreatewnddata"></a>CAtlWinModule:: ExtractCreateWndData

이 메서드는 `_AtlCreateWndData` 구조체에 대 한 포인터를 반환 합니다.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Return Value

[AddCreateWndData](#addcreatewnddata)를 사용 하 여 이전에 추가 된 `_AtlCreateWndData` 구조체에 대 한 포인터를 반환 하거나, 사용할 수 있는 개체가 없으면 NULL을 반환 합니다.

## <a name="see-also"></a>참고 항목

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
