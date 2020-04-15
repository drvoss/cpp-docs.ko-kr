---
title: CWinForms제어 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: c91f50be1ea30efac81ff67c43633bedd7b0ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377186"
---
# <a name="cwinformscontrol-class"></a>CWinForms제어 클래스

Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>매개 변수

*TManagedControl*<br/>
MFC 응용 프로그램에 표시할 .NET 프레임워크 Windows Forms 컨트롤입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWinForms 제어::CWinForms제어](#cwinformscontrol)|MFC Windows Forms 컨트롤 래퍼 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinForms 제어::만들기관리제어](#createmanagedcontrol)|MFC 컨테이너에서 Windows 양식 컨트롤을 만듭니다.|
|[CWinForms 제어::Getcontrol](#getcontrol)|Windows 양식 컨트롤에 대한 포인터를 검색합니다.|
|[CWinForms 제어::GetControl핸들](#getcontrolhandle)|Windows 양식 컨트롤에 대한 핸들을 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CWinForms제어::연산자 -&gt;](#operator_-_gt)|[CWinFormsControl::GetControl](#getcontrol) 식에서 대체합니다.|
|[CWinForms제어::연산자 TManagedControl^](#operator_tmanagedcontrol)|Windows 양식 컨트롤에 대한 포인터로 형식을 캐스팅합니다.|

## <a name="remarks"></a>설명

클래스는 `CWinFormsControl` Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공합니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

MFC 코드는 Window 핸들(일반적으로 저장됨)을 캐시해서는 안 됩니다. `m_hWnd` 일부 Windows Forms 컨트롤 속성은 기본 `Window` Win32를 `DestroyWindow` 삭제하고 `CreateWindow`을 사용하여 다시 만들어야 합니다. MFC Windows Forms 구현은 `Destroy` `Create` 멤버를 업데이트하는 컨트롤의 이벤트와 이벤트를 처리합니다. `m_hWnd`

> [!NOTE]
> MFC Windows Forms 통합은 AFXDLL이 정의된 MFC와 동적으로 연결되는 프로젝트에서만 작동합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinForms 제어::만들기관리제어

MFC 컨테이너에서 Windows 양식 컨트롤을 만듭니다.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>매개 변수

*p유형*<br/>
만들 컨트롤의 데이터 형식입니다. [형식](/dotnet/api/system.type) 데이터 형식이어야 합니다.

*dwStyle*<br/>
컨트롤에 적용할 창 스타일입니다. 창 스타일 조합을 [지정합니다.](../../mfc/reference/styles-used-by-mfc.md#window-styles) 현재 WS_TABSTOP, WS_VISIBLE, WS_DISABLED 및 WS_GROUP 다음과 같은 스타일만 지원됩니다.

*rect*<br/>
컨트롤의 왼쪽 위 및 오른쪽 아래 모서리의 좌표를 정의하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조체입니다(첫 번째 오버로드만 해당).

*n플레이스홀더ID*<br/>
리소스 편집기에 배치된 정적 자리 홀더 컨트롤의 핸들입니다. 새로 만든 Windows Forms 컨트롤은 위치, z 차수 및 스타일(두 번째 오버로드만 해당)을 가정하여 정적 컨트롤을 대체합니다.

*pParentWnd*<br/>
상위 창에 대한 포인터입니다.

*nID*<br/>
새로 만든 컨트롤에 할당할 리소스 ID 번호입니다.

*pControl*<br/>
[CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) 개체와 연결되는 Windows Forms 컨트롤의 인스턴스입니다(네 번째 오버로드만).

### <a name="return-value"></a>Return Value

성공하면 영하지 않은 값을 반환합니다. 실패하면 0을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 MFC 컨테이너에서 .NET 프레임 워크 Windows Forms 컨트롤을 인스턴스화 합니다.

메서드의 첫 번째 오버로드는 MFC가 이 형식의 새 개체를 인스턴스화할 수 있도록 .NET Framework 데이터 형식 *pType을* 허용합니다. *pType은* [형식](/dotnet/api/system.type) 데이터 형식이어야 합니다.

메서드의 두 번째 오버로드클래스의 `TManagedControl` 템플릿 매개 변수를 `CWinFormsControl` 기반으로 Windows Forms 컨트롤을 만듭니다. 컨트롤의 크기와 위치는 메서드에 전달된 `RECT` 구조를 기반으로 합니다. 스타일에 는 *dw스타일만* 중요합니다.

메서드의 세 번째 오버로드는 정적 컨트롤을 대체하여 해당 컨트롤을 파괴하고 위치, z-순서 및 스타일을 가정하는 Windows Forms 컨트롤을 만듭니다. 정적 컨트롤은 Windows Forms 컨트롤의 자리 표시자로만 사용할 수 있습니다. 컨트롤을 만들 때 이 오버로드는 *dwStyle의* 스타일을 정적 컨트롤의 리소스 스타일과 결합합니다.

메서드의 네 번째 오버로드를 사용하면 MFC가 래핑할 이미 인스턴스화된 Windows Forms 컨트롤 *pControl을* 전달할 수 있습니다. 클래스의 `TManagedControl` 템플릿 매개 변수와 동일한 형식이어야 `CWinFormsControl` 합니다.

Windows 양식 컨트롤을 사용하는 샘플은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 참조하십시오.

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CWinForms 제어::CWinForms제어

MFC Windows Forms 컨트롤 래퍼 개체를 생성합니다.

```
CWinFormsControl();
```

### <a name="remarks"></a>설명

Windows 양식 컨트롤은 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)을 호출할 때 인스턴스화됩니다.

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinForms 제어::Getcontrol

Windows 양식 컨트롤에 대한 포인터를 검색합니다.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Return Value

Windows 양식 컨트롤에 대한 포인터를 반환합니다.

### <a name="example"></a>예제

  [CWinForms제어::만들기관리관리.](#createmanagedcontrol)

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinForms 제어::GetControl핸들

Windows 양식 컨트롤에 대한 핸들을 검색합니다.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Return Value

핸들을 Windows 양식 컨트롤에 반환합니다.

### <a name="remarks"></a>설명

`GetControlHandle`는 .NET Framework 컨트롤 속성에 저장된 창 핸들을 반환하는 도우미 메서드입니다. 창 핸들 값은 [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) 호출 하는 동안 [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#attach)복사 됩니다.

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinForms제어::연산자 -&gt;

[CWinFormsControl::GetControl](#getcontrol) 식에서 대체합니다.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>설명

이 연산자는 식에서 대체하는 `GetControl` 편리한 구문을 제공합니다.

Windows 양식에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinForms제어::연산자 TManagedControl^

Windows 양식 컨트롤에 대한 포인터로 형식을 캐스팅합니다.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>설명

이 연산자는 Windows Forms 컨트롤에 대한 포인터를 허용하는 함수를 전달합니다. `CWinFormsControl<TManagedControl>`

## <a name="see-also"></a>참고 항목

[CWinForms디아로그 클래스](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinForms뷰 클래스](../../mfc/reference/cwinformsview-class.md)
