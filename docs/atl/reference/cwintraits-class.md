---
title: CWinTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: fd73f733e4eff21da92937d1e1b0cce21552a48c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330307"
---
# <a name="cwintraits-class"></a>CWinTraits 클래스

이 클래스는 창 개체를 만들 때 사용되는 스타일을 표준화하는 방법을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>매개 변수

*t_dwStyle*<br/>
기본 표준 창 스타일입니다.

*t_dwExStyle*<br/>
기본 확장 창 스타일입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinTraits::GetWndEx스타일](#getwndexstyle)|(정적) 개체에 대한 확장 `CWinTraits` 스타일을 검색합니다.|
|[CWinTraits:::GetWnd스타일](#getwndstyle)|(정적) 개체에 대한 표준 `CWinTraits` 스타일을 검색합니다.|

## <a name="remarks"></a>설명

이 [창 특성](../../atl/understanding-window-traits.md) 클래스는 ATL 창 개체를 만드는 데 사용되는 스타일을 표준화하는 간단한 방법을 제공합니다. 이 클래스의 특수화를 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 또는 ATL의 다른 창 클래스에 템플릿 매개 변수로 사용하여 해당 창 클래스의 인스턴스에 사용되는 기본 표준 및 확장 스타일을 지정합니다.

[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)에 대한 호출에서 다른 스타일을 지정하지 않은 경우에만 사용되는 기본 창 스타일을 제공하려는 경우 이 템플릿을 사용합니다.

ATL은 일반적으로 사용되는 창 스타일 조합에 대해 이 템플릿의 미리 정의된 세 가지 특수화를 제공합니다.

- `CControlWinTraits`

   표준 제어 창을 위해 설계되었습니다. WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 다음과 같은 표준 스타일이 사용됩니다. 확장 된 스타일이 없습니다.

- `CFrameWinTraits`

   표준 프레임 창을 위해 설계되었습니다. 사용되는 표준 스타일은 WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 포함합니다. 사용되는 확장 된 스타일은 다음과 같습니다 : WS_EX_APPWINDOW WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`

   표준 MDI 자식 창을 위해 설계되었습니다. 사용되는 표준 스타일은 WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 포함합니다. 사용되는 확장 스타일은 다음과 같습니다 WS_EX_MDICHILD.

다른 스타일을 인스턴스별로 설정할 수 있도록 허용하면서 창 클래스의 모든 인스턴스에 대해 특정 스타일을 설정하려면 [대신 CWinTraitsOR를](../../atl/reference/cwintraitsor-class.md) 사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a>CWinTraits:::GetWnd스타일

이 함수를 호출하여 개체의 `CWinTraits` 표준 스타일을 검색합니다.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창 작성에 사용되는 표준 스타일입니다. *dwStyle이* 0이면 템플릿 스타일`t_dwStyle`값()이 반환됩니다. *dwStyle이* 0이 아닌 경우 *dwStyle이* 반환됩니다.

### <a name="return-value"></a>Return Value

개체의 표준 창 스타일입니다.

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraits::GetWndEx스타일

이 함수를 호출하여 개체의 `CWinTraits` 확장된 스타일을 검색합니다.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
창 작성에 사용되는 확장 스타일입니다. *dwExStyle이* 0이면 템플릿 스타일`t_dwExStyle`값()이 반환됩니다. *dwExStyle이* 0이 아닌 경우 *dwExStyle이* 반환됩니다.

### <a name="return-value"></a>Return Value

개체의 확장된 창 스타일입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[창 특성 이해](../../atl/understanding-window-traits.md)
