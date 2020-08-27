---
title: '예외 처리 타이밍: 요약'
description: Microsoft c + +에서 예외 처리의 실행 시간 및 순서입니다.
ms.date: 08/24/2020
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 2ce501d8d74b6f0f7ca92e193c39f8ce58a66053
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898357"
---
# <a name="timing-of-exception-handling-a-summary"></a>예외 처리 타이밍: 요약

종료 처리기는 **`__try`** 문 블록이 종료 되는 방법에 관계 없이 실행 됩니다. 블록 밖으로 점프 하는 경우 **`__try`** , `longjmp` 블록 외부로 제어를 전송 하 고 예외 처리로 인해 스택을 해제 하는 문이 포함 됩니다.

> [!NOTE]
> Microsoft c + + 컴파일러는 두 가지 형태의 `setjmp` 및 `longjmp` 문을 지원 합니다. 빠른 버전은 종료 처리를 건너뛰지만 더 효율적입니다. 이 버전을 사용 하려면 파일을 포함 \<setjmp.h> 합니다. 다른 버전은 이전 단락에 설명된 대로 종료 처리를 지원합니다. 이 버전을 사용 하려면 파일을 포함 \<setjmpex.h> 합니다. 빠른 버전의 성능 향상 정도는 하드웨어 구성에 따라 달라집니다.

운영 체제는 다른 코드를 실행하기 전에 예외 처리기의 본문을 포함한 모든 종료 처리기를 적절한 순서대로 실행합니다.

예외로 인해 중단된 경우 시스템은 먼저 예외 처리기 하나 이상의 필터 부분을 실행한 다음 무엇을 종료할지 결정해야 합니다. 이벤트의 순서는 다음과 같습니다.

1. 예외가 발생합니다.

1. 시스템은 활성 예외 처리기의 계층 구조를 확인 하 고 우선 순위가 가장 높은 처리기의 필터를 실행 합니다. 가장 최근에 설치 되 고 가장 많이 중첩 된 예외 처리기는 블록 및 함수 호출로 이동 합니다.

1. 이 필터가 제어를 전달 하는 경우 (0 반환) 제어를 전달 하지 않는 필터가 발견 될 때까지 프로세스가 계속 됩니다.

1. 이 필터가-1을 반환 하는 경우 예외가 발생 한 위치에서 실행이 계속 되 고 종료가 수행 되지 않습니다.

1. 필터가 1을 반환하는 경우 다음 이벤트가 발생합니다.

   - 시스템이 스택을 해제 합니다. 그러면 예외가 발생 한 위치와 예외 처리기가 포함 된 스택 프레임 사이의 모든 스택 프레임이 지워집니다.

   - 스택이 해제되면서 스택의 각 종료 처리기가 실행됩니다.

   - 예외 처리기 자체가 실행됩니다.

   - 코드 줄에서 이 예외 처리기 끝 다음으로 제어가 전달됩니다.

## <a name="see-also"></a>참조

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
