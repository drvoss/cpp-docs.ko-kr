---
title: new(vtable의 새 슬롯)(C++/CLI 및 C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: 29e43fe4c462fa6ac6523f8627abf923f02247a8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214245"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>new(vtable의 새 슬롯)(C++/CLI 및 C++/CX)

**`new`** 키워드는 가상 멤버가 vtable에서 새 슬롯을 가져오도록 지정 합니다.

## <a name="all-runtimes"></a>모든 런타임

(이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)

## <a name="windows-runtime"></a>Windows 런타임

Windows 런타임에서는 지원되지 않습니다.

## <a name="common-language-runtime"></a>공용 언어 런타임

### <a name="remarks"></a>설명

컴파일에서는 `/clr` **`new`** 가상 멤버가 vtable에서 새 슬롯을 가져오기 때문에 함수가 기본 클래스 메서드를 재정의 하지 않음을 나타냅니다.

**`new`** 는 함수에 대 한 IL에 newslot 한정자를 추가 합니다.  newslot에 대한 자세한 내용은 다음을 참조하세요.

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/clr`

### <a name="examples"></a>예제

다음 샘플에서는의 효과를 보여 줍니다 **`new`** .

```cpp
// newslot.cpp
// compile with: /clr
ref class C {
public:
   virtual void f() {
      System::Console::WriteLine("C::f() called");
   }

   virtual void g() {
      System::Console::WriteLine("C::g() called");
   }
};

ref class D : public C {
public:
   virtual void f() new {
      System::Console::WriteLine("D::f() called");
   }

   virtual void g() override {
      System::Console::WriteLine("D::g() called");
   }
};

ref class E : public D {
public:
   virtual void f() override {
      System::Console::WriteLine("E::f() called");
   }
};

int main() {
   D^ d = gcnew D;
   C^ c = gcnew D;

   c->f();   // calls C::f
   d->f();   // calls D::f

   c->g();   // calls D::g
   d->g();   // calls D::g

   D ^ e = gcnew E;
   e->f();   // calls E::f
}
```

```Output
C::f() called

D::f() called

D::g() called

D::g() called

E::f() called
```

## <a name="see-also"></a>참고 항목

[.NET 및 UWP 용 구성 요소 확장](component-extensions-for-runtime-platforms.md)<br/>
[Override 지정자](override-specifiers-cpp-component-extensions.md)
