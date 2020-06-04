---
title: 링커 도구 오류 LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: 6090478c3761c477250b6706a350e261b51f2a05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353230"
---
# <a name="linker-tools-error-lnk2005"></a>링커 도구 오류 LNK2005

> *개체에* 이미 정의된 기호

기호 *기호가* 두 번 이상 정의되었습니다.

이 오류 뒤에 치명적인 오류 [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).

### <a name="possible-causes-and-solutions"></a>가능한 원인과 해결책

일반적으로 이 오류는 지정된 개체 파일에서 사용된 템플릿, 함수, 형식 또는 개체에 대해 하나의 정의만 허용하고 외부에서 보이는 개체 또는 함수에 대해 전체 실행 파일에 대해 하나의 정의만 허용하는 *하나의 정의 규칙을*위반했다는 것을 의미합니다.

이 오류의 몇 가지 일반적인 원인은 다음과 같습니다.

- 이 오류는 헤더 파일이 변수를 정의할 때 발생할 수 있습니다. 예를 들어 이 헤더 파일을 프로젝트에 두 개 이상의 소스 파일에 포함하면 다음과 같은 오류가 발생합니다.

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   가능한 솔루션은 다음과 같습니다.

  - 헤더 파일에서 `extern` 변수선언: `extern int global_int;`을 정의하고 선택적으로 하나의 소스 파일에서 만 `int global_int = 17;`초기화합니다. 이 변수는 이제 헤더 파일을 포함하여 선언하여 모든 `extern`소스 파일에서 사용할 수 있는 전역입니다. 전역이어야 하지만 좋은 소프트웨어 엔지니어링 사례는 전역 변수를 최소화하는 변수에 대해 이 솔루션을 권장합니다.

  - 변수 [정적](../../cpp/storage-classes-cpp.md#static)선언 `static int static_int = 17;`: . 이렇게 하면 정의 범위가 현재 개체 파일로 제한되고 여러 개체 파일이 변수의 고유한 복사본을 가질 수 있습니다. 전역 변수와 혼동될 수 있으므로 헤더 파일에서 정적 변수를 정의하는 것은 권장되지 않습니다. 정적 변수 정의를 사용하는 원본 파일로 이동하는 것을 선호합니다.

  - 변수 [selectany](../../cpp/selectany.md)선언 `__declspec(selectany) int global_int = 17;`: . 이렇게 하면 링커가 모든 외부 참조에서 사용할 하나의 정의를 선택하고 나머지는 삭제하도록 지시합니다. 이 솔루션은 가져오기 라이브러리를 결합할 때 유용할 수 있습니다. 그렇지 않으면 링커 오류를 방지하는 방법으로 사용하지 않는 것이 좋습니다.

- 이 오류는 헤더 파일이 없는 `inline`함수를 정의할 때 발생할 수 있습니다. 이 헤더 파일을 두 개 이상의 소스 파일에 포함하면 실행 파일에서 함수에 대한 여러 정의가 표시됩니다.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   가능한 솔루션은 다음과 같습니다.

  - 함수에 `inline` 키워드를 추가합니다.

    ```h
    // LNK2005_func_inline.h
    inline int sample_function(int k) { return 42 * (k % 167); }
    ```

  - 헤더 파일에서 함수 본문을 제거하고 선언만 남긴 다음 함수를 하나의 소스 파일에서만 구현합니다.

    ```h
    // LNK2005_func_decl.h
    int sample_function(int);
    ```

    ```cpp
    // LNK2005_func_impl.cpp
    int sample_function(int k) { return 42 * (k % 167); }
    ```

- 이 오류는 헤더 파일에서 클래스 선언 외부의 멤버 함수를 정의하는 경우에도 발생할 수 있습니다.

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   이 문제를 해결하려면 멤버 함수 정의를 클래스 내부로 이동합니다. 클래스 선언 내에 정의된 멤버 함수는 암시적으로 인라인됩니다.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- 이 오류는 표준 라이브러리 또는 CRT의 두 개 이상의 버전을 연결하는 경우 발생할 수 있습니다. 예를 들어 소매 CRT 라이브러리와 디버그 CRT 라이브러리또는 라이브러리의 정적 및 동적 버전 또는 표준 라이브러리의 두 가지 다른 버전을 실행 컴퓨터에 모두 연결하려고 하면 이 오류가 여러 번 보고될 수 있습니다. 이 문제를 해결하려면 링크 명령에서 각 라이브러리의 복사본을 제외한 모든 복사본을 제거합니다. 동일한 실행 에서 소매 및 디버그 라이브러리 또는 라이브러리의 다른 버전을 혼합 하지 않는 것이 좋습니다.

   링커에게 명령줄에서 기본값 이외의 라이브러리를 사용하도록 지시하려면 사용할 라이브러리를 지정하고 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 옵션을 사용하여 기본 라이브러리를 사용하지 않도록 설정합니다. IDE에서 사용할 라이브러리를 지정하기 위해 프로젝트에 대한 참조를 추가한 다음 프로젝트에 대한 **속성 페이지** 대화 상자를 열고 **Linker**의 **Input** 속성 페이지에서 모든 기본 **라이브러리 무시**또는 특정 기본 라이브러리 **속성을 무시하여** 기본 라이브러리를 사용하지 않도록 설정합니다.

- 이 오류는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용할 때 정적 및 동적 라이브러리사용을 혼합하는 경우에 발생할 수 있습니다. 예를 들어 정적 CRT에 연결되는 실행 수에서 사용할 DLL을 빌드하는 경우 이 오류가 발생할 수 있습니다. 이 문제를 해결하려면 전체 실행 및 실행 에서 사용할 빌드하는 라이브러리에 정적 라이브러리 또는 동적 라이브러리만 사용합니다.

- 이 오류는 기호가 [/Gy로](../../build/reference/gy-enable-function-level-linking.md)컴파일하여 생성된 패키지 함수이고 두 개 이상의 파일에 포함되었지만 컴파일 간에 변경된 경우에 발생할 수 있습니다. 이 문제를 해결하려면 패키지된 함수를 포함하는 모든 파일을 다시 컴파일합니다.

- 이 오류는 기호가 서로 다른 라이브러리의 두 멤버 개체에서 다르게 정의되고 두 멤버 개체가 모두 사용되는 경우에 발생할 수 있습니다. 라이브러리가 정적으로 연결된 경우 이 문제를 해결하는 한 가지 방법은 하나의 라이브러리에서만 멤버 개체를 사용하고 링커 명령줄에 먼저 해당 라이브러리를 포함하는 것입니다. 두 심볼을 모두 사용하려면 기호를 구분하는 방법을 만들어야 합니다. 예를 들어 소스에서 라이브러리를 빌드할 수 있는 경우 고유한 네임스페이스에서 각 라이브러리를 래핑할 수 있습니다. 또는 고유한 이름을 사용하여 참조를 원래 라이브러리 중 하나에 래핑하고 새 라이브러리를 원래 라이브러리에 연결한 다음 실행 파일을 원래 라이브러리 대신 새 라이브러리에 연결하는 새 래퍼 라이브러리를 만들 수 있습니다.

- 이 오류는 변수가 `extern const` 두 번 정의되고 각 정의에 다른 값을 가진 경우에 발생할 수 있습니다. 이 문제를 해결하려면 상수를 한 번만 정의하거나 `enum class` 네임스페이스 또는 정의를 사용하여 상수를 구별합니다.

- 이 오류는 GUID를 정의하는 다른 .lib 파일(예: oledb.lib 및 adsiid.lib)과 함께 uuid.lib를 사용하는 경우 발생할 수 있습니다. 다음은 그 예입니다.

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   이 문제를 해결하려면 링커 명령줄 [옵션에 /FORCE:MULTIPLE을](../../build/reference/force-force-file-output.md) 추가하고 uuid.lib가 참조된 첫 번째 라이브러리인지 확인합니다.
