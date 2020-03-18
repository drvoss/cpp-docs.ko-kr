---
title: '&lt;numeric&gt; 함수'
description: C++ 표준 라이브러리의 &lt;numeric&gt;헤더에서 제공 하는 함수 템플릿에 대해 설명 합니다.
ms.date: 10/30/2019
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::exclusive_scan
- numeric/std::gcd
- numeric/std::inclusive_scan
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::lcm
- numeric/std::partial_sum
- numeric/std::reduce
- numeric/std::transform_exclusive_scan
- numeric/std::transform_inclusive_scan
- numeric/std::transform_reduce
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::exclusive_scan [C++]
- std::gcd [C++]
- std::inclusive_scan [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::lcm [C++]
- std::partial_sum [C++]
- std::reduce [C++]
- std::transform_exclusive_scan [C++]
- std::transform_inclusive_scan [C++]
- std::transform_reduce [C++]
ms.openlocfilehash: 88a97a3d110c684090b78570077927e32541eed7
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425366"
---
# <a name="ltnumericgt-functions"></a>&lt;numeric&gt; 함수

## <a name="accumulate"></a>누적

연속 부분 합계를 계산 하 여 일부 초기 값을 포함 하 여 지정 된 범위에 있는 모든 요소의 합계를 계산 합니다. 또는는 지정 된 이항 연산의 연속 부분 결과를 계산 하 여 결과를 계산 합니다.

```cpp
template <class InputIterator, class Type>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type init);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

첫 번째 템플릿 함수에 대해 지정 된 범위에 있는 *init* 의 합계와 모든 요소를 반환 합니다. 두 번째 템플릿 함수의 경우에는 (* partialresult, *in_iter*)에 sum 연산 대신 *binary_op* 이항 연산을 적용 한 결과입니다. 여기서 *partialresult* 는 작업의 이전 응용 프로그램의 결과이 고 *in_iter* 는 범위의 다음 요소를 가리키는 반복기입니다.

### <a name="remarks"></a>설명

초기 값은 범위가 비어 있을 때 잘 정의 된 결과가 있는지 확인 합니다 .이 경우 *init* 가 반환 됩니다. 이항 연산은 연관성이 나 비가 환 일 필요가 없습니다. 결과는 초기 값 *init* 로 초기화 된 다음 *결과* = *binary_op*(*결과*, *in_iter*)는 범위를 통해 반복적으로 계산 됩니다. 여기서 *in_iter* 은 범위의 각 연속 요소를 가리키는 반복기입니다. 범위는 유효 해야 하 고 복잡성은 범위의 크기와 선형입니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>adjacent_difference

입력 범위에서 각 요소와 선행 작업 간의 연속 차이를 계산 합니다. 결과를 대상 범위에 출력 합니다. 또는는 차이 연산을 지정 된 다른 이진 연산으로 대체 한 일반화 된 절차의 결과를 계산 합니다.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template <class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 adjacent_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*마지막*\
입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 마지막 요소를 주소 지정하는 입력 반복기입니다.

*결과*\
일련의 차이 또는 지정된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정하는 출력 반복기입니다.

*binary_op*\
일반적인 작업에서 적용할 이항 연산이 며, 차이점 보관용 프로시저에서 빼기 연산을 대체 합니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정 하는 출력 반복기입니다. `result` + (`last` - `first`).

### <a name="remarks"></a>설명

출력 반복기 *결과* 는 *입력 반복기와*동일한 반복기 일 수 있으므로 `adjacent_difference` 값이 현재 위치의 계산 될 수 있습니다.

입력 범위에서 *1,* *a*2, 3의 값 시퀀스에 대해 첫 번째 템플릿 함수는 대상 범위에 연속 `adjacent_difference` *값 1,* 2- *a* *1,* a3- *a* *2를 저장*합니다.

입력 범위에서 1, *a* *a*2, 3의 값 *a*시퀀스에 대해 두 번째 템플릿 함수는 연속 `adjacent_difference` 값 1, 2 *binary_op* 1 *,* *3*binary_op *2를*대상 범위에 저장 합니다. *binary_op* *a* *a*

적용 되는 작업의 순서가 지정 되어 있으므로 이항 연산 *binary_op* 는 결합형 또는 교환 일 필요가 없습니다.

### <a name="example"></a>예제

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="exclusive_scan"></a>exclusive_scan

초기 값이 지정 된 경우 범위에 대해 `std::plus<>()` 또는 지정 된 이항 연산자를 사용 하 여 배타적 접두사 합계 연산을 계산 합니다. 지정 된 대상에서 시작 하는 범위에 결과를 씁니다. *제외 접두사* 합계는 *n*번째 입력 요소가 *n*번째 합계에 포함 되지 않음을 의미 합니다. 실행 정책 인수를 포함 하는 오버 로드는 지정 된 정책에 따라 실행 됩니다.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init);

template<class InputIterator, class OutputIterator, class Type, class BinaryOperation>
OutputIterator exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
ForwardIterator2 exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation>
ForwardIterator2 exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정 하는 출력 반복기: *result* + (*last* - *first*).

## <a name="gcd"></a>gcd

M과 n 정수의 최대 공약수를 계산 합니다.

```cpp
template <class M, class N>
constexpr common_type_t<M,N> gcd(M m, N n);
```

### <a name="parameters"></a>매개 변수

*m*, *n*\
정수 계열 형식의 값입니다.

### <a name="return-value"></a>반환 값

*M* 과 *n*의 절대값에 대 한 최대 공약수를 반환 하거나, *m* 과 *n* 이 모두 0 이면 0을 반환 합니다. *M* 또는 *n* 의 절대값을 `common_type_t<M,N>`형식의 값으로 표현할 수 없는 경우 결과가 정의 되지 않습니다.

## <a name="inclusive_scan"></a>inclusive_scan

초기 값이 지정 된 경우 범위에 대해 `std::plus<>()` 또는 지정 된 이항 연산자를 사용 하 여 포괄 접두사 sum 연산을 계산 합니다. 지정 된 대상에서 시작 하는 범위에 결과를 씁니다. *포함 접두사* 합계는 *n*번째 입력 요소가 *n*번째 합계에 포함 됨을 의미 합니다. 실행 정책 인수를 포함 하는 오버 로드는 지정 된 정책에 따라 실행 됩니다.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template<class InputIterator, class OutputIterator, class BinaryOperation>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);

template<class InputIterator, class OutputIterator, class BinaryOperation, class Type>
OutputIterator inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryOperation, class Type>
ForwardIterator2 inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    Type init);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정 하는 출력 반복기: *result* + (*last* - *first*).

## <a name="inner_product"></a>inner_product

두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             init);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);
```

### <a name="parameters"></a>매개 변수

*first1*\
두 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 첫 번째 범위의 첫 번째 요소 주소를 지정하는 입력 반복기입니다.

*last1*\
두 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 첫 번째 범위의 마지막 번째 요소 주소를 지정하는 입력 반복기입니다.

*first2*\
첫 번째 범위와의 일반화된 내부 곱 또는 내부 곱을 계산할 두 번째 범위의 첫 번째 요소 주소를 지정하는 입력 반복기입니다.

*init*\
범위 간의 내부 곱 또는 일반화된 내부 곱을 더할 초기값입니다.

*binary_op1*\
내부 곱 일반화에서 요소별 곱에 적용되는 합계의 내부 곱 연산을 대체하는 이진 연산입니다.

*binary_op2*\
내부 곱 일반화에서 곱하기의 내부 곱 요소별 연산을 대체하는 이진 연산입니다.

### <a name="return-value"></a>반환 값

첫 번째 구성원 함수는 요소별 곱의 합을 반환하고 해당 합을 지정된 초기값에 더합니다. 따라서 값 *a*i 및 *b*i의 범위에 대해 이 함수는 다음 결과를 반환합니다.

*init* + (*a*1 \* *b*1) + (*a*2 \* *b*2) + ... + (*a*n \* *b*n)

*init* 를 *init* + (*a*i \* *b*i)로 반복적으로 대체 합니다.

두 번째 구성원 함수는 다음 결과를 반환합니다.

*init* *binary_op1* (*1* *binary_op2* *b*1) *binary_op1* (*a*2 *binary_op2* *b*2) *binary_op1* ... *binary_op1* (*n* *binary_op2* *b*n)

*init* 를 *init* *binary_op1* 로 반복적으로 바꿔서 *(* i *binary_op2* *b*i).

### <a name="remarks"></a>설명

초기 값은 범위가 비어 있을 때 잘 정의 된 결과가 있는지 확인 합니다. 이 경우 *init* 가 반환 됩니다. 이항 연산은 연관성이 나 비가 환 필요가 없습니다. 범위는 유효 해야 하 고 복잡성은 범위의 크기와 선형입니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>iota

시작 값을 저장 하 고, 첫 번째 요소부터 시작 하 여 간격 `[first,  last)`간격의 각 요소에서 해당 값의 연속 증가값 (`value++`)을 채웁니다.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
채울 범위의 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*마지막*\
채울 범위의 마지막 요소를 주소 지정하는 입력 반복기입니다.

*value*\
첫 번째 요소에 저장 하 고 이후 요소에 대해 연속적으로 증가 하는 시작 값입니다.

### <a name="example"></a>예제

다음 예제에서는 `iota`random_shuffle[ 함수를 사용할 수 있도록 정수 ](../standard-library/list.md)list[를 채운 다음 ](../standard-library/vector.md)로 `list`vector[를 채우는 ](../standard-library/algorithm-functions.md#random_shuffle) 함수의 몇 가지 사용 방법을 보여 줍니다.

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="lcm"></a>lcm

```cpp
template <class M, class N>
constexpr common_type_t<M,N> lcm(M m, N n);
```

## <a name="partial_sum"></a>partial_sum

N 번째 요소부터 *n*번째 요소까지 입력 범위에서 일련의 합계를 계산 하 고 각 합계의 결과를 대상 범위의 *n*번째 요소에 저장 합니다. 또는는 sum 연산을 지정 된 다른 이진 연산으로 대체 한 일반화 된 절차의 결과를 계산 합니다.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
지정된 이진 연산에 따라 부분적으로 합을 계산하거나 결합할 범위의 첫 번째 요소를 주소 지정하는 입력 반복기입니다.

*마지막*\
반복된 누적에 실제로 포함된 마지막 요소 하나 다음 위치의 지정된 이진 연산에 따라 부분적으로 합을 계산하거나 결합할 범위의 마지막 요소를 주소 지정하는 입력 반복기입니다.

*결과*\
일련의 부분 합계를 저장할 대상 범위의 첫 번째 요소 또는 지정 된 이항 연산의 후속 결과를 주소 지정 하는 출력 반복기입니다.

*binary_op*\
부분 합계 프로시저에서 sum 연산을 대체 하 여 일반화 된 작업에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정 하는 출력 반복기: *result* + (*last* - *first*).

### <a name="remarks"></a>설명

출력 반복기 *결과* 는 입력 반복기와 동일한 반복기 일 수 있으므로 부분 *합계를 계산*하는 데 사용할 수 있습니다.

*값 시퀀스의 경우 1*, *a*2, ... 입력 범위의 x 인 첫 번째 템플릿 함수는 연속 부분 합계를 대상 범위에 *저장 합니다.* *N*번째 요소*는 (1*+ *a*2 + *a*3 + ... + *a*n)로 지정 됩니다.

입력 범위에서 *1,* *a*2, 3의 값 시퀀스에 대해 두 번째 템플릿 *함수는 연속*된 부분 결과를 대상 범위에 저장 합니다. *N*번째 요소는 ((... ((*a*1 *binary_op* *a*2) *binary_op* *3)* *binary_op* ...) n) *을* *binary_op* 합니다.

적용 되는 작업의 순서가 지정 되어 있으므로 이항 연산 *binary_op* 는 결합형 또는 교환 일 필요가 없습니다.

### <a name="example"></a>예제

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="reduce"></a>줄이십시오

임의 및 가능한 요소가 순열의 합계를 계산 하 여 일부 초기 값을 포함 하 여 지정 된 범위의 모든 요소를 줄입니다. 또는 지정 된 이항 연산의 결과를 계산 하 여 감소 시킵니다. 실행 정책 인수를 포함 하는 오버 로드는 지정 된 정책에 따라 실행 됩니다.

```cpp
template<class InputIterator>
typename iterator_traits<InputIterator>::value_type reduce(
    InputIterator first,
    InputIterator last);

template<class InputIterator, class Type>
Type reduce(
    InputIterator first,
    InputIterator last,
    Type init);

template<class InputIterator, class Type, class BinaryOperation>
Type reduce(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op);

template<class ExecutionPolicy, class ForwardIterator>
typename iterator_traits<ForwardIterator>::value_type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Type>
Type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init);

template<class ExecutionPolicy, class ForwardIterator, class Type, class BinaryOperation>
Type reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

*Init* 에 *binary_op* 또는 `std::plus<>()`를 적용 하 고 지정 된 범위의 모든 요소를 (* partialresult, *in_iter*)에 적용 한 결과입니다. 여기서 *partialresult* 는 이전 작업 응용 프로그램의 결과이 고 *in_iter* 는 범위의 일부 요소를 가리키는 반복기입니다. *Init*를 지정 하지 않는 오버 로드에서 사용 되는 *init* 값은 `typename iterator_traits<InputIterator>::value_type{}`와 동일 합니다.

### <a name="remarks"></a>설명

*binary_op* 를 연결 하 고 교환 하지 않는 한 `reduce` 동작은 명확 하지 않습니다. *Binary_op* 요소를 수정 하거나 interval \[*first*, *last*], 포함 된 모든 반복기를 무효화 하는 경우 동작이 정의 되지 않습니다.

## <a name="transform_exclusive_scan"></a>transform_exclusive_scan

지정 된 단항 연산자를 사용 하 여 범위의 요소를 변환한 다음, 지정 된 초기 값을 사용 하 여 범위에 대해 `std::plus<>()` 또는 지정 된 이항 연산자를 사용 하 여 배타적 접두사 합계 연산을 계산 합니다. 지정 된 대상에서 시작 하는 범위에 결과를 씁니다. *제외 접두사* 합계는 *n*번째 입력 요소가 *n*번째 합계에 포함 되지 않음을 의미 합니다. 실행 정책 인수를 포함 하는 오버 로드는 지정 된 정책에 따라 실행 됩니다. 합계는 임의의 순서로 수행 될 수 있습니다.

```cpp
template<class InputIterator, class OutputIterator, class Type, class BinaryOperation, class UnaryOperation>
OutputIterator transform_exclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_exclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

*unary_op*\
지정 된 범위에 있는 각 요소에 적용할 단항 연산입니다.

## <a name="transform_inclusive_scan"></a>transform_inclusive_scan

지정 된 단항 연산자를 사용 하 여 범위의 요소를 변환한 다음, `std::plus<>()` 또는 범위에 대해 지정 된 이항 연산자를 사용 하 여 (초기 값이 지정 된 경우) 포괄 접두사 sum 연산을 계산 합니다. 지정 된 대상에서 시작 하는 범위에 결과를 씁니다. *포함 접두사* 합계는 *n*번째 입력 요소가 *n*번째 합계에 포함 됨을 의미 합니다. 실행 정책 인수를 포함 하는 오버 로드는 지정 된 정책에 따라 실행 됩니다. 합계는 임의의 순서로 수행 될 수 있습니다.

```cpp
template<class InputIterator, class OutputIterator, class BinaryOperation, class UnaryOperation>
OutputIterator transform_inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class InputIterator, class OutputIterator, class BinaryOperation, class UnaryOperation, class Type>
OutputIterator transform_inclusive_scan(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op,
    UnaryOperation unary_op,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryOperation, class UnaryOperation>
ForwardIterator2 transform_inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryOperation, class UnaryOperation, class Type>
ForwardIterator2 transform_inclusive_scan(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryOperation binary_op,
    UnaryOperation unary_op,
    Type init);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

*unary_op*\
지정 된 범위에 있는 각 요소에 적용할 단항 연산입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

## <a name="transform_reduce"></a>transform_reduce

요소 범위를 변환한 다음 임의의 순서로 변환 된 요소를 줄이는 함수를 적용 합니다. 효과적으로 `transform` 뒤에 `reduce`합니다.

```cpp
template<class InputIterator1, class InputIterator2, class Type>
Type transform_reduce(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    Type init);

template<class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type transform_reduce(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    Type init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);

template<class InputIterator, class Type, class BinaryOperation, class UnaryOperation>
Type transform_reduce(
    InputIterator first,
    InputIterator last,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    Type init);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    Type init,
    BinaryOperation1 binary_op1,
    BinaryOperation2 binary_op2);

template<class ExecutionPolicy, class ForwardIterator, class Type, class BinaryOperation, class UnaryOperation>
Type transform_reduce(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Type init,
    BinaryOperation binary_op,
    UnaryOperation unary_op);
```

### <a name="parameters"></a>매개 변수

*exec*\
실행 정책입니다.

*첫 번째*\
*Binary_op*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*first1*\
*Binary_op1*를 사용 하 여 합계를 계산 하거나 결합할 범위의 첫 번째 요소를 주소 지정 하는 입력 반복기입니다.

*마지막*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*last1*\
반복 된 누적에 실제로 포함 된 마지막 요소 하나 다음의 한 위치인 *binary_op1*를 사용 하 여 합계 또는 결합 범위의 마지막 요소를 주소 지정 하는 입력 반복기입니다.

*결과*\
일련의 합계 또는 지정 된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

*init*\
*Binary_op*를 사용 하 여 각 요소가 차례로 추가 되거나 결합 되는 초기 값입니다.

*binary_op*\
지정 된 범위의 각 요소와 이전 응용 프로그램의 결과에 적용할 이항 연산입니다.

*unary_op*\
지정 된 범위에 있는 각 요소에 적용할 단항 연산입니다.

### <a name="return-value"></a>반환 값

변환 된 다음 결과가 줄어듭니다.
