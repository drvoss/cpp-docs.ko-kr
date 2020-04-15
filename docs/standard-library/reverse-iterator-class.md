---
title: reverse_iterator 클래스
ms.date: 03/27/2019
f1_keywords:
- xutility/std::reverse_iterator
- iterator/std::reverse_iterator::difference_type
- iterator/std::reverse_iterator::iterator_type
- iterator/std::reverse_iterator::pointer
- iterator/std::reverse_iterator::reference
- iterator/std::reverse_iterator::base
- iterator/std::reverse_iterator::operator_star
helpviewer_keywords:
- std::reverse_iterator [C++]
- std::reverse_iterator [C++], difference_type
- std::reverse_iterator [C++], iterator_type
- std::reverse_iterator [C++], pointer
- std::reverse_iterator [C++], reference
- std::reverse_iterator [C++], base
- std::reverse_iterator [C++], operator_star
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
ms.openlocfilehash: 882d0f7f4930e9d809098a29384a962d0aa8f4ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373431"
---
# <a name="reverse_iterator-class"></a>reverse_iterator 클래스

클래스 템플릿은 역방향 액세스 또는 양방향 이터레이터처럼 작동되는 역방향 이터레이터 개체를 역방향으로만 설명하는 이터레이터 어댑터입니다. 범위를 뒤로 이동할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class RandomIterator>
class reverse_iterator
```

### <a name="parameters"></a>매개 변수

RandomIterator 반대로 작동하도록 조정될 것을 상기를 나타내는 형식입니다.

## <a name="remarks"></a>설명

기존 C++ 표준 라이브러리에는 `reverse_iterator` 및 `const_reverse_iterator` 형식이 정의되어 있으며 역방향 반복기를 반환하는 구성원 함수 `rbegin` 및 `rend`가 있습니다. 이러한 반복기는 덮어쓰기 의미 체계가 있습니다. 어댑터는 `reverse_iterator` 삽입 의미체계를 제공하고 스트림에서도 사용할 수 있으므로 이 기능을 보완합니다.

양방향 `reverse_iterator` 이터레이터가 필요한 것은 임의 액세스 이터레이터에서만 `operator+=` `operator+`사용할 `operator-=` `operator-`수 `operator[]`있는 멤버 함수 , 또는

반복기의 범위는 *[첫 번째,* *last*마지막)]이며, 왼쪽의 대괄호는 *첫 번째* 대괄호가 포함됨을 나타내고 오른쪽에 괄호는 최대 요소포함을 나타내지만 *마지막* 자체는 제외합니다. 동일한*first* 엘리먼트가 역전 시퀀스 **[rev** - *first*, **rev** - *last)에*포함되므로 *마지막이* 시퀀스의 한-과거-종단 요소인 경우, 다음 첫 번째 엘리먼트는 **rev** - 먼저 역순시퀀스 포인트(last-1)를*last* \*가리킵니다. 모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.

&\***(reverse_iterator** *(i)* ) \*= = &*(i* - 1).

실제로, 역방향 시퀀스에서 reverse_iterator는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[reverse_iterator](#reverse_iterator)|기본 반복기에서 기본 `reverse_iterator` 또는 `reverse_iterator`를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[difference_type](#difference_type)|동일한 컨테이너 안에서 요소를 참조하는 두 `reverse_iterator` 사이의 차이를 제공하는 형식입니다.|
|[iterator_type](#iterator_type)|`reverse_iterator`의 기본 반복기를 제공하는 형식입니다.|
|[포인터(pointer)](#pointer)|`reverse_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.|
|[참조](#reference)|`reverse_iterator`로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[base](#base)|`reverse_iterator`에서 기본 반복기를 복구합니다.|

### <a name="operators"></a>연산자

|연산자|Description|
|-|-|
|[operator_star](#op_star)|`reverse_iterator`가 주소 지정하는 요소를 반환합니다.|
|[연산자+](#op_add)|반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.|
|[연산자++](#op_add_add)|`reverse_iterator`를 다음 요소로 증가시킵니다.|
|[연산자+=](#op_add_eq)|`reverse_iterator`에서 지정된 오프셋을 추가합니다.|
|[연산자-](#operator-)|`reverse_iterator`에서 오프셋을 차감하고 오프셋 위치에서 요소를 주소 지정하는 `reverse_iterator`를 반환합니다.|
|[연산자-](#operator--)|`reverse_iterator`를 이전 요소로 감소시킵니다.|
|[연산자-=](#operator-_eq)|`reverse_iterator`에서 지정된 오프셋을 차감합니다.|
|[연산자 >](#op-arrow)|`reverse_iterator`가 주소 지정하는 요소로 포인터를 반환합니다.|
|[operator&#91;&#93;](#op_at)|`reverse_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<iterator>

**네임스페이스:** std

## <a name="reverse_iteratorbase"></a><a name="base"></a>reverse_iterator::베이스

`reverse_iterator`에서 기본 반복기를 복구합니다.

```cpp
RandomIterator base() const;
```

### <a name="return-value"></a>Return Value

`reverse_iterator`의 기본이 되는 반복기입니다.

### <a name="remarks"></a>설명

모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.

&\*(((i) `reverse_iterator` ) \*= = &*(i* - 1). *i*

실제로, 역방향 시퀀스에서 `reverse_iterator`는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_base.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos, bpos;
   pos = find ( vec.begin ( ), vec.end ( ), 6 );
   cout << "The iterator pos points to: " << *pos << "." << endl;

   typedef reverse_iterator<vector<int>::iterator>::iterator_type it_vec_int_type;

   reverse_iterator<it_vec_int_type> rpos ( pos );
   cout << "The reverse_iterator rpos points to: " << *rpos
        << "." << endl;

   bpos = rpos.base ( );
   cout << "The iterator underlying rpos is bpos & it points to: "
        << *bpos << "." << endl;
}
```

## <a name="reverse_iteratordifference_type"></a><a name="difference_type"></a>reverse_iterator::d리프런스_타입

동일한 컨테이너 안에서 요소를 참조하는 두 `reverse_iterator` 사이의 차이를 제공하는 형식입니다.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type;
```

### <a name="remarks"></a>설명

`reverse_iterator` 차이 형식은 반복기 차이 형식과 같습니다.

형식은 이터레이터 특성 `iterator_traits` \< **[randomiterator::pointer**> **::pointer**.)의 동의어입니다.

### <a name="example"></a>예제

`difference_type`을 선언하고 사용하는 방법의 예제는 [reverse_iterator::operator&#91;&#93;](#op_at)를 참조하세요.

## <a name="reverse_iteratoriterator_type"></a><a name="iterator_type"></a>reverse_iterator:iterator_type

`reverse_iterator`의 기본 반복기를 제공하는 형식입니다.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Iterator`의 동의어입니다.

### <a name="example"></a>예제

`iterator_type`을 선언하고 사용하는 방법의 예제는 [reverse_iterator::base](#base)를 참조하세요.

## <a name="reverse_iteratoroperator"></a><a name="op_star"></a>reverse_iterator::연산자\*

reverse_iterator가 주소를 지정하는 요소를 반환합니다.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Return Value

reverse_iterator에 의해 주소가 지정되는 요소값입니다.

### <a name="remarks"></a>설명

연산자가 \*반환합니다(현재 - 1). **current**

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_ref.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos, bpos;
   pos = find ( vec.begin ( ), vec.end ( ), 6 );

   // Declare a difference type for a parameter
   // declare a reference return type
   reverse_iterator<vector<int>::iterator>::reference refpos = *pos;
   cout << "The iterator pos points to: " << refpos << "." << endl;
}
```

## <a name="reverse_iteratoroperator"></a><a name="op_add"></a>reverse_iterator::연산자+

반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `reverse_iterator`를 반환합니다.

```cpp
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```

### <a name="parameters"></a>매개 변수

*꺼기*\
역방향 반복기에 추가할 오프셋입니다.

### <a name="return-value"></a>Return Value

오프셋 요소의 주소를 지정하는 `reverse_iterator`입니다.

### <a name="remarks"></a>설명

이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_add.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   vector <int>::reverse_iterator rVPOS2 =rVPOS1 + 2; // offset added
   cout << "After the +2 offset, the iterator rVPOS2 points\n"
        << " to the 3rd element in the reversed sequence: "
        << *rVPOS2 << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 10.
After the +2 offset, the iterator rVPOS2 points
to the 3rd element in the reversed sequence: 6.
```

## <a name="reverse_iteratoroperator"></a><a name="op_add_add"></a>reverse_iterator::연산자++

reverse_iterator를 이전 요소로 증가시킵니다.

```cpp
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```

### <a name="return-value"></a>Return Value

첫 번째 연산자는 사전 증가된 `reverse_iterator`를 반환하고, 두 번째(사후 증가) 연산자는 증가된 `reverse_iterator`의 복사본을 반환합니다.

### <a name="remarks"></a>설명

이 구성원 함수는 `reverse_iterator`가 양방향 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i - 1 );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1++;  // postincrement, preincrement: ++rVPSO1

   cout << "After incrementing, the iterator rVPOS1 points\n"
        << " to the second element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 1 3 5 7 9 ).
The vector vec reversed is: ( 9 7 5 3 1 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 9.
After incrementing, the iterator rVPOS1 points
to the second element in the reversed sequence: 7.
```

## <a name="reverse_iteratoroperator"></a><a name="op_add_eq"></a>reverse_iterator::연산자+=

reverse_iterator에서 지정된 오프셋을 추가합니다.

```cpp
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```

### <a name="parameters"></a>매개 변수

*꺼기*\
반복기를 증가시킬 오프셋입니다.

### <a name="return-value"></a>Return Value

`reverse_iterator`에서 주소를 지정한 요소에 대한 참조입니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_addoff.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1+=2;   // addition of an offset
   cout << "After the +2 offset, the iterator rVPOS1 now points\n"
        << " to the third element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 10.
After the +2 offset, the iterator rVPOS1 now points
to the third element in the reversed sequence: 6.
```

## <a name="reverse_iteratoroperator-"></a><a name="operator-"></a>reverse_iterator::연산자-

`reverse_iterator`에서 오프셋을 차감하고 오프셋 위치에서 요소를 주소 지정하는 `reverse_iterator`를 반환합니다.

```cpp
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```

### <a name="parameters"></a>매개 변수

*꺼기*\
reverse_iterator에서 뺄 오프셋입니다.

### <a name="return-value"></a>Return Value

오프셋 요소의 주소를 지정하는 `reverse_iterator`입니다.

### <a name="remarks"></a>설명

이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_sub.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 3 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   vector <int>::reverse_iterator rVPOS2 =rVPOS1 - 2; // offset subtracted
   cout << "After the -2 offset, the iterator rVPOS2 points\n"
        << " to the 2nd element from the last in the reversed sequence: "
        << *rVPOS2 << "." << endl;
}
```

```Output
The vector vec is: ( 3 6 9 12 15 ).
The vector vec reversed is: ( 15 12 9 6 3 ).
The iterator rVPOS1 initially points to the last element
in the reversed sequence: 3.
After the -2 offset, the iterator rVPOS2 points
to the 2nd element from the last in the reversed sequence: 9.
```

## <a name="reverse_iteratoroperator--"></a><a name="operator--"></a>reverse_iterator::연산자-

reverse_iterator를 이전 요소로 감소시킵니다.

```cpp
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```

### <a name="return-value"></a>Return Value

첫 번째 연산자는 사전 감소된 `reverse_iterator`를 반환하고, 두 번째(사후 감소) 연산자는 감소된 `reverse_iterator`의 복사본을 반환합니다.

### <a name="remarks"></a>설명

이 구성원 함수는 `reverse_iterator`가 양방향 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_decr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i - 1 );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;
   rVPOS1--;  // postdecrement, predecrement: --rVPSO1

   cout << "After the decrement, the iterator rVPOS1 points\n"
        << " to the next-to-last element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 1 3 5 7 9 ).
The vector vec reversed is: ( 9 7 5 3 1 ).
The iterator rVPOS1 initially points to the last element
in the reversed sequence: 1.
After the decrement, the iterator rVPOS1 points
to the next-to-last element in the reversed sequence: 3.
```

## <a name="reverse_iteratoroperator-"></a><a name="operator-_eq"></a>reverse_iterator::연산자-=

`reverse_iterator`에서 지정된 오프셋을 차감합니다.

```cpp
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```

### <a name="parameters"></a>매개 변수

*꺼기*\
`reverse_iterator`에서 뺄 오프셋입니다.

### <a name="remarks"></a>설명

이 구성원 함수는 `reverse_iterator`가 임의 액세스 반복기에 대한 요구 사항을 충족하는 경우에만 사용할 수 있습니다.

연산자는 **현재** + *Off를* 평가한 다음 ** \*이 을 반환합니다.**

### <a name="example"></a>예제

```cpp
// reverse_iterator_op_suboff.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 3 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1-=2;      // Subtraction of an offset
   cout << "After the -2 offset, the iterator rVPOS1 now points\n"
        << " to the 2nd element from the last in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 3 6 9 12 15 ).
The vector vec reversed is: ( 15 12 9 6 3 ).
The iterator rVPOS1 initially points to the last element
in the reversed sequence: 3.
After the -2 offset, the iterator rVPOS1 now points
to the 2nd element from the last in the reversed sequence: 9.
```

## <a name="reverse_iteratoroperator-gt"></a><a name="op-arrow"></a>reverse_iterator::연산자-&gt;

`reverse_iterator`가 주소 지정하는 요소로 포인터를 반환합니다.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Return Value

`reverse_iterator`에서 주소를 지정한 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

연산자가 ** & \* \*이 을**반환합니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_ptrto.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

int main( )
{
   using namespace std;

   typedef vector<pair<int,int> > pVector;
   pVector vec;
   vec.push_back(pVector::value_type(1,2));
   vec.push_back(pVector::value_type(3,4));
   vec.push_back(pVector::value_type(5,6));

   pVector::iterator pvIter;
   cout << "The vector vec of integer pairs is:\n( ";
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";
   cout << ")" << endl << endl;

   pVector::reverse_iterator rpvIter;
   cout << "The vector vec reversed is:\n( ";
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++ )
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";
   cout << ")" << endl << endl;

   pVector::iterator pos = vec.begin ( );
   pos++;
   cout << "The iterator pos points to:\n( " << pos -> first << ", "
   << pos -> second << " )" << endl << endl;

   pVector::reverse_iterator rpos (pos);

   // Use operator -> with return type: why type int and not int*
   int fint = rpos -> first;
   int sint = rpos -> second;

   cout << "The reverse_iterator rpos points to:\n( " << fint << ", "
   << sint << " )" << endl;
}
```

```Output
The vector vec of integer pairs is:
( ( 1, 2) ( 3, 4) ( 5, 6) )

The vector vec reversed is:
( ( 5, 6) ( 3, 4) ( 1, 2) )

The iterator pos points to:
( 3, 4 )

The reverse_iterator rpos points to:
( 1, 2 )
```

## <a name="reverse_iteratoroperator"></a><a name="op_at"></a>reverse_iterator::연산자[]

`reverse_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.

```cpp
reference operator[](difference_type Off) const;
```

### <a name="parameters"></a>매개 변수

*꺼기*\
`reverse_iterator` 주소의 오프셋입니다.

### <a name="return-value"></a>Return Value

요소 오프셋에 대한 참조입니다.

### <a name="remarks"></a>설명

연산자가 <strong>\*</strong>반환합니다(이). ** \*** + `Off`

### <a name="example"></a>예제

```cpp
// reverse_iterator_ret_ref.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos;
   pos = find ( vec.begin ( ), vec.end ( ), 8 );
   reverse_iterator<vector<int>::iterator> rpos ( pos );

   // Declare a difference type for a parameter
   reverse_iterator<vector<int>::iterator>::difference_type diff = 2;

   cout << "The iterator pos points to: " << *pos << "." << endl;
   cout << "The iterator rpos points to: " << *rpos << "." << endl;

   // Declare a reference return type & use operator[]
   reverse_iterator<vector<int>::iterator>::reference refrpos = rpos [diff];
   cout << "The iterator rpos now points to: " << refrpos << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator pos points to: 8.
The iterator rpos points to: 6.
The iterator rpos now points to: 2.
```

## <a name="reverse_iteratorpointer"></a><a name="pointer"></a>reverse_iterator::p

`reverse_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.

```cpp
typedef typename iterator_traits<RandomIterator>::pointer pointer;
```

### <a name="remarks"></a>설명

형식은 이터레이터 특성 `iterator_traits` \< *[randomiterator::pointer*> **::pointer**.)의 동의어입니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_pointer.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

int main( )
{
   using namespace std;

   typedef vector<pair<int,int> > pVector;
   pVector vec;
   vec.push_back( pVector::value_type( 1,2 ) );
   vec.push_back( pVector::value_type( 3,4 ) );
   vec.push_back( pVector::value_type( 5,6 ) );

   pVector::iterator pvIter;
   cout << "The vector vec of integer pairs is:\n" << "( ";
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";
   cout << ")" << endl;

   pVector::reverse_iterator rpvIter;
   cout << "\nThe vector vec reversed is:\n" << "( ";
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++)
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";
   cout << ")" << endl;

   pVector::iterator pos = vec.begin ( );
   pos++;
   cout << "\nThe iterator pos points to:\n"
        << "( " << pos -> first << ", "
        << pos -> second << " )" << endl;

   pVector::reverse_iterator rpos (pos);
   cout << "\nThe iterator rpos points to:\n"
        << "( " << rpos -> first << ", "
        << rpos -> second << " )" << endl;
}
```

```Output
The vector vec of integer pairs is:
( ( 1, 2) ( 3, 4) ( 5, 6) )

The vector vec reversed is:
( ( 5, 6) ( 3, 4) ( 1, 2) )

The iterator pos points to:
( 3, 4 )

The iterator rpos points to:
( 1, 2 )
```

## <a name="reverse_iteratorreference"></a><a name="reference"></a>reverse_iterator::참조

reverse_iterator로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.

```cpp
typedef typename iterator_traits<RandomIterator>::reference reference;
```

### <a name="remarks"></a>설명

형식은 이터레이터 특성 형기 `iterator_traits` \< 이름 *RandomIterator*> **::reference의**동의어입니다.

### <a name="example"></a>예제

[reverse_iterator::연산자&#91;&#93;](#op_at) 또는 [reverse_iterator::operator*를](#op_star) 선언하고 `reference`사용하는 방법에 대한 예제를 참조하십시오.

## <a name="reverse_iteratorreverse_iterator"></a><a name="reverse_iterator"></a>reverse_iterator:reverse_iterator

기본 반복기에서 기본 `reverse_iterator` 또는 `reverse_iterator`를 생성합니다.

```cpp
reverse_iterator();
explicit reverse_iterator(RandomIterator right);

template <class Type>
reverse_iterator(const reverse_iterator<Type>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`reverse_iterator`로 조정할 반복기입니다.

### <a name="return-value"></a>Return Value

기본 반복기를 조정하는 기본 `reverse_iterator` 또는 `reverse_iterator`입니다.

### <a name="remarks"></a>설명

모든 역방향 반복기를 기본 역방향과 연결하는 ID는 다음과 같습니다.

&\*(((i) `reverse_iterator` ) \*= = &*(i* - 1). *i*

실제로, 역방향 시퀀스에서 reverse_iterator는 반복기가 원래 시퀀스에서 참조한 요소에서 하나 다음의(오른쪽으로) 요소를 참조함을 의미합니다. 따라서 반복기가 시퀀스(2, 4, 6, 8)에서 요소 6을 주소 지정한 경우 `reverse_iterator`는 역방향 시퀀스(8, 6, 4, 2)에서 요소 4를 주소 지정합니다.

### <a name="example"></a>예제

```cpp
// reverse_iterator_reverse_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos;
   pos = find ( vec.begin ( ), vec.end ( ), 4 );
   cout << "The iterator pos = " << *pos << "." << endl;

   vector <int>::reverse_iterator rpos ( pos );
   cout << "The reverse_iterator rpos = " << *rpos
        << "." << endl;
}
```

## <a name="see-also"></a>참고 항목

[\<>](../standard-library/iterator.md)\
[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
