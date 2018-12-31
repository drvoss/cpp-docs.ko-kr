---
title: '방법: 다양한 문자열 형식 간 변환'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- converting string types
- string conversion [C++]
- strings [C++], converting
ms.assetid: e7e4f741-3c82-45f0-b8c0-1e1e343b0e77
ms.openlocfilehash: 8ee8790e960c05827404d932a2305a7de79cbced
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443357"
---
# <a name="how-to-convert-between-various-string-types"></a>방법: 다양한 문자열 형식 간 변환

이 항목에서는 다양 한 Visual c + + 문자열 형식을 다른 문자열로 변환 하는 방법에 설명 합니다. 적용 되는 문자열 형식 포함 `char *`, `wchar_t*`를 [_bstr_t](../cpp/bstr-t-class.md)를 [CComBSTR](../atl/reference/ccombstr-class.md)를 [CString](../atl-mfc-shared/using-cstring.md), [basic_string](../standard-library/basic-string-class.md), 및 <xref:System.String?displayProperty=fullName>합니다. 모든 경우에 새 형식으로 변환할 때 문자열의 복사본이 만들어집니다. 새 문자열을 변경한 내용을 원래 문자열에서 영향을 주지 것입니다 그 반대로 가능 합니다.

## <a name="converting-from-char-"></a>Char에서 변환 \*

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `char *` 위에 나열 된 다른 문자열 형식입니다. `char *` 문자열 (라고도: C 스타일 문자열)는 null 문자를 사용 하 여 문자열의 끝을 나타냅니다. C 스타일 문자열에는 대개 문자당 1 바이트가 필요 하지만 2 바이트를 사용할 수도 있습니다. 아래 예제에서 `char *` 문자열은 라고도 멀티 바이트 문자열이 유니코드 문자열에서 변환 결과로 생성 되는 문자열 데이터 때문입니다. 싱글바이트 및 멀티 바이트 문자 (`MBCS`) 함수에서 작동할 수 있습니다 `char *` 문자열입니다.

### <a name="code"></a>코드

```cpp
// convert_from_char.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"

using namespace std;
using namespace System;

int main()
{
    // Create and display a C style string, and then use it
    // to create different kinds of strings.
    char *orig = "Hello, World!";
    cout << orig << " (char *)" << endl;

    // newsize describes the length of the
    // wchar_t string called wcstring in terms of the number
    // of wide characters, not the number of bytes.
    size_t newsize = strlen(orig) + 1;

    // The following creates a buffer large enough to contain
    // the exact number of characters in the original string
    // in the new format. If you want to add more characters
    // to the end of the string, increase the value of newsize
    // to increase the size of the buffer.
    wchar_t * wcstring = new wchar_t[newsize];

    // Convert char* string to a wchar_t* string.
    size_t convertedChars = 0;
    mbstowcs_s(&convertedChars, wcstring, newsize, orig, _TRUNCATE);
    // Display the result and indicate the type of string that it is.
    wcout << wcstring << _T(" (wchar_t *)") << endl;

    // Convert the C style string to a _bstr_t string.
    _bstr_t bstrt(orig);
    // Append the type of string to the new string
    // and then display the result.
    bstrt += " (_bstr_t)";
    cout << bstrt << endl;

    // Convert the C style string to a CComBSTR string.
    CComBSTR ccombstr(orig);
    if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
    {
        CW2A printstr(ccombstr);
        cout << printstr << endl;
    }

    // Convert the C style string to a CstringA and display it.
    CStringA cstringa(orig);
    cstringa += " (CStringA)";
    cout << cstringa << endl;

    // Convert the C style string to a CStringW and display it.
    CStringW cstring(orig);
    cstring += " (CStringW)";
    // To display a CStringW correctly, use wcout and cast cstring
    // to (LPCWSTR).
    wcout << (LPCWSTR)cstring << endl;

    // Convert the C style string to a basic_string and display it.
    string basicstring(orig);
    basicstring += " (basic_string)";
    cout << basicstring << endl;

    // Convert the C style string to a System::String and display it.
    String ^systemstring = gcnew String(orig);
    systemstring += " (System::String)";
    Console::WriteLine("{0}", systemstring);
    delete systemstring;
}
```

```Output
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (_bstr_t)
Hello, World! (CComBSTR)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (basic_string)
Hello, World! (System::String)
```

