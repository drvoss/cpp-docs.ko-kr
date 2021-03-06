---
title: "add_rvalue_reference 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a42d8807763651f92ad87120fb50990821d03649
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference 클래스
개체 또는 함수 형식인 경우 템플릿 매개 변수의 rvalue 참조 형식을 만듭니다. 아닌 경우, 참조 축소에 대한 의미 체계 때문에 형식이 템플릿 매개 변수와 동일합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>매개 변수  
 T  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 `add_rvalue_reference` 클래스에 템플릿 매개 변수 `T`에 대한 rvalue 참조 형식의 별칭인 `type`이라는 이름의 멤버가 있습니다. 참조 축소의 의미 체계는 비 개체 및 비 함수 형식 `T`에 대해 `T&&`가 `T`임을 의미합니다. 예를 들어 `T`가 lvalue 참조 형식이면 `add_rvalue_reference<T>::type`은 lvalue 참조 형식이며 rvalue 참조가 아닙니다.  
  
 편의상 <type_traits>는 `add_rvalue_reference`의 `type` 멤버를 별칭으로 지정하는 도우미 템플릿 `add_rvalue_reference_t`를 정의합니다.  
  
## <a name="example"></a>예  
 static_assert를 사용하는 이 코드 예제에서는 `add_rvalue_reference` 및 `add_rvalue_reference_t`를 사용하여 rvalue 참조 형식을 만드는 방법과 lvalue 참조 형식에 대한 `add_rvalue_reference`의 결과가 rvalue 참조가 아닌 lvalue 참조 형식으로 축소되는 방법을 보여 줍니다.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: <type_traits> 네임스페이스: std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_lvalue_reference 클래스](../standard-library/add-lvalue-reference-class.md)   
 [is_rvalue_reference 클래스](../standard-library/is-rvalue-reference-class.md)
