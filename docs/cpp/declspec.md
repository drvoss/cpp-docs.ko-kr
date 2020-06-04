---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: e0c99ea9379aa6e29096250e8bd36ce3d4f183e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180227"
---
# <a name="__declspec"></a>__declspec

**Microsoft 전용**

저장소 클래스 정보를 지정 하기 위한 확장 특성 구문은 **__declspec** 키워드를 사용 합니다 .이 키워드는 지정 된 형식의 인스턴스가 아래 나열 된 Microsoft 전용 저장소 클래스 특성과 함께 저장 되도록 지정 합니다. 다른 저장소 클래스 한정자의 예로는 **static** 및 **extern** 키워드를 들 수가 있습니다. 그러나 이 키워드는 C 및 C++ 언어의 ANSI 사양에 포함되므로 확장 특성 구문에는 사용되지 않습니다. 확장명 특성 구문은 C 및 C++ 언어에 대한 Microsoft 전용 확장을 간소화하고 표준화합니다.

## <a name="grammar"></a>문법

*decl-지정자*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *확장-decl-시퀀스* **)**

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;확장- *decl* -한정자- *시퀀스*

*extended-decl-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**맞춤 (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**할당 ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**할당자**<br/>
**appdomain** &nbsp;&nbsp;&nbsp;&nbsp;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**사용 되지 않음**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**프로세스**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**속성 (** { **get =** _get_func_name_ &#124; **, put =** _put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**제한**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**스펙터 (nomitigation)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uuid ("** *comobjectguid* **")**

공백은 선언 한정자 시퀀스를 구분합니다. 뒤에 나오는 단원에 예제가 있습니다.

확장 특성 문법은 이러한 Microsoft 전용 저장소 클래스 특성을 지원 합니다. [align](../cpp/align-cpp.md), [allocate](../cpp/allocate.md), [할당자](../cpp/allocator.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [사용 되지 않음](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noalias](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md), [process](../cpp/process.md), [restrict](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [ 스펙터](../cpp/spectre.md)및 [thread](../cpp/thread.md) 또한 [속성](../cpp/property-cpp.md) 및 [UUID](../cpp/uuid-cpp.md)와 같은 COM 개체 특성도 지원 합니다.

**Code_seg**, **dllexport**, **dllimport**, **naked**, **noalias**, **nothrow**, **property**, **restrict**, **selectany**, **thread**및 **uuid** 저장소 클래스 특성은 해당 특성이 적용 되는 개체 또는 함수의 선언에만 해당 되는 속성입니다. **Thread** 특성은 데이터 및 개체에만 영향을 줍니다. **Naked** 및 **스펙터** 특성은 함수에만 영향을 줍니다. **Dllimport** 및 **dllexport** 특성은 함수, 데이터 및 개체에 영향을 줍니다. **속성**, **selectany**및 **uuid** 특성은 COM 개체에 영향을 줍니다.

이전 버전과의 호환성을 위해 **_declspec** 는 컴파일러 옵션 [/za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__declspec** 의 동의어입니다.

**__Declspec** 키워드는 간단한 선언의 시작 부분에 배치 해야 합니다. 컴파일러는 * 또는 & 뒤에, 선언에서 변수 식별자 앞에 배치 된 **__declspec** 키워드를 경고 없이 무시 합니다.

사용자 정의 형식 선언의 시작 부분에 지정 된 **__declspec** 특성은 해당 형식의 변수에 적용 됩니다. 다음은 그 예입니다.

```cpp
__declspec(dllimport) class X {} varX;
```

이 경우 특성이 `varX`에 적용됩니다. **클래스** 또는 **구조체** 키워드 뒤에 배치 되는 **__declspec** 특성은 사용자 정의 형식에 적용 됩니다. 다음은 그 예입니다.

```cpp
class __declspec(dllimport) X {};
```

이 경우 특성이 `X`에 적용됩니다.

단순 선언에 **__declspec** 특성을 사용 하기 위한 일반적인 지침은 다음과 같습니다.

*decl-지정자-시퀀스* *init-선언 목록*

*Decl 지정자-시퀀스* 에는 기타 항목, 기본 형식 (예: **int**, **float**, **typedef**또는 클래스 이름), 저장소 클래스 (예: **static**, **extern**) 또는 **__declspec** 확장을 포함 해야 합니다. *Init 선언 자 목록* 에는 선언의 포인터 부분을 포함 해야 합니다. 다음은 그 예입니다.

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

다음 코드는 정수 스레드 지역 변수를 선언하고 값을 사용하여 초기화합니다.

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[C 확장 스토리지 클래스 특성](../c-language/c-extended-storage-class-attributes.md)