## <a name="converting-from-wchart-"></a>Wchar_t에서 변환 \*

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `wchar_t *` 위에 나열 된 다른 문자열 형식입니다. 여러 문자열을 비롯 한 형식 `wchar_t *`, 와이드 문자 형식을 구현 합니다. 멀티 바이트 및 와이드 문자 형식 간에 문자열을 변환 하려면 같은 단일 함수 호출을 사용할 수 있습니다 `mbstowcs_s` 클래스에 대 한 생성자 호출 하거나 `CStringA`합니다.

### <a name="code"></a>코드

```cpp
// convert_from_wchar_t.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"

using namespace std;
using namespace System;

int main()
{
    // Create a string of wide characters, display it, and then
    // use this string to create other types of strings.
    wchar_t *orig = _T("Hello, World!");
    wcout << orig << _T(" (wchar_t *)") << endl;

    // Convert the wchar_t string to a char* string. Record
    //.the length of the original string and add 1 to it to
    //.account for the terminating null character.
    size_t origsize = wcslen(orig) + 1;
    size_t convertedChars = 0;

    // Use a multibyte string to append the type of string
    // to the new string before displaying the result.
    char strConcat[] = " (char *)";
    size_t strConcatsize = (strlen( strConcat ) + 1)*2;

    // Allocate two bytes in the multibyte output string for every wide
    // character in the input string (including a wide character
    // null). Because a multibyte character can be one or two bytes,
    // you should allot two bytes for each character. Having extra
    // space for the new string is not an error, but having
    // insufficient space is a potential security problem.
    const size_t newsize = origsize*2;
    // The new string will contain a converted copy of the original
    // string plus the type of string appended to it.
    char *nstring = new char[newsize+strConcatsize];

    // Put a copy of the converted string into nstring
    wcstombs_s(&convertedChars, nstring, newsize, orig, _TRUNCATE);
    // append the type of string to the new string.
    _mbscat_s((unsigned char*)nstring, newsize+strConcatsize, (unsigned char*)strConcat);
    // Display the result.
    cout << nstring << endl;

    // Convert a wchar_t to a _bstr_t string and display it.
    _bstr_t bstrt(orig);
    bstrt += " (_bstr_t)";
    cout << bstrt << endl;

    // Convert the wchar_t string to a BSTR wide character string
    // by using the ATL CComBSTR wrapper class for BSTR strings.
    // Then display the result.

    CComBSTR ccombstr(orig);
    if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
    {
        // CW2A converts the string in ccombstr to a multibyte
        // string in printstr, used here for display output.
        CW2A printstr(ccombstr);
        cout << printstr << endl;
        // The following line of code is an easier way to
        // display wide character strings:
        wcout << (LPCWSTR) ccombstr << endl;
    }

    // Convert a wide wchar_t string to a multibyte CStringA,
    // append the type of string to it, and display the result.
    CStringA cstringa(orig);
    cstringa += " (CStringA)";
    cout << cstringa << endl;

    // Convert a wide character wchar_t string to a wide
    // character CStringW string and append the type of string to it
    CStringW cstring(orig);
    cstring += " (CStringW)";
    // To display a CStringW correctly, use wcout and cast cstring
    // to (LPCWSTR).
    wcout << (LPCWSTR)cstring << endl;

    // Convert the wide character wchar_t string to a
    // basic_string, append the type of string to it, and
    // display the result.
    wstring basicstring(orig);
    basicstring += _T(" (basic_string)");
    wcout << basicstring << endl;

    // Convert a wide character wchar_t string to a
    // System::String string, append the type of string to it,
    // and display the result.
    String ^systemstring = gcnew String(orig);
    systemstring += " (System::String)";
    Console::WriteLine("{0}", systemstring);
    delete systemstring;
}
```

```Output
Hello, World! (wchar_t *)
Hello, World! (char *)
Hello, World! (_bstr_t)
Hello, World! (CComBSTR)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (basic_string)
Hello, World! (System::String)
```

## <a name="converting-from-bstrt"></a>_Bstr_t에서 변환

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `_bstr_t` 위에 나열 된 다른 문자열 형식입니다. 합니다 `_bstr_t` 개체가 와이드 문자를 캡슐화 하는 방법을 `BSTR` 문자열입니다. BSTR 문자열 길이 값이 고, 문자열을 종결 null 문자를 사용 하지 않습니다 하지만 변환할 문자열 형식에 종결 null 필요할 수 있습니다.

