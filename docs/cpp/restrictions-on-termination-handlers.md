---
title: 종료 처리기에 대한 제한
description: 구조화 된 예외 처리 종료 처리기에 대 한 제한 사항입니다.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 60fdb4c2a105f2fce4a32f475563a04f8e7bfaf9
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898272"
---
# <a name="restrictions-on-termination-handlers"></a>종료 처리기에 대한 제한

문을 사용 하 여 문 **`goto`** **`__try`** 블록 또는 문 블록으로 점프할 수 없습니다 **`__finally`** . 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 그러나 문 블록 밖으로 이동할 수도 있습니다 **`__try`** . 또한 블록 안에 예외 처리기 나 종료 처리기를 중첩할 수 없습니다 **`__finally`** .

종료 처리기에서 허용 되는 일부 종류의 코드는 불확실 한 결과를 생성 하므로 주의 해 서 사용 해야 합니다. 하나는 **`goto`** 문 블록 밖으로 이동 하는 문입니다 **`__finally`** . 블록이 정상적인 종료의 일부로 실행 되는 경우 비정상 상황이 발생 하지 않습니다. 그러나 시스템이 스택을 해제 하는 경우 해제가 중지 됩니다. 그런 다음 현재 함수는 비정상적인 종료가 없는 것 처럼 제어를 얻습니다.

**`return`** 문 블록 내의 문은 **`__finally`** 거의 동일한 상황을 나타냅니다. 종료 처리기를 포함 하는 함수의 직접 실행 호출자에 게 제어가 반환 됩니다. 시스템이 스택을 해제 한 경우에는이 프로세스가 중단 됩니다. 그런 다음 예외가 발생 하지 않은 것 처럼 프로그램이 진행 됩니다.

## <a name="see-also"></a>참조

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
