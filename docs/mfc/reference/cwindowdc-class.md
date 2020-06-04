---
title: CWindowDC 클래스
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 89a822280ddebca942016f9a3a334a7128d8456a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371975"
---
# <a name="cwindowdc-class"></a>CWindowDC 클래스

`CDC`에서 파생됩니다.

## <a name="syntax"></a>구문

```
class CWindowDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` 개체를 생성합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CWindowDC::m_hWnd](#m_hwnd)|이 `CWindowDC` 가 첨부되는 HWND입니다.|

## <a name="remarks"></a>설명

생성 시 Windows 함수 [GetWindowDC를](/windows/win32/api/winuser/nf-winuser-getwindowdc)호출하고 소멸 시 [릴리스DC를](/windows/win32/api/winuser/nf-winuser-releasedc) 호출합니다. 즉, `CWindowDC` 개체가 [CWnd](../../mfc/reference/cwnd-class.md) (클라이언트 및 비클라이언트 영역)의 전체 화면 영역에 액세스합니다.

사용에 `CWindowDC`대한 자세한 내용은 [장치 컨텍스트 를 참조하십시오.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>요구 사항

헤더: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a>C윈도우DC::CWindowDC

`CWindowDC` *pWnd로*가리키는 개체의 전체 화면 영역(클라이언트 및 `CWnd` 비클라이언트 모두)에 액세스하는 개체를 생성합니다.

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
장치 컨텍스트 개체가 액세스할 클라이언트 영역의 창입니다.

### <a name="remarks"></a>설명

생성자는 Windows 함수 [GetWindowDC를](/windows/win32/api/winuser/nf-winuser-getwindowdc)호출합니다.

Windows `GetWindowDC` 호출에 `CResourceException`실패하면 예외(형식)가 throw됩니다. Windows에서 사용 가능한 모든 장치 컨텍스트를 이미 할당한 경우 장치 컨텍스트를 사용하지 못할 수 있습니다. 응용 프로그램은 Windows에서 지정된 시간에 사용할 수 있는 다섯 가지 일반적인 디스플레이 컨텍스트에 대해 경쟁합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a>CWindowDC::m_hWnd

포인터의 `CWnd` HWND는 `CWindowDC` 개체를 생성하는 데 사용됩니다.

```
HWND m_hWnd;
```

### <a name="remarks"></a>설명

`m_hWnd`는 HWND 형식의 보호된 변수입니다.

### <a name="example"></a>예제

  [CWindowDC::CWindowDC에](#cwindowdc)대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
