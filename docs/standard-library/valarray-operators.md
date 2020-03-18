---
title: '&lt;valarray&gt; 연산자'
ms.date: 03/27/2019
f1_keywords:
- valarray/std::operator!=
- valarray/std::operator%
- valarray/std::operator&amp;
- valarray/std::operator&amp;&amp;
- valarray/std::operator&gt;
- valarray/std::operator&gt;&gt;
- valarray/std::operator&gt;=
- valarray/std::operator&lt;
- valarray/std::operator&lt;&lt;
- valarray/std::operator&lt;=
- valarray/std::operator*
- valarray/std::operator+
- valarray/std::operator-
- valarray/std::operator/
- valarray/std::operator==
- valarray/std::operator^
- valarray/std::operator|
- valarray/std::operator||
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: 231bad65e2af1ee2ab800890c83cc50e584a8c6a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427586"
---
# <a name="ltvalarraygt-operators"></a>&lt;valarray&gt; 연산자

## <a name="op_neq"></a> operator!=

크기가 같은 두 valarray의 해당 요소가 서로 같지 않은지 또는 valarray의 모든 요소가 지정된 값과 같지 않은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator!=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소가 같지 않은지 테스트할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소가 같지 않은지 테스트할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- 해당 요소가 같지 않은 경우 **true**

- 해당 요소가 같은 경우 **false**

### <a name="remarks"></a>설명

첫 번째 템플릿 연산자는 각 `I` 요소가 `left[I] != right[I]`인 [valarray\<bool >](../standard-library/valarray-bool-class.md)의 개체를 반환 합니다.

두 번째 템플릿 연산자는 요소 `I` `left[I] != right`에 저장 합니다.

세 번째 템플릿 연산자는 요소 `I` `left != right[I]`에 저장 합니다.

### <a name="example"></a>예제

```cpp
// valarray_op_ne.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL != vaR );
   cout << "The element-by-element result of "
        << "the not equal comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="op_mod"></a>연산자

크기가 같은 두 valarray의 해당 요소를 나눈 나머지 또는 valarray를 지정된 값으로 나누거나 지정된 값을 valarray로 나눈 나머지를 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator%(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
다른 값이나 valarray를 나눌 피제수로 사용되는 값 또는 valarray입니다.

*오른쪽*\
다른 값이나 valarray를 나누는 제수로 사용되는 값 또는 valarray입니다.

### <a name="return-value"></a>Return Value

해당 요소를 *왼쪽* 에서 *오른쪽*으로 나눈 요소가 있는 valarray입니다.

### <a name="example"></a>예제

```cpp
// valarray_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   valarray<int> vaREM ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaREM = ( vaL % vaR );
   cout << "The remainders from the element-by-element "
        << "division is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
```

## <a name="op_amp"></a> 연산자&amp;

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 요소 형식의 지정된 값 간에 비트 **AND**를 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개별 요소를 비트 `AND`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
개별 요소를 비트 `AND`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

해당 요소가 *left* 및 *RIGHT*의 비트 and 연산의 요소 전체 조합인 valarray입니다.

### <a name="remarks"></a>설명

비트 연산은 **char** 및 **int** 데이터 형식 및 variant의 비트를 조작 하는 데만 사용할 수 있으며 **float**, **double**, **valdouble**, **void**, **bool** 또는 그 밖의 복합 데이터 형식은 사용할 수 없습니다.

비트 `AND`은 논리적 `AND`과 같은 진리표를 포함하지만 개별 비트 수준에서 데이터 형식에 적용됩니다. [operator&&](#op_amp_amp)는 요소 수준에서 적용되어 0이 아닌 모든 값을 true로 계산하며, 결과는 부울 값의 valarray입니다. 이와 대조적으로 비트 `AND` [연산자 &](#op_amp)는 비트 연산의 결과에 따라 0 이나 1이 아닌 값의 valarray를 발생 시킬 수 있습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaBWA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i+1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBWA = ( vaL & vaR );
   cout << "The element-by-element result of "
        << "the bitwise operator & is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
```

## <a name="op_amp_amp"></a>연산자&amp;&amp;

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 valarray 요소 형식의 지정된 값 간에 논리적 **AND**를 가져옵니다.

