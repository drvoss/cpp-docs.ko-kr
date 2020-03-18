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
ms.openlocfilehash: 3f4104b28f5becfdbf62ede16faa81e855fcac8c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427076"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; 형식 정의

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>  filebuf

**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_filebuf` 합니다.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_filebuf](../standard-library/basic-filebuf-class.md)의 동의어입니다.

## <a name="fstream"></a>  fstream

**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_fstream` 합니다.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_fstream](../standard-library/basic-fstream-class.md)의 동의어입니다.

## <a name="ifstream"></a>  ifstream

파일에서 직렬로 싱글바이트 문자 데이터를 읽는 데 사용할 스트림을 정의합니다. `ifstream`은 **char**에 대 한 클래스 템플릿 `basic_ifstream`를 특수화 하는 typedef입니다.

또한 `basic_ifstream` **wchar_t** 양방향 문자를 읽을 수 있도록 특수화 하는 typedef 인 `wifstream`있습니다. 자세한 내용은 [wifstream](../standard-library/fstream-typedefs.md#wifstream)을 참조하세요.

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 char 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ifstream](../standard-library/basic-ifstream-class.md)의 동의어입니다. 예제는 다음과 같습니다.

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a>  ofstream

**문자** 템플릿 매개 변수에서 특수화 된 형식 `basic_ofstream` 합니다.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 포함 하는 **char** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ofstream](../standard-library/basic-ofstream-class.md)의 동의어입니다.

## <a name="wfstream"></a>  wfstream

**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_fstream`입니다.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 여 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_fstream](../standard-library/basic-fstream-class.md)의 동의어입니다.

## <a name="wifstream"></a>  wifstream

**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_ifstream`입니다.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 여 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ifstream](../standard-library/basic-ifstream-class.md)의 동의어입니다.

## <a name="wofstream"></a>  wofstream

**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_ofstream`입니다.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 여 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_ofstream](../standard-library/basic-ofstream-class.md)의 동의어입니다.

## <a name="wfilebuf"></a>  wfilebuf

**Wchar_t** 템플릿 매개 변수에서 특수화 된 형식 `basic_filebuf`입니다.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>설명

이 형식은 기본 문자 특성을 사용 하 여 **wchar_t** 형식의 요소에 대해 특수화 된 클래스 템플릿 [basic_filebuf](../standard-library/basic-filebuf-class.md)의 동의어입니다.

## <a name="see-also"></a>참고 항목

[\<fstream>](../standard-library/fstream.md)
