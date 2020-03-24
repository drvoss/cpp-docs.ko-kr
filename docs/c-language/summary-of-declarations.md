---
title: 선언 요약
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: e553f4bdfffcd4bba6a39b2d37af6ba25a3d65d9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170438"
---
# <a name="summary-of-declarations"></a>선언 요약

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*선언-지정자* *특성-seq*<sub>opt</sub> *init-선언 자 목록*<sub>opt</sub> **;**

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*저장소 클래스 지정자* *선언-지정자*<sub>옵트인</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*형식 지정자* *선언-지정자*<sub>옵트인</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*형식-한정자* *선언-지정자*<sub>옵트인</sub>

*특성-seq* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*특성* *특성-seq*<sub>opt</sub>

*특성* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall](../cpp/clrcall.md) [__stdcall](../cpp/stdcall.md) [__based](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__thiscall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline __vectorcall](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-선언 목록* **,** *init-선언 자*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*선언 자* **=** *이니셜라이저* /\* 스칼라 초기화 \*    /

*storage-class-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**auto**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**register**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *확장 decl* - **)**  /Microsoft 전용 \* \*/

*type-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**short**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int8** /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int16** /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int32** /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int64** /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**long**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**signed**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**unsigned**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-name*

*type-qualifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**const**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**volatile**

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*포인터*<sub>opt</sub> *direct-선언 자*

*direct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *선언 자* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*직접 선언 자* **[** *상수 식*<sub>옵트인</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*직접 선언* 자 **(** *매개 변수 형식 목록* **)**  /새 스타일 선언 자 \* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*직접 선언 자* **(** *식별자 목록*<sub>옵트인</sub> **)**  /사용 되지 않는 스타일 선언 자 \* \*/

*pointer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *형식-한정자-목록*<sub>옵트인</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *형식-한정자-목록*<sub>옵트인</sub> *포인터*

*parameter-type-list*:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* 매개 변수 목록 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*매개 변수 목록* **,** ...

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;매개 변수 *목록* **,** *매개 변수 선언*

*type-qualifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;형식-한정자 *-목록* *형식-한정자*

*enum-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *identifier*<sub>opt</sub> **{** *enumerator-list* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**열거형** *식별자*

*enumerator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumerator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;열거자 *목록* **,** *열거자*

*enumerator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*열거형 상수* **=** *상수 식*

*enumeration-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*struct-or-union-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*구조체 또는 공용 구조체* *식별자*<sub>옵트인</sub> **{** *struct-선언 목록* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*구조체 또는 공용 구조체* *식별자*

*struct-or-union*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**struct**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**union**

*struct-declaration-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;구조체 선언- *선언* *목록*

*struct-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*지정자-목록* *구조체-선언 자 목록* **;**

*specifier-qualifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*형식 지정자* *지정자-한정자-목록*<sub>옵트인</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*형식-한정자* *지정자-한정자-목록*<sub>옵트인</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp; *&nbsp;&nbsp;구조체-선언 자* *구조체* -선언 자 목록 **,** *구조체-선언* 자

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*형식 지정자* *선언*<sub>옵트인</sub> **:** *상수 식*

*parameter-declaration*:<br/>
선언 자가 /\* \*/ *선언* *자가* 를 &nbsp;&nbsp;&nbsp;&nbsp;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*선언-지정자* *추상-선언 자*<sub>옵트인</sub> /\* 익명 선언 자 \*/

*identifier-list*: /\* 이전 스타일 선언자의 경우 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*식별자 목록* **,** *식별자*

*abstract-declarator*: /\* 익명 선언자에서 사용됨 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*포인터*<sub>opt</sub> *직접-추상-선언 자*

*direct-abstract-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *추상 선언 자* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*직접 추상 선언 자*<sub>옵트인</sub> **[** *상수 식*<sub>옵트인</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*직접 추상 선언 자*<sub>옵트인</sub> **(** *매개 변수 형식-목록*<sub>opt</sub> **)**

*initializer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
집계 초기화 /에 대 한 &nbsp;&nbsp;&nbsp;&nbsp; **{** *이니셜라이저 목록* **}** \* \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *이니셜라이저 목록* **}**

*initializer-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*initializer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*이니셜라이저 목록* **,** *이니셜라이저*

*type-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*지정자-한정자 목록* *추상-선언 자*<sub>옵트인</sub>

*typedef-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*확장-decl-modifier-seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 관련 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;확장- *decl-시퀀스* *확장-decl-한정자*

*확장-decl-한정자*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 관련 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)<br/>
[구 구조 문법](../c-language/phrase-structure-grammar.md)<br/>
[사용되지 않는 호출 규칙](../cpp/obsolete-calling-conventions.md)
