---
title: "duration 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
dev_langs:
- C++
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::chrono [C++], duration
ms.workload:
- cplusplus
ms.openlocfilehash: 742c6acf9f404275fbf9c74a55abd661224d5bc6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="duration-class"></a>duration 클래스
두 시점 사이에 경과된 시간을 나타내는 *시간 간격*을 포함하는 형식을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Rep, class Period = ratio<1>>  
class duration;  
template <class Rep, class Period>  
class duration;  
template <class Rep, class Period1, class Period2>  
class duration <duration<Rep, Period1>, Period2>;  
```  
  
## <a name="remarks"></a>설명  
 템플릿 인수 `Rep`는 간격에 클록 틱 수를 포함하는 데 사용되는 형식을 설명합니다. 템플릿 인수 `Period`는 각 틱이 나타내는 간격 크기를 설명하는 [ratio](../standard-library/ratio.md)의 인스턴스화입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|duration::period Typedef|템플릿 매개 변수 `Period`의 동의어를 나타냅니다.|  
|duration::rep Typedef|템플릿 매개 변수 `Rep`의 동의어를 나타냅니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[duration](#duration)|`duration` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[count](#count)|시간 간격의 클록 틱 수를 반환합니다.|  
|[max](#max)|정적. 템플릿 매개 변수 `Ref`의 최대 허용 값을 반환합니다.|  
|[분](#min)|정적. 템플릿 매개 변수 `Ref`의 최저 허용 값을 반환합니다.|  
|[zero](#zero)|정적. 실제로 `Rep`(0)를 반환합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[duration::operator-](#operator-)|`duration` 개체의 복사본을 부정 틱 개수와 함께 반환합니다.|  
|[duration::operator--](#operator--)|저장된 틱 개수를 줄입니다.|  
|[duration::operator=](#op_eq)|저장된 틱 개수 모듈로를 지정된 값으로 줄입니다.|  
|[duration::operator*=](#op_star_eq)|저장된 틱 개수에 지정된 값을 곱합니다.|  
|[duration::operator/=](#op_div_eq)|저장된 틱 개수를 지정된 `duration` 개체의 틱 개수로 나눕니다.|  
|[duration::operator+](#op_add)|`*this`를 반환합니다.|  
|[duration::operator++](#op_add_add)|저장된 틱 개수를 늘립니다.|  
|[duration::operator+=](#op_add_eq)|지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에 더합니다.|  
|[duration::operator-=](#operator-_eq)|지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에서 뺍니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<c h >  
  
 **네임스페이스:** std::chrono  
  
##  <a name="count"></a>  duration::count  
 시간 간격의 클록 틱 수를 검색합니다.  
  
```  
constexpr Rep count() const;
```  
  
### <a name="return-value"></a>반환 값  
 시간 간격의 클록 틱 수입니다.  
  
##  <a name="duration"></a>  duration::duration Constructor  
 `duration` 개체를 생성합니다.  
  
```  
constexpr duration() = default;  
 
template <class Rep2>  
constexpr explicit duration(const Rep2& R);

 
template <class Rep2, class Period2>  
constexpr duration(const duration<Rep2, Period2>& Dur);
```  
  
### <a name="parameters"></a>매개 변수  
 `Rep2`  
 틱 수를 나타내는 산술 형식입니다.  
  
 `Period2`  
 틱 기간(초)을 나타내는 `std::ratio` 템플릿 특수화입니다.  
  
 `R`  
 기본 기간의 틱 수입니다.  
  
 `Dur`  
 `Period2`로 지정되는 기간의 틱 수입니다.  
  
### <a name="remarks"></a>설명  
 기본 생성자는 초기화되지 않은 개체를 생성합니다. 빈 중괄호를 사용한 값 초기화는 0 클록 틱의 시간 간격을 나타내는 개체를 초기화합니다.  
  
 두 번째 하나의 템플릿 인수 생성자는 `std::ratio<1>`의 기본 기간을 사용하여 `R` 클록 팁의 시간 간격을 나타내는 개체를 생성합니다. 틱 개수 반올림을 방지하려는 경우, `duration::rep`를 부동 소수점 형식으로 처리할 수 없을 때 부동 소수점 형식으로 처리 가능한 표현 형식`Rep2`에서 기간 개체를 생성하는 것은 오류입니다.  
  
 세 번째 두 개의 템플릿 인수 생성자는 `Dur`로 지정되는 시간 간격과 같은 길이를 가진 시간 간격을 나타내는 개체를 생성합니다. 틱 개수 잘림을 방지하려는 경우, 대상 형식과 *전혀 다른* 형식을 가진 다른 기간 개체에서 기간 개체를 생성하는 것은 오류입니다.  
  
 `D2`를 부동 소수점 형식으로 처리할 수 없으며 [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md)이 1이 아닌 경우 기간 형식 `D1`은 또 다른 기간 형식 `D2`와 *전혀 다른* 형식입니다.  
  
 `Rep2`가 암시적으로 `rep`로 변환 가능하고 `treat_as_floating_point<rep>`*가 true를 포함*하거나 `treat_as_floating_point<Rep2>`*가 false를 포함*할 경우 두 번째 생성자가 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.  
  
 오버플로가 변환에서 유도되고 `treat_as_floating_point<rep>`*가 true를 포함*하거나, `ratio_divide<Period2, period>::den`가 1과 같고 `treat_as_floating_point<Rep2>`*가 false를 포함*할 경우 세 번째 생성자는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.  
  
##  <a name="max"></a>  duration::max  
 템플릿 매개 변수 형식 `Ref`의 값에 대한 상한을 반환하는 정적 메서드입니다.  
  
```  
static constexpr duration max();
```  
  
### <a name="return-value"></a>반환 값  
 실제로 `duration(duration_values<rep>::max())`를 반환합니다.  
  
##  <a name="min"></a>  duration::min  
 템플릿 매개 변수 형식 `Ref`의 값에 대한 하한을 반환하는 정적 메서드입니다.  
  
```  
static constexpr duration min();
```  
  
### <a name="return-value"></a>반환 값  
 실제로 `duration(duration_values<rep>::min())`를 반환합니다.  
  
##  <a name="duration__operator-"></a>  duration::operator-  
 `duration` 개체의 복사본을 부정 틱 개수와 함께 반환합니다.  
  
```  
constexpr duration operator-() const;
```  
  
##  <a name="duration__operator--"></a>  duration::operator--  
 저장된 틱 개수를 줄입니다.  
  
```  
duration& operator--();

