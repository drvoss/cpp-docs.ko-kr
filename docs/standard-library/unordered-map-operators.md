---
title: '&lt;unordered_map&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: 6a22ccfaf77c3be524bf7127eac3d76c7be827ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201858"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map&gt; 연산자

|||||
|-|-|-|-|
|[연산자! =](#op_neq)|[연산자 = =](#op_eq_eq)|[연산자! =](#op_neq_multimap)|[연산자 = =](#op_eq_eq_multimap)|

## <a name="operator"></a><a name="op_neq"></a>연산자! =

연산자의 좌변에 있는 [unordered_map](../standard-library/unordered-map-class.md) 개체가 우변에 있는 unordered_map 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
`unordered_map` 형식의 개체입니다.

*오른쪽*\
`unordered_map` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

**`true`** unordered_maps 같지 않으면이 고, 그렇지 않으면입니다. **`false`** 같으면이 고, 그렇지 않으면입니다.

### <a name="remarks"></a>설명

unordered_map 개체 간의 비교는 해당 요소를 저장하는 임의의 순서에 의해 영향을 받지 않습니다. 두 unordered_map은 요소 수가 같고 특정 컨테이너의 요소가 다른 컨테이너의 요소 순열이면 동일합니다. 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// unordered_map_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}
```

**출력:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq"></a>연산자 = =

연산자의 좌변에 있는 [unordered_map](../standard-library/unordered-map-class.md) 개체가 우변에 있는 unordered_map 개체와 같은지 테스트합니다.

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
`unordered_map` 형식의 개체입니다.

*오른쪽*\
`unordered_map` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

**`true`** unordered_maps 같으면이 고, 그렇지 않으면입니다. **`false`** 동일 하지 않은 경우입니다.

### <a name="remarks"></a>설명

unordered_map 개체 간의 비교는 해당 요소를 저장하는 임의의 순서에 의해 영향을 받지 않습니다. 두 unordered_map은 요소 수가 같고 특정 컨테이너의 요소가 다른 컨테이너의 요소 순열이면 동일합니다. 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// unordered_map_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}
```

**출력:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="operator"></a><a name="op_neq_multimap"></a>연산자! =

연산자의 좌변에 있는 [unordered_multimap](../standard-library/unordered-multimap-class.md) 개체가 우변에 있는 unordered_multimap 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
`unordered_multimap` 형식의 개체입니다.

*오른쪽*\
`unordered_multimap` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

**`true`** unordered_multimaps 같지 않으면이 고, 그렇지 않으면입니다. **`false`** 같으면이 고, 그렇지 않으면입니다.

### <a name="remarks"></a>설명

unordered_multimap 개체 간의 비교는 해당 요소를 저장하는 임의의 순서에 의해 영향을 받지 않습니다. 두 unordered_multimap은 요소 수가 같고 특정 컨테이너의 요소가 다른 컨테이너의 요소 순열이면 동일합니다. 그렇지 않으면 두 unordered_multimap은 같지 않습니다.

### <a name="example"></a>예제

```cpp
// unordered_multimap_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}
```

**출력:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq_multimap"></a>연산자 = =

연산자의 좌변에 있는 [unordered_multimap](../standard-library/unordered-multimap-class.md) 개체가 우변에 있는 unordered_multimap 개체와 같은지 테스트합니다.

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
`unordered_multimap` 형식의 개체입니다.

*오른쪽*\
`unordered_multimap` 형식의 개체입니다.

### <a name="return-value"></a>Return Value

**`true`** unordered_multimaps 같으면이 고, 그렇지 않으면입니다. **`false`** 동일 하지 않은 경우입니다.

### <a name="remarks"></a>설명

unordered_multimap 개체 간의 비교는 해당 요소를 저장하는 임의의 순서에 의해 영향을 받지 않습니다. 두 unordered_multimap은 요소 수가 같고 특정 컨테이너의 요소가 다른 컨테이너의 요소 순열이면 동일합니다. 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// unordered_multimap_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}
```

**출력:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="see-also"></a>참고 항목

[<unordered_map>](../standard-library/unordered-map.md)
