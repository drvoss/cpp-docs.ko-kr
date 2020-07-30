---
title: once_flag 구조체
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 55c3f90f72857a4e4cd3f9075ce5bae10e14d218
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202729"
---
# <a name="once_flag-structure"></a>once_flag 구조체

**`struct`** 실행 스레드가 여러 개 있는 경우에도 초기화 코드를 한 번만 호출 하도록 템플릿 함수 [call_once](../standard-library/mutex-functions.md#call_once) 에 사용 되는를 나타냅니다.

## <a name="syntax"></a>구문

struct once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>설명

에는 `once_flag` **`struct`** 기본 생성자만 있습니다.

`once_flag` 형식의 개체는 만들 수는 있지만 복사할 수는 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:**\<mutex>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
