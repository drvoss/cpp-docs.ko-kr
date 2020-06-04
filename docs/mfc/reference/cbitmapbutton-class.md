---
title: CBitmapButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: df21591dec1da5861125d7e9480fb9345aaad061
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752954"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton 클래스

텍스트가 아닌 비트맵 이미지로 레이블이 표시된 누름 단추 컨트롤을 만듭니다.

## <a name="syntax"></a>구문

```
class CBitmapButton : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CBitmap 버튼::CBitmap 버튼](#cbitmapbutton)|`CBitmapButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBitmap 단추::자동 로드](#autoload)|대화 상자의 단추를 `CBitmapButton` 클래스의 개체와 연결하고, 비트맵을 이름으로 로드하고, 단추의 크기를 조정하여 비트맵에 맞게 조정합니다.|
|[CBitmap 버튼::로드비트맵](#loadbitmaps)|응용 프로그램의 리소스 파일에서 하나 이상의 명명된 비트맵 리소스를 로드하고 개체에 비트맵을 연결하여 개체를 초기화합니다.|
|[CBitmap 버튼::크기토콘텐츠](#sizetocontent)|비트맵을 수용할 수 있도록 단추의 크기를 조정합니다.|

## <a name="remarks"></a>설명

`CBitmapButton`개체에는 최대 4개의 비트맵이 포함되어 있으며, 여기에는 버튼이 가정할 수 있는 다른 상태에 대한 이미지가 포함됩니다: 위(또는 보통), 아래(또는 선택), 포커스 및 비활성화됨. 첫 번째 비트맵만 필요합니다. 다른 것들은 선택 사항입니다.

비트맵 단추 이미지에는 이미지 주변의 테두리와 이미지 자체가 포함됩니다. 테두리는 일반적으로 단추의 상태를 표시하는 역할을 합니다. 예를 들어 포커스가 있는 상태에 대한 비트맵은 일반적으로 위업 상태의 비트맵과 같지만 테두리에서 파선사각형이 인세트되거나 테두리에 두꺼운 실선이 있습니다. 비활성화된 상태의 비트맵은 일반적으로 위쪽 상태의 비트맵과 유사하지만 대비가 낮습니다(예: 흐리게 표시되거나 회색 메뉴 선택).

이러한 비트맵은 모든 크기일 수 있지만 모두 업 상태의 비트맵과 크기가 같은 것처럼 처리됩니다.

다양한 응용 프로그램에는 비트맵 이미지의 다양한 조합이 요구됩니다.

|위로|아래로|포커스 있음|사용 안 함|애플리케이션|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||WS_TABSTOP 스타일이없는 버튼|
|×|×|×|×|모든 상태의 대화 버튼|
|×|×|×||WS_TABSTOP 스타일의 대화 버튼|

비트맵 단추 컨트롤을 만들 때 BS_OWNERDRAW 스타일을 설정하여 단추를 소유자가 그리도록 지정합니다. 이렇게 하면 Windows단추에 대 WM_MEASUREITEM 및 WM_DRAWITEM 메시지를 보냅니다. 프레임워크는 이러한 메시지를 처리하고 단추의 모양을 관리합니다.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>창의 클라이언트 영역에서 비트맵 단추 컨트롤을 만들려면

1. 단추에 대해 1~4개의 비트맵 이미지를 만듭니다.

1. [CBitmapButton](#cbitmapbutton) 개체를 구성합니다.

1. [만들기](../../mfc/reference/cbutton-class.md#create) 함수를 호출하여 Windows 단추 컨트롤을 `CBitmapButton` 만들고 개체에 연결합니다.

1. Bitmap 단추를 생성 한 후 비트 맵 리소스를 로드 하려면 [LoadBitmaps](#loadbitmaps) 멤버 함수를 호출 합니다.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>대화 상자에 비트맵 단추 컨트롤을 포함하려면

1. 단추에 대해 1~4개의 비트맵 이미지를 만듭니다.

1. 비트맵 단추를 원하는 위치에 소유자-그리기 버튼이 배치된 대화 상자 템플릿을 만듭니다. 템플릿의 단추 크기는 중요하지 않습니다.

1. 단추의 캡션을 "MYIMAGE"와 같은 값으로 설정하고 IDC_MYIMAGE 같은 단추에 대한 기호를 정의합니다.

1. 응용 프로그램의 리소스 스크립트에서 단추에 대해 생성된 각 이미지에 3단계의 단추 캡션에 사용되는 문자열에 "U", "D", "F" 또는 "X"(위, 아래, 포커스 및 사용 안 함)를 추가하여 생성된 ID를 지정합니다. 예를 들어 단추 캡션 "MYIMAGE"의 경우 ID는 "MYIMAGEU", "MYIMAGED", "MYIMAGEF", "MYIMAGEX"입니다. 큰따옴표 내에서 비트맵의 ID를 **지정해야 합니다.** 그렇지 않으면 리소스 편집기는 리소스에 정수를 할당하고 이미지를 로드할 때 MFC가 실패합니다.

1. 응용 프로그램의 대화 상자 클래스(파생)에서 `CDialog`멤버 `CBitmapButton` 개체를 추가합니다.

1. `CDialog` 개체의 [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) 루틴에서 단추의 `CBitmapButton` 컨트롤 ID와 개체의 **이** 포인터를 매개 변수로 `CDialog` 사용하여 개체의 자동 [로드](#autoload) 함수를 호출합니다.

비트맵 단추 컨트롤에서 부모(일반적으로 파생된 `CDialog`클래스)로 전송된 BN_CLICKED 같은 Windows 알림 메시지를 처리하려면 `CDialog`-derive개체에 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가합니다. 개체에서 `CBitmapButton` 보낸 알림은 [CButton](../../mfc/reference/cbutton-class.md) 개체에서 보낸 알림과 동일합니다.

클래스 [CToolBar](../../mfc/reference/ctoolbar-class.md) 비트 맵 단추에 다른 접근 방식을 걸립니다.

에 대한 `CBitmapButton`자세한 내용은 [컨트롤](../../mfc/controls-mfc.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a>CBitmap 단추::자동 로드

대화 상자의 단추를 `CBitmapButton` 클래스의 개체와 연결하고, 비트맵을 이름으로 로드하고, 단추의 크기를 조정하여 비트맵에 맞게 조정합니다.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
단추의 제어 ID입니다.

*pParent*<br/>
단추를 소유 하는 개체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 `AutoLoad` 함수를 사용하여 대화 상자에서 소유자-그리기 단추를 비트맵 단추로 초기화합니다. 이 함수를 사용하는 방법에 대한 `CBitmapButton` 지침은 클래스의 설명에 나와 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>CBitmap 버튼::CBitmap 버튼

`CBitmapButton` 개체를 만듭니다.

```
CBitmapButton();
```

### <a name="remarks"></a>설명

C++ `CBitmapButton` 개체를 만든 후 [CButton::Create를](../../mfc/reference/cbutton-class.md#create) 호출하여 Windows 단추 `CBitmapButton` 컨트롤을 만들고 개체에 연결합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>CBitmap 버튼::로드비트맵

리소스 이름 이나 ID 번호로 식별 된 비트 맵 이미지를 로드 하려는 경우 `AutoLoad` 또는 예를 들어 대화 상자의 일부가 아닌 비트 맵 단추를 만들 수 있기 때문에 함수를 사용할 수 없는 경우이 기능을 사용 합니다.

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>매개 변수

*lpsz비트맵리소스*<br/>
비트맵 단추의 정상 또는 "위"상태에 대한 비트맵 이름을 포함하는 null 종료된 문자열을 가리킵니다. 필수 사항입니다.

*lpsz비트맵리소스셀*<br/>
비트맵 단추의 선택 또는 "다운" 상태에 대한 비트맵 이름이 포함된 null 종료 된 문자열을 가리킵니다. NULL일 수 있습니다.

*lpsz비트맵리소스포커스*<br/>
비트맵 단추의 포커스가 있는 상태에 대한 비트맵 이름을 포함하는 null 종료된 문자열을 가리킵니다. NULL일 수 있습니다.

*lpsz비트맵사용안드하이드*<br/>
비트맵 단추의 비활성화된 상태에 대한 비트맵 이름을 포함하는 null 종료된 문자열을 가리킵니다. NULL일 수 있습니다.

*니드비트맵리소스*<br/>
비트맵 단추의 정상 또는 "최대" 상태에 대한 비트맵 리소스 리소스 ID 번호를 지정합니다. 필수 사항입니다.

*니드비트맵리소스셀*<br/>
비트맵 단추의 선택 또는 "다운" 상태에 대한 비트맵 리소스 리소스 번호를 지정합니다. 0일 수 있습니다.

*니드비트맵리소스포커스*<br/>
비트맵 단추의 포커스가 있는 상태에 대한 비트맵 리소스 리소스 ID 번호를 지정합니다. 0일 수 있습니다.

*니드비트맵사용성*<br/>
비트맵 단추의 비활성화된 상태에 대한 비트맵 리소스 리소스 ID 번호를 지정합니다. 0일 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>CBitmap 버튼::크기토콘텐츠

이 함수를 호출하여 비트맵 단추의 크기를 비트맵 크기로 조정합니다.

```cpp
void SizeToContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