### <a name="code"></a>코드

```cpp
// convert_from_bstr_t.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"

using namespace std;
using namespace System;

int main()
{
    // Create a _bstr_t string, display the result, and indicate the
    // type of string that it is.
    _bstr_t orig("Hello, World!");
    wcout << orig << " (_bstr_t)" << endl;

    // Convert the wide character _bstr_t string to a C style
    // string. To be safe, allocate two bytes for each character
    // in the char* string, including the terminating null.
    const size_t newsize = (orig.length()+1)*2;
    char *nstring = new char[newsize];

    // Uses the _bstr_t operator (char *) to obtain a null
    // terminated string from the _bstr_t object for
    // nstring.
    strcpy_s(nstring, newsize, (char *)orig);
    strcat_s(nstring, newsize, " (char *)");
    cout << nstring << endl;

    // Prepare the type of string to append to the result.
    wchar_t strConcat[] = _T(" (wchar_t *)");
    size_t strConcatLen = wcslen(strConcat) + 1;

    // Convert a _bstr_t to a wchar_t* string.
    const size_t widesize = orig.length()+ strConcatLen;
    wchar_t *wcstring = new wchar_t[newsize];
    wcscpy_s(wcstring, widesize, (wchar_t *)orig);
    wcscat_s(wcstring, widesize, strConcat);
    wcout << wcstring << endl;

    // Convert a _bstr_t string to a CComBSTR string.
    CComBSTR ccombstr((char *)orig);
    if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
    {
        CW2A printstr(ccombstr);
        cout << printstr << endl;
    }

    // Convert a _bstr_t to a CStringA string.
    CStringA cstringa(orig.GetBSTR());
    cstringa += " (CStringA)";
    cout << cstringa << endl;

    // Convert a _bstr_t to a CStringW string.
    CStringW cstring(orig.GetBSTR());
    cstring += " (CStringW)";
    // To display a cstring correctly, use wcout and
    // "cast" the cstring to (LPCWSTR).
    wcout << (LPCWSTR)cstring << endl;

    // Convert the _bstr_t to a basic_string.
    string basicstring((char *)orig);
    basicstring += " (basic_string)";
    cout << basicstring << endl;

    // Convert the _bstr_t to a System::String.
    String ^systemstring = gcnew String((char *)orig);
    systemstring += " (System::String)";
    Console::WriteLine("{0}", systemstring);
    delete systemstring;
}
```

```Output
Hello, World! (_bstr_t)
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (CComBSTR)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (basic_string)
Hello, World! (System::String)
```

## <a name="converting-from-ccombstr"></a>CComBSTR에서 변환

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `CComBSTR` 위에 나열 된 다른 문자열 형식입니다. _Bstr_t와 마찬가지로 `CComBSTR` 개체가 와이드 문자 BSTR 문자열을 캡슐화 할 수 있습니다. BSTR 문자열 길이 값이 고, 문자열을 종결 null 문자를 사용 하지 않습니다 하지만 변환할 문자열 형식에 종결 null 필요할 수 있습니다.

### <a name="code"></a>코드

