---
title: '#line 지시문(C/C++)'
description: '전처리기 매크로에서 보고 하는 줄 번호와 파일 이름을 설정 하는 데 사용 되는 #line 지시문에 대해 설명 합니다.'
ms.date: 07/06/2020
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 7b671cfdf5d5ce43024ac3e038c214396ac8679c
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058622"
---
# <a name="line-directive-cc"></a>#line 지시문 (C/c + +)

**#Line** 지시문은 전처리기에 줄 번호 및 파일 이름에 대 한 컴파일러의 보고 된 값을 지정 된 줄 번호 및 파일 이름으로 설정 하도록 지시 합니다.

## <a name="syntax"></a>구문

> **`#line`***숫자 시퀀스* ["*filename*"]

## <a name="remarks"></a>설명

컴파일러는 줄 번호와 선택적 파일 이름을 사용 하 여 컴파일하는 동안 발견 된 오류를 참조 합니다. 줄 번호는 일반적으로 현재 입력 줄을 참조 하 고, 파일 이름은 현재 입력 파일을 참조 합니다. 줄 번호는 각 줄이 처리 된 후에 증가 합니다.

*숫자 시퀀스* 값은 임의의 정수 상수일 수 있습니다. 전처리 토큰에서 매크로 대체를 사용할 수 있지만 결과는 올바른 구문으로 계산 되어야 합니다. *파일 이름은* 모든 문자를 조합 하 여 사용할 수 있으며 큰따옴표 ()로 묶어야 합니다 `" "` . *Filename* 을 생략 하면 이전 파일 이름이 변경 되지 않은 상태로 유지 됩니다.

지시문을 작성 하 여 소스 줄 번호와 파일 이름을 변경할 수 있습니다 **`#line`** . **`#line`** 지시문은 소스 파일에서 지시문 바로 다음에 오는 줄의 값을 설정 합니다. 변환기는 줄 번호와 파일 이름을 사용 하 여 미리 정의 된 매크로 및의 값을 확인 합니다 `__FILE__` `__LINE__` . 이러한 매크로를 사용 하 여 자체 설명 오류 메시지를 프로그램 텍스트에 삽입할 수 있습니다. 이러한 미리 정의 된 매크로에 대 한 자세한 내용은 [미리 정의 된 매크로](../preprocessor/predefined-macros.md)를 참조 하세요.

매크로는 해당 `__FILE__` 내용이 파일 이름인 문자열로 확장 되며 큰따옴표 ()로 둘러싸여 `" "` 있습니다.

줄 번호와 파일 이름을 변경 하는 경우 컴파일러는 이전 값을 무시 하 고 새 값을 사용 하 여 처리를 계속 합니다. **#Line** 지시문은 일반적으로 프로그램 생성기에서 사용 됩니다. 이는 생성 된 프로그램이 아니라 원래 원본 파일을 참조 하는 오류 메시지를 발생 시키는 데 사용 됩니다.

## <a name="example"></a>예제

다음 예에서는 및 매크로를 보여 줍니다 **`#line`** `__LINE__` `__FILE__` .

첫 번째 예제에서 줄 번호는 10으로 설정 되 고, 20으로 설정 되 고, 파일 이름은 *hello.exe*로 변경 됩니다.

```cpp
// line_directive.cpp
// Compile by using: cl /W4 /EHsc line_directive.cpp
#include <stdio.h>

int main()
{
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 10
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 20 "hello.cpp"
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
}
```

```Output
This code is on line 7, in file line_directive.cpp
This code is on line 10, in file line_directive.cpp
This code is on line 20, in file hello.cpp
This code is on line 21, in file hello.cpp
```

이 예제에서 매크로는 `ASSERT` 미리 정의 된 매크로를 사용 하 `__LINE__` 고 `__FILE__` 지정 된 어설션이 참이 아닌 경우 소스 파일에 대 한 오류 메시지를 인쇄 합니다.

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>참고 항목

[전처리기 지시문](../preprocessor/preprocessor-directives.md)
