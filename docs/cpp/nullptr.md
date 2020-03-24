---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 223f4c3e8c838698f9716e241543db405c9394af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177770"
---
# <a name="nullptr"></a>nullptr

어떠한 원시 포인터 형식으로도 변환될 수 있는 `std::nullptr_t` 형식의 null 포인터 상수를 지정합니다.  헤더를 포함 하지 않고 **nullptr** 키워드를 사용할 수 있지만 코드에서 `std::nullptr_t`형식을 사용 하는 경우 헤더 `<cstddef>`를 포함 하 여 정의 해야 합니다.

> [!NOTE]
>  **Nullptr** 키워드는 관리 코드 응용 프로그램 C++에 대 한/cli에도 정의 되며 ISO 표준 C++ 키워드와는 상호 교환할 수 없습니다. 관리 코드를 대상으로 하는 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용 하 여 코드를 컴파일할 수 있는 경우 컴파일러에서 네이티브 C++ 해석을 사용 하도록 보장 해야 하는 코드 줄에 `__nullptr`를 사용 합니다. 자세한 내용은 [nullptr](../extensions/nullptr-cpp-component-extensions.md)를 참조 하세요.

## <a name="remarks"></a>설명

Null 또는 0 (`0`)을 null 포인터 상수로 사용 하지 마십시오. **nullptr** 은 오용에 취약 하 고 대부분의 상황에서 효과적으로 작동 합니다.  예를 들어 `func(std::pair<const char *, double>)`가 주어진 경우 `func(std::make_pair(NULL, 3.14))`를 호출하면 컴파일러 오류가 발생합니다.  NULL 매크로는 `0`으로 확장되므로 `std::make_pair(0, 3.14)` 호출은 func()의 `std::pair<int, double>` 매개 변수 형식으로 변환될 수 없는 `std::pair<const char *, double>`를 반환합니다.  `func(std::make_pair(nullptr, 3.14))`는 `std::make_pair(nullptr, 3.14)`로 변환될 수 있는 `std::pair<std::nullptr_t, double>`를 반환하기 때문에 `std::pair<const char *, double>`를 호출하면 성공적으로 컴파일됩니다.

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/cli)