```cpp
// convert_from_ccombstr.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"
#include "vcclr.h"

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

int main()
{
    // Create and initialize a BSTR string by using a CComBSTR object.
    CComBSTR orig("Hello, World!");
    // Convert the BSTR into a multibyte string, display the result,
    // and indicate the type of string that it is.
    CW2A printstr(orig);
    cout << printstr << " (CComBSTR)" << endl;

    // Convert a wide character CComBSTR string to a
    // regular multibyte char* string. Allocate enough space
    // in the new string for the largest possible result,
    // including space for a terminating null.
    const size_t newsize = (orig.Length()+1)*2;
    char *nstring = new char[newsize];

    // Create a string conversion object, copy the result to
    // the new char* string, and display the result.
    CW2A tmpstr1(orig);
    strcpy_s(nstring, newsize, tmpstr1);
    cout << nstring << " (char *)" << endl;

    // Prepare the type of string to append to the result.
    wchar_t strConcat[] = _T(" (wchar_t *)");
    size_t strConcatLen = wcslen(strConcat) + 1;

    // Convert a wide character CComBSTR string to a wchar_t*.
    // The code first determines the length of the converted string
    // plus the length of the appended type of string, then
    // prepares the final wchar_t string for display.
    const size_t widesize = orig.Length()+ strConcatLen;
    wchar_t *wcstring = new wchar_t[widesize];
    wcscpy_s(wcstring, widesize, orig);
    wcscat_s(wcstring, widesize, strConcat);

    // Display the result. Unlike CStringW, a wchar_t does not need
    // a cast to (LPCWSTR) with wcout.
    wcout << wcstring << endl;

    // Convert a wide character CComBSTR to a wide character _bstr_t,
    // append the type of string to it, and display the result.
    _bstr_t bstrt(orig);
    bstrt += " (_bstr_t)";
    cout << bstrt << endl;

    // Convert a wide character CComBSTR to a multibyte CStringA,
    // append the type of string to it, and display the result.
    CStringA cstringa(orig);
    cstringa += " (CStringA)";
    cout << cstringa << endl;

    // Convert a wide character CComBSTR to a wide character CStringW.
    CStringW cstring(orig);
    cstring += " (CStringW)";
    // To display a cstring correctly, use wcout and cast cstring
    // to (LPCWSTR).
    wcout << (LPCWSTR)cstring << endl;

    // Convert a wide character CComBSTR to a wide character
    // basic_string.
    wstring basicstring(orig);
    basicstring += _T(" (basic_string)");
    wcout << basicstring << endl;

    // Convert a wide character CComBSTR to a System::String.
    String ^systemstring = gcnew String(orig);
    systemstring += " (System::String)";
    Console::WriteLine("{0}", systemstring);
    delete systemstring;
}
```

```Output
Hello, World! (CComBSTR)
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (_bstr_t)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (basic_string)
Hello, World! (System::String)
```

## <a name="converting-from-cstring"></a>CString에서 변환

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `CString` 위에 나열 된 다른 문자열 형식입니다. `CString` 기반에 있는지 여부에 따라 달라 지는 TCHAR 데이터 형식으로 기호 `_UNICODE` 정의 됩니다. 하는 경우 `_UNICODE` 정의 되어 있지 `TCHAR` char로 정의 됩니다 및 `CString` 경우 멀티 바이트 문자 문자열을 포함 `_UNICODE` 정의 된 `TCHAR` 다음과 같이 정의 됩니다 `wchar_t` 및 `CString` 와이드 문자를 포함 합니다. 문자열입니다.

`CStringA` 멀티 바이트 문자열 전용 버전이 `CString`, `CStringW` 와이드 문자열 전용 버전입니다. 모두 `CStringA` 나 `CStringW` 사용 하 여 `_UNICODE` 컴파일 방식을 확인 하려면. `CStringA` 및 `CStringW` 이 예제의 버퍼 크기 할당에 약간의 차이가 분명히 설명 하 고 처리를 출력 하는 데 사용 됩니다.

### <a name="code"></a>코드

```cpp
// convert_from_cstring.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"

using namespace std;
using namespace System;

int main()
{
    // Set up a multibyte CStringA string.
    CStringA origa("Hello, World!");
    cout << origa << " (CStringA)" << endl;
```

