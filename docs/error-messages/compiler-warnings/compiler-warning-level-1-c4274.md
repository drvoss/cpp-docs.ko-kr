---
title: 컴파일러 경고(수준 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5d005fccc5920aea61698a65edf9284d56366a1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377071"
---
# <a name="compiler-warning-level-1-c4274"></a>컴파일러 경고(수준 1) C4274

\#무시된 ID입니다. #pragma 주석에 대한 설명서 보기(exestr, '문자열')

개체 `#ident` 또는 실행 파일에 사용자 지정 문자열을 삽입하는 지시문은 더 이상 사용되지 않습니다. 따라서 컴파일러는 지시문을 무시합니다.

> [!CAUTION]
> 경고 C4274는 [#pragma 주석(exestr, '문자열')](../../preprocessor/comment-c-cpp.md) 지시문을 사용하도록 권장합니다. 그러나 이 조언은 더 이상 사용되지 않으며 컴파일러의 향후 릴리스에서 수정될 예정입니다. 지시문을 `#pragma` 사용하는 경우 링커 도구(LINK.exe)는 지시문에 의해 생성된 주석 레코드를 무시하고 [LNK4229에](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)경고하는 문제를 발생시다. `#ident` 지시문 대신 응용 프로그램에서 파일 버전 리소스 문자열을 사용하는 것이 좋습니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `#ident "` *string* 문자열`"` 지시문을 제거합니다.

## <a name="see-also"></a>참고 항목

[C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[링커 도구 경고 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[리소스 파일 작업](../../windows/working-with-resource-files.md)
