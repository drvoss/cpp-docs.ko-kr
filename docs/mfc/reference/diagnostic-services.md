---
title: 진단 서비스
ms.date: 11/04/2016
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
ms.openlocfilehash: f952044f4320aea1a757559b3c9c51e8ffb7c3a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751650"
---
# <a name="diagnostic-services"></a>진단 서비스

MFC 라이브러리는 프로그램을 더 쉽게 디버그할 수 있는 많은 진단 서비스를 제공합니다. 이러한 진단 서비스에는 매크로 및 전역 함수가 포함되며, 이러한 함수를 통해 프로그램의 메모리 할당을 추적하고 런타임 중 개체의 내용을 덤프하고 런타임 중 디버깅 메시지를 인쇄할 수 있습니다. 진단 서비스의 매크로 및 전역 함수는 다음과 같은 범주로 그룹화됩니다.

- 일반 진단 매크로

- 일반 진단 함수 및 변수

- 개체 진단 함수

이러한 매크로 및 함수는 MFC 디버그 및 릴리스 버전의 `CObject` 에서 파생된 모든 클래스에서 사용할 수 있습니다. 그러나 DEBUG_NEW 및 VERIFY를 제외한 모든 릴리스 버전에서는 아무 것도 수행하지 않습니다.

디버그 라이브러리에서, 할당된 모든 메모리 블록은 일련의 "보호 바이트"와 함께 묶입니다. 이러한 바이트가 잘못된 메모리 쓰기로 인해 교란되면 진단 루틴이 문제를 보고할 수 있습니다. 다음 줄을 포함하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

구현 파일에서 **new에** 대한 모든 호출은 메모리 할당이 수행된 파일 이름과 줄 번호를 저장합니다. 함수 [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) 메모리 누수 식별할 수 있도록 이 추가 정보를 표시 합니다. 진단 출력에 대한 추가 정보는 [클래스 CDumpContext를](../../mfc/reference/cdumpcontext-class.md) 참조하십시오.

또한 C 런타임 라이브러리는 애플리케이션을 디버그하는 데 사용할 수 있는 진단 함수 집합도 지원합니다. 자세한 내용은 런타임 라이브러리 참조의 [디버그 루틴을](../../c-runtime-library/debug-routines.md) 참조하십시오.

### <a name="mfc-general-diagnostic-macros"></a>MFC 일반 진단 매크로

