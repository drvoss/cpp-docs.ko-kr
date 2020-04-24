---
title: CMFCDynamicLayout 클래스
ms.date: 08/29/2019
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 77dd3a84a0c76b92495bb062eeb83ff013933087
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752396"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout 클래스

사용자가 창의 크기를 조정할 때 창에서 컨트롤이 이동하고 컨트롤의 크기가 조정되는 방식을 지정합니다.

## <a name="syntax"></a>구문

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` 개체를 생성합니다.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|
|[CMFCDynamicLayout::Adjust](#adjust)|자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.|
|[CMFCDynamicLayout::Create](#create)|호스트 창을 저장하고 유효성을 검사합니다.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|호스트 창에 대한 포인터를 반환합니다.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|레이아웃이 그 이하로 조정되지 않는 창 크기를 반환합니다.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|창의 현재 클라이언트 영역에 대한 사각형을 검색합니다.|
|[CMFCDynamicLayout::HasItem](#hasitem)|자식 컨트롤이 동적 레이아웃에 추가되었는지 확인합니다.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|동적 레이아웃에 추가된 자식 창이 없는지 확인합니다.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|AFX_DIALOG_LAYOUT 리소스에서 동적 레이아웃을 읽고 레이아웃을 호스트 창에 적용합니다.|
|정적 [CMFC 동적 레이아웃::이동수평](#movehorizontal)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 가로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃::이동수평및수직](#movehorizontalandvertical)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 가로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃::이동 없음](#movenone)|자식 컨트롤에 대해 세로 또는 수평의 모션을 나타내지 않는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃::이동수직](#movevertical)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 세로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|레이아웃이 그 이하로 조정되지 않는 창 크기를 설정합니다.|
|정적 [CMFC 동적 레이아웃 ::크기수평](#sizehorizontal)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 가로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃 ::크기수평및수직](#sizehorizontalandvertical)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 가로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃::크기 없음](#sizenone)|자식 컨트롤의 크기 변경을 나타내지 않는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.|
|정적 [CMFC 동적 레이아웃::크기수직](#sizevertical)|사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 세로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.|

## <a name="nested-types"></a>중첩 형식

|속성|Description|
|----------|-----------------|
|[CMFCDynamicLayout::MoveSettings 구조체](#movesettings_structure)|동적 레이아웃의 컨트롤에 대한 이동 데이터를 캡슐화합니다.|
|[CMFCDynamicLayout::SizeSettings 구조체](#sizesettings_structure)|동적 레이아웃의 컨트롤에 대한 크기 변경 데이터를 캡슐화합니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxlayout.h

## <a name="cmfcdynamiclayoutadditem"></a><a name="additem"></a>CMFC 동적 레이아웃::추가 항목

자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
추가할 창에 대한 핸들입니다.

*nID*<br/>
추가할 자식 컨트롤의 ID입니다.

*이동 설정*<br/>
창 크기가 변경될 때 컨트롤을 이동하는 방법을 설명하는 구조체입니다.

*크기설정*<br/>
창 크기가 변경될 때 컨트롤의 크기를 조정하는 방법을 설명하는 구조체입니다.

### <a name="return-value"></a>Return Value

항목이 성공적으로 추가되었으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경됩니다.

## <a name="cmfcdynamiclayoutadjust"></a><a name="adjust"></a>CMFC 동적 레이아웃::조정

자식 창(일반적으로 컨트롤)을 동적 레이아웃 관리자가 제어하는 창 목록에 추가합니다.

```cpp
void Adjust();
```

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경됩니다.

## <a name="cmfcdynamiclayoutcreate"></a><a name="create"></a>CMFC 동적 레이아웃::만들기

호스트 창을 저장하고 유효성을 검사합니다.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>매개 변수

*pHostWnd*<br/>
호스트 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

생성에 성공하면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutgethostwnd"></a><a name="gethostwnd"></a>CMFC 동적 레이아웃::GetHostWnd

호스트 창에 대한 포인터를 반환합니다.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Return Value

호스트 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 모든 자식 컨트롤 위치가 이 창을 기준으로 다시 계산됩니다.

## <a name="cmfcdynamiclayoutgetminsize"></a><a name="getminsize"></a>CMFC 동적 레이아웃 ::GetMinSize

레이아웃이 그 이하로 조정되지 않는 창 크기를 반환합니다.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Return Value

레이아웃이 그 이하로 조정되지 않는 창 크기입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경되지만 레이아웃이 그 이하로 조정되지 않는 최소 크기가 있습니다. 사용자는 창의 크기를 더 작은 크기로 조정할 수 있지만 이렇게 하면 창 부분이 뷰에서 숨겨집니다.

## <a name="cmfcdynamiclayoutgetwindowrect"></a><a name="getwindowrect"></a>CMFC 동적 레이아웃::GetWindowRect

창의 현재 클라이언트 영역에 대한 사각형을 검색합니다.

```cpp
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
함수에서 반환된 이 매개 변수에는 레이아웃 영역의 경계 사각형이 포함됩니다. 이는 출력 매개 변수이며, 입력 값은 덮어써집니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayouthasitem"></a><a name="hasitem"></a>CMFC 동적 레이아웃::하스아이템

