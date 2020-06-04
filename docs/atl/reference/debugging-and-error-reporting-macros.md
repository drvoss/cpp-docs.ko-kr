---
title: 디버깅 및 오류 보고 매크로
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: 69ab6e17bfb1ec85ddb5b8c19c18010a9b4f3df6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330195"
---
# <a name="debugging-and-error-reporting-macros"></a>디버깅 및 오류 보고 매크로

이러한 매크로는 유용한 디버깅 및 추적 시설을 제공합니다.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|출력 창에 호출될 때 `_Module.Term` 검색되는 모든 인터페이스 누수에 기록합니다.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|출력 창에 `QueryInterface` 대한 모든 호출을 씁니다.|
|[아틀레어 (약들)](#atlassert)|C 런타임 라이브러리에 있는 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로와 동일한 기능을 수행합니다.|
|[ATLENSURE](#atlensure)|매개 변수 유효성 검사를 수행합니다. 필요한 `AtlThrow` 경우 전화 걸기|
|[아틀트레이스노딤플](#atltracenotimpl)|지정된 함수가 구현되지 않은 메시지를 덤프 장치에 보냅니다.|
|[아틀트레이스](#atltrace)|표시된 플래그 및 수준에 따라 디버거 창과 같은 출력 장치에 경고를 보고합니다. 이전 버전과의 호환성을 위해 포함되어 있습니다.|
|[ATLTRACE2](#atltrace2)|표시된 플래그 및 수준에 따라 디버거 창과 같은 출력 장치에 경고를 보고합니다.|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES

모든 `AddRef` 것을 추적하고 출력 창에 구성 요소의 인터페이스를 `Release` 호출하는 ATL 헤더 파일을 포함하기 전에이 매크로를 정의합니다.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>설명

추적 출력은 다음과 같이 표시됩니다.

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

각 추적의 첫 번째 `ATL: QIThunk`부분은 항상 입니다. 다음은 사용 중인 특정 *인터페이스 썽크를* 식별하는 값입니다. 인터페이스 썽크는 참조 수를 유지하고 여기에 사용되는 추적 기능을 제공하는 데 사용되는 개체입니다. 새로운 인터페이스 썽크는 `QueryInterface` `IUnknown` 인터페이스에 대한 요청을 제외한 모든 호출에서 만들어집니다(이 경우 COM의 ID 규칙을 준수하기 위해 매번 동일한 썽크가 반환됨).

다음으로 어떤 메서드가 `Release` 호출되는지 표시하거나 표시합니다. `AddRef` 그런 다음 인터페이스 참조 수가 변경된 개체를 식별하는 값을 볼 수 있습니다. 추적된 값은 개체의 **이** 포인터입니다.

추적되는 참조 수는 호출된 후 `AddRef` 또는 `Release` 호출된 썽크의 참조 개수입니다. 이 참조 수는 개체의 참조 수와 일치하지 않을 수 있습니다. 각 썽크는 COM의 참조 계수 규칙을 완전히 준수할 수 있도록 자체 참조 수를 유지 관리합니다.

추적되는 정보의 마지막 조각은 개체의 이름과 `AddRef` 또는 `Release` 호출의 영향을 받는 인터페이스입니다.

서버가 종료되고 `_Module.Term` 호출될 때 감지되는 모든 인터페이스 누수는 다음과 같이 기록됩니다.

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

여기에 제공된 정보는 이전 추적 문에 제공된 정보에 직접 매핑되므로 인터페이스 썽크의 전체 수명 동안 참조 수를 검사할 수 있습니다. 또한 해당 인터페이스 썽크에서 최대 참조 수를 표시합니다.

> [!NOTE]
> _ATL_DEBUG_INTERFACES 소매 빌드에 사용할 수 있습니다.

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a>_ATL_DEBUG_QI

출력 창에 `QueryInterface` 대한 모든 호출을 씁니다.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>설명

호출에 `QueryInterface` 실패하면 출력 창에 다음이 표시됩니다.

*인터페이스 이름* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a>아틀레어 (약들)

ATLASSERT 매크로는 C 런타임 라이브러리에 있는 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로와 동일한 기능을 수행합니다.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>매개 변수

*부울 표현식*<br/>
0이 아닌 값 또는 0으로 계산되는 식(포인터 포함)입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 ATLASSERT는 *부울 표현식을* 평가하고 결과가 false일 때 디버그 보고서를 생성합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

## <a name="atlensure"></a><a name="atlensure"></a>ATLENSURE

이 매크로는 함수에 전달된 매개 변수의 유효성을 검사하는 데 사용됩니다.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>매개 변수

*부울 표현식*<br/>
테스트할 부울 식을 지정합니다.

*Hr*<br/>
반환할 오류 코드를 지정합니다.

### <a name="remarks"></a>설명

이러한 매크로는 잘못된 매개 변수 사용을 감지하고 사용자에게 알리는 메커니즘을 제공합니다.

매크로는 ATLASSERT를 호출하고 조건이 `AtlThrow`실패하면 호출합니다.

ATLENSURE의 경우, `AtlThrow` E_FAIL 호출됩니다.

ATLENSURE_THROW 경우 지정된 `AtlThrow` HRESULT를 호출합니다.

ATLENSURE와 ATLASSERT의 차이점은 ATLENSURE가 디버그 빌드뿐만 아니라 릴리스 빌드에서 예외를 throw한다는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a>아틀트레이스노딤플

ATL의 디버그 빌드에서 *"funcname이* 구현되지 않음"문자열을 덤프 장치에 보내고 E_NOTIMPL 반환합니다.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>매개 변수

*펑크나임*<br/>
【인】 구현되지 않은 함수의 이름을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

릴리스 빌드에서 E_NOTIMPL 반환하기만 하면 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** atltrace.h

## <a name="atltrace"></a><a name="atltrace"></a>아틀트레이스

표시된 플래그 및 수준에 따라 디버거 창과 같은 출력 장치에 경고를 보고합니다. 이전 버전과의 호환성을 위해 포함되어 있습니다.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>매개 변수

*특급*<br/>
【인】 출력 창 또는 이러한 메시지를 트래피싱하는 모든 응용 프로그램으로 보낼 문자열 및 변수입니다.

*범주*<br/>
【인】 보고할 이벤트 또는 방법의 유형입니다. 범주 목록은 비고를 참조하십시오.

*수준*<br/>
【인】 보고할 추적 수준입니다. 자세한 내용은 비고를 참조하십시오.

*lpszFormat*<br/>
【인】 덤프 장치에 보낼 형식이 지정된 문자열입니다.

### <a name="remarks"></a>설명

ATLTRACE에 대한 설명은 [ATLTRACE2를](#atltrace2) 참조하십시오. ATLTRACE와 ATLTRACE2는 동일한 동작을 가지며, 이전 버전과의 호환성을 위해 ATLTRACE가 포함되어 있습니다.

## <a name="atltrace2"></a><a name="atltrace2"></a>ATLTRACE2

표시된 플래그 및 수준에 따라 디버거 창과 같은 출력 장치에 경고를 보고합니다.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>매개 변수

*특급*<br/>
【인】 출력 창 또는 이러한 메시지를 트래스트하는 모든 응용 프로그램으로 보낼 문자열입니다.

*범주*<br/>
【인】 보고할 이벤트 또는 방법의 유형입니다. 범주 목록은 비고를 참조하십시오.

*수준*<br/>
【인】 보고할 추적 수준입니다. 자세한 내용은 비고를 참조하십시오.

*lpszFormat*<br/>
【인】 덤프 `printf`장치에 보낼 문자열을 만드는 데 사용할 -style 형식 문자열입니다.

### <a name="remarks"></a>설명

짧은 형식의 ATLTRACE2는 디버거의 출력 창에 문자열을 씁니다. ATLTRACE2의 두 번째 형태는 디버거의 출력 창에 출력을 쓰지만 ATL/MFC 추적 도구의 설정이 [적용됩니다(ATLTraceTool 샘플](../../overview/visual-cpp-samples.md)참조). 예를 들어 *레벨을* 4로 설정하고 ATL/MFC 추적 도구를 수준 0으로 설정하면 메시지가 표시되지 않습니다. *레벨은* 0, 1, 2, 3 또는 4일 수 있습니다. 기본값인 0은 가장 심각한 문제만 보고합니다.

*범주* 매개 변수에는 설정할 추적 플래그가 나열됩니다. 이러한 플래그는 보고하려는 메서드 유형에 해당합니다. 아래 표에는 *범주* 매개 변수에 사용할 수 있는 유효한 추적 플래그가 나열됩니다.

### <a name="atl-trace-flags"></a>ATL 추적 플래그

|ATL 카테고리|Description|
|------------------|-----------------|
|`atlTraceGeneral`|모든 ATL 응용 프로그램에 대한 보고서입니다. 기본값입니다.|
|`atlTraceCOM`|COM 메서드에 대한 보고서입니다.|
|`atlTraceQI`|쿼리인터페이스 호출에 대한 보고서입니다.|
|`atlTraceRegistrar`|개체 등록에 대한 보고서입니다.|
|`atlTraceRefcount`|참조 수 변경에 대한 보고서입니다.|
|`atlTraceWindowing`|창 메서드에 대한 보고서; 예를 들어 잘못된 메시지 맵 ID를 보고합니다.|
|`atlTraceControls`|컨트롤에 대한 보고서; 예를 들어 컨트롤 또는 해당 창이 소멸될 때 보고합니다.|
|`atlTraceHosting`|메시지를 호스팅하는 보고서; 예를 들어 컨테이너의 클라이언트가 활성화될 때 보고합니다.|
|`atlTraceDBClient`|OLE DB 소비자 템플릿에 대한 보고서; 예를 들어 GetData 호출에 실패하면 출력에 HRESULT가 포함될 수 있습니다.|
|`atlTraceDBProvider`|OLE DB 공급자 템플릿에 대한 보고서; 예를 들어 열 생성에 실패한 경우 보고합니다.|
|`atlTraceSnapin`|MMC SnapIn 응용 프로그램에 대한 보고서입니다.|
|`atlTraceNotImpl`|표시된 함수가 구현되지 않았다고 보고합니다.|
|`atlTraceAllocation`|atldbgmem.h에서 메모리 디버깅 도구에 의해 인쇄된 메시지를 보고합니다.|

### <a name="mfc-trace-flags"></a>MFC 추적 플래그

|MFC 카테고리|Description|
|------------------|-----------------|
|`traceAppMsg`|범용, MFC 메시지. 항상 추천합니다.|
|`traceDumpContext`|[CDumpContext의](../../mfc/reference/cdumpcontext-class.md)메시지 .|
|`traceWinMsg`|MFC의 메시지 처리 코드의 메시지입니다.|
|`traceMemory`|MFC의 메모리 관리 코드에서 보낸 메시지입니다.|
|`traceCmdRouting`|MFC의 Windows 명령 라우팅 코드의 메시지입니다.|
|`traceHtml`|MFC의 DHTML 대화 상자 지원에서 메시지입니다.|
|`traceSocket`|MFC의 소켓 지원에서 메시지.|
|`traceOle`|MFC의 OLE 지원메시지입니다.|
|`traceDatabase`|MFC의 데이터베이스 지원메시지입니다.|
|`traceInternet`|MFC의 인터넷 지원 메시지입니다.|

사용자 지정 추적 범주를 선언하려면 다음과 `CTraceCategory` 같이 클래스의 전역 인스턴스를 선언합니다.

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

이 예제에서 MY_CATEGORY 범주 이름은 *범주* 매개 변수에 지정한 이름입니다. 첫 번째 매개 변수는 ATL/MFC 추적 도구에 표시되는 범주 이름입니다. 두 번째 매개 변수는 기본 추적 수준입니다. 이 매개 변수는 선택 사항이며 기본 추적 수준은 0입니다.

사용자 정의 범주를 사용하려면 다음을 수행합니다.

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

추적 메시지를 필터링할 지정하려면 `#include <atlbase.h>` 이러한 매크로에 대한 정의를 명령문 앞에 Stdafx.h에 삽입합니다.

또는 **속성 페이지** 대화 상자의 전처리기 지시문에서 필터를 설정할 수 있습니다. **전처리기** 탭을 클릭한 다음 **전역을 전처리기 정의** 편집 상자에 삽입합니다.

Atlbase.hATLTRACE2 매크로의 기본 정의를 포함 하며 이러한 정의는 atlbase.h 처리 하기 전에 이러한 기호를 정의 하지 않는 경우 사용 됩니다.

릴리스 빌드에서 ATLTRACE2는 을 `(void) 0`컴파일합니다.

ATLTRACE2는 서식을 지정한 후 덤프 장치로 전송되는 문자열의 내용을 1023자 이하로 제한합니다.

ATLTRACE와 ATLTRACE2는 동일한 동작을 가지며, 이전 버전과의 호환성을 위해 ATLTRACE가 포함되어 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)<br/>
[디버깅 및 오류 보고 전역 함수](../../atl/reference/debugging-and-error-reporting-global-functions.md)
