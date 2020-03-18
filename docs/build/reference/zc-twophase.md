---
title: /Zc:twoPhase-(2단계 이름 조회를 사용하지 않도록 설정)
description: '/Zc: twoPhase-/permissive-가 지정 된 경우 2 단계 이름 조회를 사용 하지 않도록 설정 하는 방법을 설명 합니다.'
ms.date: 12/03/2019
f1_keywords:
- twoPhase
- /Zc:twoPhase
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: 3464759793a2dd243024a9f3f52263f76514033a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438645"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(2단계 이름 조회를 사용하지 않도록 설정)

**/Permissive-** 아래의 C++ **/Zc: twophase-** 옵션은 컴파일러에 준수 하지 않는 원래 Microsoft 컴파일러 동작을 사용 하 여 클래스 템플릿 및 함수 템플릿을 구문 분석 하 고 인스턴스화합니다.

## <a name="syntax"></a>구문

> **/Zc: twoPhase-**

## <a name="remarks"></a>설명

Visual Studio 2017 버전 15.3 이상: [/Permissive-](permissive-standards-conformance.md)에서 컴파일러는 템플릿 이름 확인을 위해 2 단계 이름 조회를 사용 합니다. **/Zc: twoPhase-** 도 지정 하는 경우 컴파일러는 이전의 비호환 클래스 템플릿과 함수 템플릿 이름 확인 및 대체 동작으로 되돌립니다. **/Permissive-** 가 지정 되지 않은 경우에는 순응 하지 않는 동작이 기본값입니다.

버전 10.0.15063.0 (크리에이터 Update 또는 RS2) 및 이전 버전의 Windows SDK 헤더 파일은 규칙 모드에서 작동 하지 않습니다. **/Zc: twoPhase-** **/permissive-** 를 사용 하는 경우 해당 SDK 버전에 대 한 코드를 컴파일하는 데 필요 합니다. 버전 10.0.15254.0 () 버전으로 시작 하는 Windows SDK 버전은 규칙 모드에서 제대로 작동 합니다. **/Zc: twoPhase-** 옵션은 필요 하지 않습니다.

코드에 이전 동작이 올바르게 컴파일되도록 하려면 **/zc: twoPhase** 를 사용 합니다. 표준에 맞게 코드를 업데이트 하는 것이 좋습니다.

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc: twoPhase에서의 컴파일러 동작

기본적으로 **/permissive-** 및 **/Zc: twoPhase**를 둘 다 지정 하는 경우 Visual Studio 2017 버전 15.3 이상에서는 컴파일러에서 다음 동작을 사용 합니다.

- 템플릿 선언, 클래스 헤드 및 기본 클래스 목록만 구문 분석 합니다. 템플릿 본문은 토큰 스트림으로 캡처됩니다. 함수 본문, 이니셜라이저, 기본 인수 또는 noexcept 인수는 구문 분석 되지 않습니다. 클래스 템플릿은 클래스 템플릿의 선언이 올바른지 유효성을 검사 하기 위해 미정 형식에 대해 의사 (pseudo)로 인스턴스화됩니다. 이 클래스 템플릿을 살펴보겠습니다.

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   템플릿 선언 `template <typename T>`, 클래스 헤드 `class Derived`및 기본 클래스 목록 `public Base<T>` 구문 분석 되지만 템플릿 본문은 토큰 스트림으로 캡처됩니다.

- 함수 템플릿을 구문 분석할 때 컴파일러는 함수 서명만 구문 분석 합니다. 함수 본문은 구문 분석 되지 않습니다. 대신 토큰 스트림으로 캡처됩니다.

결과적으로 템플릿 본문에 구문 오류가 있지만 템플릿이 인스턴스화되지 않을 경우 컴파일러는 오류를 진단 하지 않습니다.

