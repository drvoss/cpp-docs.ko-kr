---
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 4e793f23581f7dc62a39fcd8c5c504fb5a2ccbc9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301472"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Microsoft 전용**

Microsoft C/C++는 크기가 지정된 정수 형식을 지원합니다. **__int**<em>n</em> 형식 지정자를 사용하여 8, 16, 32 또는 64비트 정수 변수를 선언할 수 있습니다. 여기서 n은 8, 16, 32 또는 64입니다.

다음 예제에서는 이러한 형식의 크기가 지정된 정수 각각에 대해 변수 하나를 선언합니다.

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

**__int8**, **__int16** 및 **__int32** 형식은 동일한 크기를 가진 ANSI 형식에 대한 동의어이고, 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다. **__Int8** 데이터 형식은 **char**형식과 동의어이 고, **__int16** 는 **short**형식과 동의어 이며, **__int32** 는 **int**형식과 동의어입니다. **__Int64** 형식은 **long long**형식의 동의어입니다.

이전 버전과의 호환성을 위해 **_int8**, **_int16**, **_int32**및 **_int64** 는 컴파일러 옵션 [/za __int8 언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 **고 __int16,** **__int32**, **__int64**및 **\(** 의 동의어입니다.

## <a name="example"></a>예

다음 예제에서는 __int *xx* 매개 변수가 **int**로 승격되는 것을 보여 줍니다.

```cpp
// sized_int_types.cpp

#include <stdio.h>

void func(int i) {
    printf_s("%s\n", __FUNCTION__);
}

int main()
{
    __int8 i8 = 100;
    func(i8);   // no void func(__int8 i8) function
                // __int8 will be promoted to int
}
```

```Output
func
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[기본 제공 형식](../cpp/fundamental-types-cpp.md)<br/>
[데이터 형식 범위](../cpp/data-type-ranges.md)<br/>
