---
title: 컴파일러 오류 C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 9747b1edadc76ceeb502b2c6fd03496b91769f5a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208067"
---
# <a name="compiler-error-c2026"></a>컴파일러 오류 C2026

문자열이 너무 커서 후행 문자가 잘렸습니다.

문자열이 16380 바이트의 한도 보다 깁니다.

인접 문자열이 연결 되기 전에는 문자열을 16380 싱글바이트 문자 보다 길 수 없습니다.

이 길이에 대 한 유니코드 문자열은이 오류도 생성 합니다.

다음과 같이 정의 된 문자열이 있는 경우 C2026을 생성 합니다.

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

다음과 같이 나눌 수 있습니다.

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

사용자 지정 리소스나 외부 파일에 매우 긴 문자열 리터럴 (32K 이상)을 저장 하는 것이 좋습니다. 자세한 내용은 [새 사용자 지정 또는 데이터 리소스 만들기](../../windows/creating-a-new-custom-or-data-resource.md) 를 참조 하세요.
