---
title: '&lt;sstream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::istringstream
- iosfwd/std::ostringstream
- iosfwd/std::stringbuf
- iosfwd/std::stringstream
- iosfwd/std::wistringstream
- iosfwd/std::wostringstream
- iosfwd/std::wstringbuf
- iosfwd/std::wstringstream
ms.assetid: d102edd2-ecea-4a35-a398-cf96e58dd422
ms.openlocfilehash: c25d3fa66b5105ad2e1ff5a08ebdde90d1d156be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336643"
---
# <a name="ltsstreamgt-typedefs"></a>&lt;sstream&gt; 형식 정의

||||
|-|-|-|
|[아이스트링스트림](#istringstream)|[ostringstream](#ostringstream)|[스트링부프](#stringbuf)|
|[stringstream](#stringstream)|[위스트링스트림](#wistringstream)|[워스트링스트림](#wostringstream)|
|[스트링부프](#wstringbuf)|[스트링 스트림](#wstringstream)|

## <a name="istringstream"></a><a name="istringstream"></a>아이스트링스트림

char 템플릿 `basic_istringstream` 매개 **char** 변수에 특수화된 형식을 만듭니다.

```cpp
typedef basic_istringstream<char> istringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_istringstream](../standard-library/basic-istringstream-class.md)동의어이며 형식 **char의**요소에 대해 특수합니다.

## <a name="ostringstream"></a><a name="ostringstream"></a>오스트링스트림

char 템플릿 `basic_ostringstream` 매개 **char** 변수에 특수화된 형식을 만듭니다.

```cpp
typedef basic_ostringstream<char> ostringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_ostringstream](../standard-library/basic-ostringstream-class.md)동의어이며 형식 **char의**요소에 대해 특수합니다.

## <a name="stringbuf"></a><a name="stringbuf"></a>스트링부프

char 템플릿 `basic_stringbuf` 매개 **char** 변수에 특수화된 형식을 만듭니다.

```cpp
typedef basic_stringbuf<char> stringbuf;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)동의어이며 형식 **char의**요소에 대해 특수합니다.

## <a name="stringstream"></a><a name="stringstream"></a>스트링 스트림

char 템플릿 `basic_stringstream` 매개 **char** 변수에 특수화된 형식을 만듭니다.

```cpp
typedef basic_stringstream<char> stringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_stringstream](../standard-library/basic-stringstream-class.md)동의어이며 형식 **char의**요소에 대해 특수합니다.

## <a name="wistringstream"></a><a name="wistringstream"></a>위스트링스트림

wchar_t 템플릿 `basic_istringstream` 매개 **wchar_t** 변수에 특화된 형식을 만듭니다.

```cpp
typedef basic_istringstream<wchar_t> wistringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_istringstream](../standard-library/basic-istringstream-class.md)동의어이며 형식 **wchar_t**요소에 대해 전문화됩니다.

## <a name="wostringstream"></a><a name="wostringstream"></a>워스트링스트림

wchar_t 템플릿 `basic_ostringstream` 매개 **wchar_t** 변수에 특화된 형식을 만듭니다.

```cpp
typedef basic_ostringstream<wchar_t> wostringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_ostringstream](../standard-library/basic-ostringstream-class.md)동의어이며 형식 **wchar_t**요소에 특화된 것입니다.

## <a name="wstringbuf"></a><a name="wstringbuf"></a>스트링부프

wchar_t 템플릿 `basic_stringbuf` 매개 **wchar_t** 변수에 특화된 형식을 만듭니다.

```cpp
typedef basic_stringbuf<wchar_t> wstringbuf;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)동의어이며 형식 **wchar_t**요소에 대해 전문화됩니다.

## <a name="wstringstream"></a><a name="wstringstream"></a>스트링 스트림

wchar_t 템플릿 `basic_stringstream` 매개 **wchar_t** 변수에 특화된 형식을 만듭니다.

```cpp
typedef basic_stringstream<wchar_t> wstringstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_stringstream](../standard-library/basic-stringstream-class.md)동의어이며 형식 **wchar_t**요소에 대해 전문화됩니다.

## <a name="see-also"></a>참고 항목

[\<>](../standard-library/sstream.md)
