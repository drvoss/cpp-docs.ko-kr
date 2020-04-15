---
title: __cdecl
ms.date: 10/09/2018
f1_keywords:
- __cdecl_cpp
- __cdecl
- _cdecl
- cdecl
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
ms.openlocfilehash: b4a86c49880b0c40d402c7cec863f79e24bc4dc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371560"
---
# <a name="__cdecl"></a>__cdecl

**__cdecl** C 및 C++ 프로그램의 기본 호출 규칙입니다. 스택은 호출자에 의해 정리되므로 함수를 `vararg` 수행할 수 있습니다. **__cdecl** 호출 규칙은 스택 정리 코드를 포함하기 위해 각 함수 호출이 필요하기 때문에 [__stdcall](../cpp/stdcall.md)것보다 더 큰 실행 수(실행 가능)를 만듭니다. 다음 목록에서는 이러한 호출 규칙의 구현을 보여 줍니다. **__cdecl** 수정자는 Microsoft에 따라 다릅니다.

|요소|구현|
|-------------|--------------------|
|인수 전달 순서|오른쪽에서 왼쪽|
|스택 유지 관리 책임|호출하는 함수가 스택에서 인수를 꺼냅니다.|
|이름 데코레이션 규칙|밑줄 문자(_)는 C 연결을 사용하는 \__cdecl 함수를 내보내는 경우를 제외하고 이름에 접두사입니다.|
|대/소문자 변환 규칙|대/소문자 변환은 수행되지 않습니다.|

> [!NOTE]
> 관련 정보는 [장식된 이름을](../build/reference/decorated-names.md)참조하십시오.

변수 또는 함수 이름 앞에 **__cdecl** 수정자를 배치합니다. C 명명 및 호출 규칙이 기본값이므로 x86 코드에서 **__cdecl** 사용해야 하는 유일한 시간은 `/Gv` (벡터콜), (stdcall) `/Gz` 또는 `/Gr` (fastcall) 컴파일러 옵션을 지정한 경우에만 가능합니다. [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) 컴파일러 옵션은 **__cdecl** 호출 규칙을 강제로 사용합니다.

ARM 및 x64 프로세서에서는 **__cdecl** 허용되지만 일반적으로 컴파일러에서 무시됩니다. ARM 및 x64에서는 규칙에 따라 인수는 가능한 경우 레지스터로 전달되고 이후 인수는 스택에 전달됩니다. x64 코드에서 **__cdecl** 사용하여 **/Gv** 컴파일러 옵션을 재정의하고 기본 x64 호출 규칙을 사용합니다.

비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다. 다음의 클래스 정의를 가정해 봅니다.

```cpp
struct CMyClass {
   void __cdecl mymethod();
};
```

다음 코드는

```cpp
void CMyClass::mymethod() { return; }
```

다음 코드 조각과 일치합니다.

```cpp
void __cdecl CMyClass::mymethod() { return; }
```

이전 버전과의 호환성을 위해 **cdecl** 및 **_cdecl** 컴파일러 옵션 [ \(/Za Disable 언어 확장)이](../build/reference/za-ze-disable-language-extensions.md) 지정되지 않는 한 **__cdecl** 동의어입니다.

## <a name="example"></a>예제

다음 예제에서 컴파일러는 `system` 함수에 대해 C 명명 규칙 및 호출 규칙을 사용하도록 지시되었습니다.

```cpp
// Example of the __cdecl keyword on function
int __cdecl system(const char *);
// Example of the __cdecl keyword on function pointer
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);
```

## <a name="see-also"></a>참고 항목

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)<br/>
[키워드](../cpp/keywords-cpp.md)
