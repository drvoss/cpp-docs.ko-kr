---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 51df20ea00e5dd77ab1fc1a2a01253b8f788ad0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358849"
---
# <a name="nullptr"></a>nullptr

어떠한 원시 포인터 형식으로도 변환될 수 있는 `std::nullptr_t` 형식의 null 포인터 상수를 지정합니다.  헤더를 포함하지 않고 **nullptr** 라는 키워드를 사용할 수 있지만 `std::nullptr_t`코드에서 형식을 사용하는 경우 헤더를 `<cstddef>`포함하여 정의해야합니다.

> [!NOTE]
> **nullptr** 키워드는 관리되는 코드 응용 프로그램에 대해 C++/CLI에도 정의되며 ISO 표준 C++ 키워드와 상호 교환할 수 없습니다. 관리 되는 코드를 대상으로 하는 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용 하 여 `__nullptr` 코드를 컴파일할 수 있는 경우 컴파일러 네이티브 C ++ 해석을 사용 하 여 보장 해야 하는 코드의 모든 줄에 사용 합니다. 자세한 내용은 [nullptr](../extensions/nullptr-cpp-component-extensions.md)을 참조하십시오.

## <a name="remarks"></a>설명

null 또는 0`0`() 을 null 포인터 상수로 사용하지 마십시오. **nullptr오사용에** 덜 취약하 고 대부분의 상황에서 더 잘 작동 합니다.  예를 들어 `func(std::pair<const char *, double>)`가 주어진 경우 `func(std::make_pair(NULL, 3.14))`를 호출하면 컴파일러 오류가 발생합니다.  NULL 매크로는 `0`으로 확장되므로 `std::make_pair(0, 3.14)` 호출은 func()의 `std::pair<int, double>` 매개 변수 형식으로 변환될 수 없는 `std::pair<const char *, double>`를 반환합니다.  `func(std::make_pair(nullptr, 3.14))`는 `std::make_pair(nullptr, 3.14)`로 변환될 수 있는 `std::pair<std::nullptr_t, double>`를 반환하기 때문에 `std::pair<const char *, double>`를 호출하면 성공적으로 컴파일됩니다.

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)널프트르(C++/CLI)
