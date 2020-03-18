---
title: '&lt;ostream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: d0ceae12069712c7a124990d0f81968c21bc683a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425306"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Char에서 특수화 된 basic_ostream에서 **문자 및 `char_traits`** 특수화 된 형식을 **만듭니다.**

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ostream](../standard-library/basic-ostream-class.md)의 동의어입니다.

## <a name="wostream"></a>  wostream

**Wchar_t** 에서 특수화 된 basic_ostream와 **wchar_t**에서 특수화 된 `char_traits` 형식을 만듭니다.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 여 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ostream](../standard-library/basic-ostream-class.md)의 동의어입니다.

## <a name="see-also"></a>참고 항목

[\<ostream>](../standard-library/ostream.md)
