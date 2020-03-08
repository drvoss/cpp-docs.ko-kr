---
title: '&lt;streambuf&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 1c9850ad7d7ec9b9c3554e6806f4790ef3613b08
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866214"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; 형식 정의

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

**Char** 를 템플릿 매개 변수로 사용 하는 `basic_streambuf`의 특수화입니다.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_streambuf](../standard-library/basic-streambuf-class.md)의 동의어입니다.

## <a name="wstreambuf"></a>  wstreambuf

**Wchar_t** 를 템플릿 매개 변수로 사용 하는 `basic_streambuf`의 특수화입니다.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_streambuf](../standard-library/basic-streambuf-class.md)의 동의어입니다.

## <a name="see-also"></a>참고 항목

[\<streambuf>](../standard-library/streambuf.md)
