---
title: 컴파일러 경고(수준 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 72ab87b34e07717112f5af1727a216b4f786ae0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186792"
---
# <a name="compiler-warning-level-1-c4420"></a>컴파일러 경고(수준 1) C4420

' operator ': 연산자를 사용할 수 없습니다. 대신 ' operator '를 사용 합니다. 런타임 검사가 손상 될 수 있습니다.

이 경고는 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vector new/delete 검사)를 사용 하 고 벡터 폼을 찾을 수 없는 경우에 생성 됩니다. 이 경우 벡터가 아닌 형식이 사용 됩니다.

/RTCv가 올바르게 작동 하려면 컴파일러는 vector 구문이 사용 [된 경우 항상](../../cpp/delete-operator-cpp.md) [새](../../cpp/new-operator-cpp.md)/의 vector 형식을 호출 해야 합니다.
