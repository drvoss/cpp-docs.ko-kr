---
title: C덤프컨텍스트 클래스
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: e89bbc5f263dc9303140e43914619090109b8315
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753205"
---
# <a name="cdumpcontext-class"></a>C덤프컨텍스트 클래스

사용자가 읽을 수 있는 텍스트 형식으로 스트림 지향 진단 출력을 지원합니다.

## <a name="syntax"></a>구문

```
class CDumpContext
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C덤프컨텍스트::C덤프컨텍스트](#cdumpcontext)|`CDumpContext` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C덤프컨텍스트::D움프아헥스](#dumpashex)|표시된 항목을 육각형 형식으로 덤프합니다.|
|[C덤프 컨텍스트::플러시](#flush)|덤프 컨텍스트 버퍼의 모든 데이터를 플러시합니다.|
|[C덤프 컨텍스트::GetDepth](#getdepth)|덤프의 깊이에 해당하는 정수를 가져옵니다.|
|[C덤프컨텍스트::헥스덤프](#hexdump)|헥사데피말 형식의 배열에 포함된 바이트를 덤프합니다.|
|[C덤프 컨텍스트::세트 심층](#setdepth)|덤프의 깊이를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C덤프컨텍스트::연산자&lt;&lt;](#operator_lt_lt)|변수와 개체를 덤프 컨텍스트에 삽입합니다.|

## <a name="remarks"></a>설명

`CDumpContext`기본 클래스가 없습니다.

대부분의 덤프에 대해 미리 선언된 `CDumpContext` 개체인 [afxDump를](diagnostic-services.md#afxdump)사용할 수 있습니다. 개체는 `afxDump` Microsoft 재단 클래스 라이브러리의 디버그 버전에서만 사용할 수 있습니다.

몇몇 메모리 [진단](../../mfc/reference/diagnostic-services.md) 서비스는 `afxDump` 출력에 사용합니다.

Windows 환경에서 는 개념적으로 `afxDump` `cerr` 스트림과 유사한 미리 정의된 개체의 출력이 Windows 함수를 `OutputDebugString`통해 디버거로 라우팅됩니다.

`CDumpContext` 클래스에는 개체의 데이터를 덤프하는 **<<** 포인터에 `CObject` 대한 오버로드된 삽입() 연산자가 있습니다. 파생 된 개체에 대 한 사용자 지정 덤프 형식이 필요한 경우 [CObject::Dump](../../mfc/reference/cobject-class.md#dump)를 재정의 합니다. 대부분의 Microsoft Foundation 클래스는 `Dump` 재정의된 멤버 함수를 구현합니다.

`CObject` `CTimeSpan` `CDumpContext` `CFileStatus` `CPoint` `CRect`에서 파생 되지 않는 클래스 는 `CTime`" 및 및 에 대 한 자주 사용 되는 구조와 마찬가지로 자체 오버로드 된 삽입 연산자 및 . `CString`

클래스의 `CObject::Dump` 구현에 [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) 또는 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로를 사용하는 경우 -derived `CObject`클래스의 이름을 인쇄합니다. 그렇지 않으면 인쇄됩니다. `CObject`

클래스는 `CDumpContext` 라이브러리의 디버그 및 릴리스 버전 모두에서 사용할 `Dump` 수 있지만 멤버 함수는 디버그 버전에서만 정의됩니다. **#ifdef _DEBUG**  /  `#endif` 문을 사용하여 사용자 지정 `Dump` 멤버 함수를 포함하여 진단 코드를 괄호로 묶습니다.

사용자 고유의 `CDumpContext` 개체를 `CFile` 만들기 전에 덤프 대상 역할을 하는 개체를 만들어야 합니다.

자세한 `CDumpContext`내용은 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDumpContext`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>C덤프컨텍스트::C덤프컨텍스트

클래스의 `CDumpContext`개체를 생성합니다.

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
덤프 대상인 `CFile` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체가 `afxDump` 자동으로 생성됩니다.

덤프 컨텍스트가 활성 `CFile` 상태인 동안에는 기본에 쓰지 마십시오. 그렇지 않으면 덤프를 방해합니다. Windows 환경에서 출력은 Windows 함수를 `OutputDebugString`통해 디버거로 라우팅됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>C덤프컨텍스트::D움프아헥스

육각형 숫자로 서식이 지정된 형식을 덤프합니다.

```
CDumpContext& DumpAsHex(BYTE b);
CDumpContext& DumpAsHex(DWORD dw);
CDumpContext& DumpAsHex(int n);
CDumpContext& DumpAsHex(LONG l);
CDumpContext& DumpAsHex(LONGLONG n);
CDumpContext& DumpAsHex(UINT u);
CDumpContext& DumpAsHex(ULONGLONG n);
CDumpContext& DumpAsHex(WORD w);
```

### <a name="return-value"></a>Return Value

`CDumpContext` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 지정된 형식의 항목을 육각형 번호로 덤프합니다. 배열을 덤프하려면 [CDumpContext::HexDump](#hexdump)를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>C덤프 컨텍스트::플러시

버퍼에 남아 있는 모든 데이터를 덤프 컨텍스트에 연결된 파일에 기록하도록 강제합니다.

```cpp
void Flush();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>C덤프 컨텍스트::GetDepth

