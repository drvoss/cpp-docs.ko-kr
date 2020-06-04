---
title: EDITBIN 참조
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: 266347de063b4e050cb032aa2d8d74e7934b8081
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328344"
---
# <a name="editbin-reference"></a>EDITBIN 참조

마이크로 소프트 COFF 바이너리 파일 편집기 (편집빈. EXE)는 COFF(일반 개체 파일 형식) 이진 파일을 수정합니다. EDITBIN을 사용하여 개체 파일, 실행 파일 및 동적 링크 라이브러리(DLL)를 수정할 수 있습니다.

> [!NOTE]
> Visual Studio 명령 프롬프트에서만 이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.

[/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 생성된 파일에서 EDITBIN을 사용할 수 없습니다. /GL로 생성된 이진 파일에 대한 수정은 다시 컴파일하고 연결하여 이루어져야 합니다.

- [편집빈 명령줄](editbin-command-line.md)

- [편집빈 옵션](editbin-options.md)

## <a name="see-also"></a>참고 항목

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)