이 동작의 또 다른 효과는 오버 로드 확인입니다. 비표준 동작은 인스턴스화 사이트에서 토큰 스트림이 확장 되는 방식 때문에 발생 합니다. 템플릿 선언에 표시 되지 않은 기호는 인스턴스화 시점에 표시 될 수 있습니다. 이는 오버 로드 확인에 참여할 수 있음을 의미 합니다. 표준에 따라 템플릿 정의에 표시 되지 않는 코드를 기반으로 템플릿 변경 동작을 찾을 수 있습니다.

다음 코드를 예로 들 수 있습니다.

```cpp
// zctwophase.cpp
// To test options, compile by using
// cl /EHsc /nologo /W4 zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- zctwophase.cpp
// cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp

#include <cstdio>

void func(long) { std::puts("Standard two-phase") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("Microsoft one-phase"); }

int main()
{
    g(6174);
}
```

다음은 **/zc: twoPhase-** 컴파일러 옵션을 사용 하 여 기본 모드, 규칙 모드 및 규칙 모드를 사용 하는 경우의 출력입니다.

```cmd
C:\Temp>cl /EHsc /nologo /W4 zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- zctwophase.cpp && zctwophase
zctwophase.cpp
Standard two-phase

C:\Temp>cl /EHsc /nologo /W4 /permissive- /Zc:twoPhase- zctwophase.cpp && zctwophase
zctwophase.cpp
Microsoft one-phase
```

**/Permissive-** 아래의 규칙 모드에서 컴파일될 때이 프로그램은 컴파일러가 템플릿에 도달할 때 `func`의 두 번째 오버 로드가 표시 되지 않기 때문에 "`Standard two-phase`"을 출력 합니다. **/Zc: twoPhase-** 를 추가 하면 프로그램에서 "`Microsoft one-phase`"을 출력 합니다. 출력은 **/permissive-** 를 지정 하지 않는 경우와 동일 합니다.

*종속 이름은* 템플릿 매개 변수에 종속 된 이름입니다. 이러한 이름에는 **/zc: twoPhase-** 와도 다른 조회 동작이 있습니다. 규칙 모드에서 종속 이름은 템플릿의 정의 지점에서 바인딩되지 않습니다. 대신, 컴파일러가 템플릿을 인스턴스화할 때이를 찾습니다. 종속 함수 이름을 사용 하는 함수 호출의 경우 이름이 템플릿 정의의 호출 사이트에서 표시 되는 함수에 바인딩됩니다. 인수 종속 조회의 추가 오버 로드는 템플릿 정의의 지점 및 템플릿 인스턴스화 시점에 추가 됩니다.

2 단계 조회는 템플릿 정의 중에 종속 되지 않은 이름에 대 한 조회와 템플릿 인스턴스화 중에 종속 이름을 조회 하는 두 부분으로 구성 됩니다. **/Zc: twoPhase-** 에서 컴파일러는 정규화 되지 않은 조회와는 별도로 인수 종속 조회를 수행 하지 않습니다. 즉, 2 단계 조회를 수행 하지 않으므로 오버 로드 확인 결과가 다를 수 있습니다.

다른 예제는 다음과 같습니다.

