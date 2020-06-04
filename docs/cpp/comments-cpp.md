---
title: 설명 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: 3326ad7d0b5118182a5d582061fd0c103986f232
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189756"
---
# <a name="comments-c"></a>설명 (C++)

주석이란 컴파일 시에는 무시되지만 프로그래머에게 해설을 제공하고 이해를 돕는 유용한 문장입니다. 주석은 향후 참조를 위해 일반적으로 코드에 설명을 덧붙이는 데 사용됩니다. 컴파일러에서는 주석을 공백으로 취급합니다. 테스트에 주석을 사용 하 여 특정 코드 줄을 비활성 상태로 만들 수 있습니다. 그러나 주석을 포함 하는 코드를 감쌀 수는 있지만 주석을 중첩할 수는 없으므로 전처리기 지시문을 `#if`/`#endif` 하는 것이 더 효율적입니다.

C++ 주석은 다음 방법 중 하나로 기록됩니다.

- `/*` (슬래시, 별표) 문자 뒤에 문자 (새 줄 포함)의 시퀀스와 `*/` 문자가 차례로 나옵니다. 이 구문은 ANSI C와 같습니다.

- `//` (두 개의 슬래시) 문자 뒤에 문자 시퀀스가 나옵니다. 백슬래시가 바로 앞에 오지 않는 새 줄은 이러한 형식의 주석을 종료합니다. 따라서 일반적으로 "한 줄 주석"이라고 합니다.

주석 문자 (`/*`, `*/`및 `//`)는 문자 상수, 문자열 리터럴 또는 주석 내에서 특별 한 의미가 없습니다. 따라서 첫 번째 구문을 사용하는 주석은 중첩할 수 없습니다.

## <a name="see-also"></a>참고 항목

[어휘 규칙](../cpp/lexical-conventions.md)
