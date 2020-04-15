---
title: 수학 오류 M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: c6bd403437ee5e55eaf4add288995d0e4aa76c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361966"
---
# <a name="math-error-m6108"></a>수학 오류 M6108

제곱근

제곱근 연산의 피연산은 음수였습니다.

종료 코드 136으로 프로그램이 종료됩니다.

> [!NOTE]
> C `sqrt` 런타임 라이브러리와 FORTRAN 내장 함수 **SQRT의** 함수는 이 오류를 생성하지 않습니다. C `sqrt` 함수는 작업을 수행하기 전에 인수를 검사하고 피연산이 음수인 경우 오류 값을 반환합니다. FORTRAN **SQRT** 함수는 이 오류 대신 DOMAIN [오류 M6201을](../../error-messages/tool-errors/math-error-m6201.md) 생성합니다.
