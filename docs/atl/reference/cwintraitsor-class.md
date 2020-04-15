---
title: CWinTraitsOR 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 825f79190c6f68cd1372154e4e02f430f545aa48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330276"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR 클래스

이 클래스는 창 개체를 만들 때 사용되는 스타일을 표준화하는 방법을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>매개 변수

*t_dwStyle*<br/>
기본 창 스타일입니다.

*t_dwExStyle*<br/>
기본 확장 창 스타일입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinTraitsOR::GetWndEx스타일](#getwndexstyle)|개체에 대한 확장 `CWinTraitsOR` 스타일을 검색합니다.|
|[CWinTraitsOR::GetWnd스타일](#getwndstyle)|개체에 대한 표준 `CWinTraitsOR` 스타일을 검색합니다.|

## <a name="remarks"></a>설명

이 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체를 만드는 데 사용되는 스타일을 표준화하는 간단한 방법을 제공합니다. 이 클래스의 특수화를 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 ATL의 다른 창 클래스에 템플릿 매개 변수로 사용하여 해당 창 클래스의 인스턴스에 사용할 최소 표준 및 확장 스타일 집합을 지정합니다.

[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)를 호출할 때 인스턴스별로 다른 스타일을 설정할 수 있도록 허용하면서 창 클래스의 모든 인스턴스에 대해 특정 스타일을 설정하려는 경우 이 템플릿의 특수화를 사용합니다.

호출에 다른 스타일이 지정되지 않은 경우에만 사용되는 기본 창 스타일을 `CWindowImpl::Create`제공하려면 [대신 CWinTraits를](../../atl/reference/cwintraits-class.md) 사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>CWinTraitsOR::GetWnd스타일

이 함수를 호출하여 `CWinTraits` 개체의 표준 스타일과 *t_dwStyle*지정한 기본 스타일의 조합(논리 OR 연산자 사용)을 검색합니다.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창 만들기에 사용되는 스타일입니다.

### <a name="return-value"></a>Return Value

*dwStyle에서* 전달되는 스타일과 논리적 OR 연산자사용에서 지정한 `t_dwStyle`기본 스타일의 조합입니다.

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraitsOR::GetWndEx스타일

이 함수를 호출하여 `CWinTraits` 개체의 확장된 스타일과 에 의해 `t_dwStyle`지정된 기본 스타일의 조합(논리 OR 연산자 사용)을 검색합니다.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
창 작성에 사용되는 확장 스타일입니다.

### <a name="return-value"></a>Return Value

*dwExStyle에서* 전달되는 확장 스타일과 논리 OR `t_dwExStyle`연산자 사용으로 지정된 기본 스타일 조합

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[창 특성 이해](../../atl/understanding-window-traits.md)
