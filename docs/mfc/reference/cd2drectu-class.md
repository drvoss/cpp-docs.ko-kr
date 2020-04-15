---
title: CD2DRectU 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: 26e647ae01a498a6ad8ca2d7c866f33b01910881
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369105"
---
# <a name="cd2drectu-class"></a>CD2DRectU 클래스

`D2D1_RECT_U`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|오버로드되었습니다. 개체에서 `D2D1_RECT_U` `CD2DRectU` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2DRectU::이스널](#isnull)|식에 유효한 데이터(NULL)가 포함되어 있지 않은지 여부를 나타내는 **부울** 값을 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2DRectU::연산자 CRect](#operator_crect)|개체로 `CD2DRectU` `CRect` 변환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU

CRect 개체에서 CD2DRectU 개체를 생성합니다.

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형

*uLeft*<br/>
소스 왼쪽 좌표

*유톱*<br/>
소스 상단 좌표

*uRight*<br/>
소스 오른쪽 좌표

*uBottom*<br/>
소스 하단 좌표

## <a name="cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::이스널

식에 유효한 데이터(Null)가 포함되어 있지 않은지 여부를 나타내는 부울 값을 반환합니다.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Return Value

사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 모두 0인 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::연산자 CRect

CD2DRectU를 CRect 개체로 변환합니다.

```
operator CRect();
```

### <a name="return-value"></a>Return Value

D2D 사각형의 현재 값입니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
