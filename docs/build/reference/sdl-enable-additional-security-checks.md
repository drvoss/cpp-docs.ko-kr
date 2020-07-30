---
title: /sdl(추가 보안 검사 사용)
ms.date: 11/26/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: d5a85f9648ebcc4064146f22cf5da020e06b7ba3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218977"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl(추가 보안 검사 사용)

권장되는 SDL(Security Development Lifecycle) 검사를 추가합니다. 이러한 검사에는 오류와 같은 추가 보안 관련 경고 및 추가 보안 코드 생성 기능이 포함됩니다.

## <a name="syntax"></a>구문

> **`/sdl`**[**`-`**]

## <a name="remarks"></a>설명

**/sdl** 은에서 제공 하는 기본 보안 검사의 상위 집합을 사용 하도록 설정 [`/GS`](gs-buffer-security-check.md) **`/GS-`** 합니다. 기본적으로 **`/sdl`** 는 해제 되어 있습니다. **`/sdl-`** 추가 보안 검사를 사용 하지 않도록 설정 합니다.

## <a name="compile-time-checks"></a>컴파일 시 검사

**`/sdl`** 이러한 경고를 오류로 설정 합니다.

|/SDL에 의해 활성화된 경고|해당 명령줄 스위치|설명|
|------------------------------|-------------------------------------|-----------------|
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|단항 빼기 연산자가 부호 없는 형식에 적용되어 부호 없는 결과가 발생했습니다.|
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|음의 정수 상수가 부호 없는 형식으로 변환되어 의미 없는 결과가 발생할 수 있습니다.|
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|`continue` `break` 블록에서 또는 키워드를 사용 하면 `goto` `__finally` / `finally` 비정상 종료 중에 정의 되지 않은 동작이 발생 합니다.|
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|변수를 초기화 하는 코드가 실행되지 않습니다.|
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|초기화되지 않은 지역 변수 사용.|
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|잠재적으로 초기화되지 않은 지역 포인터 변수 사용.|
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|특정 CRT(C 런타임) 함수를 사용할 때 버퍼가 오버런됩니다.|
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Pragma로 표시 된 함수를 사용 [`deprecated`](../../preprocessor/deprecated-c-cpp.md) 합니다.|
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|로 표시 된 함수를 사용 [`deprecated`](../../cpp/deprecated-cpp.md) 합니다.|

## <a name="runtime-checks"></a>런타임 검사

을 사용 하는 경우 **`/sdl`** 컴파일러는 런타임에 이러한 검사를 수행 하는 코드를 생성 합니다.

- 를 사용 하 여 **`/GS`** 컴파일하는 것과 동등한, 런타임 버퍼 오버런 검색의 strict 모드를 사용 하도록 설정 `#pragma strict_gs_check(push, on)` 합니다.

- 제한된 포인터 삭제를 수행합니다. 사용자 정의 소멸자가 없는 형식에서 역참조 및를 포함 하지 않는 식에서는를 호출한 후 포인터 참조가 유효 하지 않은 주소로 설정 됩니다 **`delete`** . 이렇게 하면 오래된 포인터 참조가 재사용되지 않습니다.

- 클래스 멤버 포인터 초기화를 수행 합니다. **`nullptr`** 생성자가 실행 되기 전에 개체 인스턴스화에 대 한 포인터 형식의 클래스 멤버를 자동으로 초기화 합니다. 이렇게 하면 생성자가 명시적으로 초기화 하지 않는 초기화 되지 않은 포인터를 사용할 수 없습니다. 컴파일러에서 생성 된 멤버 포인터 초기화는 다음을 수행 하는 동안 호출 됩니다.

  - 사용자 지정 (사용자 정의)을 사용 하 여 개체가 할당 되지 않았습니다.`operator new`

  - 개체가 배열의 일부로 할당 되지 않은 경우 (예: `new A[x]` )

  - 클래스를 관리 하거나 가져올 수 없습니다.

  - 클래스에는 사용자 정의 기본 생성자가 있습니다.

  컴파일러에서 생성 된 클래스 초기화 함수로 초기화 되려면 멤버는 속성 또는 상수가 아니라 포인터 여야 합니다.

## <a name="remarks"></a>설명

자세한 내용은 [경고,/또는 sdl 및 초기화 되지 않은 변수 검색 향상](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)을 참조 하세요.

#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/c + +** 폴더를 선택 합니다.

1. **일반** 페이지의 **SDL 확인** 드롭다운 목록에서 옵션을 선택 합니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
