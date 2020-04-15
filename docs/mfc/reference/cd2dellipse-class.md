---
title: CD2DEllipse 클래스
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 82ad2fbfb8558486134f85d7ec9bcaa6eb4e7507
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369267"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse 클래스

`D2D1_ELLIPSE`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|오버로드되었습니다. 개체에서 `D2D1_ELLIPSE` `CD2DEllipse` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse

CD2DRectF 개체에서 CD2DEllipse 개체를 생성합니다.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형

*ellipse*<br/>
소스 타원

*pt센터*<br/>
타원의 중심점입니다.

*크기경수경*<br/>
타원의 X 반지름과 Y 반지름입니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
