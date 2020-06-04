---
title: CClientDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: abe8a3220fd37a0375fcf37504c715edf4c6962e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352302"
---
# <a name="cclientdc-class"></a>CClientDC 클래스

Windows 함수 [GetDC를](/windows/win32/api/winuser/nf-winuser-getdc) 시공 시 및 소멸 시 [ReleaseDC로](/windows/win32/api/winuser/nf-winuser-releasedc) 호출합니다.

## <a name="syntax"></a>구문

```
class CClientDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C클라이언트DC::CClientDC](#cclientdc)|`CWnd`에 연결된 `CClientDC` 개체를 생성합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C클라이언트DC:m_hWnd](#m_hwnd)|유효한 `CClientDC` 창의 HWND입니다.|

## <a name="remarks"></a>설명

즉, `CClientDC` 개체와 연결된 장치 컨텍스트가 창의 클라이언트 영역입니다.

자세한 `CClientDC`내용은 장치 [컨텍스트 를 참조하십시오.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a>C클라이언트DC::CClientDC

`CClientDC` *pWnd로*가리키는 [CWnd의](../../mfc/reference/cwnd-class.md) 클라이언트 영역에 액세스하는 개체를 생성합니다.

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
장치 컨텍스트 개체가 액세스할 클라이언트 영역의 창입니다.

### <a name="remarks"></a>설명

생성자는 Windows 함수 [GetDC를](/windows/win32/api/winuser/nf-winuser-getdc)호출합니다.

Windows `GetDC` 호출에 `CResourceException`실패하면 예외(형식)가 throw됩니다. Windows에서 사용 가능한 모든 장치 컨텍스트를 이미 할당한 경우 장치 컨텍스트를 사용하지 못할 수 있습니다. 응용 프로그램은 Windows에서 지정된 시간에 사용할 수 있는 다섯 가지 일반적인 디스플레이 컨텍스트에 대해 경쟁합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a>C클라이언트DC:m_hWnd

`HWND` 개체를 `CWnd` 생성하는 데 사용되는 `CClientDC` 포인터입니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

*m_hWnd* 보호된 변수입니다.

### <a name="example"></a>예제

  [CClientDC::CClientDC에](#cclientdc)대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
