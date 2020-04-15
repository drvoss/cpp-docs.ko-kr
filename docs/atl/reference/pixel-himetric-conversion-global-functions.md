---
title: 픽셀 하이메트릭 변환 전역 기능
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 08c72c0d8f3d061950d6945d9fb412c0a16355da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326152"
---
# <a name="pixelhimetric-conversion-global-functions"></a>픽셀/하이메트릭 변환 전역 함수

이러한 함수는 픽셀 및 HIMETRIC 단위로 변환하는 데 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 단위(각 단위는 0.01밀리미터)를 픽셀로 변환합니다.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|픽셀을 HIMETRIC 단위로 변환합니다(각 단위는 0.01밀리미터).|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>아틀하이메트릭토픽셀

개체의 HIMETRIC 단위 크기(각 단위는 0.01mm)를 화면 디바이스의 픽셀 크기로 변환합니다.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>매개 변수

*lpSizeInHiMetric*<br/>
【인】 HIMETRIC 단위의 개체 크기에 대한 포인터입니다.

*lpSizeInPix*<br/>
【아웃】 개체의 크기를 픽셀 단위로 반환할 위치에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>아틀픽셀토히메트릭

화면 디바이스에서 개체의 픽셀 크기를 HIMETRIC 단위의 크기(각 단위는 0.01mm)로 변환합니다.

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>매개 변수

*lpSizeInPix*<br/>
【인】 개체의 크기에 대한 픽셀 을 포인터입니다.

*lpSizeInHiMetric*<br/>
【아웃】 HIMETRIC 단위의 개체 크기를 반환할 위치에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
