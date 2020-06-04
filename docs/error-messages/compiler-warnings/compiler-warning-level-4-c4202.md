---
title: 컴파일러 경고(수준 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: 8a449ee7650196d34d30df646ebdc333c1333af2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161428"
---
# <a name="compiler-warning-level-4-c4202"></a>컴파일러 경고(수준 4) C4202

비표준 확장이 사용 됨: ' ... ': 이름 목록의 프로토타입 매개 변수가 잘못 되었습니다.

이전 스타일의 함수 정의에는 가변 인수가 들어 있습니다. 이러한 정의는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 오류를 생성 합니다.

## <a name="example"></a>예제

```c
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```
