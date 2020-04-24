---
title: CIPAddressCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: 0613dea766b022acf140a82bb4b01784793c2589
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754969"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl 클래스

Windows의 공용 IP 주소 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CIPAddressCtrl:::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CIPAddressCtrl::클리어 주소](#clearaddress)|IP 주소 제어의 내용을 지웁니다.|
|[CIPAddressCtrl::만들기](#create)|IP 주소 컨트롤을 만들고 개체에 `CIPAddressCtrl` 연결합니다.|
|[CIPAddressCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 IP 주소 컨트롤을 `CIPAddressCtrl` 만들고 개체에 연결합니다.|
|[CIPAddressCtrl::GetAddress](#getaddress)|IP 주소 컨트롤의 네 필드 모두에 대한 주소 값을 검색합니다.|
|[CIPAddressCtrl::공백](#isblank)|IP 주소 컨트롤의 모든 필드가 비어 있는지 확인합니다.|
|[CIPAddressCtrl::세트 주소](#setaddress)|IP 주소 컨트롤의 네 필드 모두에 대한 주소 값을 설정합니다.|
|[CIPAddressCtrl::세트필드 포커스](#setfieldfocus)|키보드 포커스를 IP 주소 제어의 지정된 필드로 설정합니다.|
|[CIPAddressCtrl::세트필드 레인지](#setfieldrange)|IP 주소 제어에서 지정된 필드의 범위를 설정합니다.|

## <a name="remarks"></a>설명

편집 컨트롤과 유사한 컨트롤인 IP 주소 컨트롤을 사용하면 IP(인터넷 프로토콜) 형식으로 숫자 주소를 입력하고 조작할 수 있습니다.

이 컨트롤(및 `CIPAddressCtrl` 따라서 클래스)은 Microsoft Internet Explorer 4.0 이상에서 실행되는 프로그램에서만 사용할 수 있습니다. 또한 Windows 및 Windows NT의 향후 버전에서도 사용할 수 있습니다.

IP 주소 제어에 대한 자세한 내용은 Windows SDK의 [IP 주소 컨트롤을](/windows/win32/Controls/ip-address-controls) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>CIPAddressCtrl:::CIPAddressCtrl

`CIPAddressCtrl` 개체를 만듭니다.

```
CIPAddressCtrl();
```

## <a name="cipaddressctrlclearaddress"></a><a name="clearaddress"></a>CIPAddressCtrl::클리어 주소

IP 주소 제어의 내용을 지웁니다.

```cpp
void ClearAddress();
```

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress)Win32 메시지의 동작을 구현합니다.

## <a name="cipaddressctrlcreate"></a><a name="create"></a>CIPAddressCtrl::만들기

IP 주소 컨트롤을 만들고 개체에 `CIPAddressCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용합니다. 컨트롤이 자식 창이어야 하기 때문에 WS_CHILD 스타일을 포함해야 합니다. 창 스타일 목록은 Windows SDK의 [창 만들기를](/windows/win32/api/winuser/nf-winuser-createwindoww) 참조하십시오.

*rect*<br/>
IP 주소 컨트롤의 크기와 위치에 대한 참조입니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
IP 주소 컨트롤의 상위 창에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
IP 주소 제어의 ID입니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CIPAddressCtrl` 객체를 생성합니다.

1. 개체를 만드는 생성자 `CIPAddressCtrl` 호출합니다.

1. IP `Create`주소 제어를 만드는 호출입니다.

컨트롤과 함께 확장 된 창 스타일을 사용 하려면 `Create`호출 [CreateEx](#createex) 대신 .

## <a name="cipaddressctrlcreateex"></a><a name="createex"></a>CIPAddressCtrl::만들기

이 함수를 호출하여 컨트롤(자식 창)을 `CIPAddressCtrl` 만들고 개체와 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
생성되는 컨트롤의 확장 스타일을 지정합니다. 확장 된 Windows 스타일 목록은 Windows SDK에서 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

*dwStyle*<br/>
IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용합니다. 컨트롤이 자식 창이어야 하기 때문에 WS_CHILD 스타일을 포함해야 합니다. 창 스타일 목록은 Windows SDK의 [창 만들기를](/windows/win32/api/winuser/nf-winuser-createwindoww) 참조하십시오.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 생성할 창의 크기와 위치를 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

만들기 `CreateEx` 대신 [Create](#create) Windows 확장 스타일 **서문 WS_EX_** 지정된 확장 된 Windows 스타일을 적용합니다.

## <a name="cipaddressctrlgetaddress"></a><a name="getaddress"></a>CIPAddressCtrl::GetAddress

IP 주소 컨트롤의 네 필드 모두에 대한 주소 값을 검색합니다.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>매개 변수

*n필드0*<br/>
압축된 IP 주소에서 필드 0 값에 대한 참조입니다.

*n필드1*<br/>
압축된 IP 주소에서 필드 1 값에 대한 참조입니다.

*n필드2*<br/>
압축된 IP 주소에서 필드 2 값에 대한 참조입니다.

*n필드3*<br/>
압축된 IP 주소에서 필드 3 값에 대한 참조입니다.

*dwAddress*<br/>
IP 주소를 받는 DWORD 값의 주소에 대한 참조입니다. *dwAddress가* 채워지는 방법을 보여 주는 표에 대한 **비고를** 참조하십시오.

### <a name="return-value"></a>Return Value

IP 주소 컨트롤의 비블 필드 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 IPM_GETADDRESS Win32 [메시지의](/windows/win32/Controls/ipm-getaddress)동작을 구현합니다. 위의 첫 번째 프로토타입에서 컨트롤의 0에서 3까지의 필드의 숫자는 각각 왼쪽에서 오른쪽으로 읽혀네 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입에서 *dwAddress는* 다음과 같이 채워집니다.

|필드|필드 값을 포함하는 비트|
|-----------|-------------------------------------|
|0|24 ~31|
|1|16 ~23|
|2|8 ~ 15|
|3|0 ~ 7|

## <a name="cipaddressctrlisblank"></a><a name="isblank"></a>CIPAddressCtrl::공백

IP 주소 컨트롤의 모든 필드가 비어 있는지 확인합니다.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Return Value

모든 IP 주소 제어 필드가 비어 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [IPM_ISBLANK](/windows/win32/Controls/ipm-isblank)Win32 메시지의 동작을 구현합니다.

## <a name="cipaddressctrlsetaddress"></a><a name="setaddress"></a>CIPAddressCtrl::세트 주소

IP 주소 컨트롤의 네 필드 모두에 대한 주소 값을 설정합니다.

```cpp
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>매개 변수

*n필드0*<br/>
압축된 IP 주소의 필드 0 값입니다.

*n필드1*<br/>
압축된 IP 주소의 필드 1 값입니다.

*n필드2*<br/>
압축된 IP 주소의 필드 2 값입니다.

*n필드3*<br/>
압축된 IP 주소의 필드 3 값입니다.

*dwAddress*<br/>
새 IP 주소를 포함하는 DWORD 값입니다. DWORD 값이 채워지는 방법을 보여 주는 표에 대한 **설명(설명)을** 참조하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress)Win32 메시지의 동작을 구현합니다. 위의 첫 번째 프로토타입에서 컨트롤의 0에서 3까지의 필드의 숫자는 각각 왼쪽에서 오른쪽으로 읽혀네 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입에서 *dwAddress는* 다음과 같이 채워집니다.

|필드|필드 값을 포함하는 비트|
|-----------|-------------------------------------|
|0|24 ~31|
|1|16 ~23|
|2|8 ~ 15|
|3|0 ~ 7|

## <a name="cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>CIPAddressCtrl::세트필드 포커스

키보드 포커스를 IP 주소 제어의 지정된 필드로 설정합니다.

```cpp
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>매개 변수

*n필드 (것)들*<br/>
포커스를 설정해야 하는 제로 기반 필드 인덱스입니다. 이 값이 필드 수보다 크면 포커스가 첫 번째 빈 필드로 설정됩니다. 모든 필드가 비어 없는 경우 포커스가 첫 번째 필드로 설정됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus)Win32 메시지의 동작을 구현합니다.

## <a name="cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>CIPAddressCtrl::세트필드 레인지

IP 주소 제어에서 지정된 필드의 범위를 설정합니다.

```cpp
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>매개 변수

*n필드 (것)들*<br/>
범위가 적용되는 0기반 필드 인덱스입니다.

*nLower*<br/>
이 IP 주소 제어에서 지정된 필드의 하한을 받는 정수에 대한 참조입니다.

*어퍼*<br/>
이 IP 주소 제어에서 지정된 필드의 상한을 받는 정수에 대한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 IPM_SETRANGE Win32 [메시지의](/windows/win32/Controls/ipm-setrange)동작을 구현합니다. 두 매개 변수인 *nLower* 및 *nUpper를*사용하여 Win32 메시지와 함께 사용되는 *wRange* 매개 변수 대신 필드의 하한및 상한을 나타냅니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