```cpp
template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator&&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개별 요소를 논리적 `AND`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 결합할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
개별 요소를 논리적 `AND`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 결합할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

요소가 bool 형식이 고 *left* 및 *right*의 논리적 `AND` 연산의 요소 전체 조합인 valarray입니다.

### <a name="remarks"></a>설명

논리적 `ANDoperator&&` 요소 수준에서 적용 되 고 0이 아닌 모든 값을 true로 계산 하며, 결과는 부울 값의 valarray입니다. 이와 대조적으로 `AND`[연산자 &](#op_amp)의 비트 버전은 비트 연산의 결과에 따라 0 이나 1이 아닌 값의 valarray를 발생 시킬 수 있습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_logand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL && vaR );
   cout << "The element-by-element result of "
        << "the logical AND operator&& is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
```

## <a name="op_gt"></a> 연산자&gt;

한 valarray의 요소가 크기가 같은 valarray의 요소보다 큰지 또는 valarray의 모든 요소가 지정된 값보다 크거나 작은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 크면 **true** 입니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 크지 않으면 **false** 입니다.

### <a name="remarks"></a>설명

두 valarray의 요소 수가 같지 않으면 결과는 정의되지 않습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_gt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL > vaR );
   cout << "The element-by-element result of "
        << "the greater than comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="op_gt_eq"></a>연산자&gt;=

한 valarray의 요소가 크기가 같은 valarray의 요소보다 크거나 같은지 또는 valarray의 모든 요소가 지정된 값보다 크거나 같거나 작거나 같은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 크거나 같으면 **true** 입니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 작은 경우 **false** 입니다.

### <a name="remarks"></a>설명

두 valarray의 요소 수가 같지 않으면 결과는 정의되지 않습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_ge.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >= vaR );
   cout << "The element-by-element result of "
        << "the greater than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="op_gt_gt"></a>연산자&gt;&gt;

valarray의 각 요소에 대한 비트를 지정된 위치 수 또는 두 번째 valarray에 지정된 요소 양만큼 오른쪽으로 이동합니다.

```cpp
template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator>>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
이동할 값 또는 해당 요소를 이동할 valarray

*오른쪽*\
오른쪽으로 이동할 크기를 나타내는 값 또는 해당 요소가 요소 전체 오른쪽 이동 크기를 나타내는 valarray

### <a name="return-value"></a>Return Value

해당 요소가 지정한 크기만큼 오른쪽으로 이동된 valarray

### <a name="remarks"></a>설명

부호 있는 숫자의 부호는 유지됩니다.

### <a name="example"></a>예제

```cpp
// valarray_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >> vaR );
   cout << "The element-by-element result of "
        << "the right shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
```

## <a name="op_lt"></a> 연산자&lt;

한 valarray의 요소가 크기가 같은 valarray의 요소보다 작은지 또는 valarray의 모든 요소가 지정된 값보다 크거나 작은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 작은 경우 **true** 입니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 작지 않으면 **false** 입니다.

### <a name="remarks"></a>설명

두 valarray의 요소 수가 같지 않으면 결과는 정의되지 않습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_lt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL < vaR );
   cout << "The element-by-element result of "
        << "the less-than comparson test is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="op_lt_eq"></a>연산자&lt;=

한 valarray의 요소가 크기가 같은 valarray의 요소보다 작거나 같은지 또는 valarray의 모든 요소가 지정된 값보다 크거나 같거나 작거나 같은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 비교하거나 지정된 값을 valarray의 각 요소와 비교할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 작거나 같으면 **true** 입니다.

- *왼쪽* 요소나 값이 해당 하는 *오른쪽* 요소나 값 보다 크면 **false** 입니다.

### <a name="remarks"></a>설명

두 valarray의 요소 수가 같지 않으면 결과는 정의되지 않습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_le.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL <= vaR );
   cout << "The element-by-element result of "
        << "the less than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="op_lt_lt"></a>연산자&lt;&lt;

valarray의 각 요소에 대한 비트를 지정된 위치 수 또는 두 번째 valarray에 지정된 요소 양만큼 왼쪽으로 이동합니다.

```cpp
template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator<<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
이동할 값 또는 해당 요소를 이동할 valarray

