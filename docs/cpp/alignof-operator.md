---
title: __alignof 연산자
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 6bddce29dd97d965303a58cc72aa97dfe8cbd8d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181540"
---
# <a name="__alignof-operator"></a>__alignof 연산자

C + + 11에는 지정 된 형식의 맞춤 (바이트)을 반환 하는 **alignof** 연산자가 도입 되었습니다. 최대 이식성을 제공하려면 Microsoft 전용 __alignof 연산자가 아닌 alignof 연산자를 사용해야 합니다.

**Microsoft 전용**

형식의 맞춤 요구 사항인 `size_t` 형식의 값을 반환 합니다.

## <a name="syntax"></a>구문

```cpp
  __alignof( type )
```

## <a name="remarks"></a>주의

예를 들면 다음과 같습니다.

|식|값|
|----------------|-----------|
|**__alignof (char)**|1|
|**__alignof (short)**|2|
|**__alignof (int)**|4|
|**__alignof (\__int64)**|8|
|**__alignof (부동 소수점)**|4|
|**__alignof (double)**|8|
|**__alignof (char\*)**|4|

**__Alignof** 값은 기본 형식의 `sizeof` 값과 동일 합니다. 그러나 다음과 같은 예제를 고려해야 합니다.

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

이 경우 **__alignof** 값은 구조체에서 가장 큰 요소의 맞춤 요구 사항입니다.

마찬가지로

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)`가 `32`와 같은 경우

**__Alignof** 사용 하는 한 가지 용도는 사용자 고유의 메모리 할당 루틴 중 하나에 대 한 매개 변수입니다. 예를 들어, 다음의 정의된 구조인 `S`가 지정된 경우 `aligned_malloc`이라는 메모리 할당 루틴을 호출하여 특정한 할당 경계에서 메모리를 할당할 수 있습니다.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

이전 버전과의 호환성을 위해 **_alignof** 는 컴파일러 옵션 [/za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__alignof** 의 동의어입니다.

맞춤 수정에 대한 자세한 내용은 다음을 참조하세요.

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)

- [구조 맞춤 예](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 특정)

X86 및 x64 관련 코드에서 맞춤의 차이점에 대한 자세한 내용은 다음을 참조하세요.

- [x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[키워드](../cpp/keywords-cpp.md)
