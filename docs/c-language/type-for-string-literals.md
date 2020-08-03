---
title: 문자열 리터럴의 형식
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
ms.openlocfilehash: cd84a8c37e2929394e34010d14fc9264080539cc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198998"
---
# <a name="type-for-string-literals"></a>문자열 리터럴의 형식

문자열 리터럴은 **`char`** 배열(즉, **char[ ]** ) 형식입니다. 와이드 문자 문자열은 **`wchar_t`** 배열(즉, **wchar_t[ ]** ) 형식입니다. 즉, 문자열은 **`char`** 형식의 요소가 포함된 배열입니다. 배열에 있는 요소의 수는 문자열의 문자 개수에 null 종결 문자에 해당하는 1을 더한 값입니다.

## <a name="see-also"></a>참조

[C 문자열 리터럴](../c-language/c-string-literals.md)
