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
ms.openlocfilehash: e131ca1b4eb6e320d533ad1292c23add6ffa46e5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748558"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule 클래스

이 클래스는 ATL 창 구성 요소에 대한 지원을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀윈 모듈::CAtlWin모듈](#catlwinmodule)|생성자입니다.|
|[카틀윈 모듈::~카틀윈모듈](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlWin모듈::추가 생성WndData](#addcreatewnddata)|데이터 개체를 추가합니다.|
|[CAtlWin모듈::추출생성WndData](#extractcreatewnddata)|창 모듈 데이터 개체에 대한 포인터를 반환합니다.|

## <a name="remarks"></a>설명

이 클래스는 창 기능을 필요로 하는 모든 ATL 클래스에 대 한 지원을 제공 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWin모듈::추가 생성WndData

이 메서드는 구조를 초기화 하고 추가 합니다. `_AtlCreateWndData`

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>매개 변수

*Pdata*<br/>
초기화되고 `_AtlCreateWndData` 현재 모듈에 추가할 구조에 대한 포인터입니다.

*pObject*<br/>
개체의 **이** 포인터에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조를 초기화하는 [AtlWinModuleAddCreateWndData를](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) 호출합니다. 이 구조는 창 프로시저에서 클래스 인스턴스를 가져오는 데 사용되는 **이** 포인터를 저장합니다.

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>카틀윈 모듈::CAtlWin모듈

생성자입니다.

```
CAtlWinModule();
```

### <a name="remarks"></a>설명

초기화가 실패하면 **EXCEPTION_NONCONTINUABLE** 예외가 발생합니다.

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>카틀윈 모듈::~카틀윈모듈

소멸자입니다.

```
~CAtlWinModule();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWin모듈::추출생성WndData

이 메서드는 구조체에 대한 포인터를 반환합니다. `_AtlCreateWndData`

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Return Value

`_AtlCreateWndData` [CAtlWinModule::AddCreateWndData](#addcreatewnddata)및 사용할 수 있는 개체가 없는 경우 NULL로 이전에 추가된 구조에 대한 포인터를 반환합니다.

## <a name="see-also"></a>참조

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