```cpp
// zctwophase1.cpp
// To test options, compile by using
// cl /EHsc /W4 zctwophase1.cpp
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

**/Permissive-** 없이 컴파일될 때이 코드는 다음을 출력 합니다.

```Output
func(int)
NS::func(NS::S)
```

**/Permissive-** 를 사용 하 여 컴파일할 때 **/Zc: twoPhase**를 사용 하지 않으면이 코드는 다음을 출력 합니다.

```Output
func(long)
NS::func(NS::S)
```

**/Permissive-** 및 **/Zc: twoPhase**를 모두 사용 하 여 컴파일하면이 코드는 다음과 같이 출력 됩니다.

```Output
func(int)
NS::func(NS::S)
```

**/Permissive-** 아래의 규칙 모드에서 호출 `tfunc(1729)` `void func(long)` 오버 로드로 확인 됩니다. **/Zc: twoPhase-** 에서와 같이 `void func(int)` 오버 로드로 확인 되지 않습니다. 정규화 되지 않은 `func(int)`는 템플릿 정의 후에 선언 되 고 인수 종속 조회를 통해 찾을 수 없기 때문입니다. 그러나 `void func(S)`는 인수 종속 조회에 참여 하므로 템플릿 함수 다음에 선언 된 경우에도 호출 `tfunc(s)`에 대해 설정 된 오버 로드에 추가 됩니다.

### <a name="update-your-code-for-two-phase-conformance"></a>2 단계 규칙에 맞게 코드를 업데이트 합니다.

이전 버전의 컴파일러에서는 `template` 키워드가 필요 하지 않으며 표준에 C++ 필요한 모든 곳에서 `typename`. 이러한 키워드는 컴파일러가 조회의 첫 번째 단계에서 종속 이름을 구문 분석 해야 하는 방법을 구분 하기 위해 일부 위치에서 필요 합니다. 다음은 그 예입니다.

`T::Foo<a || b>(c);`

준수 하는 컴파일러는 `T`범위에서 변수로 `Foo`를 구문 분석 합니다. 즉,이 코드는 왼쪽 피연산자로 `T::foo < a`를 사용 하 고 오른쪽 피연산자와 `b > (c)`는 논리적 or 식입니다. `Foo`를 함수 템플릿으로 사용 하는 경우 `template` 키워드를 추가 하 여 템플릿이 되도록 지정 해야 합니다.

`T::template Foo<a || b>(c);`

Visual Studio 2017 버전 15.3 이상에서 **/permissive-** 및 **/Zc: twoPhase가** 지정 된 경우 컴파일러는 `template` 키워드 없이이 코드를 허용 합니다. 이 코드는 제한 된 방식 으로만 템플릿을 구문 분석 하므로 `a || b`의 인수를 사용 하 여 코드를 함수 템플릿에 대 한 호출로 해석 합니다. 위의 코드는 첫 번째 단계에서는 구문 분석 되지 않습니다. 두 번째 단계에서는 `T::Foo`가 변수가 아니라 템플릿이 되도록 지시할 수 있는 충분 한 컨텍스트가 있으므로 컴파일러는 키워드 사용을 적용 하지 않습니다.

이 동작은 함수 템플릿 본문의 이름 앞에 `typename` 키워드를 제거 하거나 이니셜라이저, 기본 인수 및 noexcept 인수를 제거 하 여 볼 수도 있습니다. 다음은 그 예입니다.

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

함수 본문에서 `typename` 키워드를 사용 하지 않는 경우이 코드는 **/Permissive-/zc: twoPhase-** 에서 컴파일되지만 **/permissive-** 만으로는 사용 되지 않습니다. `typename` 키워드는 `TYPE` 종속 되어 있음을 나타내는 데 필요 합니다. 이 본문은 **/zc: twoPhase**에서 구문 분석 되지 않으므로 컴파일러 does't에 키워드가 필요 합니다. **/Permissive-** 규칙 모드에서 `typename` 키워드가 없는 코드는 오류를 생성 합니다. Visual Studio 2017 버전 15.3 이상에서 코드를 준수 하도록 마이그레이션하려면 `typename` 키워드가 없는 위치에 삽입 합니다.

마찬가지로, 다음 코드 샘플을 고려해 보세요.

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

**/Permissive-/zc: twoPhase-** 및 이전 컴파일러에서 컴파일러는 2 줄의 `template` 키워드만 필요 합니다. 규칙 모드에서 컴파일러는 이제 `T::X<T>` 템플릿이 템플릿인 것을 나타내기 위해 줄 4의 `template` 키워드가 필요 합니다. 이 키워드가 누락 된 코드를 찾고 코드를 표준에 맞게 설정 합니다.

규칙 문제에 대 한 자세한 내용은 [ C++ Visual Studio의 규칙 향상](../../overview/cpp-conformance-improvements.md) 및 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조 하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **/Zc: twoPhase** 를 포함 하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참고 항목

[/Zc(규칙)](zc-conformance.md)
