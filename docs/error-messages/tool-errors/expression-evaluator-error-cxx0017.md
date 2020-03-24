---
title: 식 계산기 오류 CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 64ebce0161d67c298d55095f6bc409820120c34a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196016"
---
# <a name="expression-evaluator-error-cxx0017"></a>식 계산기 오류 CXX0017

기호를 찾을 수 없습니다.

식에 지정 된 기호를 찾을 수 없습니다.

이 오류의 한 가지 가능한 원인은 기호 이름에서 대/소문자가 일치 하지 않는 경우입니다. C와 C++ 는 대/소문자를 구분 하기 때문에 소스에 정의 된 정확한 경우에 기호 이름을 제공 해야 합니다.

이 오류는 디버깅 하는 동안 변수를 조사 하기 위해 변수를 형식 캐스팅 할 때 발생할 수 있습니다. `typedef`는 형식의 새 이름을 선언 하지만 새 형식을 정의 하지는 않습니다. 디버거에서 시도한 형식 캐스팅에는 정의 된 형식의 이름이 필요 합니다.

이 오류는 CAN0017와 동일 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 기호가 사용 되 고 있는 프로그램의 지점에서 기호가 이미 선언 되었는지 확인 합니다.

1. 실제 형식 이름을 사용 하 여 `typedef`정의 된 이름이 아니라 디버거의 변수를 캐스팅 합니다.
