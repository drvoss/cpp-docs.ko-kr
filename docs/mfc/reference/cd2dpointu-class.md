---
title: CD2DPointU 클래스
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 8c6db55f1dde1fd054a1f75590f5969c097b2f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369152"
---
# <a name="cd2dpointu-class"></a>CD2DPointU 클래스

`D2D1_POINT_2U`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|오버로드되었습니다. 개체 개체에서 `CD2DPointU` `D2D1_POINT_2U` 를 생성합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DPointU::연산자 C포인트](#operator_cpoint)|개체로 `CD2DPointU` `CPoint` 변환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dpointucd2dpointu"></a><a name="cd2dpointu"></a>CD2DPointU::CD2DPointU

CPoint 개체에서 CD2DPointU 개체를 생성합니다.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
소스 점

*Ux*<br/>
소스 X

*Uy*<br/>
소스 Y

## <a name="cd2dpointuoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointU::연산자 C포인트

CD2DPointU를 CPoint 개체로 변환합니다.

```
operator CPoint();
```

### <a name="return-value"></a>Return Value

D2D 점의 현재 값입니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
