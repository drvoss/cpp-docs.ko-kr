---
title: 컴파일러 오류 C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 7426df1970dee58cd4363ee345e2286165e375b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202179"
---
# <a name="compiler-error-c2722"></a>컴파일러 오류 C2722

':: operator ': 다음 연산자 명령이 잘못 되었습니다. ' operator operator ' 사용

`operator` 문에서 `::new` 또는 `::delete`를 다시 정의 합니다. `new` 및 `delete` 연산자는 전역 이므로 범위 확인 연산자 (`::`)는 의미가 없습니다. `::` 연산자를 제거합니다.
