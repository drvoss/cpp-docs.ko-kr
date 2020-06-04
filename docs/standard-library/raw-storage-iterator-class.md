---
title: raw_storage_iterator 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
ms.openlocfilehash: 9372fa884d75e10c1a0f2ec92d6cca9caa65808e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167617"
---
# <a name="raw_storage_iterator-class"></a>raw_storage_iterator 클래스

초기화되지 않은 메모리에 결과를 저장하는 알고리즘을 사용할 수 있도록 제공되는 어댑터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class OutputIterator, class Type>
    class raw_storage_iterator
```

### <a name="parameters"></a>매개 변수

*Outputiterator*\
저장되는 개체에 대한 출력 반복기를 지정합니다.

*형식*\
스토리지를 할당할 개체 형식입니다.

## <a name="remarks"></a>설명

클래스는 생성 하는 시퀀스에서 `Type` 형식의 개체를 생성 하는 출력 반복기를 설명 합니다. 개체를 생성할 때 지정 하는 클래스 `ForwardIterator`의 전달 반복기 **개체를 통해**저장소 **>에 액세스**하는 \< `raw_storage_iterator`클래스의 개체입니다. `ForwardIterator`클래스의 첫 번째 개체의 경우 **\*먼저&** 식이 생성 된 시퀀스에서 다음 개체 (형식 `Type`)에 대해 생성 되지 않은 저장소를 지정 해야 합니다.

이 어댑터 클래스는 메모리 할당 및 개체 생성을 구분하는 데 필요한 경우에 사용됩니다. `raw_storage_iterator`를 사용하여 `malloc` 함수를 통해 할당된 메모리와 같은 초기화되지 않은 스토리지에 개체를 복사할 수 있습니다.

## <a name="members"></a>구성원

### <a name="constructors"></a>생성자

|||
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|지정된 기본 출력 반복기를 사용하여 원시 스토리지 반복기를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[element_type](#element_type)|원시 스토리지 반복기를 저장할 요소를 설명하는 형식을 제공합니다.|
|[iter_type](#iter_type)|원시 스토리지 반복기의 기반이 되는 반복기를 설명하는 형식을 제공합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator*](#op_star)|`ii` = `x`\* 출력 반복기 식을 구현 하는 데 사용 되는 역참조 연산자입니다.|
|[operator=](#op_eq)|원시 저장소 반복기 식을 구현 하는 데 사용 되는 할당 연산자는 메모리에 저장 하기 위해 `x`  = `i`\* 합니다.|
|[operator++](#op_add_add)|원시 스토리지 반복기에 대한 사전 증가 및 사후 증가 연산자입니다.|

### <a name="element_type"></a><a name="element_type"></a>element_type

원시 스토리지 반복기를 저장할 요소를 설명하는 형식을 제공합니다.

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>설명

형식은 raw_storage_iterator 클래스 템플릿 매개 변수 `Type`의 동의어입니다.

### <a name="iter_type"></a><a name="iter_type"></a>iter_type

원시 스토리지 반복기의 기반이 되는 반복기를 설명하는 형식을 제공합니다.

```cpp
typedef ForwardIterator iter_type;
```

#### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `ForwardIterator`의 동의어입니다.

### <a name="operator"></a><a name="op_star"></a> 연산자\*

원시 저장소 반복기 식 \* *ii* = *x*를 구현 하는 데 사용 되는 역참조 연산자입니다.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

#### <a name="return-value"></a>Return Value

원시 스토리지 반복기에 대한 참조

#### <a name="remarks"></a>설명

`ForwardIterator`에 대 한 요구 사항은 원시 저장소 반복기에는 = *t* \* *ii* 식만 유효 해야 하 고 **연산자** 또는 `operator=`에 대해 아무 것도 지정 하지 않아야 한다는 것입니다. 이 구현의 멤버 연산자는 **\*** 반환 하므로 [operator =](#op_eq)(**constType**&)가 \* *ptr* = `val`와 같은 식의 실제 저장소를 수행할 수 있습니다.

#### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
*pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_eq"></a>연산자 =

원시 저장소 반복기 식을 구현 하는 데 사용 되는 할당 연산자는 메모리에 저장 하는 데 *x* *를 = \** .

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

#### <a name="parameters"></a>매개 변수

*val*\
메모리에 삽입할 `Type` 형식 개체의 값입니다.

#### <a name="return-value"></a>Return Value

연산자는 `val`을 메모리에 삽입한 다음 원시 스토리지 반복기에 대한 참조를 반환합니다.

#### <a name="remarks"></a>설명

원시 저장소 반복기가 충족 해야 하는 `ForwardIterator` 상태에 대 한 요구 사항은 \* = *ii* 식만 *유효 해야* 하며 연산자 `operator=` 또는 해당 **연산자** 에 대해 아무 것도 표시 되지 않습니다. 이러한 구성원 연산자는 **\*this**를 반환합니다.

대입 연산자는 배치 new expression **new** ((`void` \*) &\* **first**) **형식**(`val`)을 평가 하 여 먼저 저장 된 반복기 값을 사용 하 여 출력 시퀀스에서 다음 개체를 생성 합니다.

#### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_add_add"></a>operator + +

원시 스토리지 반복기에 대한 사전 증가 및 사후 증가 연산자입니다.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

#### <a name="return-value"></a>Return Value

원시 스토리지 반복기 또는 원시 스토리지 반복기에 대한 참조입니다.

#### <a name="remarks"></a>설명

첫 번째 연산자는 연결 된 입력 스트림에서 `CharType` 형식의 개체를 추출 하 고 저장 하려고 합니다. 두 번째 연산자는 개체의 복사본을 만들고 개체를 증가시킨 다음 복사본을 반환합니다.

첫 번째 preincrement 연산자는 저장된 출력 반복기 개체를 증가시키고 **\*this**를 반환합니다.

두 번째 postincrement 연산자는 **\*this**의 복사본을 만들고 저장된 출력 반복기 개체를 증가시킨 다음 해당 복사본을 반환합니다.

생성자는 `first`를 출력 반복기 개체로 저장 합니다.

#### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
      *it = 2 * i;
   };

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
```

```Output
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
```

### <a name="raw_storage_iterator"></a><a name="raw_storage_iterator"></a>raw_storage_iterator

지정된 기본 출력 반복기를 사용하여 원시 스토리지 반복기를 생성합니다.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

#### <a name="parameters"></a>매개 변수

*첫 번째*\
생성 중인 `raw_storage_iterator`의 기준으로 사용할 정방향 반복기입니다.

#### <a name="example"></a>예제

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
```

```Output
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
```
