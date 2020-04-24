---
title: CHotKeyCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: a79cc0ab2c01633f96430477aa536a60385461e9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750807"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl 클래스

Windows의 공용 바로 가기 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHotKeyCtrl:::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHotKeyCtrl::만들기](#create)|단축키 컨트롤을 만들고 개체에 `CHotKeyCtrl` 연결합니다.|
|[CHotKeyCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 단축키 컨트롤을 만들고 `CHotKeyCtrl` 개체에 연결합니다.|
|[CHotKeyCtrl::GetHotKey](#gethotkey)|단축키 컨트롤에서 핫 키의 가상 키 코드 및 수정자 플래그를 검색합니다.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|핫 키에 할당된 로컬 문자 집합에서 키 이름을 검색합니다.|
|[CHotKeyCtrl::getKeyName](#getkeyname)|지정된 가상 키 코드에 할당된 로컬 문자 집합에서 키 이름을 검색합니다.|
|[CHotKeyCtrl::SetHotKey](#sethotkey)|단축키 컨트롤의 단축키 조합을 설정합니다.|
|[CHotKeyCtrl::SetRules](#setrules)|핫 키 컨트롤에 대한 잘못된 조합과 기본 수정자 조합을 정의합니다.|

## <a name="remarks"></a>설명

"바로 이동 키 컨트롤"은 사용자가 바로 키를 만들 수 있는 창입니다. "바로 가기 키"는 사용자가 빠르게 작업을 수행하기 위해 누를 수 있는 키 조합입니다. 예를 들어 사용자는 지정된 창을 활성화하고 Z 순서의 맨 위로 가져오는 바로 가있는 키를 만들 수 있습니다. 바로 가기 키 컨트롤은 사용자의 선택을 표시하고 사용자가 유효한 키 조합을 선택하도록 합니다.

이 컨트롤(및 `CHotKeyCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

사용자가 키 조합을 선택하면 응용 프로그램은 컨트롤에서 지정된 키 조합을 검색하고 WM_SETHOTKEY 메시지를 사용하여 시스템의 단축키를 설정할 수 있습니다. 이후 사용자가 시스템의 모든 부분에서 핫 키를 누를 때마다 WM_SETHOTKEY 메시지에 지정된 창은 SC_HOTKEY 지정하는 WM_SYSCOMMAND 메시지를 받습니다. 이 메시지는 수신하는 창을 활성화합니다. 바로 간전화 키는 WM_SETHOTKEY 호출한 응용 프로그램이 종료될 때까지 유효합니다.

이 메커니즘은 WM_HOTKEY 메시지와 Windows [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey) 및 [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-unregisterhotkey) 기능 취소 기능에 종속된 바로 키 지원과 다릅니다.

사용에 `CHotKeyCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CHotKeyCtrl 사용](../../mfc/using-chotkeyctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>CHotKeyCtrl:::CHotKeyCtrl

`CHotKeyCtrl` 개체를 생성합니다.

```
CHotKeyCtrl();
```

## <a name="chotkeyctrlcreate"></a><a name="create"></a>CHotKeyCtrl::만들기

단축키 컨트롤을 만들고 개체에 `CHotKeyCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
단축키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용합니다. 자세한 내용은 Windows SDK의 [일반 제어 스타일을](/windows/win32/Controls/common-control-styles) 참조하십시오.

*rect*<br/>
단축키 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조일](/windows/win32/api/windef/ns-windef-rect)수 있습니다.

*pParentWnd*<br/>
단축키 컨트롤의 부모 창(일반적으로 [CDialog)을](../../mfc/reference/cdialog-class.md)지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
단축키 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

비제로, 초기화가 성공한 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CHotKeyCtrl` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 `CHotKeyCtrl` 합니다 .

컨트롤과 함께 확장 된 창 스타일을 사용 하려면 `Create`호출 [CreateEx](#createex) 대신 .

## <a name="chotkeyctrlcreateex"></a><a name="createex"></a>CHotKeyCtrl::만들기

이 함수를 호출하여 컨트롤(자식 창)을 `CHotKeyCtrl` 만들고 개체와 연결합니다.

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
단축키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용합니다. 자세한 내용은 Windows SDK의 [일반 제어 스타일을](/windows/win32/Controls/common-control-styles) 참조하십시오.

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

## <a name="chotkeyctrlgethotkey"></a><a name="gethotkey"></a>CHotKeyCtrl::GetHotKey

바로 가기 키 컨트롤에서 키보드 단축키의 가상 키 코드 및 수정자 플래그를 검색합니다.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>매개 변수

*w버추얼키코드*<br/>
【아웃】 키보드 바로 가기의 가상 키 코드입니다. 표준 가상 키 코드 목록은 Winuser.h를 참조하십시오.

*모디 피어*<br/>
【아웃】 키보드 바로 가기키에서 수정자 키를 나타내는 플래그의 비트 조합(OR)입니다.

수정자 플래그는 다음과 같습니다.

|플래그|해당 키|
|----------|-----------------------|
|HOTKEYF_ALT|Alt 키|
|HOTKEYF_CONTROL|CTRL 키|
|HOTKEYF_EXT|확장 키|
|HOTKEYF_SHIFT|시프트 키|

### <a name="return-value"></a>Return Value

첫 번째 오버로드된 메서드에서는 가상 키 코드와 수정자 플래그를 포함하는 DWORD입니다. 낮은 순서 단어의 낮은 순서 바이트는 가상 키 코드를 포함, 낮은 순서 단어의 높은 순서 바이트는 수정자 플래그를 포함 하 고 높은 순서 단어는 0.

### <a name="remarks"></a>설명

가상 키 코드와 수정자 키가 함께 키보드 바로 가기를 정의합니다.

## <a name="chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName

이 멤버 함수를 호출하여 핫 키의 지역화된 이름을 가져옵니다.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Return Value

현재 선택한 핫 키의 지역화된 이름입니다. 선택한 단축키가 없는 `GetHotKeyName` 경우 빈 문자열을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수가 반환하는 이름은 키보드 드라이버에서 비롯됩니다. 지역화된 버전의 Windows에 지역화되지 않은 키보드 드라이버를 설치할 수 있으며 그 반대의 경우도 마찬가지입니다.

## <a name="chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>CHotKeyCtrl::getKeyName

지정된 가상 키 코드에 할당된 키의 지역화된 이름을 얻으려면 이 멤버 함수를 호출합니다.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>매개 변수

*Vk*<br/>
가상 키 코드입니다.

*fExtended*<br/>
가상 키 코드가 확장 키인 경우 TRUE; 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

*vk* 매개 변수에 의해 지정된 키의 지역화된 이름입니다. 키에 매핑된 이름이 없는 `GetKeyName` 경우 빈 문자열을 반환합니다.

### <a name="remarks"></a>설명

이 함수가 반환하는 키 이름은 키보드 드라이버에서 비롯되므로 지역화된 버전의 Windows에 지역화되지 않은 키보드 드라이버를 설치할 수 있으며 그 반대의 경우도 마찬가지입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

## <a name="chotkeyctrlsethotkey"></a><a name="sethotkey"></a>CHotKeyCtrl::SetHotKey

바로 가기 키 컨트롤의 바로 가기를 설정합니다.

```cpp
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>매개 변수

*w버추얼키코드*<br/>
【인】 키보드 바로 가기의 가상 키 코드입니다. 표준 가상 키 코드 목록은 Winuser.h를 참조하십시오.

*모디 피어*<br/>
【인】 키보드 바로 가기키에서 수정자 키를 나타내는 플래그의 비트 조합(OR)입니다.

수정자 플래그는 다음과 같습니다.

|플래그|해당 키|
|----------|-----------------------|
|HOTKEYF_ALT|Alt 키|
|HOTKEYF_CONTROL|CTRL 키|
|HOTKEYF_EXT|확장 키|
|HOTKEYF_SHIFT|시프트 키|

### <a name="remarks"></a>설명

가상 키 코드와 수정자 키가 함께 키보드 바로 가기를 정의합니다.

## <a name="chotkeyctrlsetrules"></a><a name="setrules"></a>CHotKeyCtrl::SetRules

이 함수를 호출하여 잘못된 조합과 핫 키 컨트롤에 대한 기본 수정자 조합을 정의합니다.

```cpp
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>매개 변수

*w앵발리콤*<br/>
잘못된 키 조합을 지정하는 플래그 배열입니다. 다음 값의 조합일 수 있습니다.

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL+ALT

- 수정되지 않은 키HKCOMB_NONE

- HKCOMB_S 시프트

- HKCOMB_SA 시프트+ALT

- HKCOMB_SC 시프트+CTRL

- HKCOMB_SCA 시프트+CTRL+ALT

*모디 피어*<br/>
사용자가 잘못된 조합을 입력할 때 사용할 키 조합을 지정하는 플래그 배열입니다. 수정자 플래그에 대한 자세한 내용은 [GetHotKey](#gethotkey)를 참조하십시오.

### <a name="remarks"></a>설명

사용자가 *wInvalidComb에*지정된 플래그에 의해 정의된 대로 잘못된 키 조합을 입력하면 시스템은 OR 연산자를 사용하여 사용자가 입력한 키를 *wModifiers에*지정된 플래그와 결합합니다. 결과 키 조합은 문자열로 변환된 다음 단축키 컨트롤에 표시됩니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
