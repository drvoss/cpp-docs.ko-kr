---
title: 컴파일러 오류 C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 321ccd23bc273f5fa548f75fd44bc320bcf4c426
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225516"
---
# <a name="compiler-error-c2384"></a>컴파일러 오류 C2384

'member' : 관리되는 클래스 또는 WinRT 클래스의 멤버에__declspec(thread)를 적용할 수 없습니다.

[Thread](../../cpp/thread.md) **`__declspec`** 한정자는 관리 되는 클래스 또는 Windows 런타임 클래스의 멤버에서 사용할 수 없습니다.

관리 코드의 정적 스레드 로컬 스토리지는 정적으로 로드된 DLL에 대해서만 사용할 수 있습니다(프로세스가 시작될 때 DLL을 정적으로 로드해야 함). Windows 런타임은 스레드 로컬 스토리지를 지원하지 않습니다.

다음 줄은 C++/CLI 코드에서 C2384 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2384.cpp
// compile with: /clr /c
public ref class B {
public:
   __declspec( thread ) static int tls_i = 1;   // C2384

   // OK - declare with attribute instead
   [System::ThreadStaticAttribute]
   static int tls_j;
};
```
