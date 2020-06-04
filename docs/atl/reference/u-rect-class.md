---
title: _U_RECT 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 8a4d5b2a770b3f0ecfe10be0fbad22a702aa0531
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325804"
---
# <a name="_u_rect-class"></a>_U_RECT 클래스

이 인수 어댑터 `RECT` 클래스를 사용하면 포인터 또는 참조를 포인터 측면에서 구현되는 함수에 전달할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class _U_RECT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[_U_RECT:_U_RECT](#_u_rect___u_rect)|생성자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[_U_RECT:m_lpRect](#_u_rect__m_lprect)|`RECT`에 대한 포인터|

## <a name="remarks"></a>설명

클래스는 두 개의 생성자 오버로드를 정의합니다: 하나는 **RECT**&`LPRECT` 인수를 받아들이고 다른 하나는 인수를 수락합니다. 첫 번째 생성자는 참조 인수의 주소를 클래스의 단일 데이터 [멤버인 m_lpRect](#_u_rect__m_lprect)에 저장합니다. 포인터 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a>_U_RECT:m_lpRect

클래스는 공용 `LPRECT` 데이터 멤버로 생성자 중 하나에 전달 된 값을 보유 합니다.

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a>_U_RECT:_U_RECT

참조 인수의 주소는 클래스의 단일 데이터 [멤버에](#_u_rect__m_lprect)저장되며 m_lpRect.

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Rc*<br/>
`RECT` 참조입니다.

*Lprect*<br/>
`RECT` 포인터입니다.

### <a name="remarks"></a>설명

포인터 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
