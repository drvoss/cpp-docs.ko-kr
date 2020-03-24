---
title: 변경할 수 있는 데이터 멤버(C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: db3a9594a77a9ada971213eaea74a9842bd96a54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179343"
---
# <a name="mutable-data-members-c"></a>변경할 수 있는 데이터 멤버(C++)

이 키워드는 클래스의 비정적 데이터 멤버 중에서 const가 아닌 멤버에만 적용할 수 있습니다. 데이터 멤버가 **변경**가능한 것으로 선언 된 경우에는 **const** 멤버 함수에서이 데이터 멤버에 값을 할당할 수 있습니다.

## <a name="syntax"></a>구문

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>설명

예를 들어 다음 코드는 `m_accessCount` **변경**가능 하도록 선언 되었으므로 오류가 발생 하지 않고 컴파일되고 따라서 `GetFlag`가 const 멤버 함수 이더라도 `GetFlag`에서 수정할 수 있습니다.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)
