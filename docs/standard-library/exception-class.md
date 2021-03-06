---
title: "exception 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24aa11044218257b3471e2d65fe652ca32d39196
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="exception-class"></a>exception 클래스
이 클래스는 특정 식과 C++ 표준 라이브러리로 throw된 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## <a name="syntax"></a>구문  
```  
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };  
``` 
## <a name="remarks"></a>설명  
 특히 이 기본 클래스는 [\<stdexcept>](../standard-library/stdexcept.md)에 정의된 표준 예외 클래스의 루트입니다. `what`에서 반환된 C 문자열 값은 기본 생성자에 의해서는 지정되지 않지만 특정 파생 클래스의 생성자에 의해 구현이 정의된 C 문자열로 정의될 수 있습니다. 멤버 함수는 예외를 발생시키지 않습니다.  
  
 `int` 매개 변수를 사용하여 메모리가 할당되지 않도록 지정할 수 있습니다. `int` 값이 무시됩니다.  
  
> [!NOTE]
>  생성자 `exception(const char* const &message)` 및 `exception(const char* const &message, int)`는 C++ 표준 라이브러리에 대한 Microsoft 확장입니다.  
  
## <a name="example"></a>예  
 `exception` 클래스에서 상속된 표준 예외 클래스 사용의 예는 [\<stdexcept>](../standard-library/stdexcept.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<exception>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



