---
title: CNetAddressCtrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: c6f391966ef6657363e8f23e5666a57a935b08e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752779"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl 클래스

`CNetAddressCtrl` 클래스에 입력 한 IPv4, IPv6 및 DNS 주소를 이름이 지정된 형식의 유효성을 검사하는 데 사용할 수 있는 네트워크 주소 컨트롤을 나타냅니다.

## <a name="syntax"></a>구문

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|`CNetAddressCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CNetAddressCtrl::만들기](#create)|지정된 스타일로 네트워크 주소 컨트롤을 만들고 현재 `CNetAddressCtrl` 개체에 연결합니다.|
|[CNetAddressCtrl::CreateEx](#createex)|지정된 확장 스타일을 사용하여 네트워크 주소 컨트롤을 만들고 `CNetAddressCtrl` 현재 개체에 연결합니다.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|사용자가 현재 네트워크 주소 컨트롤에서 지원되지 않는 네트워크 주소를 입력할 때 오류 풍선 팁을 표시합니다.|
|[CNetAddressCtrl::GetAddress](#getaddress)|현재 네트워크 주소 컨트롤과 연결된 네트워크 주소의 유효성이 검사되고 구문 분석된 표현을 검색합니다.|
|[CNetAddressCtrl::getAllowType](#getallowtype)|현재 네트워크 주소 제어에서 지원할 수 있는 네트워크 주소 유형을 검색합니다.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|현재 네트워크 주소 제어에서 지원할 수 있는 네트워크 주소 유형을 설정합니다.|

## <a name="remarks"></a>설명

네트워크 주소 컨트롤은 사용자가 입력하는 주소의 형식이 올바른지 확인합니다. 컨트롤이 실제로 네트워크 주소에 연결되지 않습니다. [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드가 구문 분석및 확인할 수 있는 하나 이상의 주소 유형을 지정합니다. 주소는 IPv4, IPv6 또는 서버, 네트워크, 호스트 또는 브로드캐스트 메시지 대상의 명명된 주소의 형태일 수 있습니다. 주소 형식이 올바르지 않은 경우 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 메서드를 사용하여 네트워크 주소 컨트롤의 텍스트 상자를 그래픽으로 가리키고 미리 정의된 오류 메시지를 표시하는 인포팁 메시지 상자를 표시할 수 있습니다.

`CNetAddressCtrl` 클래스는 [CEdit](../../mfc/reference/cedit-class.md) 클래스에서 파생 됩니다. 따라서 네트워크 주소 컨트롤은 모든 Windows 편집 제어 메시지에 대한 액세스를 제공합니다.

다음 그림에서는 네트워크 주소 컨트롤이 포함된 대화 상자를 설명합니다. 네트워크 주소 컨트롤의 텍스트 상자(1)에는 잘못된 네트워크 주소가 포함되어 있습니다. 네트워크 주소가 잘못되면 정보 팁 메시지(2)가 표시됩니다.

![네트워크 주소 컨트롤 및 정보 팁이 있는 대화 상자](../../mfc/reference/media/cnetaddctrl.png "네트워크 주소 컨트롤 및 정보 팁이 있는 대화 상자")

## <a name="example"></a>예제

다음 코드 예제는 네트워크 주소의 유효성을 검사하는 대화 상자의 일부입니다. 세 개의 라디오 단추에 대한 이벤트 처리기는 네트워크 주소가 세 가지 주소 유형 중 하나가 될 수 있음을 지정합니다. 사용자는 네트워크 컨트롤의 텍스트 상자에 주소를 입력한 다음 단추를 눌러 주소의 유효성을 검사합니다. 주소가 유효하면 성공 메시지가 표시됩니다. 그렇지 않으면 미리 정의된 인포팁 오류 메시지가 표시됩니다.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>예제

대화 상자 헤더 파일의 다음 코드 예제는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드에 필요한 [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) 및 [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) 변수를 정의합니다.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

이 클래스는 Windows Vista 및 이후에서 지원됩니다.

이 클래스에 대한 추가 요구 사항은 [Windows Vista 공용 컨트롤에 대한 빌드 요구 사항에](../../mfc/build-requirements-for-windows-vista-common-controls.md)설명되어 있습니다.

## <a name="cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>C넷주소Ctrl::CNetAddressCtrl

`CNetAddressCtrl` 개체를 생성합니다.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>설명

[CNetAddressCtrl::만들기](#create) 또는 [CNetAddressCtrl:CreateEx](#createex) 메서드를 사용하여 네트워크 컨트롤을 만들고 `CNetAddressCtrl` 개체에 연결합니다.

## <a name="cnetaddressctrlcreate"></a><a name="create"></a>CNetAddressCtrl::만들기

지정된 스타일로 네트워크 주소 컨트롤을 만들고 현재 `CNetAddressCtrl` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwStyle*|【인】 컨트롤에 적용할 스타일의 비트 조합입니다. 자세한 내용은 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)을 참조하십시오.|
|*rect*|【인】 컨트롤의 위치와 크기를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.|
|*pParentWnd*|【인】 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 null이 아닌 포인터입니다.|
|*nID*|【인】 컨트롤의 ID입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cnetaddressctrlcreateex"></a><a name="createex"></a>CNetAddressCtrl::만들기

지정된 확장 스타일을 사용하여 네트워크 주소 컨트롤을 만들고 `CNetAddressCtrl` 현재 개체에 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwExStyle*|【인】 컨트롤에 적용할 확장 된 스타일의 비트 조합(OR)입니다. 자세한 내용은 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 함수의 *dwExStyle* 매개 변수를 참조하십시오.|
|*dwStyle*|【인】 컨트롤에 적용할 스타일의 비트 조합(OR)입니다. 자세한 내용은 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)을 참조하십시오.|
|*rect*|【인】 컨트롤의 위치와 크기를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.|
|*pParentWnd*|【인】 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 null이 아닌 포인터입니다.|
|*nID*|【인】 컨트롤의 ID입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip

현재 네트워크 주소 컨트롤과 연결된 풍선 팁에 오류 메시지가 표시됩니다.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Return Value

이 `S_OK` 메서드가 성공한 경우 값입니다. 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

[CNetAddressCtrl::SetAllowType](#setallowtype) 메서드를 사용하여 현재 네트워크 주소 제어에서 지원할 수 있는 주소 유형을 지정합니다. [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 사용하여 사용자가 입력하는 네트워크 주소를 확인하고 구문 분석합니다. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 메서드를 사용하여 [CNetAddressCtrl::GetAddress](#getaddress) 메서드가 실패한 경우 오류 메시지 정보 팁을 표시합니다.

이 메시지는 Windows SDK에 설명된 [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) 매크로를 호출합니다. 해당 매크로는 `NCM_DISPLAYERRORTIP` 메시지를 보냅니다.

## <a name="cnetaddressctrlgetaddress"></a><a name="getaddress"></a>CNetAddressCtrl::GetAddress

현재 네트워크 주소 컨트롤과 연결된 네트워크 주소의 유효성이 검사되고 구문 분석된 표현을 검색합니다.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>매개 변수

*pAddress*<br/>
【인, 아웃】 [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) 구조에 대한 포인터입니다.  GetAddress 메서드를 호출하기 전에 이 구조체의 *pAddrInfo* 멤버를 [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) 구조의 주소로 설정합니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 값이 S_OK. 그렇지 않으면 COM 오류 코드입니다. 가능한 오류 코드에 대한 자세한 내용은 [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) 매크로의 값 반환 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 메서드가 성공하면 [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) 구조에는 네트워크 주소에 대한 추가 정보가 포함됩니다.

[CNetAddressCtrl::SetAllowType](#setallowtype) 메서드를 사용하여 현재 네트워크 주소 제어가 지원할 수 있는 주소 유형을 지정합니다. [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 사용하여 사용자가 입력하는 네트워크 주소를 확인하고 구문 분석합니다. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 메서드를 사용하여 [CNetAddressCtrl::GetAddress](#getaddress) 메서드가 실패한 경우 오류 메시지 정보 팁을 표시합니다.

이 메서드는 Windows SDK에 설명 된 [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) 매크로를 호출 합니다. 이 매크로는 NCM_GETADDRESS 메시지를 보냅니다.

## <a name="cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>CNetAddressCtrl::getAllowType

현재 네트워크 주소 제어에서 지원할 수 있는 네트워크 주소 유형을 검색합니다.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Return Value

네트워크 주소 제어가 지원할 수 있는 주소 유형을 지정하는 플래그의 비트 조합(OR)입니다. 자세한 내용은 [NET_STRING](/windows/win32/shell/net-string)를 참조하십시오.

### <a name="remarks"></a>설명

이 메시지는 Windows SDK에 설명된 [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) 매크로를 호출합니다. 이 매크로는 NCM_GETALLOWTYPE 메시지를 보냅니다.

## <a name="cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>CNetAddressCtrl::설정 허용 형식

현재 네트워크 주소 제어에서 지원할 수 있는 네트워크 주소 유형을 설정합니다.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwAddrMask*|【인】 네트워크 주소 제어가 지원할 수 있는 주소 유형을 지정하는 플래그의 비트 조합(OR)입니다. 자세한 내용은 [NET_STRING](/windows/win32/shell/net-string)를 참조하십시오.|

### <a name="return-value"></a>Return Value

이 메서드가 성공했는지 S_OK. 그렇지 않으면 COM 오류 코드입니다.

### <a name="remarks"></a>설명

[CNetAddressCtrl::SetAllowType](#setallowtype) 메서드를 사용하여 현재 네트워크 주소 제어에서 지원할 수 있는 주소 유형을 지정합니다. [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 사용하여 사용자가 입력하는 네트워크 주소를 확인하고 구문 분석합니다. [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 메서드를 사용하여 [CNetAddressCtrl::GetAddress](#getaddress) 메서드가 실패한 경우 오류 메시지 정보 팁을 표시합니다.

이 메시지는 Windows SDK에 설명된 [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) 매크로를 호출합니다. 이 매크로는 NCM_SETALLOWTYPE 메시지를 보냅니다.

## <a name="see-also"></a>참조

[CNetAddressCtrl 클래스](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)