심층 또는 얕은 덤프가 처리 중인지 여부를 결정합니다.

```
int GetDepth() const;
```

### <a name="return-value"></a>Return Value

에 의해 `SetDepth`설정된 덤프의 깊이

### <a name="example"></a>예제

  [SetDepth](#setdepth)에 대한 예제를 참조하십시오.

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>C덤프컨텍스트::헥스덤프

헥사데피수 숫자로 서식이 지정된 바이트 배열을 덤프합니다.

```cpp
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>매개 변수

*lpszLine*<br/>
새 줄의 시작 부분에 출력할 문자열입니다.

*pby*<br/>
덤프할 바이트를 포함하는 버퍼에 대한 포인터입니다.

*n바이트*<br/>
덤프할 바이트 수입니다.

*nWidth*<br/>
줄당 덤프된 최대 바이트 수(출력 줄의 너비가 아님).

### <a name="remarks"></a>설명

단일 특정 항목 형식을 헥사데피수 번호로 덤프하려면 [CDumpContext::DumpAsHex](#dumpashex)를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>C덤프컨텍스트::연산자&lt;&lt;

지정된 데이터를 덤프 컨텍스트에 출력합니다.

```
CDumpContext& operator<<(const CObject* pOb);
CDumpContext& operator<<(const CObject& ob);
CDumpContext& operator<<(LPCTSTR lpsz);
CDumpContext& operator<<(const void* lp);
CDumpContext& operator<<(BYTE by);
CDumpContext& operator<<(WORD w);
CDumpContext& operator<<(DWORD dw);
CDumpContext& operator<<(int n);
CDumpContext& operator<<(double d);
CDumpContext& operator<<(float f);
CDumpContext& operator<<(LONG l);
CDumpContext& operator<<(UINT u);
CDumpContext& operator<<(LPCWSTR lpsz);
CDumpContext& operator<<(LPCSTR lpsz);
CDumpContext& operator<<(LONGLONG n);
CDumpContext& operator<<(ULONGLONG n);
CDumpContext& operator<<(HWND h);
CDumpContext& operator<<(HDC h);
CDumpContext& operator<<(HMENU h);
CDumpContext& operator<<(HACCEL h);
CDumpContext& operator<<(HFONT h);
```

### <a name="return-value"></a>Return Value

`CDumpContext` 참조입니다. 반환 값을 사용하여 한 줄의 소스 코드에 여러 삽입을 작성할 수 있습니다.

### <a name="remarks"></a>설명

삽입 연산자는 `CObject` 포인터뿐만 아니라 대부분의 기본 형식에 대해서도 오버로드됩니다. 문자에 대한 포인터는 문자열 내용의 덤프를 초래합니다. **void에** 대한 포인터는 주소의 육각형 덤프만 생성합니다. LONGLONG은 64비트 서명된 정수의 덤프를 초래합니다. ULONGLONG은 64비트 서명되지 않은 정수의 덤프를 생성합니다.

클래스의 구현에 IMPLEMENT_DYNAMIC 또는 IMPLEMENT_SERIAL 매크로를 사용하는 경우 삽입 연산자는 을 통해 `CObject::Dump`-derived 클래스의 이름을 인쇄합니다. `CObject` 그렇지 않으면 인쇄됩니다. `CObject` 클래스의 함수를 `Dump` 재정의하면 육각형 덤프 대신 개체 내용의 보다 의미 있는 출력을 제공할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>C덤프 컨텍스트::세트 심층

덤프의 깊이를 설정합니다.

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>매개 변수

*nNewDepth*<br/>
새 깊이 값입니다.

### <a name="remarks"></a>설명

다른 개체에 대한 포인터가 없는 `CObject` 기본 형식 또는 단순을 덤프하는 경우 0 값으로 충분합니다. 값이 0보다 큰 값은 모든 개체가 재귀적으로 덤프되는 딥 덤프를 지정합니다. 예를 들어 컬렉션의 딥 덤프는 컬렉션의 모든 요소를 덤프합니다. 파생 클래스에서 다른 특정 깊이 값을 사용할 수 있습니다.

> [!NOTE]
> 순환 참조는 딥 덤프에서 검색되지 않으며 무한 루프가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
