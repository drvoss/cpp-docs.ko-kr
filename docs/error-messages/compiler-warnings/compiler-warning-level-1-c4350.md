---
title: 컴파일러 경고(수준 1) C4350
ms.date: 11/04/2016
f1_keywords:
- C4350
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
ms.openlocfilehash: 890ecd4fcec1212fa04a58b0eaab8c2eb4206763
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187221"
---
# <a name="compiler-warning-level-1-c4350"></a>컴파일러 경고(수준 1) C4350

동작 변경: 'member1'이(가) 'member2' 대신 호출됩니다.

Rvalue는 비 const 참조에 바인딩할 수 없습니다. Visual Studio 2003 이전 C++ 버전의 visual Studio에서는 직접 초기화에서 rvalue를 비 const 참조에 바인딩할 수 있었습니다. 이제이 코드는 경고를 제공 합니다.

이전 버전과의 호환성을 위해 여전히 rvalue을 비 const 참조에 바인딩할 수 있지만 가능한 경우 표준 변환이 선호 됩니다.

이 경고는 Visual C++ .net 2002 컴파일러의 동작 변경을 나타냅니다. 사용 하도록 설정 된 경우 올바른 코드에 대해이 경고가 발생할 수 있습니다. 예를 들어 **std:: auto_ptr** 클래스 템플릿을 사용할 때이를 지정할 수 있습니다.

이 경고가 표시 되는 경우 코드를 검사 하 여 const가 아닌 참조에 바인딩 rvalue에 따라 달라 지는 지 확인 합니다. 참조에 const를 추가 하거나 추가 const 참조 오버 로드를 제공 하면 문제가 해결 될 수 있습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

다음 샘플에서는 C4350를 생성 합니다.

```cpp
// C4350.cpp
// compile with: /W1
#pragma warning (default : 4350)
class A {};

class B
{
public:
   B(B&){}
   // try the following instead:
   // B(const B&){}

   B(A){}
   operator A(){ return A();}
};

B source() { return A(); }

int main()
{
   B ap(source());   // C4350
}
```
