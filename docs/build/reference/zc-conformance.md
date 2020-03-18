---
title: /Zc(규칙)
ms.date: 03/06/2018
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 4422524deab2a749c96d5e967bc3223d0c9c9873
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438663"
---
# <a name="zc-conformance"></a>/Zc(규칙)

**/Zc** 컴파일러 옵션을 사용 하 여 표준 또는 Microsoft 전용 컴파일러 동작을 지정할 수 있습니다.

## <a name="syntax"></a>구문

> **/Zc:** _option_{,_option_}

## <a name="remarks"></a>설명

Visual Studio가 C에 대 한 확장을 구현 C++ 하거나 표준과 호환 되지 않는 경우 `/Zc` 규칙 옵션을 사용 하 여 표준에 맞는 또는 Microsoft 특정 동작을 지정할 수 있습니다. 일부 옵션의 경우 기존 코드에 대 한 대규모 주요 변경 사항을 방지 하기 위해 Microsoft 고유의 동작이 기본값입니다. 다른 경우에 기본값은 표준 동작으로, 보안, 성능 또는 호환성의 향상 된 기능이 주요 변경 비용 보다 더 중요 합니다. 각 규칙 옵션의 기본 설정은 최신 버전의 Visual Studio에서 변경 될 수 있습니다. 각 규칙 옵션에 대 한 자세한 내용은 특정 옵션에 대 한 항목을 참조 하세요. [/Permissive-](permissive-standards-conformance.md) 컴파일러 옵션은 기본적으로 설정 되지 않은 규칙 옵션을 해당 하는 규칙 설정으로 암시적으로 설정 합니다.

`/Zc` 컴파일러 옵션은 다음과 같습니다.

|옵션|동작|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C + + 17 오버 정렬 된 동적 할당을 사용 합니다 (기본적으로 c + + 17의 경우).|
|[자동\[-\]](zc-auto-deduce-variable-type.md)|`auto`에 대해 새로운 C++ 표준 의미를 적용 합니다 (기본적으로 설정).|
|[__cplusplus\[-\]](zc-cplusplus.md)|**__Cplusplus** 매크로를 사용 하 여 지원 되는 표준 (기본적으로 해제)을 보고 합니다.|
|[externConstexpr\[-\]](zc-externconstexpr.md)|`constexpr` 변수에 대해 외부 링크를 사용 하도록 설정 합니다 (기본적으로 해제).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|표준 C++ `for` 범위 지정 규칙을 적용 합니다 (기본적으로 설정).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|필요한 함수에 대해 암시적 `noexcept`를 사용 하도록 설정 합니다 (기본적으로 설정).|
|[인라인\[-\]](zc-inline-remove-unreferenced-comdat.md)|참조 되지 않은 함수 또는 데이터는 COMDAT 이거나 내부 링크만 있는 경우 (기본적으로 해제 됨) 제거 합니다.|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C + + 17 noexcept 규칙을 적용 합니다 (c + + 17 이상에서는 기본적으로 설정).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT 임시는 비 const lvalue 참조에 바인딩되지 않습니다 (기본적으로 해제 됨).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|표준 C++ 명시적 형식 변환 규칙을 적용 합니다 (기본적으로 해제).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C + + 14 전역 크기 할당 해제 함수를 사용 합니다 (기본적으로 설정).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|문자열 리터럴을 사용 하지 않도록 설정 하 `char*` 또는 `wchar_t*` 변환 (기본적으로 해제).|
|[삼항\[-\]](zc-ternary.md)|피연산자 형식에 조건부 연산자 규칙을 적용 합니다 (기본적으로 꺼져 있습니다).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|스레드로부터 안전한 로컬 정적 초기화를 사용 하도록 설정 합니다 (기본적으로 설정).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|오류가 발생 한 경우 (기본적으로 해제) `operator new` throw 한다고 가정 합니다.|
|[삼중 자\[-\]](zc-trigraphs-trigraphs-substitution.md)|삼중 자 (사용 되지 않음, 기본적으로 해제)를 사용 합니다.|
|[twoPhase](zc-twophase.md)|순응 하지 않는 템플릿 구문 분석 동작을 사용 합니다 (기본적으로 준수).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t`는 typedef가 아닌 네이티브 형식입니다 (기본적으로 설정 됨).|

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
