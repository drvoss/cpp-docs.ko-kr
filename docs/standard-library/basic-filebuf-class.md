---
title: basic_filebuf 클래스
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: 35bed08f2495c971df7f79f62e32b3ff68dfb3d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376876"
---
# <a name="basic_filebuf-class"></a>basic_filebuf 클래스

문자 특성이 *Tr*클래스에 의해 결정되는 형식 *Char_T*요소의 전송을 제어하는 스트림 버퍼를 설명하고 외부 파일에 저장된 요소 시퀀스에서

## <a name="syntax"></a>구문

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>매개 변수

*Char_T*\
파일 버퍼의 기본 요소입니다.

*Tr*\
파일 버퍼의 기본 요소(일반적으로)의 `char_traits<Char_T>`특성입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 tr *클래스에*의해 결정되는 문자 특성인 *Char_T*형식의 요소 전송을 제어하는 스트림 버퍼를 설명하고 외부 파일에 저장된 요소 시퀀스에서 연결됩니다.

> [!NOTE]
> 형식의 `basic_filebuf` 개체는 형식 매개 변수 *Char_T*지정 된 에 관계 없이 형식 __char의\* __ `char_type` 내부 버퍼로 만들어집니다. 즉, 내부 버퍼에 기록되기 전에 유니코드 **문자열(wchar_t** 문자 포함)이 ANSI **문자열(문자** 포함)으로 변환됩니다. 버퍼에 유니코드 문자열을 저장하려면 **wchar_t** 형식의 새 버퍼를 [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` 만들고 메서드를 사용하여 설정합니다. 이 동작을 보여 주는 예제를 보려면 아래를 참조하세요.

클래스의 `basic_filebuf<Char_T, Tr>` 개체는 열린 파일과 연결된 스트림을 제어하는 `FILE` 개체를 지정하는 파일 포인터를 저장합니다. 또한 보호된 멤버 함수 [overflow](#overflow) 및 [underflow](#underflow)에서 사용하도록 두 가지 파일 변환 패싯에 대한 포인터를 저장합니다. 자세한 내용은 을 [`basic_filebuf::open`](#open)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `basic_filebuf<wchar_t>` 형식의 개체가 `pubsetbuf()` 메서드를 호출하여 유니코드 문자열을 내부 버퍼에 강제로 저장하도록 하는 방법을 보여 줍니다.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_filebuf](#basic_filebuf)|`basic_filebuf` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[char_type](#char_type)|형식 이름을 `Char_T` 템플릿 매개 변수와 연결합니다.|
|[int_type](#int_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[off_type](#off_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[pos_type](#pos_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[traits_type](#traits_type)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[가까이](#close)|파일을 닫습니다.|
|[is_open](#is_open)|파일이 열려 있는지 여부를 나타냅니다.|
|[열기](#open)|파일을 엽니다.|
|[오버플로](#overflow)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|
|[pbackfail](#pbackfail)|보호된 가상 멤버 함수는 요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|
|[seekoff](#seekoff)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[seekpos](#seekpos)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[setbuf](#setbuf)|보호된 가상 멤버 함수는 파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.|
|[스왑](#swap)|이 `basic_filebuf`의 콘텐츠를 제공된 `basic_filebuf` 매개 변수의 콘텐츠로 교환합니다.|
|[동기화](#sync)|보호된 가상 함수는 제어된 스트림을 연결된 외부 스트림과 동기화하려고 합니다.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|
|[언더플로](#underflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<fstream>

**네임스페이스:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf:basic_filebuf

`basic_filebuf` 형식의 개체를 생성합니다.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>설명

첫 번째 생성자는 입력 버퍼와 출력 버퍼를 제어하는 모든 포인터에 null 포인터를 저장합니다. 또한 파일 포인터에 null 포인터를 저장합니다.

두 번째 생성자는 rvalue 참조로 처리된 *오른쪽의*내용을 통해 개체를 초기화합니다.

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf:char_type

형식 이름을 `Char_T` 템플릿 매개 변수와 연결합니다.

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf::닫기

파일을 닫습니다.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Return Value

파일 포인터가 null 포인터인 경우 멤버 함수는 null 포인터를 반환합니다.

### <a name="remarks"></a>설명

`close`은 `fclose(fp)`를 호출합니다. 해당 함수가 0이 아닌 값을 반환하는 경우 이 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환하여 파일을 성공적으로 닫았음을 나타냅니다.

와이드 스트림의 경우 스트림이 열린 이후 또는 마지막으로 호출된 이후 `streampos`함수가 호출된 [`overflow`](#overflow)이후 삽입이 발생한 경우. 또한 필요에 따라 `fac` 호출하는 `fac.unshift` 파일 변환 면을 사용하여 초기 변환 상태를 복원하는 데 필요한 모든 시퀀스를 삽입합니다. 형식 **char의** 각 생성된 요소는 `fp` `fputc(byte, fp)` `byte` 양식의 연속 호출에 의해 마치 파일 포인터에 의해 지정된 연결된 스트림에 기록됩니다. 호출 또는 `fac.unshift` 쓰기에 실패하면 함수가 성공하지 못합니다.

### <a name="example"></a>예제

다음 샘플에서는 현재 디렉터리에 있는 두 개의 *파일(basic_filebuf_close.txt(콘텐츠는* "테스트") 및 *iotest.txt(내용은* "sss")로 가정합니다.

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf::int_type

범위 내에서 `basic_filebuf` 이 형식을 범위에서 동일한 이름의 `Tr` 형식과 동일하게 만듭니다.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf:is_open

파일이 열려 있는지 여부를 나타냅니다.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Return Value

파일 포인터가 null이 아닌 경우 **true입니다.**

### <a name="example"></a>예제

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf:off_type

범위 내에서 `basic_filebuf` 이 형식을 범위에서 동일한 이름의 `Tr` 형식과 동일하게 만듭니다.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf:::열기

파일을 엽니다.

```cpp
basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode);
```

### <a name="parameters"></a>매개 변수

*파일*\
열어야 할 파일의 이름입니다.

*모드*\
의 열거형 중 [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode)하나입니다.

*보호*\
_fsopen *shflag* 매개 변수와 동일한 기본 파일 열기 보호가 [_wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="return-value"></a>Return Value

버퍼가 이미 열려 있거나 파일 포인터가 null 포인터인 경우 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환합니다.

### <a name="remarks"></a>설명

멤버 함수는 을 호출하여 [`fopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)`이름 *파일 이름으로*파일을 엽니다. `strmode``)`에서 결정됩니다. `mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode)

