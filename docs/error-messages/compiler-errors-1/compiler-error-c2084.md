---
title: 컴파일러 오류 C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: f217e0b94e27c0f85879e80b3ae887cb4f76f486
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216364"
---
# <a name="compiler-error-c2084"></a>컴파일러 오류 C2084

'*function*' 함수에 이미 본문이 있습니다.

함수가 이미 정의 되어 있습니다.

Visual Studio 2002 이전

- 컴파일러는 추가 정의를 사용할 수 없더라도 동일한 실제 형식으로 확인 되는 여러 템플릿 특수화를 허용 합니다. 이제 컴파일러에서 이러한 여러 정의를 검색 합니다.

- **`__int32`** 및 **`int`** 는 개별 형식으로 처리 되었습니다. 이제 컴파일러에서 **`__int32`** 를 동의어로 처리 합니다 **`int`** . 즉, 함수가 및에서 오버 로드 되 고 오류를 발생 시키는 경우 컴파일러는 여러 정의를 검색 합니다 **`__int32`** **`int`** .

## <a name="example"></a>예제

다음 샘플에서는 C2084를 생성 합니다.

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

이 오류를 해결 하려면 중복 된 정의를 제거 합니다.

```cpp
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```
