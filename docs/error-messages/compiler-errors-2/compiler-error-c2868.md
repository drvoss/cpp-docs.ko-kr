---
title: 컴파일러 오류 C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 0cbcf7dc80aedc554594f88992059f98b7091c21
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201640"
---
# <a name="compiler-error-c2868"></a>컴파일러 오류 C2868

> '*identifier*': using 선언 구문이 잘못 되었습니다. 정규화 된 이름이 필요 합니다.

[Using 선언](../../cpp/using-declaration.md) 에는 *정규화 된 이름이*필요 합니다. 범위 연산자 (`::`)는 식별자 이름으로 끝나는 네임 스페이스, 클래스 또는 열거형 이름의 시퀀스를 구분 합니다. 단일 범위 확인 연산자를 사용 하 여 전역 네임 스페이스의 이름을 도입할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2868를 생성 하 고 올바른 사용법도 보여 줍니다.

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```
