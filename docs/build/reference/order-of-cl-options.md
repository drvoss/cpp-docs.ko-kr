---
title: CL 옵션 순서 (C++)-Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 6c57a68dd15d82a9d6a01bfe145374bda6eb1510
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439205"
---
# <a name="order-of-cl-options"></a>CL 옵션 순서

옵션은 마지막에 발생 해야 하는/link 옵션을 제외 하 고 CL 명령줄의 어디에 나 나타날 수 있습니다. 컴파일러는 [CL 환경 변수에](cl-environment-variables.md) 지정 된 옵션으로 시작한 다음, 명령 파일을 순서 대로 처리 하 여 왼쪽에서 오른쪽으로 명령 파일을 읽습니다. 각 옵션은 명령줄의 모든 파일에 적용 됩니다. CL은 충돌 하는 옵션을 발견할 경우 가장 오른쪽에 있는 옵션을 사용 합니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
