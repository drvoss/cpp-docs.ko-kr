---
title: "common_type 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::common_type
dev_langs:
- C++
helpviewer_keywords:
- common_type class
- common_type
ms.assetid: 02bc4e7b-c63d-49de-9f8a-511d3a5c1e7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72a243969a9b80c086b78e0d90898274d84c3925
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="commontype-class"></a>common_type 클래스
여러 형식의 공용 형식을 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class... T>  
struct common_type;

template <class T>  
struct common_type<T> {
    typedef typename decay<T>::type type;
};

template <class T, class U>  
struct common_type<T, U> {
    typedef typename decay<decltype(true declval<T>() :
    declval<U>())>::type type;
};

template <class T, class U, class... V>  
struct common_type<T, U, V...> {
    typedef typename common_type<typename common_type<T, U>::type, V...>::type type;
};
```  
  
#### <a name="parameters"></a>매개 변수  
 [완전한 형식](../c-language/incomplete-types.md)이거나 void인 형식 목록입니다.  
  
## <a name="remarks"></a>설명  
 `type` 멤버는 매개 변수 목록의 모든 형식을 변환할 수 있는 공용 형식입니다.  
  
## <a name="example"></a>예  
 다음 프로그램에서는 몇 가지 적절한 사용 시나리오를 보여 주고 결과를 테스트합니다.  
  
```cpp  
// Compile using cl.exe /EHsc  
// common_type sample  
#include <iostream>  
#include <type_traits>  
  
struct Base {};  
struct Derived : Base {};  
  
int main()   
{  
    typedef std::common_type<unsigned char, short, int>::type NumericType;  
    typedef std::common_type<float, double>::type FloatType;  
    typedef std::common_type<const int, volatile int>::type ModifiedIntType;  
    typedef std::common_type<Base, Derived>::type ClassType;  
  
    std::cout << std::boolalpha;  
    std::cout << "Test for typedefs of common_type int" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<int, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<int, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<int, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<int, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type double" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<double, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<double, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<double, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<double, ClassType>::value << std::endl;  
    std::cout << "---------------------------" << std::endl;  
    std::cout << "Test for typedefs of common_type Base" << std::endl;  
    std::cout << "NumericType: "     << std::is_same<Base, NumericType>::value << std::endl;  
    std::cout << "FloatType: "       << std::is_same<Base, FloatType>::value << std::endl;  
    std::cout << "ModifiedIntType: " << std::is_same<Base, ModifiedIntType>::value << std::endl;  
    std::cout << "ClassType: "       << std::is_same<Base, ClassType>::value << std::endl;  
  
    return 0;  
}  
```  
  
## <a name="output"></a>출력  
  
```
Test for typedefs of common_type int
NumericType: true
FloatType: false
ModifiedIntType: true
ClassType: false
---------------------------
Test for typedefs of common_type double
NumericType: false
FloatType: true
ModifiedIntType: false
ClassType: false
---------------------------
Test for typedefs of common_type Base
NumericType: false
FloatType: false
ModifiedIntType: false
ClassType: true
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



