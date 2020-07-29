---
title: 예외 처리기에 대한 제한
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 1f80cb1574cbfef0783c7e55dcd198dfb822f566
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225906"
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한

코드에서 예외 처리기를 사용 하는 주요 제한 사항은 문을 사용 하 여 **`goto`** **__try** 문 블록으로 이동할 수 없다는 것입니다. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. **__Try** 문 블록 밖으로 이동 하 고 선택 하는 예외 처리기를 중첩할 수 있습니다.

## <a name="see-also"></a>참고 항목

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
