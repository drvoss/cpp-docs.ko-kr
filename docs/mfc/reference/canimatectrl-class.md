---
title: 카니메이트Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
ms.openlocfilehash: e570681c899d58e8659635d55da843c23d1e95ee
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752887"
---
# <a name="canimatectrl-class"></a>카니메이트Ctrl 클래스

Windows 공용 애니메이션 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAnimateCtrl:::CAnimateCtrl](#canimatectrl)|`CAnimateCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[애니메이트Ctrl::닫기](#close)|AVI 클립을 닫습니다.|
|[CAnimateCtrl::만들기](#create)|애니메이션 컨트롤을 만들고 오브젝트에 `CAnimateCtrl` 연결합니다.|
|[CAnimateCtrl::CreateEx](#createex)|지정된 Windows 확장 스타일로 애니메이션 컨트롤을 만들고 개체에 `CAnimateCtrl` 연결합니다.|
|[애니메이트트르::플레이 중](#isplaying)|오디오 비디오 인터리브(AVI) 클립이 재생되고 있는지 여부를 나타냅니다.|
|[애니메이트Ctrl::열기](#open)|파일 또는 리소스에서 AVI 클립을 열고 첫 번째 프레임을 표시합니다.|
|[카니메이트트툴::P레이](#play)|소리 없이 AVI 클립을 재생합니다.|
|[CAnimateCtrl::검색](#seek)|AVI 클립의 선택한 단일 프레임을 표시합니다.|
|[애니메이트Ctrl::정지](#stop)|AVI 클립 재생을 중지합니다.|

## <a name="remarks"></a>설명

이 컨트롤(및 `CAnimateCtrl` 따라서 클래스)은 Windows 95, Windows 98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

애니메이션 컨트롤은 표준 Windows 비디오/오디오 형식인 AVI(오디오 비디오 인터리브) 형식으로 클립을 표시하는 직사각형 창입니다. AVI 클립은 영화와 같은 일련의 비트맵 프레임입니다.

애니메이션 컨트롤은 간단한 AVI 클립만 재생할 수 있습니다. 특히 애니메이션 컨트롤에서 재생할 클립은 다음 요구 사항을 충족해야 합니다.

- 정확히 하나의 비디오 스트림이 있어야 하며 프레임이 하나 이상 있어야 합니다.

- 파일에는 거의 두 개의 스트림이 있을 수 있습니다(일반적으로 다른 스트림이 있는 경우 애니메이션 컨트롤은 오디오 정보를 무시하지만 오디오 스트림입니다).

- 클립은 RLE8 압축으로 압축되지 않았거나 압축되어야 합니다.

- 비디오 스트림에서는 팔레트 변경이 허용되지 않습니다.

응용 프로그램에 AVI 클립을 AVI 리소스로 추가하거나 응용 프로그램을 별도의 AVI 파일로 함께 사용할 수 있습니다.

AVI 클립이 표시되는 동안 스레드가 계속 실행되므로 애니메이션 컨트롤의 일반적인 용도 중 하나는 긴 작업 중에 시스템 활동을 나타내는 것입니다. 예를 들어 파일 탐색기의 대화 상자찾기상자에는 시스템이 파일을 검색할 때 움직이는 돋보기가 표시됩니다.

대화 상자 `CAnimateCtrl` 내에서 또는 대화 상자 편집기사용 대화 상자 리소스에서 개체를 만들면 사용자가 대화 상자를 닫으면 자동으로 소멸됩니다.

창 내에서 `CAnimateCtrl` 객체를 만드는 경우 객체를 삭제해야 할 수 있습니다. 스택에서 객체를 `CAnimateCtrl` 만들면 자동으로 소멸됩니다. 새 함수를 `CAnimateCtrl` 사용하여 힙에 개체를 **new** 만드는 경우 개체에서 **삭제를** 호출하여 삭제해야 삭제해야 합니다. 해당 클래스에서 `CAnimateCtrl` 새 클래스를 파생하고 해당 클래스의 메모리를 할당하는 경우 `CAnimateCtrl` 소멸자 재정의하여 할당을 삭제합니다.

사용에 `CAnimateCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CAnimateCtrl 사용](../../mfc/using-canimatectrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl:::CAnimateCtrl

`CAnimateCtrl` 개체를 생성합니다.

```
CAnimateCtrl();
```

### <a name="remarks"></a>설명

만드는 개체에서 다른 작업을 수행하려면 먼저 멤버 [만들기](#create) 함수를 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

## <a name="canimatectrlclose"></a><a name="close"></a>애니메이트Ctrl::닫기

애니메이션 컨트롤에서 이전에 열린 AVI 클립을 닫고 메모리에서 제거합니다.

```
BOOL Close();
```

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::만들기

애니메이션 컨트롤을 만들고 오브젝트에 `CAnimateCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
애니메이션 컨트롤의 스타일을 지정합니다. 아래 설명 섹션에 설명된 창 스타일과 Windows SDK의 애니메이션 제어 스타일에 설명된 애니메이션 컨트롤 스타일 조합을 [적용합니다.](/windows/win32/Controls/animation-control-styles)

*rect*<br/>
애니메이션 컨트롤의 위치와 크기를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
애니메이션 컨트롤의 부모 창(일반적으로 을 `CDialog`지정합니다.) NULL이 아니어야 합니다.

*nID*<br/>
애니메이션 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CAnimateCtrl` 구성합니다. 먼저 생성자 호출 한 다음 `Create`애니메이션 컨트롤을 만들고 `CAnimateCtrl` 개체에 연결 하는 호출 합니다.

다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 애니메이션 컨트롤에 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

애니메이션 컨트롤에서 확장 된 창 스타일을 사용 하려면 호출 `Create` [CreateEx](#createex) 대신.

위에 나열된 창 스타일 외에도 애니메이션 컨트롤 스타일 중 하나 이상을 애니메이션 컨트롤에 적용할 수 있습니다. [애니메이션 제어 스타일에](/windows/win32/Controls/animation-control-styles)대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="example"></a>예제

  [CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::CreateEx

컨트롤(하위 창)을 만들고 `CAnimateCtrl` 개체와 연결합니다.

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
애니메이션 컨트롤의 스타일을 지정합니다. Windows SDK의 애니메이션 제어 스타일에 설명된 창 및 애니메이션 컨트롤 스타일의 조합을 [적용합니다.](/windows/win32/Controls/animation-control-styles)

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

## <a name="canimatectrlisplaying"></a><a name="isplaying"></a>애니메이트트르::플레이 중

오디오 비디오 인터리브(AVI) 클립이 재생되고 있는지 여부를 나타냅니다.

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>Return Value

AVI 클립이 재생되는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [ACM_ISPLAYING](/windows/win32/Controls/acm-isplaying) 메시지를 보냅니다.

## <a name="canimatectrlopen"></a><a name="open"></a>애니메이트Ctrl::열기

이 함수를 호출하여 AVI 클립을 열고 첫 번째 프레임을 표시합니다.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
AVI `CString` 파일의 이름이나 AVI 리소스의 이름을 포함하는 null 종료 된 문자열에 대한 개체 또는 포인터입니다. 이 매개변수가 NULL이면 시스템은 애니메이션 컨트롤에 대해 이전에 열린 AVI 클립을 닫습니다(있는 경우).

*nID*<br/>
AVI 리소스 식별자입니다. 이 매개변수가 NULL이면 시스템은 애니메이션 컨트롤에 대해 이전에 열린 AVI 클립을 닫습니다(있는 경우).

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

AVI 리소스는 애니메이션 컨트롤을 만든 모듈에서 로드됩니다.

`Open`AVI 클립의 사운드는 지원하지 않습니다. 당신은 단지 자동 AVI 클립을 열 수 있습니다.

애니메이션 컨트롤에 스타일이 `ACS_AUTOPLAY` 있는 경우 애니메이션 컨트롤이 열리자마자 자동으로 클립 재생이 시작됩니다. 스레드가 계속 실행되는 동안 백그라운드에서 클립을 계속 재생합니다. 클립 재생이 완료되면 자동으로 반복됩니다.

애니메이션 컨트롤에 스타일이 `ACS_CENTER` 있는 경우 AVI 클립이 컨트롤의 가운데에 배치되고 컨트롤의 크기는 변경되지 않습니다. 애니메이션 컨트롤에 스타일이 `ACS_CENTER` 없는 경우 AVI 클립이 AVI 클립의 이미지 크기로 열리면 컨트롤의 크기가 조정됩니다. 컨트롤의 왼쪽 위 모서리의 위치는 변경되지 않고 컨트롤의 크기만 변경됩니다.

애니메이션 컨트롤에 스타일이 `ACS_TRANSPARENT` 있는 경우 첫 번째 프레임은 애니메이션 클립에 지정된 배경 색이 아닌 투명한 배경을 사용하여 그려집니다.

### <a name="example"></a>예제

  [CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="canimatectrlplay"></a><a name="play"></a>카니메이트트툴::P레이

이 함수를 호출하여 애니메이션 컨트롤에서 AVI 클립을 재생합니다.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>매개 변수

*nFrom*<br/>
재생이 시작되는 프레임의 0기반 인덱스입니다. 값은 65,536보다 낮아야 합니다. 값이 0이면 AVI 클립의 첫 번째 프레임으로 시작됩니다.

*nTo*<br/>
재생이 끝나는 프레임의 0기반 인덱스입니다. 값은 65,536보다 낮아야 합니다. 값 -1은 AVI 클립의 마지막 프레임으로 끝을 의미합니다.

*nRep*<br/>
AVI 클립을 재생할 횟수입니다. 값 -1은 파일을 무기한 재생하는 것을 의미합니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

스레드가 계속 실행되는 동안 애니메이션 컨트롤이 백그라운드에서 클립을 재생합니다. 애니메이션 컨트롤에 `ACS_TRANSPARENT` 스타일이 있는 경우 AVI 클립은 애니메이션 클립에 지정된 배경 색이 아닌 투명한 배경을 사용하여 재생됩니다.

### <a name="example"></a>예제

  [CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl::검색

이 함수를 호출하여 AVI 클립의 단일 프레임을 정적으로 표시합니다.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>매개 변수

*nTo*<br/>
표시할 프레임의 0기반 인덱스입니다. 값은 65,536보다 낮아야 합니다. 값이 0이면 AVI 클립의 첫 번째 프레임을 표시합니다. 값이 -1이면 AVI 클립에 마지막 프레임이 표시됩니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤에 `ACS_TRANSPARENT` 스타일이 있는 경우 AVI 클립은 애니메이션 클립에 지정된 배경 색이 아닌 투명한 배경을 사용하여 그려집니다.

### <a name="example"></a>예제

[CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="canimatectrlstop"></a><a name="stop"></a>애니메이트Ctrl::정지

이 함수를 호출하여 애니메이션 컨트롤에서 AVI 클립 재생을 중지합니다.

```
BOOL Stop();
```

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CAnimateCtrl::CAnimateCtrl에](#canimatectrl)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::만들기](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
