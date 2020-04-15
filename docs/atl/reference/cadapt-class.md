---
title: CAdapt 클래스
ms.date: 11/04/2016
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
ms.openlocfilehash: 23544bc103de0d7b76cd73d403626ba93af6e31a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321636"
---
# <a name="cadapt-class"></a>CAdapt 클래스

이 템플릿은 개체 주소 이외의 주소를 반환하도록 연산자 주소를 다시 정의하는 클래스를 래핑하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
template <class T>
class CAdapt
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
조정된 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAdapt::적응](#cadapt)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAdapt::운영자 const T&](#operator_const_t_amp)|에 대한 const `m_T`참조를 **반환합니다.**|
|[C적응::연산자 T&](#operator_t_amp)|`m_T`에 대한 참조를 반환합니다.|
|[C적응::연산자 <](#operator_lt)|조정된 형식의 개체를 `m_T`와 비교합니다.|
|[C적응::연산자 =](#operator_eq)|조정된 형식의 개체를 `m_T`에 할당합니다.|
|[C적응::연산자 ==](#operator_eq_eq)|조정된 형식의 개체를 `m_T`와 비교합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAdapt::m_T](#m_t)|조정되는 데이터입니다.|

## <a name="remarks"></a>설명

`CAdapt`는 개체의 주소 이외의 주소를 반환하도록 연산자의 주소(`operator &`)를 다시 정의하는 클래스를 래핑하는 데 사용되는 간단한 템플릿입니다. 이러한 클래스의 예로 ATL의 `CComBSTR`, `CComPtr`, `CComQIPtr` 클래스 및 컴파일러 COM 지원 클래스인 `_com_ptr_t`가 있습니다. 이러한 클래스는 모두 해당 데이터 멤버 중 하나의 주소를 반환하는 연산자의 주소를 `CComBSTR`재정의합니다(다른 클래스의 경우 BSTR 및 다른 클래스의 경우 인터페이스 포인터).

`CAdapt`'의 주요 역할은 *클래스 T에*의해 정의 된 연산자의 주소를 숨기는 것입니다, 아직 적응 클래스의 특성을 유지. `CAdapt`이 역할을 수행하려면 공용 멤버, [m_T](#m_t), *T*형식의 변환 연산자, 비교 연산자 및 복사 `CAdapt` 생성자가 *T*형식의 개체인 것처럼 처리되도록 정의하여 이 역할을 수행합니다.

어댑터 클래스 `CAdapt`는 일부 컨테이너 스타일 클래스가 연산자 주소를 사용하여 포함된 개체의 주소를 가져올 수 있기 때문에 유용합니다. 연산자의 주소를 다시 정의하면 일반적으로 컴파일 오류가 발생하고 "작동"해야 하는 클래스에서 조정되지 않은 형식이 사용되지 않아 이 요구 사항에 맞지 않게 됩니다. `CAdapt`가 이러한 문제에 대한 해결 방법을 제공합니다.

일반적으로 컨테이너 스타일 클래스에 `CAdapt`, `CComBSTR`, `CComPtr` 또는 `CComQIPtr` 개체를 저장하려는 경우 `_com_ptr_t`를 사용합니다. 이는 C++11 표준이 지원되기 전에 C++ 표준 라이브러리 컨테이너에 대해 가장 일반적으로 필요했지만, 이제 C++11 표준 라이브러리 컨테이너가 `operator&()`를 오버로드한 형식으로 자동으로 작동합니다. 표준 라이브러리는 내부적으로 [std::addressof를](../../standard-library/memory-functions.md#addressof) 사용하여 개체의 실제 주소를 얻습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="cadaptcadapt"></a><a name="cadapt"></a>CAdapt::적응

생성자는 어댑터 개체를 기본적으로 생성하거나, 적응된 형식의 개체에서 복사하거나, 다른 어댑터 개체에서 복사할 수 있도록 합니다.

```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
새로 생성된 어댑터 개체에 복사하도록 조정되는 형식의 변수입니다.

*rSrCA*<br/>
포함된 데이터를 새로 생성된 어댑터 개체로 복사(또는 이동)해야 하는 어댑터 개체입니다.

## <a name="cadaptm_t"></a><a name="m_t"></a>CAdapt::m_T

적응중인 데이터를 보유합니다.

```
T m_T;
```

### <a name="remarks"></a>설명

이 **공용** 데이터 멤버는 [운영자 const T&](#operator_const_t_amp) 및 운영자 T&직접 또는 간접적으로 액세스할 수 [있습니다. ](#operator_t_amp)

## <a name="cadaptoperator-const-tamp"></a><a name="operator_const_t_amp"></a>CAdapt::연산자 콘스트 T&amp;

[m_T](#m_t) 멤버에 대한 **const** 참조를 반환하여 어댑터 개체가 *T*형식의 개체인 것처럼 처리될 수 있도록 합니다.

```
operator const T&() const;
```

### <a name="return-value"></a>Return Value

에 **const** 대한 `m_T`구성 일 참조입니다.

## <a name="cadaptoperator-tamp"></a><a name="operator_t_amp"></a>C적응::연산자 T&amp;

[m_T](#m_t) 멤버에 대한 참조를 반환하여 어댑터 개체가 *T*형식의 개체인 것처럼 처리될 수 있도록 합니다.

```
operator T&();
```

### <a name="return-value"></a>Return Value

`m_T`에 대한 참조입니다.

## <a name="cadaptoperator-lt"></a><a name="operator_lt"></a>C적응::연산자&lt;

적응된 형식의 개체를 [m_T](#m_t)비교합니다.

```
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
비교할 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

`m_T` *rSrc*. 사이의 비교 결과 .

## <a name="cadaptoperator-"></a><a name="operator_eq"></a>C적응::연산자 =

할당 연산자는 m_T 데이터 [멤버에](#m_t) 인수 *rSrc를*할당하고 현재 어댑터 개체를 반환합니다.

```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
복사할 적응된 형식의 개체에 대한 참조입니다.

*rSrCA*<br/>
이동할 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

현재 개체에 대한 참조입니다.

## <a name="cadaptoperator-"></a><a name="operator_eq_eq"></a>C적응::연산자 ==

적응된 형식의 개체를 [m_T](#m_t)비교합니다.

```
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
비교할 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

*m_T* *rSrc*사이의 비교의 결과 .

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
