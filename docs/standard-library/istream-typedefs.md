---
title: '&lt;istream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: e9228bddcc3b99503b6b5f0e93b5ed6eeed773d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363090"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의

||||
|-|-|-|
|[iostream](#iostream)|[Istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a><a name="iostream"></a>Iostream

`basic_iostream` **문자에**특화된 형식입니다.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_iostream](../standard-library/basic-iostream-class.md)동의어로 기본 문자 특성이 **있는** 문자 형식의 요소에 대해 특수합니다.

## <a name="istream"></a><a name="istream"></a>Istream

`basic_istream` **문자에**특화된 형식입니다.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_istream](../standard-library/basic-istream-class.md)동의어로 기본 문자 특성이 **있는** 문자 형식의 요소에 대해 전문화됩니다.

## <a name="wiostream"></a><a name="wiostream"></a>위오스트림

wchar_t `basic_iostream` 전문으로 **wchar_t**하는 타입.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 형식 **wchar_t** 요소에 특화된 클래스 템플릿 [basic_iostream](../standard-library/basic-iostream-class.md)동의어입니다.

## <a name="wistream"></a><a name="wistream"></a>와이스트림

wchar_t `basic_istream` 전문으로 **wchar_t**하는 타입.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 **wchar_t** 형식 요소에 특화된 클래스 템플릿 [basic_istream](../standard-library/basic-istream-class.md)동의어입니다.

## <a name="see-also"></a>참고 항목

[\<아이스트림>](../standard-library/istream.md)
