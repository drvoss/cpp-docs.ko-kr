---
title: 픽셀-HIMETRIC 변환 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 43a12985f259603a9b67f22f7a7891bf847c0b0f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423017"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Pixel/HIMETRIC 변환 전역 함수

이러한 함수는 픽셀 및 HIMETRIC 단위로 변환 하기 위한 지원을 제공 합니다.

> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 단위 (각 단위는 0.01 밀리미터)를 픽셀로 변환 합니다.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|픽셀을 HIMETRIC 단위로 변환 합니다 (각 단위는 0.01 밀리미터).|

##  <a name="atlhimetrictopixel"></a>AtlHiMetricToPixel

개체의 HIMETRIC 단위 크기(각 단위는 0.01mm)를 화면 디바이스의 픽셀 크기로 변환합니다.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>매개 변수

*lpSizeInHiMetric*<br/>
진행 HIMETRIC unit의 개체 크기에 대 한 포인터입니다.

*lpSizeInPix*<br/>
제한이 개체의 크기 (픽셀)가 반환 될 위치에 대 한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="atlpixeltohimetric"></a>AtlPixelToHiMetric

화면 디바이스에서 개체의 픽셀 크기를 HIMETRIC 단위의 크기(각 단위는 0.01mm)로 변환합니다.

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>매개 변수

*lpSizeInPix*<br/>
진행 개체의 크기 (픽셀)에 대 한 포인터입니다.

*lpSizeInHiMetric*<br/>
제한이 HIMETRIC unit에서 개체의 크기가 반환 될 위치에 대 한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:.**

## <a name="see-also"></a>참고 항목

[함수](../../atl/reference/atl-functions.md)
