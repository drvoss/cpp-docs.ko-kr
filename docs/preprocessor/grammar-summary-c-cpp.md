---
title: 전처리기 문법 요약(C/C++)
description: MSVC (Microsoft C/C++ 컴파일러) 전처리기 문법 구문을 정의 하 고 설명 합니다.
ms.date: 08/29/2019
helpviewer_keywords:
- grammar
- preprocessor, grammar
ms.assetid: 0acb6e9b-364c-4ef8-ace4-7be980521121
ms.openlocfilehash: 68e5f09acfc6444afb46bcbc0f7e9db10b04afed
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076869"
---
# <a name="preprocessor-grammar-summary-cc"></a>전처리기 문법 요약(C/C++)

이 문서에서는 C 및 C++ 전처리기의 공식 문법을 설명 합니다. 전처리 지시문 및 연산자의 구문에 대해 설명 합니다. 자세한 내용은 [전처리기](../preprocessor/preprocessor.md) 및 [Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조 하세요.

## <a name="definitions-for-the-grammar-summary"></a><a name="definitions"></a>문법 요약에 대 한 정의

터미널은 구문 정의에서 끝점입니다. 다른 방법은 없습니다. 터미널에는 예약어와 사용자 정의 식별자가 포함됩니다.

넌터미널은 구문에서 자리를 표시합니다. 대부분은 이 구문 요약의 다른 곳에서 정의되어 있습니다. 정의는 재귀적일 수 있습니다. 다음 비 터미널은  *C++ 언어 참조*의 [어휘 규칙](../cpp/lexical-conventions.md) 섹션에서 정의 됩니다.

*상수*, *상수 식*, *식별자*, *키워드*, *연산자*, *punctuator*

선택적 구성 요소는 첨자 <sub>opt</sub>로 나타냅니다. 예를 들어 다음 구문은 중괄호로 묶인 선택적 식을 나타냅니다.

**{** *expression*<sub>opt</sub> **}**

## <a name="document-conventions"></a><a name="conventions"></a>문서 규칙

규칙은 구문의 여러 구성 요소에 대해 여러 글꼴 특성을 사용합니다. 기호 및 글꼴은 다음과 같습니다.

| 특성 | 설명 |
|---------------|-----------------|
| *nonterminal* | 기울임꼴은 비터미널을 나타냅니다. |
| **#include** | 굵게 표시된 터미널은 다음과 같이 입력해야 할 리터럴 예약어 및 기호입니다. 이 컨텍스트의 문자는 항상 대/소문자를 구분합니다. |
| <sub>opt</sub> | 뒤에 <sub>opt</sub>가 오는 비터미널은 항상 선택 사항입니다.|
| default typeface | 이 서체에서 설명하거나 나열된 집합의 문자를 C 문의 터미널로 사용될 수 있습니다. |

비터미널 뒤에 오는 콜론( **:** )은 정의를 지정합니다. 다른 정의는 별도의 줄에 나열됩니다.

코드 구문 블록에서 기본 서체의 이러한 기호는 특별 한 의미가 있습니다.

| 기호 | 설명 |
|---|---|
| \[ ] | 대괄호는 선택적 요소를 둘러쌉니다. |
| {\|} | 세로 막대로 구분 된 중괄호 (...)입니다. |
| ... | 이전 요소 패턴을 반복할 수 있음을 나타냅니다. |

코드 구문 블록에서 쉼표 (`,`), 마침표 (`.`), 세미 콜론 (`;`), 콜론 (`:`), 괄호 (`( )`), 큰따옴표 (`"`) 및 작은따옴표 (`'`)는 리터럴입니다.

## <a name="preprocessor-grammar"></a><a name="grammar"></a>전처리기 문법

*제어 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *식별자* *토큰-문자열*<sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *식별자* **(** *identifier*<sub>opt</sub> **,** ... **,** *identifier*<sub>opt</sub> **)** *토큰 문자열*<sub>옵트인</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _경로 사양_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **\<** _경로-spec_ **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#line** *숫자 시퀀스* **"** _파일 이름_ **"** <sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *식별자*\
&nbsp;&nbsp;&nbsp;&nbsp; **#error** *토큰 문자열*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *토큰 문자열*

*상수-식*: \
&nbsp;&nbsp;&nbsp;&nbsp;**정의 된 (** *식별자* **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**정의** *식별자*\
다른 상수 식 &nbsp;&nbsp;&nbsp;&nbsp;

*조건*: \
&nbsp;&nbsp; *&nbsp;&nbsp;* *elif-parts*<sub>opt</sub> *else-part*<sub>opt</sub> *endif 줄*

*-part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*한 줄* *텍스트*

*if-line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *상수 식*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *식별자*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *식별자*

*elif-파트*: \
&nbsp;&nbsp;&nbsp;&nbsp;*elif 줄* *텍스트*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif* - *줄* *텍스트*

*elif 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *상수 식*

*else-파트*: \
&nbsp;&nbsp;&nbsp;&nbsp;*다른 줄* *텍스트*

*else 줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*endif-줄*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*숫자 시퀀스*: \
&nbsp;&nbsp;&nbsp;&nbsp;*자릿수*\
&nbsp;&nbsp;&nbsp;&nbsp;*숫자-시퀀스* *자릿수*

*digit*: \ 중 하나
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*토큰 문자열*: \
토큰의 &nbsp;문자열 &nbsp;&nbsp;&nbsp;

*토큰*: \
&nbsp;*키워드* 를 &nbsp;&nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;*식별자*\
&nbsp;*상수* 를 &nbsp;&nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;*연산자*\
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*파일 이름*: \
&nbsp;&nbsp;&nbsp;&nbsp;법적 운영 체제 파일 이름

*경로-사양*: \
&nbsp;&nbsp;&nbsp;&nbsp;Legal file path

*텍스트*: \
&nbsp;&nbsp;&nbsp;모든 텍스트 시퀀스 &nbsp;

> [!NOTE]
> 다음 비 터미널은  *C++ 언어 참조*의 [어휘 규칙](../cpp/lexical-conventions.md) 섹션에서 *상수*, *상수 식*, *식별자*, *키워드*, *연산자*및 *punctuator*로 확장 됩니다.

## <a name="see-also"></a>참고 항목

[C/C++ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)
