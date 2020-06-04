---
title: bad_array_new_length 클래스
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: c4f4f58f7b28960bbacf695a675fbe4f20a54192
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443710"
---
# <a name="bad_array_new_length-class"></a>bad_array_new_length 클래스

이 클래스는 배열 크기가 0 보다 작거나 제한 보다 크므로 할당 요청이 성공 하지 못했음을 나타내기 위해 throw 되는 예외를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>설명

`what`에서 반환 되는 값은 구현 시 정의 된 C 문자열입니다. 멤버 함수는 예외를 발생시키지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<새 >

## <a name="see-also"></a>참고 항목

[예외 클래스](../standard-library/exception-class.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