*오른쪽*\
왼쪽으로 이동할 크기를 나타내는 값 또는 해당 요소가 요소 전체 왼쪽 이동 크기를 나타내는 valarray

### <a name="return-value"></a>Return Value

해당 요소가 지정한 크기만큼 왼쪽으로 이동된 valarray

### <a name="remarks"></a>설명

부호 있는 숫자의 부호는 유지됩니다.

### <a name="example"></a>예제

```cpp
// valarray_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL << vaR );
   cout << "The element-by-element result of "
        << "the left shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
```

## <a name="op_star"></a>연산자

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 지정된 값 간에 요소 전체 곱을 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator*(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 곱하거나 지정된 값을 valarray의 각 요소와 곱할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 곱하거나 지정된 값을 valarray의 각 요소와 곱할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

요소가 *왼쪽과* *오른쪽*의 요소 전체 곱 인 valarray

### <a name="example"></a>예제

```cpp
// valarray_op_eprod.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL * vaR );
   cout << "The element-by-element result of "
        << "the multiplication is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
```

## <a name="op_add"></a>연산자 +

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 지정된 값 간에 요소 전체 합을 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator+(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소를 더하거나 지정된 값을 valarray의 각 요소와 더할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소를 더하거나 지정된 값을 valarray의 각 요소와 더할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

해당 요소가 *왼쪽과* *오른쪽*의 요소 전체 합계인 valarray

### <a name="example"></a>예제

```cpp
// valarray_op_esum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL + vaR );
   cout << "The element-by-element result of "
        << "the sum is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
```

## <a name="operator-"></a>연산자

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 지정된 값 간에 요소 전체 차를 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator-(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
차를 구하기 위해 다른 값이나 valarray를 뺄 피감수로 사용되는 값 또는 valarray

*오른쪽*\
차를 구하기 위해 다른 값이나 valarray에서 뺄 감수로 사용되는 값 또는 valarray

### <a name="return-value"></a>Return Value

요소가 *왼쪽과* *오른쪽*의 요소 전체 차 인 valarray

### <a name="remarks"></a>설명

빼기를 설명하는 데 사용되는 산술 용어입니다.

차 = 피감수 - 감수

### <a name="example"></a>예제

```cpp
// valarray_op_ediff.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL - vaR );
   cout << "The element-by-element result of "
        << "the difference is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
```

## <a name="op_div"></a>연산자

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 지정된 값 간에 요소 전체 몫을 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator/(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
몫을 구하기 위해 다른 값이나 valarray를 나눌 피제수로 사용되는 값 또는 valarray입니다.

*오른쪽*\
몫을 구하기 위해 다른 값이나 valarray를 나누는 제수로 사용되는 값 또는 valarray입니다.

### <a name="return-value"></a>Return Value

해당 요소를 *왼쪽* 에서 *오른쪽*으로 나눈 요소가 포함 된 valarray

### <a name="remarks"></a>설명

나누기를 설명하는 데 사용되는 산술 용어입니다.

몫 = 피제수/제수

### <a name="example"></a>예제

```cpp
// valarray_op_equo.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   valarray<double> vaNE ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL / vaR );
   cout << "The element-by-element result of "
        << "the quotient is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
```

## <a name="op_eq_eq"></a>연산자 = =

크기가 같은 두 valarray의 해당 요소가 서로 같은지 또는 valarray의 모든 요소가 지정된 값과 같은지 테스트합니다.

```cpp
template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator==(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
해당 요소가 같은지 테스트할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
해당 요소가 같은지 테스트할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

부울 값의 valarray. 각 valarray은 다음을 반환합니다.

- 해당 요소가 같은 경우 **true**

- 해당 요소가 같지 않은 경우 **false**

### <a name="remarks"></a>설명

첫 번째 템플릿 연산자는 각 `I` 요소가 `left[I] == right[I]`인 [valarray\<bool >](../standard-library/valarray-bool-class.md)의 개체를 반환 합니다. 두 번째 템플릿 연산자는 요소 `I` `left[I] == right`에 저장 합니다. 세 번째 템플릿 연산자는 요소 `I` `left == right[I]`에 저장 합니다.

### <a name="example"></a>예제

```cpp
// valarray_op_eq.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL == vaR );
   cout << "The element-by-element result of "
        << "the equality comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="op_xor"></a>operator ^

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 요소 형식의 지정된 값 간에 비트 배타적 `OR`(**XOR**)을 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator^(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개별 요소를 비트 **XOR**로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
개별 요소를 비트 **XOR**로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

해당 요소가 *left* 및 *Right*의 비트 **XOR** 연산의 요소 전체 조합인 valarray입니다.

### <a name="remarks"></a>설명

비트 연산은 **char** 및 **int** 데이터 형식 및 variant의 비트를 조작 하는 데만 사용할 수 있으며 **float**, **double**, **long double**, **void**, **bool** 또는 기타 복잡 한 데이터 형식은 사용할 수 없습니다.

배타적 **XOR**(배타적 비트 `OR`)의 의미 체계는 다음과 같습니다. 지정 된 비트 *b*1과 *b*2, *b*1 **XOR** *b*2는 정확히 비트 중 하나가 true 인 경우 **true** 입니다. 두 비트가 모두 false 이거나 두 비트가 모두 true 이면 **false** 입니다.

### <a name="example"></a>예제

```cpp
// valarray_op_xor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL ^ vaR );
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^ is the\n"
        << "valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
```

## <a name="op_or"></a>연산자&#124;

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 요소 형식의 지정된 값 간에 비트 `OR`을 가져옵니다.

```cpp
template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator|(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개별 요소를 비트 `OR`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
개별 요소를 비트 `OR`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 비트 결합할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

요소가 *left* 및 *right*의 비트 `OR` 연산의 요소 전체 조합인 valarray입니다.

### <a name="remarks"></a>설명

비트 연산은 **char** 및 **int** 데이터 형식 및 variant의 비트를 조작 하는 데만 사용할 수 있으며 **float**, **double**, **valdouble**, **void**, **bool** 또는 그 밖의 복합 데이터 형식은 사용할 수 없습니다.

비트 OR은 논리적 `OR`와 같은 진리표를 포함하지만 개별 비트 수준에서 데이터 형식에 적용됩니다. B 1 *및* *b*2가 지정 된 경우 *b*1 `OR` *b*2는 비트 중 하나 이상이 true 이면 **true** 이 고 두 비트가 모두 false 이면 **false** 입니다. 논리적 `OR`[operator&#124;&#124;](../standard-library/valarray-operators.md#op_lor)는 요소 수준에서 적용되어 0이 아닌 모든 값을 **true**로 계산하며, 결과는 부울 값의 valarray입니다. 반면 비트 OR `operator|`를 사용하는 경우에는 비트 연산의 결과에 따라 0이나 1이 아닌 값의 valarray가 생성될 수 있습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL | vaR );
   cout << "The element-by-element result of "
        << "the bitwise OR operator| is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
```

## <a name="op_lor"></a>연산자&#124;&#124;

크기가 같은 두 valarray의 해당 요소 간이나 valarray와 valarray 요소 형식의 지정된 값 간에 논리적 `OR`을 가져옵니다.

```cpp
template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator||(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개별 요소를 논리적 `OR`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 결합할 두 valarray 중 첫 번째 valarray입니다.

*오른쪽*\
개별 요소를 논리적 `OR`로 결합하거나 요소 형식의 지정된 값을 valarray의 각 요소와 결합할 두 valarray 중 두 번째 valarray입니다.

### <a name="return-value"></a>Return Value

요소가 **bool** 형식이 고 *left* 및 *right*의 논리적 OR 연산의 요소 전체 조합인 valarray입니다.

### <a name="remarks"></a>설명

논리적 `OR` `operator||` 요소 수준에서 적용 되 고 0이 아닌 모든 값을 **true**로 계산 하며, 결과는 부울 값의 valarray입니다. 반면 비트 버전 `OR`, [operator&#124;](../standard-library/valarray-operators.md#op_or)를 사용하는 경우에는 비트 연산의 결과에 따라 0이나 1이 아닌 값의 valarray가 생성될 수 있습니다.

### <a name="example"></a>예제

```cpp
// valarray_op_logor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLOR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLOR = ( vaL || vaR );
   cout << "The element-by-element result of "
        << "the logical OR operator|| is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
```