duration operator--(int);
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 메서드는 `*this`를 반환합니다.  
  
 두 번째 메서드는 감소 전에 만들어진 `*this`의 복사본을 반환합니다.  
  
##  <a name="op_eq"></a>  duration::operator=  
 저장된 틱 개수 모듈로를 지정된 값으로 줄입니다.  
  
```  
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>매개 변수  
 `Div`  
 첫 번째 메서드의 경우 `Div`는 틱 개수를 나타냅니다. 두 번째 메서드의 경우 `Div`는 틱 개수가 포함된 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 모듈로 연산이 수행된 후의 `duration` 개체입니다.  
  
##  <a name="op_star_eq"></a>  duration::operator*=  
 저장된 틱 개수에 지정된 값을 곱합니다.  
  
```  
duration& operator*=(const rep& Mult);
```  
  
### <a name="parameters"></a>매개 변수  
 `Mult`  
 `duration::rep`로 지정된 형식의 값입니다.  
  
### <a name="return-value"></a>반환 값  
 곱하기가 수행된 후의 `duration` 개체입니다.  
  
##  <a name="op_div_eq"></a>  duration::operator/=  
 저장된 틱 개수를 지정된 값으로 나눕니다.  
  
```  
duration& operator/=(const rep& Div);
```  
  
### <a name="parameters"></a>매개 변수  
 `Div`  
 `duration::rep`로 지정된 형식의 값입니다.  
  
### <a name="return-value"></a>반환 값  
 나누기가 수행된 후의 `duration` 개체입니다.  
  
##  <a name="op_add"></a>  duration::operator+  
 `*this`를 반환합니다.  
  
```  
constexpr duration operator+() const;
```  
  
##  <a name="op_add_add"></a>  duration::operator++  
 저장된 틱 개수를 늘립니다.  
  
```  
duration& operator++();

duration operator++(int);
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 메서드는 `*this`를 반환합니다.  
  
 두 번째 메서드는 증가 전에 만들어진 `*this`의 복사본을 반환합니다.  
  
##  <a name="op_add_eq"></a>  duration::operator+=  
 지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에 더합니다.  
  
```  
duration& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>매개 변수  
 `Dur`  
 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 더하기가 수행된 후의 `duration` 개체입니다.  
  
##  <a name="duration__operator-_eq"></a>  duration::operator-=  
 지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에서 뺍니다.  
  
```  
duration& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>매개 변수  
 `Dur`  
 `duration` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 빼기가 수행된 후의 `duration` 개체입니다.  
  
##  <a name="zero"></a>  duration::zero  
 `duration(duration_values<rep>::zero())`를 반환합니다.  
  
```  
static constexpr duration zero();
```  
  
##  <a name="op_mod_eq"></a>  duration::operator mod=  
 저장된 틱 수 모듈로 Div 또는 Div.count()를 줄입니다.  
  
```  
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>매개 변수  
 `Div`  
 기간 개체 또는 틱 수를 나타내는 값인 제수입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 저장된 틱 수 모듈로 Div를 줄이고 *this를 반환합니다. 두 번째 멤버 함수는 저장된 틱 수 모듈로 Div.count()를 줄이고 \*this를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [duration_values 구조체](../standard-library/duration-values-structure.md)
