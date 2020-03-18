---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 63fcddec8ff8afd81084bb5a2786f394db594b07
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438893"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>설명

이 옵션은 스택의 크기 (바이트)를 설정 하 고 10 진수 또는 C 언어 표기법으로 인수를 사용 합니다. /STACK 옵션은 실행 파일에만 적용 됩니다.

*Reserve* 인수는 가상 메모리의 총 스택 할당을 지정 합니다. EDITBIN은 지정 된 값을 가장 가까운 4 바이트로 반올림 합니다.

선택적 `commit` 인수는 운영 체제에서 해석할 수 있습니다. Windows NT, Windows 95 및 Windows 98에서 `commit`은 한 번에 할당할 실제 메모리의 양을 지정 합니다. 커밋된 가상 메모리를 설정 하면 페이징 파일에 공간이 예약 됩니다. `commit` 값이 높으면 응용 프로그램에 더 많은 스택 공간이 필요할 때 시간을 절약할 수 있지만 메모리 요구 사항과 시작 시간이 늘어날 수 있습니다.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](editbin-options.md)
