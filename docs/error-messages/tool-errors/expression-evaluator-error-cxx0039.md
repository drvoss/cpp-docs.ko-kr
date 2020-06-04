---
title: 식 계산기 오류 CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 5706d002eb3d566d05b059cb04b6b1626fdb3d33
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185128"
---
# <a name="expression-evaluator-error-cxx0039"></a>식 계산기 오류 CXX0039

기호가 모호 합니다.

C 식 계산기는 식에 사용할 기호의 인스턴스를 확인할 수 없습니다. 기호가 상속 트리에서 두 번 이상 나타납니다.

식에 사용할 인스턴스를 명시적으로 지정 하려면 범위 확인 연산자 (`::`)를 사용 해야 합니다.

이 오류는 CAN0039와 동일 합니다.
