---
title: CD2DPointF 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 5d66c31289f9e17df99df4681cff1d5cf6a0ec86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369153"
---
# <a name="cd2dpointf-class"></a>CD2DPointF 클래스

`D2D1_POINT_2F`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D포인트F::CD2D포인트F](#cd2dpointf)|오버로드되었습니다. 개체에서 `D2D1_POINT_2F` `CD2DPointF` 개체를 생성합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DPointF::연산자 C포인트](#operator_cpoint)|개체로 `CD2DPointF` `CPoint` 변환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a>CD2D포인트F::CD2D포인트F

CPoint 개체에서 CD2DPointF 개체를 생성합니다.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
소스 점

*Fx*<br/>
소스 X

*년도*<br/>
소스 Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointF::연산자 C포인트

CD2DPointF를 CPoint 개체로 변환합니다.

```
operator CPoint();
```

### <a name="return-value"></a>Return Value

D2D 점의 현재 값입니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
