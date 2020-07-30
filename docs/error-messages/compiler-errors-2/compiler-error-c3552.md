---
title: 컴파일러 오류 C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: d2d3a60fcd4a26238cd6cf330f47b48c5b3198ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230833"
---
# <a name="compiler-error-c3552"></a>컴파일러 오류 C3552

'typename': 컴파일하면 지정되는 반환 형식은 'auto'를 포함할 수 없습니다.

**`auto`** 키워드를 함수 반환 형식에 대 한 자리 표시자로 사용 하는 경우 런타임에 지정 된 반환 형식을 제공 해야 합니다. 그러나 다른 키워드를 사용 **`auto`** 하 여 런타임에 지정 된 반환 형식을 지정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3552 오류를 생성합니다.

`auto myFunction->auto; // C3552`
