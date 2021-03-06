---
title: "ostreambuf_iterator 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
dev_langs:
- C++
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 695b8415cd5958d200ba9120e28bebd543614f24
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator 클래스
템플릿 클래스 ostreambuf_iterator는 연속 문자 요소를 추출 **operator>>**가 포함된 출력 스트림에 쓰는 출력 반복기 개체에 대해 설명합니다. `ostreambuf_iterator`는 출력 스트림에 삽입하는 개체 형식이 제네릭 형식이 아닌 문자이라는 점에서 [ostream_iterator 클래스](../standard-library/ostream-iterator-class.md)와 다릅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType = char class Traits = char_traits <CharType>>
```  
  
#### <a name="parameters"></a>매개 변수  
 `CharType`  
 ostreambuf_iterator의 문자 형식을 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `char`입니다.  
  
 `Traits`  
 ostreambuf_iterator의 문자 형식을 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `char_traits`\< *CharType>입니다.*  
  
## <a name="remarks"></a>설명  
 ostreambuf_iterator 클래스는 출력 반복기에 대한 요구 사항을 충족해야 합니다. 알고리즘은 `ostreambuf_iterator`를 사용하여 출력 스트림에 직접 쓸 수 있습니다. 이 클래스에서는 문자의 형태로 원시(서식이 지정되지 않은) I/O 스트림 액세스를 허용하는 낮은 수준의 스트림 반복기를 제공하고 버퍼링을 우회할 수 있으며 높은 수준의 스트림 반복기에서 나타나는 문자 변환이 없습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|출력 스트림으로 문자를 쓰도록 초기화된 `ostreambuf_iterator`를 구성합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[char_type](#char_type)|`ostreambuf_iterator`의 문자 형식을 허용하는 형식입니다.|  
|[ostream_type](#ostreambuf_iterator_ostream_type)|`ostream_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[streambuf_type](#streambuf_type)|`ostreambuf_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[traits_type](#traits_type)|`ostream_iterator`의 특성 형식을 허용하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[failed](#failed)|출력 스트림 버퍼에 대한 삽입 실패를 테스트합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator*](#op_star)|출력 반복기 식 * `i` = `x`을 구현하는 데 사용된 역참조 연산자.|  
|[operator++](#op_add_add)|연산이 호출되기 전에 주소 지정한 동일한 개체에 `ostreambuf_iterator`를 반환한 비함수 증분 연산자.|  
|[operator=](#op_eq)|연산자가 연결된 스트림 버퍼에 문자를 삽입합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<iterator>  
  
 **네임스페이스:** std  
  
##  <a name="char_type"></a>  ostreambuf_iterator::char_type  
 `ostreambuf_iterator`의 문자 형식을 허용하는 형식입니다.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **CharType**의 동의어입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
##  <a name="failed"></a>  ostreambuf_iterator::failed  
 출력 스트림 버퍼에 대한 삽입 실패를 테스트합니다.  
  
```
bool failed() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 멤버 함수는 출력 스트림 버퍼에 대한 삽입이 이전에 실패하지 않은 경우 **true**를 반환하고 그렇지 않으면 **false**를 반환합니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 이전에 구성원 `operator=`를 사용할 때 **subf**_-> `sputc` 호출에서 **eof**가 반환된 경우 **true**를 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_failed.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'a';  
   charOut ++;  
 *charOut  = 'b';  
   charOut ++;     
 *charOut = 'c';  
   cout << " are characters output individually." << endl;  
  
   bool b1 = charOut.failed ( );  
   if (b1)   
       cout << "At least one insertion failed." << endl;  
   else  
       cout << "No insertions failed." << endl;  
}  
\* Output:   
abc are characters output individually.  
No insertions failed.  
*\  
```  
  
##  <a name="op_star"></a>  ostreambuf_iterator::operator*  
 출력 반복기 식 \* *i* = *x*를 구현하는 데 사용되는 작동하지 않는 역참조 연산자입니다.  
  
```
ostreambuf_iterator<CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>반환 값  
 ostreambuf 반복기 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는 스트림 버퍼로 문자를 출력하기 위한 출력 반복기 식 \* *i* = *x*에서만 작동합니다. ostreambut 반복기에 적용하는 경우 반복기가 반환되며 **\*iter**에서는 **iter**을 반환합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;   // no effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';  
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_add_add"></a>  ostreambuf_iterator::operator++  
 연산이 호출되기 전에 주소 지정한 동일한 문자에 대한 ostream 반복기를 반환하는 작동하지 않는 증분 연산자입니다.  
  
```
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```  
  
### <a name="return-value"></a>반환 값  
 `ostreambuf_iterator`\< **CharType**, **Traits**>로 변환할 수 있는 구현에서 정의된 개체 또는 원래 주소 지정된 문자에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 연산자는 출력 반복기 식 \* *i* = *x*를 구현하는 데 사용됩니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_eq"></a>  ostreambuf_iterator::operator=  
 연산자가 연결된 스트림 버퍼에 문자를 삽입합니다.  
  
```
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Char`  
 스트림 버퍼에 삽입할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 스트림 버퍼에 삽입되는 문자에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 출력 스트림에 쓰기 위해 출력 반복기 식 \* *i* = *x*를 구현하는 데 사용된 할당 연산자입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator  
 출력 스트림으로 문자를 쓰도록 초기화된 `ostreambuf_iterator`를 구성합니다.  
  
```
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `strbuf`  
 출력 스트림 버퍼 포인터를 초기화하는 데 사용되는 출력 streambuf 개체입니다.  
  
 `Ostr`  
 출력 스트림 버퍼 포인터를 초기화하는 데 사용되는 출력 stream 개체입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 `strbuf`로 출력 스트림 버퍼 포인터를 초기화합니다.  
  
 두 번째 생성자는 `Ostr`로 출력 스트림 버퍼 포인터를 초기화합니다. `rdbuf`. 저장된 포인터는 null 포인터가 아니어야 합니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iteratorOstreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'O';  
   charOut ++;  
 *charOut  = 'U';  
   charOut ++;     
 *charOut = 'T';  
   cout << " are characters output individually." << endl;  
  
   ostreambuf_iterator<char> strOut ( cout );  
   string str = "These characters are being written to the output stream.\n ";  
   copy ( str.begin ( ), str. end ( ), strOut );  
}  
\* Output:   
OUT are characters output individually.  
These characters are being written to the output stream.  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type  
 `ostream_iterator`의 스트림 형식을 허용하는 형식입니다.  
  
```
typedef basicOstream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `basicOstream`\< **CharType**, **Traits**>와 동일한 의미입니다.  
  
### <a name="example"></a>예  
  `ostream_type`을 선언하고 사용하는 방법의 예제는 [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)를 참조하세요.  
  
##  <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type  
 `ostreambuf_iterator`의 스트림 형식을 허용하는 형식입니다.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 문자 형식 `char`로 특수화하면 `streambuf`가 되는 I/O 버퍼에 대한 스트림 클래스인 `basic_streambuf`\< **CharType**, **Traits**>와 동일한 의미입니다.  
  
### <a name="example"></a>예  
  `streambuf_type`을 선언하고 사용하는 방법의 예제는 [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)를 참조하세요.  
  
##  <a name="traits_type"></a>  ostreambuf_iterator::traits_type  
 `ostream_iterator`의 특성 형식을 허용하는 형식입니다.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 **Traits**와 동일한 의미입니다.  
  
### <a name="example"></a>예  
  
```cpp  
// ostreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)



