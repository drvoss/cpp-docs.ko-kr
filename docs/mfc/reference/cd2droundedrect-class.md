---
title: CD2DRoundedRect 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 5189f3d824c008845570eac6eead4a35be1e483d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369082"
---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect 클래스

`D2D1_ROUNDED_RECT`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DRounded렉트::CD2DRounded렉트](#cd2droundedrect)|오버로드되었습니다. 개체에서 `D2D1_ROUNDED_RECT` `CD2DRoundedRect` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_ROUNDED_RECT`

[CD2DRounded렉트](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a>CD2DRounded렉트::CD2DRounded렉트

CD2DRectF 개체에서 CD2DRoundedRect 개체를 생성합니다.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>매개 변수

*정사각형*<br/>
소스 사각형

*크기경수경*<br/>
반경 크기

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
