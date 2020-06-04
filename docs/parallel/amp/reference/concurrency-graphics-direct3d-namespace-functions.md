---
title: Concurrency::graphics::direct3d 네임스페이스 함수
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 330c1aa94b1d122901fc23576686032400249d31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376387"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 네임스페이스 함수

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

## <a name="get_sampler"></a><a name="get_sampler"></a>get_sampler

지정된 샘플러 개체를 나타내는 지정된 가속기 뷰에서 D3D 샘플러 상태 인터페이스를 가져옵니다.

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
D3D 샘플러 상태를 생성할 D3D 가속기 뷰입니다.

*_Sampler*<br/>
기본 D3D 샘플러 상태 인터페이스가 만들어지는 샘플러 개체입니다.

### <a name="return-value"></a>Return Value

지정된 샘플러를 나타내는 D3D 샘플러 상태에 해당하는 IUnknown 인터페이스 포인터입니다.

## <a name="get_texture"></a><a name="get_texture"></a>get_texture

지정된 텍스처 오브젝트의 기본으로 Direct3D [텍스처](texture-class.md) 인터페이스를 가져옵니다.

```cpp
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*Value_type*<br/>
텍스처의 요소 유형입니다.

*_Rank*<br/>
텍스처의 순위입니다.

*_Texture*<br/>
기본 Direct3D 텍스처 인터페이스가 반환되는 accelerator_view 연결된 텍스처 또는 텍스처 뷰입니다.

### <a name="return-value"></a>Return Value

텍스처의 기본 기본 Direct3D 텍스처에 해당하는 IUnknown 인터페이스 포인터입니다.

## <a name="make_sampler"></a><a name="make_sampler"></a>make_sampler

D3D 샘플러 상태 인터페이스 포인터에서 샘플러를 만듭니다.

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_D3D_sampler*<br/>
에서 샘플러를 만들 수있는 D3D 샘플러 상태의 IUnknown 인터페이스 포인터.

### <a name="return-value"></a>Return Value

샘플러는 제공된 D3D 샘플러 상태를 나타냅니다.

## <a name="make_texture"></a><a name="make_texture"></a>make_texture

지정된 매개 변수를 사용하여 [텍스처](texture-class.md) 개체를 만듭니다.

```cpp
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*Value_type*<br/>
텍스처의 요소 유형입니다.

*_Rank*<br/>
텍스처의 순위입니다.

*_Av*<br/>
텍스처를 작성할 D3D 가속기 뷰입니다.

*_D3D_texture*<br/>
D3D 텍스처의 IUnknown 인터페이스 포인터를 사용하여 텍스처를 만듭니다.

*_View_format*<br/>
이 텍스처에서 만든 뷰에 사용할 DXGI 형식입니다. 기본 형식인 _D3D_texture 및 이 템플릿의 value_type 형식을 파생하려면 DXGI_FORMAT_UNKNOWN(기본값)을 전달합니다. 제공된 형식은 기본 형식의 _D3D_texture 호환되어야 합니다.

### <a name="return-value"></a>Return Value

제공된 D3D 텍스처를 사용하는 텍스처입니다.

## <a name="msad4"></a><a name="msad4"></a>msad4

4바이트 기준 값과 8바이트 소스 값을 비교하고 4합계의 벡터를 누적합니다. 각 합계는 참조 값과 소스 값 사이의 서로 다른 바이트 선형의 절대 차이의 마스크된 합계에 해당합니다.

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Reference*<br/>
하나의 uint 값에서 4바이트의 참조 배열

*_Source*<br/>
두 uint 값의 벡터에서 8 바이트의 소스 배열입니다.

*_Accum*<br/>
기준 값과 소스 값 사이의 서로 다른 바이트 정렬의 절대 차이의 마스크된 합계에 추가할 4값의 벡터입니다.

### <a name="return-value"></a>Return Value

합계 4의 벡터를 반환합니다. 각 합계는 참조 값과 소스 값 사이의 서로 다른 바이트 선형의 절대 차이의 마스크된 합계에 해당합니다.

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**네임스페이스:** 동시성::그래픽::direct3d

## <a name="see-also"></a>참고 항목

[동시성::그래픽::direct3d 네임스페이스](concurrency-graphics-direct3d-namespace.md)
