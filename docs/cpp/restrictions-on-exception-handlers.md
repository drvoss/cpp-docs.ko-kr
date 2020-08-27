---
title: 예외 처리기에 대한 제한
description: 구조적 예외 처리 블록으로 점프할 때의 제한 사항에 대해 설명 합니다.
ms.date: 08/24/2020
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: c4182f065789533bf7599621d8d2829b2d52d6ed
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898445"
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한

코드에서 예외 처리기를 사용 하는 주요 제한 사항은 문을 사용 하 여 **`goto`** 문 블록으로 점프할 수 없다는 것입니다 **`__try`** . 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 문 블록 밖으로 이동할 수 있으며 **`__try`** , 선택 하는 예외 처리기를 중첩할 수 있습니다.

## <a name="see-also"></a>참조

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
