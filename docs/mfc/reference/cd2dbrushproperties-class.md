---
title: CD2DBrushProperties 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: 2db720fd09c62f8b86baecea9229d946f3892333
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754190"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties 클래스

`D2D1_BRUSH_PROPERTIES`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D브러시속성:CD2D브러시프로퍼티](#cd2dbrushproperties)|오버로드되었습니다. 구조생성 `CD2D_BRUSH_PROPERTIES`|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CD2D브러시속성:커먼이니트](#commoninit)|개체 초기화|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a>CD2D브러시속성:CD2D브러시프로퍼티

CD2D_BRUSH_PROPERTIES 구조 생성

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>매개 변수

*_opacity*<br/>
브러시의 기본 불투명도입니다. 기본값은 1.0입니다.

*_transform*<br/>
브러시에 적용할 변환

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a>CD2D브러시속성:커먼이니트

개체 초기화

```cpp
void CommonInit();
```

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
