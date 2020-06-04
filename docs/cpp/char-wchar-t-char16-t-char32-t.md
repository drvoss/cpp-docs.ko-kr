---
title: char, wchar_t, char16_t, char32_t
ms.date: 02/14/2018
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: 8d109ec452df33b774848229837ed3e2eae80dc4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181020"
---
# <a name="char-wchar_t-char16_t-char32_t"></a>char, wchar_t, char16_t, char32_t

**Char**, **wchar_t**, **char16_t** 및 **char32_t** 형식은 영숫자 문자와 영숫자가 아닌 문자 모양 및 인쇄 되지 않는 문자를 나타내는 기본 제공 형식입니다.

## <a name="syntax"></a>구문

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>주의

**문자** 형식은 C 및 C++의 원래 문자 형식입니다. 형식 **부호 없는 문자** 는에서 C++기본 제공 형식이 아닌 *바이트*를 나타내는 데 사용 되는 경우가 많습니다. **Char** 형식은 ASCII 문자 집합 또는 ISO-8859 문자 집합의 문자를 저장 하는 데 사용할 수 있으며, Shift-jis 또는 유니코드 문자 집합의 utf-8 인코딩과 같은 멀티 바이트 문자의 개별 바이트를 저장 하는 데 사용할 수 있습니다. **문자** 형식의 문자열은 여러 바이트 문자를 인코딩하는 데 사용 되는 경우에도 *좁은* 문자열 이라고 합니다. Microsoft 컴파일러에서 **char** 는 8 비트 형식입니다.

**Wchar_t** 형식은 구현 시 정의 된 와이드 문자 형식입니다. Microsoft 컴파일러에서 Windows 운영 체제의 네이티브 문자 형식인 u t f-UTF-16LE로 인코딩된 유니코드를 저장 하는 데 사용 되는 16 비트 와이드 문자를 나타냅니다. C #의 와이드 문자 버전은 네이티브 Windows API의 와이드 문자 버전과 마찬가지로 **wchar_t** 및 해당 포인터와 배열 형식을 매개 변수 및 반환 값으로 사용 합니다.

**Char16_t** 및 **char32_t** 형식은 각각 16 비트 및 32 비트 와이드 문자를 나타냅니다. U t f-16으로 인코딩된 유니코드는 **char16_t** 형식으로 저장할 수 있으며 u t f-32로 인코딩된 유니코드는 **char32_t** 형식으로 저장할 수 있습니다. 이러한 형식 및 **wchar_t** 문자열은 모두 *와이드* 문자열 이라고 하며, 용어는 대개 **wchar_t** 형식의 문자열을 의미 합니다.

C++ 표준 라이브러리에서 `basic_string` 형식은 좁은 문자열과 와이드 문자열 모두에 대해 특수화 되어 있습니다. 문자가 **문자 형식이 면**`std::string`를 사용 하 고 문자를 **char16_t**형식으로 `std::u16string` 하는 경우에는 문자를 **char32_t**형식으로 `std::u32string` 하 고 문자가 `std::wstring` 형식인 경우 wchar_t **합니다.** `std::stringstream` 및 `std::cout`를 비롯 하 여 텍스트를 나타내는 다른 형식은 좁은 문자열과 와이드 문자열에 대 한 특수화를 가집니다.
