---
title: 컴파일러 오류 C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: c243925548f8c90bdff49421b0d38357b9e677a3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216286"
---
# <a name="compiler-error-c2212"></a>컴파일러 오류 C2212

' identifier ': 함수에 대 한 포인터에 __based 사용할 수 없습니다.

함수에 대 한 포인터는 선언할 수 없습니다 **`__based`** . 코드 기반 데이터가 필요한 경우 키워드나 pragma를 사용 합니다 **`__declspec`** `data_seg` .
