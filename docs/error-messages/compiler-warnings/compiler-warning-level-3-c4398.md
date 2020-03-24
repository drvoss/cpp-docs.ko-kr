---
title: 컴파일러 경고(수준 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 041bf9f6bfce17b16f301604bb8706be30095c13
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198668"
---
# <a name="compiler-warning-level-3-c4398"></a>컴파일러 경고(수준 3) C4398

> '*variable*': 여러 appdomain에서 프로세스별 전역 개체가 제대로 작동 하지 않을 수 있습니다. __declspec (appdomain) 사용 고려

## <a name="remarks"></a>주의

네이티브 형식에서 [__clrcall](../../cpp/clrcall.md) 호출 규칙을 사용 하는 가상 함수를 사용 하면 응용 프로그램 도메인 vtable 마다 생성 됩니다. 이러한 변수는 여러 응용 프로그램 도메인에서 사용 되는 경우 올바르게 수정 되지 않을 수 있습니다.

변수 `__declspec(appdomain)`명시적으로 표시 하 여이 경고를 해결할 수 있습니다. Visual studio 2017 이전의 Visual Studio 버전에서는 **/clr: pure**를 사용 하 여 컴파일하여이 경고를 해결할 수 있습니다. 이렇게 하면 기본적으로 appdomain 당 전역 변수가 만들어집니다. **/Clr: pure** 컴파일러 옵션은 visual studio 2015에서는 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [응용 프로그램 도메인 및 시각적 개체 C++ ](../../dotnet/application-domains-and-visual-cpp.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4398를 생성 합니다.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```