자식 컨트롤이 동적 레이아웃에 추가되었는지 확인합니다.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
컨트롤의 창 핸들입니다.

### <a name="return-value"></a>Return Value

레이아웃에 이 항목이 있으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutisempty"></a><a name="isempty"></a>CMFC 동적 레이아웃::비어 있음

동적 레이아웃에 추가된 자식 창이 없는지 확인합니다.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Return Value

레이아웃에 항목이 없으면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutloadresource"></a><a name="loadresource"></a>CMFC 동적 레이아웃::로드 리소스

AFX_DIALOG_LAYOUT 리소스에서 동적 레이아웃을 읽고 레이아웃을 호스트 창에 적용합니다.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>매개 변수

*pHostWnd*<br/>
호스트 창에 대한 포인터입니다.

*lpResource*<br/>
AFX_DIALOG_LAYOUT 리소스를 포함하는 버퍼에 대한 포인터입니다.

*dwSize*<br/>
버퍼 크기(바이트)입니다.

### <a name="return-value"></a>Return Value

리소스가 로드되어 호스트 창에 적용되면 TRUE이고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutmovehorizontal"></a><a name="movehorizontal"></a>CMFC 동적 레이아웃::이동수평

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 가로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청된 이동 비율을 캡슐화하는 [MoveSettings](#movesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutmovehorizontalandvertical"></a><a name="movehorizontalandvertical"></a>CMFC 동적 레이아웃::이동수평및수직

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 가로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>매개 변수

*nXRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 가로로 얼마나 이동하는지를 백분율로 정의합니다.

*nYRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청된 이동 비율을 캡슐화하는 [MoveSettings](#movesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutmovenone"></a><a name="movenone"></a>CMFC 동적 레이아웃::이동없음

자식 컨트롤에 대해 세로 또는 수평의 모션을 나타내지 않는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Return Value

사용자가 호스트 창의 크기를 조정할 때 이동하지 않도록 컨트롤을 제자리에 고정하는 [MoveSettings](#movesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutmovesettings-structure"></a><a name="movesettings_structure"></a>CMFC 동적 레이아웃::이동 설정 구조

동적 레이아웃의 컨트롤에 대한 이동 데이터를 캡슐화합니다.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>설명

이는 `CMFCDynamicLayout` 내부에 중첩된 클래스입니다.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFC 동적 레이아웃::이동 설정::Is수평

이동 데이터가 0이 아닌 가로 이동을 지정하는지 확인합니다.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Return Value

`MoveSettings` 개체가 0이 아닌 가로 이동을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFC 동적 레이아웃::이동 설정::없음

데이터 이동에서 이동을 지정하지 않는지 확인합니다.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Return Value

`MoveSettings` 개체가 이동을 지정하지 않는 경우 TRUE입니다.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFC 동적 레이아웃::이동 설정::IsVertical

이동 데이터가 0이 아닌 세로 이동을 지정하는지 확인합니다.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Return Value

`MoveSettings` 개체가 0이 아닌 세로 이동을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutmovevertical"></a><a name="movevertical"></a>CMFC 동적 레이아웃::이동수직

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤이 세로로 이동하는 양을 정의하는 [MoveSettings](#movesettings_structure) 값을 가져옵니다.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창의 크기를 조정할 때 자식 컨트롤이 세로로 얼마나 이동하는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청된 이동 비율을 캡슐화하는 [MoveSettings](#movesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutsetminsize"></a><a name="setminsize"></a>CMFC 동적 레이아웃::SetMinSize

레이아웃이 그 이하로 조정되지 않는 창 크기를 설정합니다.

```cpp
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
레이아웃이 그 이하로 조정되지 않는 원하는 크기입니다.

### <a name="remarks"></a>설명

호스팅 창의 크기를 조정하면 자식 컨트롤의 위치 및 크기가 동적으로 변경되지만 레이아웃이 그 이하로 조정되지 않는 최소 크기가 있습니다. 사용자는 창의 크기를 더 작은 크기로 조정할 수 있지만 이렇게 하면 창 부분이 뷰에서 숨겨집니다.

## <a name="cmfcdynamiclayoutsizehorizontal"></a><a name="sizehorizontal"></a>CMFC 동적 레이아웃 ::크기수평

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 가로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 가로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청한 크기 비율을 캡슐화하는 [SizeSettings](#sizesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutsizehorizontalandvertical"></a><a name="sizehorizontalandvertical"></a>CMFC 동적 레이아웃 ::크기수평및수직

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 가로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>매개 변수

*nXRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 가로로 얼마나 조정되는지를 백분율로 정의합니다.

*nYRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 세로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청한 크기 비율을 캡슐화하는 [SizeSettings](#sizesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutsizenone"></a><a name="sizenone"></a>CMFC 동적 레이아웃::크기 없음

자식 컨트롤의 크기 변경을 나타내지 않는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Return Value

사용자가 호스트 창의 크기를 조정할 때 크기가 변경되지 않도록 특정 크기로 컨트롤을 수정하는 [SizeSettings](#sizesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcdynamiclayoutsizesettings-structure"></a><a name="sizesettings_structure"></a>CMFC 동적 레이아웃::크기 설정 구조

동적 레이아웃의 컨트롤에 대한 크기 변경 데이터를 캡슐화합니다.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>설명

이는 `CMFCDynamicLayout` 내부에 중첩된 클래스입니다.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFC 동적 레이아웃 ::크기 설정 ::Is수평

크기 조정 데이터가 0이 아닌 가로 크기 조정을 지정하는지 확인합니다.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Return Value

`SizeSettings` 개체가 0이 아닌 가로 크기 조정을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFC 동적 레이아웃::크기 설정::IsNone

크기 조정 데이터가 크기 조정을 지정하지 않는지 여부를 확인합니다.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Return Value

`SizeSettings` 개체가 크기 조정을 지정하지 않는 경우 TRUE입니다.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFC 동적 레이아웃::크기 설정::IsVertical

크기 조정 데이터가 0이 아닌 세로 크기 조정을 지정하는지 확인합니다.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Return Value

`SizeSettings` 개체가 0이 아닌 세로 크기 조정을 지정하면 TRUE입니다.

## <a name="cmfcdynamiclayoutsizevertical"></a><a name="sizevertical"></a>CMFC 동적 레이아웃 ::크기수직

사용자가 호스팅 창크기를 조정할 때 자식 컨트롤의 크기를 세로로 조정하는 양을 정의하는 [SizeSettings](#sizesettings_structure) 값을 가져옵니다.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>매개 변수

*nRatio*<br/>
사용자가 호스트 창 크기를 조정할 때 자식 컨트롤의 크기가 세로로 얼마나 조정되는지를 백분율로 정의합니다.

### <a name="return-value"></a>Return Value

요청한 크기 비율을 캡슐화하는 [SizeSettings](#sizesettings_structure) 값입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
