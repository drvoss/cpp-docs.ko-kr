---
title: sequenced_policy 클래스
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: 5647f20b560828016231a9bbd38977c51211e6bb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444920"
---
# <a name="sequenced_policy-class"></a>sequenced_policy 클래스

병렬 알고리즘 오버 로드를 명확 하 게 구분 하기 위해 고유한 형식으로 사용 되며 병렬 알고리즘의 실행이 병렬화 될 수 있어야 합니다.

## <a name="syntax"></a>구문

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>설명

`execution::sequenced_policy` 정책을 사용 하 여 병렬 알고리즘을 실행 하는 동안 요소 액세스 함수 호출이 catch 되지 않은 예외를 통해 종료 되는 경우 `terminate()`를 호출 해야 합니다.
