---
title: '&lt;ostream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 82539a3fdadf10d340ca957756e235e8ae00b267
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373576"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a><a name="ostream"></a>오스트림 (오스트림)

**char에** 특화된 basic_ostream char에 `char_traits` 특화된 **char**형식을 만듭니다.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 **있는** 문자 문자 형식의 요소에 특화된 클래스 템플릿 [basic_ostream](../standard-library/basic-ostream-class.md)동의어입니다.

## <a name="wostream"></a><a name="wostream"></a>워스트림

**wchar_t** 전문으로 하고 `char_traits` **wchar_t**전문으로 하는 basic_ostream 형식을 만듭니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 **wchar_t** 형식의 요소에 특화된 클래스 템플릿 [basic_ostream](../standard-library/basic-ostream-class.md)동의어입니다.

## <a name="see-also"></a>참고 항목

[\<오스트림>](../standard-library/ostream.md)
