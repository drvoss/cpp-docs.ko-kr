---
title: '유니코드: 와이드 문자 집합'
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: b27641b9843d4f6f1ef39d893df5d3f26af372e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220654"
---
# <a name="unicode-the-wide-character-set"></a>유니코드: 와이드 문자 집합

와이드 문자는 2바이트 다국어 문자 코드입니다. 전 세계의 현대식 컴퓨팅 환경에서 사용되는 모든 문자(전문 기호 및 특수 출판 문자 포함)는 유니코드 지정에 따라 와이드 문자로 표현될 수 있습니다. Microsoft를 포함하는 대규모 컨소시엄을 통해 개발 및 유지되고 있는 유니코드 표준은 이제 널리 인정된 표준입니다.

와이드 문자는 형식입니다 **`wchar_t`** . 와이드 문자열은 **wchar_t[]** 배열로 표현되고 `wchar_t*` 포인터로 가리킵니다. 문자 앞에 **L** 문자를 접두사로 붙이면 모든 ASCII 문자를 와이드 문자로 나타낼 수 있습니다. 예를 들어 L'\0'은 종료 와이드(16비트) null 문자입니다. 마찬가지로 모든 ASCII 문자열 리터럴은 ASCII 리터럴 앞에 문자 L을 접두사로 사용하여(L"Hello") 간단하게 와이드 문자열 리터럴로 나타낼 수 있습니다.

일반적으로 와이드 문자는 멀티바이트 문자보다 메모리 공간을 더 많이 차지하지만 처리 속도는 더 빠릅니다. 또한 멀티바이트 인코딩 시 1개 로캘만 표현할 수 있지만 전 세계 모든 문자 집합은 유니코드 표현으로 동시에 표현할 수 있습니다.

## <a name="see-also"></a>참고 항목

[국제화](../c-runtime-library/internationalization.md)<br/>
[범주별 유버니설 C 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)<br/>
