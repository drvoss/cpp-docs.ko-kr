---
title: writeonly_texture_view 클래스
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 8978a548ed246c59d7e7f007f1180685c7343a14
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126242"
---
# <a name="writeonly_texture_view-class"></a>writeonly_texture_view 클래스

질감에 대 한 writeonly 액세스를 제공 합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
질감에 있는 요소의 형식입니다.

*_Rank*<br/>
질감의 순위입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|name|설명|
|----------|-----------------|
|`scalar_type`||
|`value_type`|질감에 있는 요소의 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[writeonly_texture_view 생성자](#ctor)|`writeonly_texture_view` 클래스의 새 인스턴스를 초기화합니다.|
|[~ writeonly_texture_view 소멸자](#ctor)|`writeonly_texture_view` 개체를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[set](#set)|지정 된 인덱스에 있는 요소의 값을 설정 합니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[operator=](#operator_eq)|지정 된 `writeonly_texture_view` 개체를이 개체에 복사 합니다.|

### <a name="public-constants"></a>공용 상수

|name|설명|
|----------|-----------------|
|[rank 상수](#rank)|`writeonly_texture_view` 개체의 순위를 가져옵니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics. h

**네임 스페이스:** Concurrency:: graphics

## <a name="dtor"></a>~ writeonly_texture_view

`writeonly_texture_view` 개체를 소멸 시킵니다.

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator_eq"></a>연산자 =

지정 된 `writeonly_texture_view` 개체를이 개체에 복사 합니다.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
복사할 개체 `writeonly_texture_view`입니다.

### <a name="return-value"></a>Return Value

이 `writeonly_texture_view` 개체에 대 한 참조입니다.

## <a name="rank"></a>배열

`writeonly_texture_view` 개체의 순위를 가져옵니다.

```cpp
static const int rank = _Rank;
```

## <a name="set"></a>설정

지정 된 인덱스에 있는 요소의 값을 설정 합니다.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 인덱스입니다.

*값*<br/>
요소의 새 값입니다.

## <a name="ctor"></a>writeonly_texture_view

`writeonly_texture_view` 클래스의 새 인스턴스를 초기화합니다.

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
질감의 순위입니다.

*value_type*<br/>
질감에 있는 요소의 형식입니다.

*_Src*<br/>
`writeonly_texture_view`를 만드는 데 사용되는 질감입니다.

## <a name="see-also"></a>참고 항목

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
