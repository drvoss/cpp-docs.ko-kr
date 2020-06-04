---
title: CPaintDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: 55342b03454a6dba07bc10ea5f0464c34e0e8db3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374771"
---
# <a name="cpaintdc-class"></a>CPaintDC 클래스

[CDC에서](../../mfc/reference/cdc-class.md)파생된 장치 컨텍스트 클래스입니다.

## <a name="syntax"></a>구문

```
class CPaintDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|지정된 `CPaintDC` [CWnd에](../../mfc/reference/cwnd-class.md)연결된 를 구성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|클라이언트 영역을 페인트하는 데 사용되는 [PAINTSTRUCT를](/windows/win32/api/winuser/ns-winuser-paintstruct) 포함합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|이 `CPaintDC` 개체가 연결된 HWND입니다.|

## <a name="remarks"></a>설명

구성 시 [CWnd::BeginPaint를](../../mfc/reference/cwnd-class.md#beginpaint) 수행하고 [CWnd::EndPaint를](../../mfc/reference/cwnd-class.md#endpaint) 파괴 할 때 수행합니다.

개체는 `CPaintDC` [일반적으로 메시지](/windows/win32/gdi/wm-paint) 처리기 멤버 함수에서 WM_PAINT `OnPaint` 메시지에 응답할 때만 사용할 수 있습니다.

사용에 `CPaintDC`대한 자세한 내용은 [장치 컨텍스트 를 참조하십시오.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cpaintdccpaintdc"></a><a name="cpaintdc"></a>CPaintDC::CPaintDC

`CPaintDC` 개체를 생성하고, 그리기를 위해 응용 프로그램 창을 준비하고, [m_ps](#m_ps) 멤버 변수에 [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) 구조체를 저장합니다.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
개체가 `CWnd` 속한 개체를 `CPaintDC` 가리킵니다.

### <a name="remarks"></a>설명

Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) 호출이 실패하면 예외 (`CResourceException`형식)가 throw됩니다. Windows에서 사용 가능한 모든 장치 컨텍스트를 이미 할당한 경우 장치 컨텍스트를 사용하지 못할 수 있습니다. 응용 프로그램은 Windows에서 지정된 시간에 사용할 수 있는 다섯 가지 일반적인 디스플레이 컨텍스트에 대해 경쟁합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

## <a name="cpaintdcm_hwnd"></a><a name="m_hwnd"></a>CPaintDC::m_hWnd

이 `HWND` `CPaintDC` 개체가 연결된 대상입니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

*m_hWnd* HWND 형식의 보호된 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

## <a name="cpaintdcm_ps"></a><a name="m_ps"></a>CPaintDC::m_ps

`m_ps`은 [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct)형식의 공용 멤버 변수입니다.

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>설명

`PAINTSTRUCT` [CWnd::BeginPaint에](../../mfc/reference/cwnd-class.md#beginpaint)의해 전달되고 채워지는 것입니다.

에는 `PAINTSTRUCT` 응용 프로그램에서 `CPaintDC` 개체와 연결된 창의 클라이언트 영역을 페인칠하는 데 사용하는 정보가 들어 있습니다.

`PAINTSTRUCT`을 통해 장치 컨텍스트 핸들에 액세스할 수 있습니다. 그러나 CDC에서 `m_hDC` `CPaintDC` 상속하는 멤버 변수를 통해 핸들에 더 직접적으로 액세스할 수 있습니다.

### <a name="example"></a>예제

  [CPaintDC:m_hWnd](#m_hwnd)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
