---
title: 컴파일러 오류 C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: c92a95b97cb4c57d3ad5cfbf8fe1d9980d5362cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221213"
---
# <a name="compiler-error-c2338"></a>컴파일러 오류 C2338

> *오류 메시지*

컴파일 중에 오류가 발생 하 여이 오류가 발생할 수 있습니다 **`static_assert`** . 메시지는 매개 변수를 통해 제공 됩니다 **`static_assert`** .

이 오류 메시지는 컴파일러에 대 한 외부 공급자에 의해 생성 될 수도 있습니다. 대부분의 경우 이러한 오류는 특성 공급자 DLL (예: ATLPROV)에 의해 보고 됩니다. 이 메시지의 일반적인 형태는 다음과 같습니다.

- '*attribute*' Atl 특성 공급자: 오류 atl*번호* *메시지*

- '*Attribute*' 특성 사용이 잘못 되었습니다.

- '*usage*': ' usage ' 특성의 형식이 잘못 되었습니다.

이러한 오류는 복구할 수 없는 경우가 많으며 심각한 컴파일러 오류가 발생할 수 있습니다.

이러한 문제를 해결 하려면 특성 사용을 수정 합니다. 예를 들어 특성 매개 변수를 사용 하려면 먼저 선언 해야 합니다. ATL 오류 번호가 제공 되는 경우 자세한 내용은 해당 오류에 대 한 설명서를 참조 하십시오.
