---
title: '&lt;fstream&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: 57e481c131a6e4a1111b1ed88217b891d6fc96a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317189"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; 형식 정의

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a><a name="filebuf"></a>파일 부프

char `basic_filebuf` 템플릿 **char** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 **있는** 문자 문자 형식의 요소에 특화된 클래스 템플릿 [basic_filebuf](../standard-library/basic-filebuf-class.md)동의어입니다.

## <a name="fstream"></a><a name="fstream"></a>fstream

char `basic_fstream` 템플릿 **char** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_fstream](../standard-library/basic-fstream-class.md)동의어로 기본 문자 특성이 **있는** 문자 형식의 요소에 대해 특수합니다.

## <a name="ifstream"></a><a name="ifstream"></a>ifstream

파일에서 직렬로 싱글바이트 문자 데이터를 읽는 데 사용할 스트림을 정의합니다. `ifstream`는 **char에**대한 클래스 `basic_ifstream` 템플릿을 전문으로하는 typedef입니다.

이중 와이드 `wifstream`문자를 **wchar_t** 읽을 `basic_ifstream` 수있는 유형 def도 있습니다. 자세한 내용은 [wifstream](../standard-library/fstream-typedefs.md#wifstream)을 참조하세요.

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_ifstream](../standard-library/basic-ifstream-class.md)대 한 동의어이며 기본 문자 특성을 가진 문자 형식 char의 요소에 대해 전문화되어 있습니다. 예제는 다음과 같습니다.

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a>의 흐름

char `basic_ofstream` 템플릿 **char** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>설명

형식은 클래스 템플릿 [basic_ofstream](../standard-library/basic-ofstream-class.md)동의어로 기본 문자 특성이 **있는** 문자 형식의 요소에 대해 특수합니다.

## <a name="wfstream"></a><a name="wfstream"></a>wfstream

wchar_t `basic_fstream` 템플릿 **wchar_t** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 **wchar_t** 형식 의 요소에 특화된 클래스 템플릿 [basic_fstream](../standard-library/basic-fstream-class.md)동의어입니다.

## <a name="wifstream"></a><a name="wifstream"></a>위스트림 (것)과

wchar_t `basic_ifstream` 템플릿 **wchar_t** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 형식 **wchar_t** 요소에 특화된 클래스 템플릿 [basic_ifstream](../standard-library/basic-ifstream-class.md)동의어입니다.

## <a name="wofstream"></a><a name="wofstream"></a>wofstream

wchar_t `basic_ofstream` 템플릿 **wchar_t** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 **wchar_t** 형식의 요소에 특화된 클래스 템플릿 [basic_ofstream](../standard-library/basic-ofstream-class.md)동의어입니다.

## <a name="wfilebuf"></a><a name="wfilebuf"></a>wfilebuf

wchar_t `basic_filebuf` 템플릿 **wchar_t** 매개 변수에 특화된 형식입니다.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>설명

형식은 기본 문자 특성이 있는 형식 **wchar_t** 요소에 특화된 클래스 템플릿 [basic_filebuf](../standard-library/basic-filebuf-class.md)동의어입니다.

## <a name="see-also"></a>참고 항목

[\<fstream>](../standard-library/fstream.md)
