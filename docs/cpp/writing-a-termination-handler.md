---
title: 종료 처리기 작성
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
ms.openlocfilehash: 8a243281e0d984a42cd4b4d9f249d867812d8bca
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187312"
---
# <a name="writing-a-termination-handler"></a>종료 처리기 작성

예외 처리기와 달리 종료 처리기는 보호된 코드 블록이 정상적으로 종료되었는지 여부와 관계없이 항상 실행됩니다. 종료 처리기의 유일한 목적은 코드 섹션의 실행 완료 방법과 관계없이 메모리, 핸들 및 파일과 같은 리소스가 제대로 닫혔는지 확인하는 것이어야 합니다.

종료 처리기는 try-finally 문을 사용합니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [Try finally 문](../cpp/try-finally-statement.md)

- [리소스 정리](../cpp/cleaning-up-resources.md)

- [예외 처리의 작업 타이밍](../cpp/timing-of-exception-handling-a-summary.md)

- [종료 처리기에 대 한 제한 사항](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>참고 항목

[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
