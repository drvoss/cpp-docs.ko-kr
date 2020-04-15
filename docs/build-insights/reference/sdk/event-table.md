---
title: 'C++ 인사이트 SDK 구축: 이벤트 테이블'
description: 비주얼 스튜디오 C++ 빌드 인사이트 SDK에 대한 이벤트 참조
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 932b78347e05d313e7962da2fdff8c3454dec963
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324132"
---
# <a name="c-build-insights-sdk-event-table"></a>C++ 인사이트 SDK 구축: 이벤트 테이블

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>컴파일러 이벤트

[컴파일러](#compiler)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>컴파일러 프런트 엔드 이벤트

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>컴파일러 백 엔드 이벤트

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[스레드](#thread)\
[함수](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>링커 이벤트

[링커](#linker)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[패스 1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[LTCG](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[패스2](#pass2)

## <a name="event-table"></a>이벤트 테이블

| 이벤트 | 속성 | Description |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | Type | 활동 |
|  | 부모 항목 | [컴파일러](#compiler) |
|  | Children | [C2_DLL](#c2-dll) |
|  | 속성 | - 입력 소스 파일에 대한 절대 경로<br/>- 출력 객체 파일에 대한 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[컴파일러 패스](cpp-event-data-types/compiler-pass.md)<br/>[백엔드 패스](cpp-event-data-types/back-end-pass.md) |
|  | Description | 컴파일러 백 엔드 패스의 시작 및 중지에서 발생합니다. 이 패스는 구문 분석된 C/C++ 소스 코드를 최적화하고 이를 컴퓨터 코드로 변환합니다. |
| <a name="bottom-up"></a>BOTTOM_UP | Type | 활동 |
|  | 부모 항목 | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[상향식](cpp-event-data-types/bottom-up.md) |
|  | Description | 전체 프로그램 분석의 상향식 패스의 시작 및 중지시 발생합니다. |
| <a name="c1-dll"></a>C1_DLL | Type | 활동 |
|  | 부모 항목 | [FRONT_END_PASS](#front-end-pass) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Description | *c1.dll 또는 c1xx.dll* 호출의 시작 및 중지에서 발생합니다. *c1xx.dll* 이러한 DLL은 컴파일러의 C 및 C++ 프런트 엔드입니다. 컴파일러*드라이버(cl.exe)에*의해서만 호출됩니다. |
| <a name="c2-dll"></a>C2_DLL | Type | 활동 |
|  | 부모 항목 | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Children | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Description | *c2.dll* 호출의 시작 및 중지에서 발생합니다. 이 DLL은 컴파일러의 백 엔드입니다. 컴파일러*드라이버(cl.exe)에서 호출합니다.* 또한 링크 시간 코드 생성을 사용할 때*링커(link.exe)에*의해 호출됩니다. |
| <a name="code-generation"></a>CODE_GENERATION | Type | 활동 |
|  | 부모 항목 | [C2_DLL](#c2-dll) |
|  | Children | [함수](#function)<br/>[스레드](#thread) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[코드 제너레이션](cpp-event-data-types/code-generation.md) |
|  | Description | 백 엔드의 코드 생성 단계의 시작 및 중지에서 발생합니다. |
| <a name="command-line"></a>COMMAND_LINE | Type | 단순 이벤트 |
|  | 부모 항목 | [컴파일러](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - *cl.exe* 또는 *link.exe를* 호출하는 데 사용된 명령줄 |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[명령줄](cpp-event-data-types/command-line.md) |
|  | Description | 컴파일러와 링커가 명령줄 평가를 완료할 때 발생합니다. 평가된 명령줄에는 응답 파일을 통해 전달된 모든 *cl.exe* 및 *link.exe* 매개 변수가 포함됩니다. 또한 CL, CL, \_\_LINK 및 \_LINK와\_같은 환경 변수를 통해 전달된 *cl.exe* 및 *link.exe매개* 변수도 포함됩니다. |
| <a name="compiler"></a>컴파일러 | Type | 활동 |
|  | 부모 항목 | 없음 |
|  | Children | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | 속성 | - 컴파일러 버전<br/>- 작업 디렉토리<br/>- 호출 된 *cl.exe에* 대한 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[호출](cpp-event-data-types/invocation.md)<br/>[컴파일러](cpp-event-data-types/compiler.md) |
|  | Description | *cl.exe* 호출의 시작 및 중지에서 발생합니다. |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Type | 단순 이벤트 |
|  | 부모 항목 | [컴파일러](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - 환경 변수의 이름<br/>- 환경 변수의 값입니다. |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Description | *cl.exe* 또는 *link.exe가* 호출될 때 모든 기존 환경 변수에 대해 한 번 발생합니다. |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - DLL 또는 실행 파일 출력 파일에 대한 절대 경로입니다. |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 출력](cpp-event-data-types/file-output.md)<br/>[실행 가능한이미지출력](cpp-event-data-types/executable-image-output.md) |
|  | Description | 링커 입력 중 하나가 DLL 또는 실행 파일 이미지 파일인 경우에 발생합니다. |
| <a name="exp-output"></a>EXP_OUTPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - *.exp* 출력 파일에 대한 절대 경로입니다. |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 출력](cpp-event-data-types/file-output.md)<br/>[출력 량](cpp-event-data-types/exp-output.md) |
|  | Description | 링커 출력 중 하나가 *.exp* 파일인 경우에 발생합니다. |
| <a name="file-input"></a>FILE_INPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [컴파일러](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - 입력 파일에 대한 절대 경로<br/>- 입력 파일의 유형 |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 입력](cpp-event-data-types/file-input.md) |
|  | Description | *cl.exe* 또는 *link.exe* 입력을 발표하기 위해 발생합니다. |
| <a name="force-inlinee"></a>FORCE_INLINEE | Type | 단순 이벤트 |
|  | 부모 항목 | [함수](#function) |
|  | Children | 없음 |
|  | 속성 | - 힘이 들어인 함수의 이름입니다.<br/>- 중간 명령 수로 표시되는 힘 인라인 함수의 크기입니다. |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[포스인린](cpp-event-data-types/force-inlinee.md) |
|  | Description | 키워드를 사용하여 `__forceinline` 함수가 다른 함수에 강제로 인라인되는 경우에 발생합니다. |
| <a name="front-end-file"></a>FRONT_END_FILE | Type | 활동 |
|  | 부모 항목 | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | - 파일에 대한 절대 경로입니다. |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[프론트 엔드 파일](cpp-event-data-types/front-end-file.md) |
|  | Description | 컴파일러 프런트 엔드가 파일 처리를 시작하고 중지할 때 발생합니다. 이 이벤트는 재귀적입니다. 재귀는 프런트 엔드가 포함된 파일을 구문 분석할 때 발생합니다. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Type | 활동 |
|  | 부모 항목 | [컴파일러](#compiler) |
|  | Children | [C1_DLL](#c1-dll) |
|  | 속성 | - 입력 소스 파일에 대한 절대 경로<br/>- 출력 객체 파일에 대한 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[컴파일러 패스](cpp-event-data-types/compiler-pass.md)<br/>[프론트엔드패스](cpp-event-data-types/front-end-pass.md) |
|  | Description | 컴파일러 프런트 엔드 패스의 시작 및 종료시 발생합니다. 이 패스는 C/C++ 소스 코드를 구문 분석하여 중간 언어로 변환합니다. |
| <a name="function"></a>함수 | Type | 활동 |
|  | 부모 항목 | [CODE_GENERATION](#code-generation)<br/>[스레드](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FORCE_INLINEE](#force-inlinee) |
|  | 속성 | - 기능의 이름 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[기능](cpp-event-data-types/function.md) |
|  | Description | 함수에 대한 코드를 생성하기 시작하고 끝낼 때 발생합니다. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - 가져오기 라이브러리 출력 파일에 대한 절대 경로입니다. |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 출력](cpp-event-data-types/file-output.md)<br/>[임립출력](cpp-event-data-types/imp-lib-output.md) |
|  | Description | 링커의 출력 중 하나가 가져오기 라이브러리인 경우에 발생합니다. |
| <a name="lib-output"></a>LIB_OUTPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - 정적 라이브러리 출력 파일에 대한 절대 경로입니다. |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 출력](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | Description | 링커의 출력 중 하나가 정적 라이브러리인 경우에 발생합니다. |
| <a name="linker"></a>링커 | Type | 활동 |
|  | 부모 항목 | 없음 |
|  | Children | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[패스 1](#pass1)<br/>[패스2](#pass2) |
|  | 속성 | - 링커 버전<br/>- 작업 디렉토리<br/>- 호출 된 *link.exe에* 대한 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[호출](cpp-event-data-types/invocation.md)<br/>[링커](cpp-event-data-types/linker.md) |
|  | Description | *link.exe* 호출의 시작 및 중지에서 발생합니다. |
| <a name="ltcg"></a>LTCG | Type | 활동 |
|  | 부모 항목 | [패스 1](#pass1) |
|  | Children | [C2_DLL](#c2-dll) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Description | 링크 시간 코드 생성의 시작 및 중지시 발생합니다. |
| <a name="obj-output"></a>OBJ_OUTPUT | Type | 단순 이벤트 |
|  | 부모 항목 | [컴파일러](#compiler) |
|  | Children | 없음 |
|  | 속성 | - *.obj* 출력 파일에 대한 절대 경로 |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[파일 출력](cpp-event-data-types/file-output.md)<br/>[Obj출력](cpp-event-data-types/obj-output.md) |
|  | Description | *cl.exe에서*생성된 모든 *.obj* 출력에 대해 한 번 발생합니다. |
| <a name="opt-icf"></a>OPT_ICF | Type | 활동 |
|  | 부모 항목 | [패스 1](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[옵티피피그](cpp-event-data-types/opt-icf.md) |
|  | Description | 동일한 COMDAT 폴딩(/OPT:ICF) 링커 최적화의 시작 및 중지에서 발생합니다. |
| <a name="opt-lbr"></a>OPT_LBR | Type | 활동 |
|  | 부모 항목 | [패스 1](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[옵틀브르](cpp-event-data-types/opt-lbr.md) |
|  | Description | 긴 분기(/OPT:LBR) 링커 최적화의 시작 및 중지에서 발생합니다. |
| <a name="opt-ref"></a>OPT_REF | Type | 활동 |
|  | 부모 항목 | [패스 1](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[옵트레프](cpp-event-data-types/opt-ref.md) |
|  | Description | 참조되지 않은 함수 및 데이터 제거(/OPT:REF) 링커 최적화의 시작 및 중지시 발생합니다. |
| <a name="pass1"></a>패스 1 | Type | 활동 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[패스 1](cpp-event-data-types/pass1.md) |
|  | Description | 링커의 패스 1의 시작과 끝에서 발생합니다. |
| <a name="pass2"></a>패스2 | Type | 활동 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[패스 2](cpp-event-data-types/pass2.md) |
|  | Description | 링커의 패스 2의 시작과 끝에서 발생합니다. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Type | 활동 |
|  | 부모 항목 | [패스 1](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[프리트CG옵트레프](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Description | 참조되지 않은 함수 및 데이터(/OPT:REF)를 제거하는 링커 최적화 패스의 시작 및 중지시 발생합니다. 링크 시간 코드 생성 전에 수행됩니다. |
| <a name="symbol-name"></a>SYMBOL_NAME | Type | 단순 이벤트 |
|  | 부모 항목 | [C1_DLL](#c1-dll) |
|  | Children | 없음 |
|  | 속성 | - 유형 키<br/> - 유형 이름 |
|  | 클래스 캡처 | [심플 이벤트](cpp-event-data-types/simple-event.md)<br/>[기호 이름](cpp-event-data-types/symbol-name.md) |
|  | Description | 프런트 엔드 패스의 끝에서 발생: 템플릿 인스턴스화에 관련 된 모든 형식에 대 한 한 번. 키는 형식의 숫자 식별자이며 이름은 텍스트 표현입니다. 형식 키는 분석중인 추적 내에서 고유합니다. 그러나 다른 컴파일러 프런트 엔드 패스에서 오는 다른 키는 동일한 형식을 가리킬 수 있습니다. 다른 컴파일러 프런트 엔드 패스 간의 형식을 비교하려면 해당 이름을 사용해야합니다. SYMBOL_NAME 이벤트는 모든 템플릿 인스턴스화가 발생한 후 컴파일러 프런트 엔드 패스의 끝에서 내보내게 됩니다. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Type | 활동 |
|  | 부모 항목 | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Children | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | - 전문 타입의 키<br/>- 기본 템플릿 유형의 키<br/>- 인스턴스화 된 템플릿의 종류 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[템플릿 인스턴스화](cpp-event-data-types/template-instantiation.md) |
|  | Description | 템플릿 인스턴스화의 시작과 끝에 발생합니다. 기본 템플릿 유형(예: `vector`인스턴스화)이 인스턴스화되어 특수화된 형식(예:)이 `std::vector<int>`생성됩니다. 두 유형 모두에 대해 키가 제공됩니다. [SYMBOL_NAME](#symbol-name) 이벤트를 사용하여 키를 형식의 이름으로 변환합니다. 형식 키는 분석중인 추적 내에서 고유합니다. 그러나 다른 컴파일러 프런트 엔드 패스에서 오는 다른 키는 동일한 형식을 가리킬 수 있습니다. 다른 컴파일러 프런트 엔드 패스 간의 형식을 비교하려면 기호 이름을 사용해야합니다. 이 이벤트는 재귀적입니다. 다시귀는 프런트 엔드가 중첩된 템플릿을 인스턴스화하는 경우에 따라 발생합니다. |
| <a name="thread"></a>스레드 | Type | 활동 |
|  | 부모 항목 | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Children | [함수](#function) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[스레드](cpp-event-data-types/thread.md) |
|  | Description | 컴파일러 백 엔드 스레드 실행의 시작과 끝에서 발생합니다. 일시 중단되는 스레드는 종료된 것으로 간주됩니다. 깨어난 스레드가 시작된 것으로 간주됩니다. |
| <a name="top-down"></a>TOP_DOWN | Type | 활동 |
|  | 부모 항목 | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | [함수](#function)<br/>[스레드](#thread) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[하향하](cpp-event-data-types/top-down.md) |
|  | Description | 전체 프로그램 분석의 하향식 패스의 시작 및 중지에서 발생합니다. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Type | 활동 |
|  | 부모 항목 | [C2_DLL](#c2-dll) |
|  | Children | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[전체 프로그램 분석](cpp-event-data-types/whole-program-analysis.md) |
|  | Description | 링크 시간 코드 생성의 전체 프로그램 분석 단계의 시작 및 중지시 발생합니다. |

::: moniker-end