- `ios_base::in`(읽기 위해 기존 파일을 엽니다)가 됩니다. `"r"`

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) `ios_base::out | ios_base::trunc` 또는 `"w"` (기존 파일을 자회하거나 작성하기 위해 작성)됩니다.

- `ios_base::out | app`(모든 쓰기를 더하기 위해 기존 파일을 엽니다)가 됩니다. `"a"`

- `ios_base::in | ios_base::out`(읽기 및 쓰기를 위해 기존 파일을 엽니다)가 됩니다. `"r+"`

- `ios_base::in | ios_base::out | ios_base::trunc`(기존 파일을 트렁크하거나 읽기 및 쓰기를 위해 작성)가 됩니다. `"w+"`

- `ios_base::in | ios_base::out | ios_base::app`(읽기 및 모든 쓰기를 적용하기 위한 기존 파일을 엽니다)가 됩니다. `"a+"`

영하지 않은 경우 `mode & ios_base::binary` 함수는 `b` `strmode` 텍스트 스트림 대신 이진 스트림을 여는 데 부속됩니다. 그런 다음 파일 포인터에서 `fopen` `fp`반환된 값을 저장합니다. 0이 아니고 파일 포인터가 null 포인터가 아닌 `mode & ios_base::ate` `fseek(fp, 0, SEEK_END)` 경우 함수는 스트림을 파일 끝에 배치하도록 호출합니다. 해당 위치 지정 작업이 실패하면 [`close`](#close) `(fp)` 함수는 null 포인터를 호출하고 파일 포인터에 저장합니다.

파일 포인터가 null 포인터가 아닌 경우 `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)`함수는 [언더플로우](#underflow) 및 [오버플로에](#overflow)의해 사용할 파일 변환 면:

파일 포인터가 null 포인터인 경우 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환합니다.

### <a name="example"></a>예제

을 [`basic_filebuf::close`](#close) 사용하는 `open`예제를 참조하십시오.

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf::연산자=

이 스트림 버퍼 개체의 콘텐츠를 할당합니다. 복사본을 남기지 않는 rvalue와 관련된 이동 할당입니다.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) 개체에 대한 rvalue 참조입니다.

### <a name="return-value"></a>Return Value

반환 __*이__.

### <a name="remarks"></a>설명

멤버 연산자는 rvalue 참조로 처리된 *오른쪽의*내용을 사용하여 개체의 내용을 대체합니다. 자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하십시오.

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf::오버플로우

가득 찬 버퍼에 새 문자를 삽입할 때 호출됩니다.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼 또는 `traits_type::eof`에 삽입할 문자입니다.

### <a name="return-value"></a>Return Value

함수가 성공할 수 없는 경우 `traits_type::eof`반환합니다. 그렇지 않으면 `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`반환합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수가 요소를 `_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` 출력 버퍼에 삽입하려고 시도하는 경우. 수행할 수 있는 방법은 다양합니다.

- 쓰기 위치를 사용할 수 있는 경우 요소를 쓰기 위칭에 저장하고 출력 버퍼에 대해 다음 포인터를 증분할 수 있습니다.

- 출력 버퍼에 대해 새 스토리지 또는 추가 스토리지를 할당하여 쓰기 위치를 사용 가능하게 만들 수 있습니다.

- 출력 버퍼에서 보류 중인 모든 출력을 `ch`변환한 다음 필요에 `fac` 따라 `fac.out` 파일 변환 면을 사용하여 호출할 수 있습니다. 형식 *char의* 각 생성된 요소는 `fp` `fputc(ch, fp)` `ch` 양식의 연속 호출에 의해 마치 파일 포인터에 의해 지정된 연결된 스트림에 기록됩니다. 변환 또는 쓰기가 실패하면 함수가 성공하지 못합니다.

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf::p백 실패

요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼에 삽입할 문자 또는 `traits_type::eof`입니다.

### <a name="return-value"></a>Return Value

함수가 성공할 수 없는 경우 `traits_type::eof`반환합니다. 그렇지 않으면 `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`반환합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정합니다. 밀어낼 요소가 현재 요소 앞에 스트림에 이미 있는 요소가 실제로 있는 경우. `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) 그렇지 않으면 해당 요소가 `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)`로 바뀝뀝습니다. 함수는 여러 가지 방법으로 요소를 다시 넣을 수 있습니다.

- `putback` 위치를 사용할 수 있고 거기에 저장된 요소가 `ch`같으면 입력 버퍼에 대한 다음 포인터가 감소할 수 있습니다.

- 함수가 `putback` 위치를 사용할 수 있도록 할 수 있는 경우 다음 포인터를 해당 `ch` 위치를 가리키도록 설정하고 해당 위치에 저장할 수 있습니다.

- 함수가 요소를 입력 스트림으로 푸시할 수 있는 경우 **char**형식의 `ungetc` 요소를 호출하는 등 이렇게 할 수 있습니다.

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::pos_type

범위 내에서 `basic_filebuf` 이 형식을 범위에서 동일한 이름의 `Tr` 형식과 동일하게 만듭니다.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf:::검색오프

제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Off*\
*_Way*상대적으로 추구하는 위치.

*_Way*\
오프셋 작업의 시작 지점입니다. 가능한 값은 [seekdir](../standard-library/ios-base-class.md#seekdir)을 참조하세요.

*_Which*\
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.

### <a name="return-value"></a>Return Value

새 위치 또는 잘못된 스트림 위치를 반환합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 시도합니다. 클래스의 [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`개체에 대 한 스트림 위치는 오프셋 `fpos_t`및 넓은 스트림을 구문 분석 하는 데 필요한 모든 상태 정보를 저장 하는 형식의 개체로 나타낼 수 있습니다. 오프셋 0은 스트림의 첫 번째 요소를 나타냅니다. (형식의 [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) 개체는 적어도 `fpos_t` 개체를 저장합니다.)

읽기 및 쓰기용으로 열린 파일의 경우 입력 스트림과 출력 스트림이 나란히 배치됩니다. 삽입과 추출 간에 전환하려면 [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) 또는 [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)을 호출해야 합니다. 호출 `pubseekoff` `seekoff`(따라서) [텍스트 스트림,](../c-runtime-library/text-and-binary-streams.md) [이진 스트림](../c-runtime-library/text-and-binary-streams.md)및 넓은 스트림에 대 한 다양 한 제한이 [있습니다.](../c-runtime-library/byte-and-wide-streams.md)

파일 포인터가 `fp` null 포인터인 경우 함수가 실패합니다. 그렇지 않으면 을 호출하여 스트림 `fseek(fp, _Off, _Way)`위치를 변경하려고 시도합니다. 해당 함수가 성공하고 결과 `fposn` 위치를 호출하여 `fgetpos(fp, &fposn)`결정할 수 있으면 함수가 성공합니다. 함수가 성공하면 을 포함하는 형식의 `pos_type` 값을 `fposn`반환합니다. 실패하면 잘못된 스트림 위치를 반환합니다.

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf::seekpos

제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Sp*\
찾을 위치입니다.

*_Which*\
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.

### <a name="return-value"></a>Return Value

파일 포인터가 `fp` null 포인터인 경우 함수가 실패합니다. `fsetpos(fp, &fposn)`그렇지 않으면 에 `fposn` 저장된 `fpos_t` 개체를 호출하여 스트림 위치를 `pos`변경하려고 시도합니다. 성공하면 함수는 `pos`을 반환합니다. 실패하면 잘못된 스트림 위치를 반환합니다. 스트림 위치가 잘못되었는지를 확인하려면 반환 값을 `pos_type(off_type(-1))`과 비교합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 시도합니다. 클래스의 [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`개체에 대 한 스트림 위치는 오프셋 `fpos_t`및 넓은 스트림을 구문 분석 하는 데 필요한 모든 상태 정보를 저장 하는 형식의 개체로 나타낼 수 있습니다. 오프셋 0은 스트림의 첫 번째 요소를 나타냅니다. (`pos_type` 형식의 개체는 최소한 `fpos_t` 개체를 저장합니다.)

읽기 및 쓰기용으로 열린 파일의 경우 입력 스트림과 출력 스트림이 나란히 배치됩니다. 삽입과 추출 간에 전환하려면 [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) 또는 [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)을 호출해야 합니다. `seekoff`(및)에 `pubseekoff` 대한 호출에는 텍스트 스트림, 이진 스트림 및 와이드 스트림에 대한 다양한 제한 사항이 있습니다.

와이드 스트림의 경우 스트림이 열린 이후 또는 `streampos`에 대한 마지막 호출 이후 삽입이 발생하면 함수는 [overflow](#overflow)를 호출합니다. 또한 필요에 따라 `fac` 호출하는 `fac.unshift` 파일 변환 면을 사용하여 초기 변환 상태를 복원하는 데 필요한 모든 시퀀스를 삽입합니다. 형식 **char의** 각 생성된 요소는 `fp` `fputc(byte, fp)` `byte` 양식의 연속 호출에 의해 마치 파일 포인터에 의해 지정된 연결된 스트림에 기록됩니다. 호출 또는 `fac.unshift` 쓰기에 실패하면 함수가 성공하지 못합니다.

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf::setbuf

파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*_Buffer*\
버퍼에 대한 포인터입니다.

*횟수*\
버퍼의 크기입니다.

### <a name="return-value"></a>Return Value

`fp` 파일 포인터가 null 포인터인 경우 보호된 멤버 함수는 0을 반환합니다.

### <a name="remarks"></a>설명

`setbuf`을 `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` 호출하여 `count` *_Buffer* 시작되는 요소의 배열을 스트림의 버퍼로 제공합니다. 해당 함수가 0이 아닌 값을 반환하는 경우 이 함수는 null 포인터를 반환합니다. 아닌 경우 성공을 알리기 위해 **this**를 반환합니다.

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf::스왑

이 `basic_filebuf`의 내용을 제공된 `basic_filebuf`의 내용으로 교환합니다.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
다른 `basic_filebuf`에 대한 lvalue 참조입니다.

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf:::동기화

제어된 스트림을 연결된 외부 스트림과 동기화하려고 합니다.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Return Value

파일 포인터가 null `fp` 포인터인 경우 0을 반환합니다. 그렇지 않으면 [오버플로에](#overflow) 대한 호출이 `fflush(fp)` 스트림에 보류 중인 출력을 플러시하는 데 성공한 경우에만 0을 반환합니다.

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf:traits_type

형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf::언더플로우

입력 스트림에서 현재 요소를 추출합니다.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Return Value

함수가 성공할 수 없는 경우 `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)반환합니다. `ch`그렇지 않으면 비고 섹션에 설명된 대로 변환됩니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 입력 `ch` 스트림에서 현재 요소를 추출하고 `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)`요소를 로 반환하려고 시도합니다. 수행할 수 있는 방법은 다양합니다.

- 읽기 위치를 사용할 수 있는 `ch` 경우 읽기 위치에 저장된 요소로 사용되며 입력 버퍼에 대한 다음 포인터를 진행합니다.

- 양식의 `fgetc(fp)`연속 호출에 의해 처럼 **문자 char의**하나 이상의 요소를 읽고 필요에 `ch` `fac.in` 따라 `Char_T` 호출 `fac` 하는 파일 변환 면을 사용 하 여 형식의 요소로 변환할 수 있습니다. 읽기 또는 변환이 실패하면 함수가 성공하지 못합니다.

## <a name="see-also"></a>참고 항목

[\<fstream>](../standard-library/fstream.md)\
[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