|||
|-|-|
|[주장](#assert)|라이브러리의 디버그 버전에서 지정된 식의 값이 FALSE로 계산된 경우 메시지를 출력한 후 프로그램을 중단합니다.|
|[ASSERT_KINDOF](#assert_kindof)|개체가 지정된 클래스의 개체인지 아니면 지정된 클래스에서 파생된 클래스의 개체인지 테스트합니다.|
|[ASSERT_VALID](#assert_valid)|해당 `AssertValid` 멤버 함수를 호출하여 개체의 내부 유효성을 테스트합니다. 일반적으로 `CObject`에서 재정의됩니다.|
|[DEBUG_NEW](#debug_new)|메모리 누수를 쉽게 찾을 수 있도록 디버그 모드에서 모든 개체 할당에 파일 이름과 줄 번호를 제공합니다.|
|[DEBUG_ONLY](#debug_only)|ASSERT와 비슷하지만, 식의 값을 테스트하지는 않습니다. 디버그 모드에서만 실행해야 하는 코드에 유용합니다.|
|[보장 하고 ENSURE_VALID](#ensure)|데이터 정확성의 유효성을 검사하는 데 사용합니다.|
|[THIS_FILE](#this_file)|컴파일 중인 파일의 이름으로 확장합니다.|
|[추적](#trace)|라이브러리의 디버그 버전에서 `printf`와 유사한 기능을 제공합니다.|
|[확인](#verify)|ASSERT와 비슷하지만, 라이브러리의 릴리스 버전뿐만 아니라 디버그 버전에서도 식을 계산합니다.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 일반 진단 변수 및 함수

|||
|-|-|
|[아fx 덤프](#afxdump)|[CDumpContext](../../mfc/reference/cdumpcontext-class.md) 정보를 디버거 출력 창 또는 디버그 터미널로 보내는 전역 변수입니다.|
|[afxMemDF](#afxmemdf)|디버깅 메모리 할당자의 동작을 제어하는 전역 변수입니다.|
|[AfxCheckError](#afxcheckerror)|전달된 SCODE를 테스트하여 오류인지 알아보고 오류인 경우 적절한 오류를 throw하는 데 사용하는 전역 변수입니다.|
|[AfxCheckMemory](#afxcheckmemory)|현재 할당된 모든 메모리의 무결성을 검사합니다.|
|[AfxDebugBreak](#afxdebugbreak)|실행 이 끊어지게 됩니다.|
|[afxDump](#cdumpcontext_in_mfc)|디버거 내에 있는 동안 호출되는 경우 디버그하는 동안 개체의 상태를 덤프합니다.|
|[afxDump](#afxdump)|디버깅하는 동안 개체의 상태를 덤프하는 내부 함수입니다.|
|[AfxDumpStack](#afxdumpstack)|현재 스택의 이미지를 생성합니다. 이 함수는 항상 정적으로 연결됩니다.|
|[AfxEnable메모리누출덤프](#afxenablememoryleakdump)|메모리 누수 덤프를 사용하도록 설정합니다.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|메모리 추적을 켜고 끕니다.|
|[AfxIsMemoryBlock](#afxismemoryblock)|메모리 블록이 제대로 할당되었는지 확인합니다.|
|[AfxIsValidAddress](#afxisvalidaddress)|메모리 주소 범위가 프로그램의 경계 내에 있는지 확인합니다.|
|[AfxIsValidString](#afxisvalidstring)|문자열에 대한 포인터가 유효한지 여부를 결정합니다.|
|[AfxSetAllocHook](#afxsetallochook)|각 메모리 할당에서 함수 호출을 사용하도록 설정합니다.|

### <a name="mfc-object-diagnostic-functions"></a>MFC 개체 진단 함수

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|런타임 형식 검사를 지원하는 모든 `CObject`파생 클래스에서 지정된 함수를 실행합니다.|
|[AfxDoForAllObjects](#afxdoforallobjects)|새 로 할당된 `CObject`모든 파생 개체에서 지정된 **new**함수를 수행합니다.|

### <a name="mfc-compilation-macros"></a>MFC 컴파일 매크로

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|더 이상 사용되지 이상MFC 함수를 사용하기 위한 컴파일러 경고를 억제합니다.|

## <a name="_afx_secure_no_warnings"></a><a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS

더 이상 사용되지 이상MFC 함수를 사용하기 위한 컴파일러 경고를 억제합니다.

### <a name="syntax"></a>구문

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>예제

이 코드 샘플에서는 _AFX_SECURE_NO_WARNINGS 정의되지 않은 경우 컴파일러 경고가 발생합니다.

```cpp
// define this before including any afx files in *pch.h* (*stdafx.h* in Visual Studio 2017 and earlier)
#define _AFX_SECURE_NO_WARNINGS
```

```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a><a name="afxdebugbreak"></a>아프스데버그브레이크

MFC 응용 프로그램의 디버그 버전 실행시 `AfxDebugBreak`이 함수를 호출하여 호출 위치(호출 위치)에 중단이 발생합니다.

### <a name="syntax"></a>구문

```cpp
void AfxDebugBreak( );
```

### <a name="remarks"></a>설명

`AfxDebugBreak`MFC 응용 프로그램의 릴리스 버전에는 영향을 미치지 않으며 제거해야 합니다. 이 함수는 MFC 응용 프로그램에서만 사용해야 합니다. Win32 API 버전을 `DebugBreak`사용하여 MFC가 아닌 응용 프로그램에서 중단을 일으킵니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxver_.h

## <a name="assert"></a><a name="assert"></a>주장

인수를 평가합니다.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>매개 변수

*부울 표현식*<br/>
0이 아닌 0으로 평가하는 식(포인터 값 포함)을 지정합니다.

### <a name="remarks"></a>설명

결과가 0이면 매크로는 진단 메시지를 인쇄하고 프로그램을 중단합니다. 조건이 0이 아닌 경우 아무 것도 수행하지 않습니다.

진단 메시지의 형식은 다음과 같습니다.

`assertion failed in file <name> in line <num>`

*여기서 이름은* 소스 파일의 이름이며 *num은* 원본 파일에서 실패한 어설션의 줄 번호입니다.

MFC의 릴리스 버전에서 ASSERT는 표현식을 평가하지 않으므로 프로그램을 중단하지 않습니다. 환경에 관계없이 식을 평가해야 하는 경우 ASSERT 대신 VERIFY 매크로를 사용합니다.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="assert_kindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF

이 매크로는 가리키는 개체가 지정된 클래스의 개체이거나 지정된 클래스에서 파생된 클래스의 개체임을 어설션합니다.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
`CObject`-derived 클래스의 이름입니다.

*대상 (것)과 같은*<br/>
클래스 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

pobject 매개 *변수는* 개체에 대한 포인터여야 하며 **const일**수 있습니다. 가리키는 개체와 클래스는 런타임 클래스 정보를 지원해야 `CObject` 합니다. 예를 들어 클래스의 `pDocument` 개체 또는 해당 파생 `CMyDoc` 함수에 대한 포인터가 되도록 하려면 다음을 코딩할 수 있습니다.

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

매크로를 `ASSERT_KINDOF` 사용하는 것은 코딩과 정확히 동일합니다.

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

이 함수는 [DECLARE_DYNAMIC](런타임-개체-model.md#declare_dynamic 또는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로로 선언된 클래스에만 작동합니다.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 사용할 수 있습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="assert_valid"></a><a name="assert_valid"></a>ASSERT_VALID

개체의 내부 상태의 유효성에 대한 가정을 테스트하는 데 사용합니다.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
멤버 함수의 재정의 버전이 `CObject` 있는 클래스에서 파생된 `AssertValid` 개체를 지정합니다.

### <a name="remarks"></a>설명

ASSERT_VALID 전달된 `AssertValid` 개체의 멤버 함수를 인수로 호출합니다.

MFC의 릴리스 버전에서 ASSERT_VALID 아무 것도 하지 않습니다. 디버그 버전에서는 포인터의 유효성을 검사하고 NULL에 대해 검사하며 `AssertValid` 개체의 고유한 멤버 함수를 호출합니다. 이러한 테스트 중 어느 라도 실패하면 [ASSERT](#assert)와 동일한 방식으로 경고 메시지가 표시됩니다.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 사용할 수 있습니다.

자세한 정보 및 예제는 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="debug_new"></a><a name="debug_new"></a>Debug_new

메모리 누수 를 찾는 데 도움을 주며,

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>설명

일반적으로 **새** 연산자에서 힙 저장소를 할당하는 데 사용하는 프로그램의 모든 곳에서 DEBUG_NEW 사용할 수 있습니다.

디버그 **모드(_DEBUG** 기호가 정의된 경우)에서 DEBUG_NEW 할당하는 각 개체의 파일 이름과 줄 번호를 추적합니다. 그런 다음 [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) 멤버 함수를 사용할 때 DEBUG_NEW 할당된 각 개체는 할당된 파일 이름과 줄 번호로 표시됩니다.

DEBUG_NEW 사용하려면 다음 지시문을 소스 파일에 삽입합니다.

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

이 지시문을 삽입하면 전처리기는 **새**를 사용할 때마다 DEBUG_NEW 삽입하고 MFC는 나머지를 수행합니다. 프로그램의 릴리스 버전을 컴파일할 때 DEBUG_NEW 간단한 **새** 작업으로 확인되며 파일 이름 및 줄 번호 정보가 생성되지 않습니다.

> [!NOTE]
> 이전 버전의 MFC(4.1 이상)에서는 IMPLEMENT_DYNCREATE 또는 `#define` IMPLEMENT_SERIAL 매크로라고 하는 모든 문 후에 문을 넣어야 했습니다. 이제 더 이상 그럴 필요가 없습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="debug_only"></a><a name="debug_only"></a>DEBUG_ONLY

디버그 **모드(_DEBUG** 기호가 정의된 경우)에서 DEBUG_ONLY 인수를 평가합니다.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>설명

릴리스 빌드에서 DEBUG_ONLY 인수를 평가하지 않습니다. 이 기능은 디버그 빌드에서만 실행해야 하는 코드가 있는 경우에 유용합니다.

DEBUG_ONLY 매크로는 을 `#endif`사용하여 `#ifdef _DEBUG` 둘러싼 *식과* 동일합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

### <a name="ensure-and-ensure_valid"></a><a name="ensure"></a>보장 하고 ENSURE_VALID

데이터 정확성의 유효성을 검사하는 데 사용합니다.

### <a name="syntax"></a>구문

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>매개 변수

*부울 표현식*<br/>
테스트할 부울 식을 지정합니다.

### <a name="remarks"></a>설명

이러한 매크로의 목적은 매개 변수의 유효성 검사를 개선하는 것입니다. 매크로는 코드에서 잘못된 매개 변수를 추가로 처리하지 못하도록 합니다. ASSERT 매크로와 달리 ENSURE 매크로는 어설션을 생성하는 것 외에도 예외를 throw합니다.

매크로는 프로젝트 구성에 따라 두 가지 방식으로 행동합니다. 매크로는 ASSERT를 호출한 다음 어설션이 실패할 경우 예외를 throw합니다. 따라서 디버그 구성(즉, _DEBUG 정의된 경우)에서 매크로는 릴리스 구성에서 어설션 및 예외를 생성하지만 매크로는 예외만 생성합니다(ASSERT는 릴리스 구성에서 식을 평가하지 않음).

매크로 ENSURE_ARG ENSURE 매크로와 같은 역할을 합니다.

ENSURE_VALID ASSERT_VALID 매크로를 호출합니다(디버그 빌드에만 영향을 미칩니다). 또한 포인터가 NULL인 경우 ENSURE_VALID 예외를 throw합니다. NULL 테스트는 디버그 및 릴리스 구성 모두에서 수행됩니다.

이러한 테스트 중 하나로 실패하면 ASSERT와 동일한 방식으로 경고 메시지가 표시됩니다. 매크로는 필요한 경우 잘못된 인수 예외를 throw합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="this_file"></a><a name="this_file"></a>THIS_FILE

컴파일 중인 파일의 이름으로 확장합니다.

### <a name="syntax"></a>구문

```
THIS_FILE
```

### <a name="remarks"></a>설명

이 정보는 ASSERT 및 VERIFY 매크로에서 사용됩니다. 응용 프로그램 마법사 및 코드 마법사는 매크로를 만드는 소스 코드 파일에 배치합니다.

### <a name="example"></a>예제

```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the
// compiler recognizes.
```

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="trace"></a><a name="trace"></a>추적

지정된 문자열을 현재 응용 프로그램의 디버거에 보냅니다.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>설명

TRACE에 대한 설명은 [ATLTRACE2를](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) 참조하십시오. TRACE와 ATLTRACE2는 동일한 동작을 갖습니다.

MFC의 디버그 버전에서 이 매크로는 지정된 문자열을 현재 응용 프로그램의 디버거에 보냅니다. 릴리스 빌드에서 이 매크로는 아무 것도 컴파일되지 않습니다(코드가 전혀 생성되지 않습니다).

자세한 내용은 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="verify"></a><a name="verify"></a>확인

MFC의 디버그 버전에서 해당 인수를 평가합니다.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>매개 변수

*부울 표현식*<br/>
0이 아닌 0으로 평가하는 식(포인터 값 포함)을 지정합니다.

### <a name="remarks"></a>설명

결과가 0이면 매크로는 진단 메시지를 인쇄하고 프로그램을 중지합니다. 조건이 0이 아닌 경우 아무 것도 수행하지 않습니다.

진단 메시지의 형식은 다음과 같습니다.

`assertion failed in file <name> in line <num>`

*여기서 이름은* 소스 파일의 이름이며 *num은* 소스 파일에서 실패한 어설션의 줄 번호입니다.

MFC 의 릴리스 버전에서 VERIFY는 표현식을 평가하지만 프로그램을 인쇄하거나 중단하지는 않습니다. 예를 들어 식이 함수 호출인 경우 호출이 이루어집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc"></a>afxDump(MFC의 C덤프컨텍스트)

응용 프로그램에서 기본 개체 덤프 기능을 제공합니다.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>설명

`afxDump`는 디버거 출력 창 또는 디버그 터미널에 `CDumpContext` 정보를 보낼 수 있도록 하는 미리 정의 된 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 개체입니다. 일반적으로 에 `afxDump` 매개 변수로 `CObject::Dump`공급합니다.

Windows NT 및 모든 버전의 `afxDump` Windows에서는 응용 프로그램을 디버깅할 때 출력이 Visual C++의 출력 디버그 창으로 전송됩니다.

이 변수는 MFC의 디버그 버전에서만 정의됩니다. 자세한 `afxDump`내용은 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdump-internal"></a><a name="afxdump"></a>아fx덤프(내부)

MFC가 디버깅하는 동안 개체의 상태를 덤프하는 데 사용하는 내부 함수입니다.

### <a name="syntax"></a>구문

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
에서 파생된 클래스의 개체에 `CObject`대한 포인터입니다.

### <a name="remarks"></a>설명

`AfxDump`은 개체의 `Dump` 멤버 함수를 호출하고 `afxDump` 변수가 지정한 위치로 정보를 보냅니다. `AfxDump`MFC의 디버그 버전에서만 사용할 수 있습니다.

프로그램 코드는 호출하지 `AfxDump`말고 대신 `Dump` 해당 개체의 멤버 함수를 호출해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxmemdf"></a><a name="afxmemdf"></a>아fx밈DF

이 변수는 디버거 또는 프로그램에서 액세스할 수 있으며 할당 진단을 조정할 수 있습니다.

```
int  afxMemDF;
```

### <a name="remarks"></a>설명

`afxMemDF`열거형에 `afxMemDF`의해 지정된 대로 다음 값을 가질 수 있습니다.

- `allocMemDF`디버깅 할당자(디버그 라이브러리의 기본 설정)를 켭니다.

- `delayFreeMemDF`메모리 를 해제 지연합니다. 프로그램에서 메모리 블록을 해제하는 동안 할당자는 해당 메모리를 기본 운영 체제로 반환하지 않습니다. 이렇게하면 프로그램에 최대 메모리 스트레스가 가해집니다.

- `checkAlwaysMemDF`메모리가 할당또는 해제될 때마다 호출됩니다. `AfxCheckMemory` 이렇게 하면 메모리 할당 및 할당 이속도가 현저히 느려집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheck오류

이 함수는 통과된 SCODE를 테스트하여 오류인지 확인합니다.

```cpp
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>설명

오류인 경우 함수는 예외를 throw합니다. 통과된 SCODE가 E_OUTOFMEMORY 함수는 [AfxThrowMemoryException을](exception-processing.md#afxthrowmemoryexception)호출하여 [CMemoryException을](../../mfc/reference/cmemoryexception-class.md) throw합니다. 그렇지 않으면 함수는 [AfxThrowOleException을](exception-processing.md#afxthrowoleexception)호출하여 [COleException을](../../mfc/reference/coleexception-class.md) throw합니다.

이 함수는 응용 프로그램에서 OLE 함수에 대한 호출의 반환 값을 확인하는 데 사용할 수 있습니다. 응용 프로그램에서 이 함수를 사용하여 반환 값을 테스트하면 최소한의 코드로 오류 조건에 적절하게 대응할 수 있습니다.

> [!NOTE]
> 이 함수는 디버그 및 비디버그 빌드에서 동일한 영향을 미칩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxcheckmemory"></a><a name="afxcheckmemory"></a>아fx체크메모리

이 함수는 사용 가능한 메모리 풀의 유효성을 검사하고 필요에 따라 오류 메시지를 인쇄합니다.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>Return Value

메모리 오류가 없는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

함수가 메모리 손상이 감지되지 않으면 아무 것도 인쇄되지 않습니다.

현재 힙에 할당된 모든 메모리 블록은 **malloc** 함수 또는 `GlobalAlloc` Windows 함수와 같은 기본 메모리 할당자에 직접 호출하여 할당되지 않은 **새** 메모리 블록에 의해 할당된 블록을 포함하여 검사됩니다. 블록이 손상된 것으로 발견되면 메시지가 디버거 출력에 인쇄됩니다.

선을 포함하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

프로그램 모듈에서 후속 호출을 `AfxCheckMemory` 통해 메모리가 할당된 파일 이름과 줄 번호를 표시합니다.

> [!NOTE]
> 모듈에 직렬화 가능한 클래스의 하나 이상의 구현이 포함되어 `#define` 있는 경우 마지막 IMPLEMENT_SERIAL 매크로 호출 다음에 줄을 배치해야 합니다.

이 함수는 MFC의 디버그 버전에서만 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdump-mfc"></a><a name="afxdump"></a>아fx덤프 (MFC)

디버거에서 이 함수를 호출하여 디버깅하는 동안 개체의 상태를 덤프합니다.

```cpp
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
에서 파생된 클래스의 개체에 `CObject`대한 포인터입니다.

### <a name="remarks"></a>설명

`AfxDump`은 개체의 `Dump` 멤버 함수를 호출하고 `afxDump` 변수가 지정한 위치로 정보를 보냅니다. `AfxDump`MFC의 디버그 버전에서만 사용할 수 있습니다.

프로그램 코드는 호출하지 `AfxDump`말고 대신 `Dump` 해당 개체의 멤버 함수를 호출해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdumpstack"></a><a name="afxdumpstack"></a>아fx덤프스택

이 전역 함수는 현재 스택의 이미지를 생성하는 데 사용할 수 있습니다.

```cpp
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*dwTarget*<br/>
덤프 출력의 대상을 나타냅니다. 비트와이즈-OR(&#124;) 연산자를 사용하여 ** **결합할 수 있는 가능한 값은 다음과 같습니다.

- AFX_STACK_DUMP_TARGET_TRACE [TRACE](#trace) 매크로를 통해 출력을 보냅니다. TRACE 매크로는 디버그 빌드에서만 출력을 생성합니다. 릴리스 빌드에서 출력을 생성하지 않습니다. 또한 TRACE는 디버거 외에 다른 대상으로 리디렉션할 수 있습니다.

- AFX_STACK_DUMP_TARGET_DEFAULT 덤프 출력을 기본 대상으로 보냅니다. 디버그 빌드의 경우 출력은 TRACE 매크로로 이동합니다. 릴리스 빌드에서 출력은 클립보드로 이동합니다.

- AFX_STACK_DUMP_TARGET_CLIPBOARD 출력을 클립보드에만 보냅니다. 데이터는 CF_TEXT 클립보드 형식을 사용하여 클립보드에 일반 텍스트로 배치됩니다.

- AFX_STACK_DUMP_TARGET_BOTH 동시에 클립보드와 TRACE 매크로에 출력을 보냅니다.

- AFX_STACK_DUMP_TARGET_ODS Win32 함수를 `OutputDebugString()`사용하여 디버거에 직접 출력을 보냅니다. 이 옵션은 디버거가 프로세스에 연결될 때 디버깅 및 릴리스 빌드 모두에서 디버거 출력을 생성합니다. AFX_STACK_DUMP_TARGET_ODS 항상 디버거에 도달하고(연결된 경우) 리디렉션할 수 없습니다.

### <a name="remarks"></a>설명

아래 예제는 MFC 대화 상자 응용 `AfxDumpStack` 프로그램의 단추 처리기에서 호출에서 생성된 출력의 한 줄을 반영합니다.

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

위의 출력의 각 줄은 마지막 함수 호출의 주소, 함수 호출을 포함하는 모듈의 전체 경로 이름 및 호출된 함수 프로토타입을 나타냅니다. 스택에 대한 함수 호출이 함수의 정확한 주소에서 발생하지 않으면 바이트의 오프셋이 표시됩니다.

예를 들어 다음 표에서는 위의 출력의 첫 번째 줄을 설명합니다.

|출력|Description|
|------------|-----------------|
|`00427D55:`|마지막 함수 호출의 반환 주소입니다.|
|`DUMP2\DEBUG\DUMP2.EXE!`|함수 호출을 포함하는 모듈의 전체 경로 이름입니다.|
|`void AfxDumpStack(unsigned long)`|함수 프로토타입이라고 합니다.|
|`+ 181 bytes`|함수 프로토타입의 주소(이 `void AfxDumpStack(unsigned long)`경우)에서 반환 주소(이 `00427D55`경우)까지의 바이트 간격띄우기입니다.|

`AfxDumpStack`MFC 라이브러리의 디버그 및 비디버그 버전에서 사용할 수 있습니다. 그러나 실행 파일이 공유 DLL에서 MFC를 사용하는 경우에도 함수는 항상 정적으로 연결됩니다. 공유 라이브러리 구현에서 이 함수는 MFCS42에서 찾을 수 있습니다. LIB 라이브러리(및 변형).

이 함수를 성공적으로 사용하려면 다음을 수행하십시오.

- 파일 이미지HLP. DLL은 경로에 있어야 합니다. 이 DLL이 없는 경우 함수에 오류 메시지가 표시됩니다. IMAGEHLP에서 제공하는 기능 집합에 대한 자세한 내용은 [이미지 도움말 라이브러리를](/windows/win32/Debug/image-help-library) 참조하십시오.

- 스택에 프레임이 있는 모듈에는 디버깅 정보가 포함되어야 합니다. 디버깅 정보가 포함되어 있지 않으면 함수는 스택 추적을 계속 생성하지만 추적은 덜 자세합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnable메모리누출덤프

AFX_DEBUG_STATE 소멸자의 메모리 누수 덤프를 활성화하고 비활성화합니다.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>매개 변수

*bDump*<br/>
【인】 TRUE는 메모리 누수 덤프가 활성화되어 있음을 나타냅니다. FALSE는 메모리 누수 덤프가 비활성화되어 있음을 나타냅니다.

### <a name="return-value"></a>Return Value

이 플래그에 대한 이전 값입니다.

### <a name="remarks"></a>설명

애플리케이션이 MFC 라이브러리를 언로드하면 MFC 라이브러리는 메모리 누수를 확인합니다. 이 시점에서 모든 메모리 누수는 Visual Studio의 **디버그** 창을 통해 사용자에게 보고됩니다.

애플리케이션이 MFC 라이브러리 전에 다른 라이브러리를 로드하는 경우, 해당 라이브러리의 일부 메모리 할당이 메모리 누수로 잘못 보고됩니다. 거짓 메모리 누수가 발생하면 MFC 라이브러리에서 이를 보고하므로 애플리케이션이 느리게 종료될 수 있습니다. 이 경우 메모리 누수 덤프를 사용하지 않으려면 `AfxEnableMemoryLeakDump` 를 사용합니다.

> [!NOTE]
> 이 방법을 사용하여 메모리 누수 덤프를 끄는 경우, 애플리케이션에서 발생하는 유효한 메모리 누수의 보고서를 받지 못합니다. 메모리 누수 보고서에 거짓 메모리 누수가 포함되어 있다고 확신하는 경우에만 이 방법을 사용해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnable메모리트래킹

진단 메모리 추적은 일반적으로 MFC의 디버그 버전에서 활성화됩니다.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>매개 변수

*bTrack*<br/>
이 값을 TRUE로 설정하면 메모리 추적이 켜집니다. FALSE는 끕니다.

### <a name="return-value"></a>Return Value

추적 사용 플래그의 이전 설정입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 블록을 올바르게 할당하고 있는 코드 섹션에 대한 추적을 비활성화합니다.

자세한 `AfxEnableMemoryTracking`내용은 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxismemoryblock"></a><a name="afxismemoryblock"></a>아프시스메모리블록

메모리 주소를 테스트하여 **새**의 진단 버전에서 할당된 현재 활성 메모리 블록을 나타내는지 확인합니다.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
테스트할 메모리 블록을 가리킵니다.

*n바이트*<br/>
메모리 블록의 길이를 바이트로 포함합니다.

*plRequestNumber*<br/>
메모리 블록의 할당 시퀀스 번호로 채워지는 **긴** 정수를 가리키거나 현재 활성 메모리 블록을 나타내지 않는 경우 0을 가리킵니다.

### <a name="return-value"></a>Return Value

메모리 블록이 현재 할당되고 길이가 올바른 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

또한 원래 할당된 크기에 대해 지정된 크기를 확인합니다. 함수가 0이 아닌 함수를 반환하면 할당 시퀀스 번호가 *plRequestNumber*에서 반환됩니다. 이 숫자는 다른 모든 **새** 할당을 기준으로 블록이 할당된 순서를 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxisvalidaddress"></a><a name="afxisvalidaddress"></a>아프시스유효주소

모든 메모리 주소를 테스트하여 프로그램의 메모리 공간에 완전히 포함되어 있는지 확인합니다.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>매개 변수

*Lp 로*<br/>
테스트할 메모리 주소를 가리킵니다.

*n바이트*<br/>
테스트할 메모리 바이트 수를 포함합니다.

*bReadWrite*<br/>
메모리가 읽기및 쓰기(TRUE) 또는 읽기(FALSE)인지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

디버그 빌드에서 지정된 메모리 블록이 프로그램의 메모리 공간 내에 완전히 포함된 경우 0이 아닙니다. 그렇지 않으면 0.

디버그가 아닌 빌드에서 *lp가* NULL이 아닌 경우 0이 아님을 알 수 있습니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

주소는 **새**에 의해 할당된 블록으로 제한되지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxIsValid스트링

이 함수를 사용하여 문자열에 대한 포인터가 유효한지 여부를 확인합니다.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
테스트할 포인터입니다.

*nLength*<br/>
테스트할 문자열의 길이를 바이트로 지정합니다. 값이 -1이면 문자열이 null-종료된다는 것을 나타냅니다.

### <a name="return-value"></a>Return Value

디버그 빌드에서 지정된 포인터가 지정된 크기의 문자열을 가리키는 경우 0이 아닌 그렇지 않으면 0.

디버그가 아닌 빌드에서 *lpsz가* NULL이 아닌 경우 0이 아님을 알 수 있습니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxsetallochook"></a><a name="afxsetallochook"></a>아프셋알로크후크

각 메모리 블록이 할당되기 전에 지정된 함수를 호출할 수 있는 후크를 설정합니다.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>매개 변수

*pfnAllocHook*<br/>
호출할 함수의 이름을 지정합니다. 할당 함수의 프로토타입에 대한 설명은 참조하세요.

### <a name="return-value"></a>Return Value

할당을 허용하려는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

Microsoft Foundation 클래스 라이브러리 디버그 메모리 할당자는 사용자가 메모리 할당을 모니터링하고 할당이 허용되는지 여부를 제어할 수 있도록 사용자 정의 후크 함수를 호출할 수 있습니다. 할당 후크 함수는 다음과 같이 프로토타입화됩니다.

**BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**

*nSize*<br/>
제안된 메모리 할당의 크기입니다.

*bObject*<br/>
TRUE 할당이 -파생 `CObject`개체에 대한 경우; 그렇지 않으면 거짓.

*lRequestNumber*<br/>
메모리 할당의 시퀀스 번호입니다.

AFXAPI 호출 규칙은 호출이 스택에서 매개 변수를 제거해야 함을 의미합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdoforallclasses"></a><a name="afxdoforallclasses"></a>아프도포올클래스

응용 프로그램의 메모리 공간에서 모든 `CObject`직렬화 가능한 파생 클래스에 대해 지정된 반복 함수를 호출합니다.

```cpp
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>매개 변수

*Pfn*<br/>
각 클래스에 대해 호출할 반복 함수를 가리킵니다. 함수 인수는 `CRuntimeClass` 개체에 대한 포인터와 호출자가 함수에 제공하는 추가 데이터에 대한 void 포인터입니다.

*pContext*<br/>
호출자는 반복 함수에 제공할 수 있는 선택적 데이터를 가리킵니다. 이 포인터는 NULL일 수 있습니다.

### <a name="remarks"></a>설명

직렬화 `CObject`가능 -파생 클래스는 DECLARE_SERIAL 매크로를 사용하여 파생된 클래스입니다. `AfxDoForAllClasses` *pContext에서* 전달되는 포인터는 호출될 때마다 지정된 반복 함수로 전달됩니다.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdoforallobjects"></a><a name="afxdoforallobjects"></a>아프도포올오브젝트

새 로 할당된 개체에서 파생된 `CObject` 모든 개체에 **new**대해 지정된 반복 함수를 실행합니다.

```cpp
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>매개 변수

*Pfn*<br/>
각 개체에 대해 실행할 반복 함수를 가리킵니다. 함수 인수는 a에 `CObject` 대한 포인터와 호출자가 함수에 제공하는 추가 데이터에 대한 void 포인터입니다.

*pContext*<br/>
호출자는 반복 함수에 제공할 수 있는 선택적 데이터를 가리킵니다. 이 포인터는 NULL일 수 있습니다.

### <a name="remarks"></a>설명

스택, 전역 또는 포함된 개체는 모두 등록되지 않습니다. *pContext에서* `AfxDoForAllObjects` 전달된 포인터는 호출될 때마다 지정된 반복 함수로 전달됩니다.

> [!NOTE]
> 이 함수는 MFC의 디버그 버전에서만 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>참조

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CObject::Dump](cobject-class.md#dump)