```cpp
// Set up a wide character CStringW string.
CStringW origw("Hello, World!");
wcout << (LPCWSTR)origw << _T(" (CStringW)") << endl;

// Convert to a char* string from CStringA string
// and display the result.
const size_t newsizea = (origa.GetLength() + 1);
char *nstringa = new char[newsizea];
strcpy_s(nstringa, newsizea, origa);
cout << nstringa << " (char *)" << endl;

// Convert to a char* string from a wide character
// CStringW string. To be safe, we allocate two bytes for each
// character in the original string, including the terminating
// null.
const size_t newsizew = (origw.GetLength() + 1)*2;
char *nstringw = new char[newsizew];
size_t convertedCharsw = 0;
wcstombs_s(&convertedCharsw, nstringw, newsizew, origw, _TRUNCATE );
cout << nstringw << " (char *)" << endl;

// Convert to a wchar_t* from CStringA
size_t convertedCharsa = 0;
wchar_t *wcstring = new wchar_t[newsizea];
mbstowcs_s(&convertedCharsa, wcstring, newsizea, origa, _TRUNCATE);
wcout << wcstring << _T(" (wchar_t *)") << endl;

// Convert to a wide character wchar_t* string from
// a wide character CStringW string.
wchar_t *n2stringw = new wchar_t[newsizew];
wcscpy_s( n2stringw, newsizew, origw );
wcout << n2stringw << _T(" (wchar_t *)") << endl;

// Convert to a wide character _bstr_t string from
// a multibyte CStringA string.
_bstr_t bstrt(origa);
bstrt += _T(" (_bstr_t)");
wcout << bstrt << endl;

// Convert to a wide character_bstr_t string from
// a wide character CStringW string.
bstr_t bstrtw(origw);
bstrtw += " (_bstr_t)";
wcout << bstrtw << endl;

// Convert to a wide character CComBSTR string from
// a multibyte character CStringA string.
CComBSTR ccombstr(origa);
if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
{
    // Convert the wide character string to multibyte
    // for printing.
    CW2A printstr(ccombstr);
    cout << printstr << endl;
}

// Convert to a wide character CComBSTR string from
// a wide character CStringW string.
CComBSTR ccombstrw(origw);
// Append the type of string to it, and display the result.

if (ccombstrw.Append(_T(" (CComBSTR)")) == S_OK)
{
    CW2A printstrw(ccombstrw);
    wcout << printstrw << endl;
}

// Convert a multibyte character CStringA to a
// multibyte version of a basic_string string.
string basicstring(origa);
basicstring += " (basic_string)";
cout << basicstring << endl;

// Convert a wide character CStringW to a
// wide character version of a basic_string
// string.
wstring basicstringw(origw);
basicstringw += _T(" (basic_string)");
wcout << basicstringw << endl;

// Convert a multibyte character CStringA to a
// System::String.
String ^systemstring = gcnew String(origa);
systemstring += " (System::String)";
Console::WriteLine("{0}", systemstring);
delete systemstring;
```

```cpp
    // Convert a wide character CStringW to a
    // System::String.
    String ^systemstringw = gcnew String(origw);
    systemstringw += " (System::String)";
    Console::WriteLine("{0}", systemstringw);
    delete systemstringw;
}
```

```Output
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (char *)
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (wchar_t *)
Hello, World! (_bstr_t)
Hello, World! (_bstr_t)
Hello, World! (CComBSTR)
Hello, World! (CComBSTR)
Hello, World! (basic_string)
Hello, World! (System::String)
```

## <a name="converting-from-basicstring"></a>Basic_string에서 변환

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서 변환 하는 방법을 보여 줍니다는 `basic_string` 위에 나열 된 다른 문자열 형식입니다.

### <a name="code"></a>코드

```cpp
// convert_from_basic_string.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"

using namespace std;
using namespace System;

int main()
{
    // Set up a basic_string string.
    string orig("Hello, World!");
    cout << orig << " (basic_string)" << endl;

    // Convert a wide char basic_string string to a multibyte char*
    // string. To be safe, we allocate two bytes for each character
    // in the original string, including the terminating null.
    const size_t newsize = (strlen(orig.c_str()) + 1)*2;
    char *nstring = new char[newsize];
    strcpy_s(nstring, newsize, orig.c_str());
    cout << nstring << " (char *)" << endl;

    // Convert a basic_string string to a wide character
    // wchar_t* string. You must first convert to a char*
    // for this to work.
    const size_t newsizew = strlen(orig.c_str()) + 1;
    size_t convertedChars = 0;
    wchar_t *wcstring = new wchar_t[newsizew];
    mbstowcs_s(&convertedChars, wcstring, newsizew, orig.c_str(), _TRUNCATE);
    wcout << wcstring << _T(" (wchar_t *)") << endl;

    // Convert a basic_string string to a wide character
    // _bstr_t string.
    _bstr_t bstrt(orig.c_str());
    bstrt += _T(" (_bstr_t)");
    wcout << bstrt << endl;

    // Convert a basic_string string to a wide character
    // CComBSTR string.
    CComBSTR ccombstr(orig.c_str());
    if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
    {
        // Make a multibyte version of the CComBSTR string
        // and display the result.
        CW2A printstr(ccombstr);
        cout << printstr << endl;
    }

    // Convert a basic_string string into a multibyte
    // CStringA string.
    CStringA cstring(orig.c_str());
    cstring += " (CStringA)";
    cout << cstring << endl;

    // Convert a basic_string string into a wide
    // character CStringW string.
    CStringW cstringw(orig.c_str());
    cstringw += _T(" (CStringW)");
    wcout << (LPCWSTR)cstringw << endl;

    // Convert a basic_string string to a System::String
    String ^systemstring = gcnew String(orig.c_str());
    systemstring += " (System::String)";
    Console::WriteLine("{0}", systemstring);
    delete systemstring;
}
```

