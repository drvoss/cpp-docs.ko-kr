---
title: 선언 요약
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: 894ed5e39ac8019048b6730d5e3b34de22f3a0c7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220849"
---
# <a name="summary-of-declarations"></a>선언 요약

*`declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`attribute-seq`* <sub>opt</sub> *`init-declarator-list`* <sub>opt</sub> **`;`**

*`declaration-specifiers`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`storage-class-specifier`* *`declaration-specifiers`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`declaration-specifiers`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`* *`declaration-specifiers`* <sub>opt</sub>

*`attribute-seq`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`attribute`* *`attribute-seq`* <sub>opt</sub>

*`attribute`* : 다음 중 하나&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[`__asm`](../assembler/inline/asm.md) [`__clrcall`](../cpp/clrcall.md) [`__stdcall`](../cpp/stdcall.md) [`__based`](../cpp/based-grammar.md) [`__fastcall`](../cpp/fastcall.md) [`__thiscall`](../cpp/thiscall.md) [`__cdecl`](../cpp/cdecl.md) [`__inline`](../cpp/inline-functions-cpp.md) [`__vectorcall`](../cpp/vectorcall.md)

*`init-declarator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`init-declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`init-declarator-list`*  **`,`**  *`init-declarator`*

*`init-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*  **`=`**  *`initializer`*  /\* 스칼라 초기화의 경우 \*/

*`storage-class-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`auto`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`register`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`static`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`extern`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`typedef`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__declspec (`** *`extended-decl-modifier-seq`* **`)`**  /\* Microsoft 전용 \*/

*`type-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`void`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`char`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`short`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`int`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int8`**  /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int16`**  /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int32`**  /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int64`**  /\* Microsoft 전용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`long`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`float`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`double`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`signed`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`unsigned`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union-specifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enum-specifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`typedef-name`*

*`type-qualifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`const`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`volatile`**

*`declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`* <sub>opt</sub> *`direct-declarator`*

*`direct-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`(`** *`declarator`* **`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`[`** *`constant-expression`* <sub>opt</sub> **`]`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`(`** *`parameter-type-list`* **`)`**  /\* 새 스타일 선언자 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-declarator`* **`(`** *`identifier-list`* <sub>opt</sub> **`)`**  /\* 사용되지 않는 스타일 선언자 \*/

*`pointer`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>`*`</strong> *`type-qualifier-list`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>`*`</strong> *`type-qualifier-list`* <sub>opt</sub> *`pointer`*

*`parameter-type-list`* :&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* 매개 변수 목록 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`* **`, ...`**

*`parameter-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-declaration`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`parameter-list`* **`,`** *`parameter-declaration`*

*`type-qualifier-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier-list`* *`type-qualifier`*

*`enum-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`enum`** *`identifier`* <sub>opt</sub> **`{`** *`enumerator-list`* **`}`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`enum`** *`identifier`*

*`enumerator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumerator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumerator-list`* **`,`** *`enumerator`*

*`enumerator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumeration-constant`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`enumeration-constant`* **`=`** *`constant-expression`*

*`enumeration-constant`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*

*`struct-or-union-specifier`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union`* *`identifier`* <sub>opt</sub> **`{`** *`struct-declaration-list`* **`}`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-or-union`* *`identifier`*

*`struct-or-union`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`struct`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`union`**

*`struct-declaration-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declaration`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declaration-list`* *`struct-declaration`*

*`struct-declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`specifier-qualifier-list`* *`struct-declarator-list`* **`;`**

*`specifier-qualifier-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`specifier-qualifier-list`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-qualifier`* *`specifier-qualifier-list`* <sub>opt</sub>

*`struct-declarator-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`struct-declarator`* *`struct-declarator-list`* **`,`** *`struct-declarator`*

*`struct-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`type-specifier`* *`declarator`* <sub>opt</sub> **`:`** *`constant-expression`*

*`parameter-declaration`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`declarator`*  /\* 명명된 선언자 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`declaration-specifiers`* *`abstract-declarator`* <sub>opt</sub> /\* 익명 선언자 \*/

*`identifier-list`* : /\* 이전 스타일 선언자의 경우 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier-list`* **`,`** *`identifier`*

*`abstract-declarator`* : /\* 익명 선언자와 함께 사용 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`pointer`* <sub>opt</sub> *`direct-abstract-declarator`*

*`direct-abstract-declarator`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`(`** *`abstract-declarator`* **`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-abstract-declarator`* <sub>opt</sub> **`[`** *`constant-expression`* <sub>opt</sub> **`]`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`direct-abstract-declarator`* <sub>opt</sub> **`(`** *`parameter-type-list`* <sub>opt</sub> **`)`**

*`initializer`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`assignment-expression`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`{`** *`initializer-list`* **`}`**  /\* 집계 초기화의 경우 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`{`** *`initializer-list`* **`, }`**

*`initializer-list`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`initializer`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`initializer-list`* **`,`** *`initializer`*

*`type-name`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`specifier-qualifier-list`* *`abstract-declarator`* <sub>opt</sub>

*`typedef-name`* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`identifier`*

*`extended-decl-modifier-seq`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`extended-decl-modifier`* <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; *`extended-decl-modifier-seq`* *`extended-decl-modifier`*

*`extended-decl-modifier`* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 전용\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`thread`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`naked`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`dllimport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`dllexport`**

## <a name="see-also"></a>참조

[호출 규칙](../cpp/calling-conventions.md)<br/>
[구 구조 문법](../c-language/phrase-structure-grammar.md)<br/>
[사용되지 않는 호출 규칙](../cpp/obsolete-calling-conventions.md)
