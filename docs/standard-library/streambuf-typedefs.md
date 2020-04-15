---
title: '&lt;streambuf&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 8eb058f161a9f30ccf5e9d49307b50c215f79c22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376687"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; 형식 정의

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>스트림부프

이 전문화는 `basic_streambuf` **char를** 템플릿 매개 변수로 사용합니다.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_streambuf](../standard-library/basic-streambuf-class.md)동의어로 기본 문자 특성이 **있는** 문자 문자 형식의 요소에 대해 특수화됩니다.

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf

이 전문화는 `basic_streambuf` **wchar_t** 템플릿 매개 변수로 사용합니다.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 **wchar_t** 형식 요소에 특화된 클래스 템플릿 [basic_streambuf](../standard-library/basic-streambuf-class.md)동의어입니다.

## <a name="see-also"></a>참고 항목

[\<스트림부프>](../standard-library/streambuf.md)