```Output
Hello, World! (basic_string)
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (_bstr_t)
Hello, World! (CComBSTR)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (System::String)
```

## <a name="converting-from-systemstring"></a>System:: string에서 변환

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예제에서는 와이드 문자 (유니코드)에서 변환 하는 방법을 보여 줍니다 [system:: string](assetId:///System::String?qualifyHint=True&autoUpgrade=True) 위에 나열 된 다른 문자열 형식입니다.

### <a name="code"></a>코드

```cpp
// convert_from_system_string.cpp
// compile with: /clr /link comsuppw.lib

#include <iostream>
#include <stdlib.h>
#include <string>

#include "atlbase.h"
#include "atlstr.h"
#include "comutil.h"
#include "vcclr.h"

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

int main()
{
    // Set up a System::String and display the result.
    String ^orig = gcnew String("Hello, World!");
    Console::WriteLine("{0} (System::String)", orig);

    // Obtain a pointer to the System::String in order to
    // first lock memory into place, so that the
    // Garbage Collector (GC) cannot move that object
    // while we call native functions.
    pin_ptr<const wchar_t> wch = PtrToStringChars(orig);

    // Make a copy of the system string as a multibyte
    // char* string. Allocate two bytes in the multibyte
    // output string for every wide character in the input
    // string, including space for a terminating null.
    size_t origsize = wcslen(wch) + 1;
    const size_t newsize = origsize*2;
    size_t convertedChars = 0;
    char *nstring = new char[newsize];
    wcstombs_s(&convertedChars, nstring, newsize, wch, _TRUNCATE);
    cout << nstring << " (char *)" << endl;

    // Convert a wide character system string to a
    // wide character wchar_t* string.
    const size_t newsizew = origsize;
    wchar_t *wcstring = new wchar_t[newsizew];
    wcscpy_s(wcstring, newsizew, wch);
    wcout << wcstring << _T(" (wchar_t *)") << endl;

    // Convert a wide character system string to a
    // wide character _bstr_t string.
    _bstr_t bstrt(wch);
    bstrt += " (_bstr_t)";
    cout << bstrt << endl;

    // Convert a wide character system string
    // to a wide character CComBSTR string.
    CComBSTR ccombstr(wch);
    if (ccombstr.Append(_T(" (CComBSTR)")) == S_OK)
    {
        // Make a multibyte copy of the CComBSTR string
        // and display the result.
        CW2A printstr(ccombstr);
        cout << printstr << endl;
    }

    // Convert a wide character System::String to
    // a multibyte CStringA string.
    CStringA cstring(wch);
    cstring += " (CStringA)";
    cout << cstring << endl;

    // Convert a wide character System::String to
    // a wide character CStringW string.
    CStringW cstringw(wch);
    cstringw += " (CStringW)";
    wcout << (LPCWSTR)cstringw << endl;

    // Convert a wide character System::String to
    // a wide character basic_string.
    wstring basicstring(wch);
    basicstring += _T(" (basic_string)");
    wcout << basicstring << endl;

    delete orig;
}
```

```Output
Hello, World! (System::String)
Hello, World! (char *)
Hello, World! (wchar_t *)
Hello, World! (_bstr_t)
Hello, World! (CComBSTR)
Hello, World! (CStringA)
Hello, World! (CStringW)
Hello, World! (basic_string)
```

## <a name="see-also"></a>참고 항목

[ATL 및 MFC 문자열 변환 매크로](../atl/reference/string-conversion-macros.md)<br/>
[C 스타일 문자열 관련 CString 작업](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
[방법: 표준 문자열을 System::String으로 변환](../dotnet/how-to-convert-standard-string-to-system-string.md)<br/>
[방법: System::String을 표준 문자열로 변환](../dotnet/how-to-convert-system-string-to-standard-string.md)<br/>
[방법: system:: string을 wchar_t * 또는 char 변환할\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)<br/>
[CComBSTR을 사용한 프로그래밍](../atl/programming-with-ccombstr-atl.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)<br/>
[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcat_s, wcscat_s, _mbscat_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)<br/>
[pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)
