---
title: 'C++Build Insights SDK: 이벤트 테이블'
description: Visual Studio C++ BUILD Insights SDK에 대 한 이벤트 참조
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ccc8a4ef707942963b85edc6db9e21e05610b54
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334513"
---
# <a name="c-build-insights-sdk-event-table"></a>C++Build Insights SDK: 이벤트 테이블

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

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
[Pass1.log](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[LTCG](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[PASS2](#pass2)

## <a name="event-table"></a>이벤트 테이블

| 이벤트 | 속성 | 설명 |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | 형식 | 작업 |
|  | 부모 항목 | [컴파일러나](#compiler) |
|  | Children | [C2_DLL](#c2-dll) |
|  | 속성 | -입력 소스 파일의 절대 경로<br/>-출력 개체 파일의 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | 설명 | 컴파일러 백 엔드 패스의 시작 및 중지 시 발생 합니다. 이 패스는 구문 분석 된 C/C++ 소스 코드를 최적화 하 고 기계어 코드로 변환 하는 일을 담당 합니다. |
| <a name="bottom-up"></a>BOTTOM_UP | 형식 | 작업 |
|  | 부모 항목 | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | 설명 | 전체 프로그램 분석의 시작 및 중지에 발생 합니다. |
| <a name="c1-dll"></a>C1_DLL | 형식 | 작업 |
|  | 부모 항목 | [FRONT_END_PASS](#front-end-pass) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | 설명 | *C1* 또는 *c1xx* 호출을 시작 및 중지할 때 발생 합니다. 이러한 Dll은 컴파일러의 C C++ 및 프런트 엔드입니다. 컴파일러 드라이버 (*cl.exe*)를 통해서만 호출 됩니다. |
| <a name="c2-dll"></a>C2_DLL | 형식 | 작업 |
|  | 부모 항목 | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Children | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | 설명 | *C2 .dll* 호출을 시작 및 중지할 때 발생 합니다. 이 DLL은 컴파일러의 백 엔드입니다. 컴파일러 드라이버 (*cl.exe*)에 의해 호출 됩니다. 링크 타임 코드 생성이 사용 되는 경우 링커 (*link .exe*) 에서도 호출 됩니다. |
| <a name="code-generation"></a>CODE_GENERATION | 형식 | 작업 |
|  | 부모 항목 | [C2_DLL](#c2-dll) |
|  | Children | [FUNCTION](#function)<br/>[스레드](#thread) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | 설명 | 백 엔드의 코드 생성 단계를 시작 하 고 중지할 때 발생 합니다. |
| <a name="command-line"></a>COMMAND_LINE | 형식 | 단순 이벤트 |
|  | 부모 항목 | [컴파일러나](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - *Cl.exe* 또는 debug.exe를 호출 하는 데 사용 된 명령줄입니다 *.* |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Ds](cpp-event-data-types/command-line.md) |
|  | 설명 | 컴파일러와 링커가 명령줄 평가를 수행 하면 발생 합니다. 평가 된 명령줄에는 지시 파일을 통해 전달 된 모든 *cl.exe* 및 *링크 .exe* 매개 변수가 포함 됩니다. Cl에 대 한 매개 변수와 cl, \_CL\_, 링크 및 \_링크\_와 같은 환경 *변수를 통해* 전달 되는 *링크* 도 포함 됩니다. |
| <a name="compiler"></a>컴파일러나 | 형식 | 작업 |
|  | 부모 항목 | 없음 |
|  | Children | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | 속성 | -컴파일러 버전<br/>-작업 디렉터리<br/>-호출 된 cl.exe에 대 한 절대 경로 *입니다.* |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[호출](cpp-event-data-types/invocation.md)<br/>[컴파일러나](cpp-event-data-types/compiler.md) |
|  | 설명 | *Cl.exe* 호출을 시작 및 중지할 때 발생 합니다. |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | 형식 | 단순 이벤트 |
|  | 부모 항목 | [컴파일러나](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | -환경 변수의 이름<br/>-환경 변수의 값입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[고 environmentvariable](cpp-event-data-types/environment-variable.md) |
|  | 설명 | *Cl.exe* 또는 *debug.exe* 가 호출 될 때 모든 기존 환경 변수에 대해 한 번 발생 합니다. |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | -DLL 또는 실행 파일 출력 파일의 절대 경로입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md) |
|  | 설명 | 링커 입력 중 하나가 DLL 또는 실행 가능한 이미지 파일인 경우 발생 합니다. |
| <a name="exp-output"></a>EXP_OUTPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | - *.Exp* 출력 파일의 절대 경로입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[출력](cpp-event-data-types/exp-output.md) |
|  | 설명 | 링커 출력 중 하나가 .exp 파일인 경우 발생 합니다 *.* |
| <a name="file-input"></a>FILE_INPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [컴파일러나](#compiler)<br/>[링커](#linker) |
|  | Children | 없음 |
|  | 속성 | -입력 파일에 대 한 절대 경로<br/>-입력 파일의 유형입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | 설명 | *Cl.exe* 또는 *link .exe* 입력을 알리기 위해 발생 합니다. |
| <a name="force-inlinee"></a>FORCE_INLINEE | 형식 | 단순 이벤트 |
|  | 부모 항목 | [FUNCTION](#function) |
|  | Children | 없음 |
|  | 속성 | -강제 인라인 함수의 이름입니다.<br/>-중간 명령 수로 표시 되는 강제 인라인 함수 크기입니다. |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | 설명 | `__forceinline` 키워드를 사용 하 여 함수가 다른 함수에 강제로 인라인 될 때 발생 합니다. |
| <a name="front-end-file"></a>FRONT_END_FILE | 형식 | 작업 |
|  | 부모 항목 | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | -파일의 절대 경로입니다. |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | 설명 | 컴파일러 프런트 엔드가 시작 되 고 파일 처리가 중지 될 때 발생 합니다. 이 이벤트는 재귀적입니다. 프런트 엔드가 포함 된 파일을 구문 분석할 때 재귀가 발생 합니다. |
| <a name="front-end-pass"></a>FRONT_END_PASS | 형식 | 작업 |
|  | 부모 항목 | [컴파일러나](#compiler) |
|  | Children | [C1_DLL](#c1-dll) |
|  | 속성 | -입력 소스 파일의 절대 경로<br/>-출력 개체 파일의 절대 경로 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | 설명 | 컴파일러 프런트 엔드 패스의 시작 및 중지 시 발생 합니다. 이 패스는 C/C++ 소스 코드를 구문 분석 하 고 중간 언어로 변환 하는 일을 담당 합니다. |
| <a name="function"></a>칩셋용으로 | 형식 | 작업 |
|  | 부모 항목 | [CODE_GENERATION](#code-generation)<br/>[스레드](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FORCE_INLINEE](#force-inlinee) |
|  | 속성 | -함수의 이름 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[Function](cpp-event-data-types/function.md) |
|  | 설명 | 함수에 대 한 코드 생성을 시작 하 고 종료 하는 경우에 발생 합니다. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | -가져오기 라이브러리 출력 파일의 절대 경로입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ImpLibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | 설명 | 링커 출력 중 하나가 가져오기 라이브러리인 경우 발생 합니다. |
| <a name="lib-output"></a>LIB_OUTPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | -정적 라이브러리 출력 파일의 절대 경로입니다. |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[을 출력 합니다.](cpp-event-data-types/lib-output.md) |
|  | 설명 | 링커 출력 중 하나가 정적 라이브러리인 경우 발생 합니다. |
| <a name="linker"></a>링커 | 형식 | 작업 |
|  | 부모 항목 | 없음 |
|  | Children | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1.LOG](#pass1)<br/>[PASS2](#pass2) |
|  | 속성 | -링커 버전<br/>-작업 디렉터리<br/>-호출 된 링크 .exe의 절대 경로 *입니다.* |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[호출](cpp-event-data-types/invocation.md)<br/>[링커](cpp-event-data-types/linker.md) |
|  | 설명 | *링크 .exe* 호출을 시작 및 중지할 때 발생 합니다. |
| <a name="ltcg"></a>LTCG | 형식 | 작업 |
|  | 부모 항목 | [PASS1.LOG](#pass1) |
|  | Children | [C2_DLL](#c2-dll) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | 설명 | 링크 타임 코드 생성이 시작 및 중지 될 때 발생 합니다. |
| <a name="obj-output"></a>OBJ_OUTPUT | 형식 | 단순 이벤트 |
|  | 부모 항목 | [컴파일러나](#compiler) |
|  | Children | 없음 |
|  | 속성 | -.Obj 출력 파일의 절대 경로 *입니다.* |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | 설명 | *Cl.exe*에 의해 생성 된 모든 *.obj* 출력에 대해 한 번 발생 합니다. |
| <a name="opt-icf"></a>OPT_ICF | 형식 | 작업 |
|  | 부모 항목 | [PASS1.LOG](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | 설명 | 동일한 COMDAT 정리 (/OPT: ICF) 링커 최적화를 시작 하 고 중지할 때 발생 합니다. |
| <a name="opt-lbr"></a>OPT_LBR | 형식 | 작업 |
|  | 부모 항목 | [PASS1.LOG](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | 설명 | 긴 분기 (/OPT: LBR) 링커 최적화의 시작 및 중지에 발생 합니다. |
| <a name="opt-ref"></a>OPT_REF | 형식 | 작업 |
|  | 부모 항목 | [PASS1.LOG](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[OptRef](cpp-event-data-types/opt-ref.md) |
|  | 설명 | 참조 되지 않은 함수 및 데이터 제거 (/OPT: REF) 링커 최적화를 시작 하 고 중지할 때 발생 합니다. |
| <a name="pass1"></a>PASS1.LOG | 형식 | 작업 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[Pass1.log](cpp-event-data-types/pass1.md) |
|  | 설명 | 링커의 pass 1을 시작 하 고 중지할 때 발생 합니다. |
| <a name="pass2"></a>PASS2 | 형식 | 작업 |
|  | 부모 항목 | [링커](#linker) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | 설명 | 링커의 pass 2를 시작 하 고 중지할 때 발생 합니다. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | 형식 | 작업 |
|  | 부모 항목 | [PASS1.LOG](#pass1) |
|  | Children | 없음 |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | 설명 | 참조 되지 않은 함수 및 데이터를 제거 하는 링커 최적화 패스의 시작 및 중지 시 발생 합니다 (/OPT: REF). 링크 타임 코드를 생성 하기 전에 수행 됩니다. |
| <a name="symbol-name"></a>SYMBOL_NAME | 형식 | 단순 이벤트 |
|  | 부모 항목 | [C1_DLL](#c1-dll) |
|  | Children | 없음 |
|  | 속성 | -형식 키<br/> -형식의 이름 |
|  | 클래스 캡처 | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[기호 이름](cpp-event-data-types/symbol-name.md) |
|  | 설명 | 프런트 엔드 pass의 끝에서 발생: 템플릿 인스턴스화에 관련 된 모든 형식에 대해 한 번씩 발생 합니다. 키는 형식에 대 한 숫자 식별자 이지만 이름은 텍스트 표현입니다. 유형 키는 분석 중인 추적 내에서 고유 합니다. 그러나 다른 컴파일러 프런트 엔드 패스에서 들어오는 여러 키는 동일한 형식을 가리킬 수 있습니다. 서로 다른 컴파일러 프런트 엔드 패스 간에 형식을 비교 하려면 이름을 사용 해야 합니다. 모든 템플릿 인스턴스화가 발생 한 후에는 컴파일러 프런트 엔드 패스의 끝에 SYMBOL_NAME 이벤트를 내보냅니다. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | 형식 | 작업 |
|  | 부모 항목 | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Children | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | 속성 | -특수화 된 형식의 키<br/>-기본 템플릿 형식의 키<br/>-인스턴스화된 템플릿 종류 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[템플릿 인스턴스화](cpp-event-data-types/template-instantiation.md) |
|  | 설명 | 템플릿 인스턴스화의 시작과 끝에서 발생 합니다. 기본 템플릿 형식 (예: `vector`)이 인스턴스화되어 특수 형식 (예: `std::vector<int>`)이 생성 됩니다. 두 형식에 대 한 키가 제공 됩니다. [SYMBOL_NAME](#symbol-name) 이벤트를 사용 하 여 키를 형식의 이름으로 변환 합니다. 유형 키는 분석 중인 추적 내에서 고유 합니다. 그러나 다른 컴파일러 프런트 엔드 패스에서 들어오는 여러 키는 동일한 형식을 가리킬 수 있습니다. 서로 다른 컴파일러 프런트 엔드 패스 간에 형식을 비교 하려면 기호 이름을 사용 해야 합니다. 이 이벤트는 재귀적입니다. 재귀는 프런트 엔드가 중첩 된 템플릿을 인스턴스화하는 경우에 발생 합니다. |
| <a name="thread"></a>스레드 | 형식 | 작업 |
|  | 부모 항목 | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FUNCTION](#function) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[스레드](cpp-event-data-types/thread.md) |
|  | 설명 | 컴파일러 백 엔드 스레드 실행의 시작과 끝에서 발생 합니다. 일시 중단 되는 스레드는 종료 된 것으로 간주 됩니다. 해제 되는 스레드가 시작 된 것으로 간주 됩니다. |
| <a name="top-down"></a>TOP_DOWN | 형식 | 작업 |
|  | 부모 항목 | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | [FUNCTION](#function)<br/>[스레드](#thread) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[위쪽 아래쪽](cpp-event-data-types/top-down.md) |
|  | 설명 | 전체 프로그램 분석 ' 하향식 패스의 시작 및 중지에 발생 합니다. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | 형식 | 작업 |
|  | 부모 항목 | [C2_DLL](#c2-dll) |
|  | Children | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | 속성 | 없음 |
|  | 클래스 캡처 | [활동](cpp-event-data-types/activity.md)<br/>[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) |
|  | 설명 | 링크 타임 코드 생성의 전체 프로그램 분석 단계를 시작 하 고 중지할 때 발생 합니다. |

::: moniker-end
