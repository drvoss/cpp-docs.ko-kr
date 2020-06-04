---
title: system_error 클래스
ms.date: 11/04/2016
f1_keywords:
- system_error/std::system_error
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
ms.openlocfilehash: 7a18d2f9f229a62a539be072870e38a990677636
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076369"
---
# <a name="system_error-class"></a>system_error 클래스

하위 수준 시스템 오류를 보고하기 위해 throw되는 모든 예외에 대한 기본 클래스를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class system_error : public runtime_error {
    explicit system_error(error_code _Errcode, const string& _Message = "");
    system_error(error_code _Errcode, const char *_Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const string& _Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const char *_Message);

    const error_code& code() const throw();
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>주의

클래스 `what`exception[에서 ](../standard-library/exception-class.md)에 의해 반환되는 값은 `_Message` 및 [error_code](../standard-library/error-code-class.md) 형식의 저장된 개체(`code` 또는 `error_code(_Errval, _Errcat)`)에서 생성됩니다.

구성원 함수 `code`는 저장된 [error_code](../standard-library/error-code-class.md) 개체를 반환합니다.
