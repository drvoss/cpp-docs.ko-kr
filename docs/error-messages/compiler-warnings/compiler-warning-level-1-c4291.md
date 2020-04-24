---
title: 컴파일러 경고(수준 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: c1972236e30be4e6ca738b606b00398f5c7860e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754860"
---
# <a name="compiler-warning-level-1-c4291"></a>컴파일러 경고(수준 1) C4291

'선언' : 일치하는 연산자 삭제가 없습니다. 초기화가 예외를 throw하면 메모리가 해제되지 않습니다.

배치 [삭제가](../../cpp/new-operator-cpp.md) 없는 배치 새 [가](../../cpp/delete-operator-cpp.md)사용됩니다.

연산자가 **새**연산자가 있는 개체에 대해 메모리가 할당되면 개체의 생성자가 호출됩니다. 생성자가 예외를 throw하는 경우 개체에 할당된 모든 메모리를 할당 해야 합니다. 연산자 **삭제** 함수가 **연산자 새**와 일치하는 함수가 없으면 이 작업을 수행할 수 없습니다.

추가 인수 없이 **새** 연산자를 사용하고 [/GX,](../../build/reference/gx-enable-exception-handling.md) [/EHs](../../build/reference/eh-exception-handling-model.md)또는 /EHa 옵션을 사용하여 컴파일하여 예외 처리를 활성화하는 경우 컴파일러는 생성자가 예외를 throw하면 생성자가 **delete를** 호출하는 코드를 생성합니다.

**새** 연산자의 배치 양식(할당 크기 이외에 인수가 있는 양식)을 사용하고 개체의 생성자가 예외를 throw하는 경우 컴파일러는 여전히 연산자 **delete를**호출하는 코드를 생성합니다. 그러나 연산자 **삭제의** 배치 양식이 메모리를 할당한 **새** 연산자의 배치 양식과 일치하는 경우에만 그렇게 합니다. 다음은 그 예입니다.

```cpp
// C4291.cpp
// compile with: /EHsc /W1
#include <malloc.h>

class CList
{
public:
   CList(int)
   {
      throw "Fail!";
   }
};

void* operator new(size_t size, char* pszFilename, int nLine)
{
   return malloc(size);
}

int main(void)
{
   try
   {
      // This will call ::operator new(unsigned int) to allocate heap
      // memory. Heap memory pointed to by pList1 will automatically be
      // deallocated by a call to ::operator delete(void*) when
      // CList::CList(int) throws an exception.
      CList* pList1 = new CList(10);
   }
   catch (...)
   {
   }

   try
   {
      // This will call the overloaded ::operator new(size_t, char*, int)
      // to allocate heap memory. When CList::CList(int) throws an
      // exception, ::operator delete(void*, char*, int) should be called
      // to deallocate the memory pointed to by pList2. Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291
   }
   catch (...)
   {
   }
}
```

위의 예제는 연산자 **삭제의** 배치 형식이 **새**연산자의 배치 양식과 일치하지 않으므로 경고 C4291을 생성합니다. 문제를 해결하려면 **main**위에 다음 코드를 삽입합니다. 오버로드된 연산자 **delete** 함수 매개 변수는 첫 번째 매개 변수를 제외한 오버로드된 연산자의 **새**매개 변수와 일치합니다.

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
