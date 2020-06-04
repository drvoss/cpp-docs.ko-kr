---
title: C툴팁매니저 클래스
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 4e721740fc100a34ea08dd7ff5f9291eea2d9b36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752175"
---
# <a name="ctooltipmanager-class"></a>C툴팁매니저 클래스

도구 설명에 대한 런타임 정보를 유지합니다. `CTooltipManager` 클래스는 애플리케이션당 한 번씩 인스턴스화됩니다.

## <a name="syntax"></a>구문

```
class CTooltipManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤을 만듭니다.|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|도구 설명 컨트롤을 삭제합니다.|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤의 시각적 모양을 사용자 지정합니다.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|도구 설명 컨트롤에 대한 텍스트 및 설명을 설정합니다.|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>설명

[CMFCToolTipCtrl 클래스를](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo`사용하고 `CTooltipManager` 함께 응용 프로그램에서 사용자 지정된 도구 설명서를 구현합니다. 이러한 도구 설명 클래스를 사용하는 방법에 대한 예제는 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipmanager.h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::만들기도구 팁

도구 설명 컨트롤을 만듭니다.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>매개 변수

*pTool팁*<br/>
【아웃】 도구 설명 포인터에 대한 참조입니다. 함수가 반환될 때 새로 작성된 도구 설명을 가리키도록 설정됩니다.

*pWndParent*<br/>
【인】 도구 설명의 상위 입니다.

*nType*<br/>
【인】 도구 설명의 유형입니다.

### <a name="return-value"></a>Return Value

도구 설명이 성공적으로 생성된 경우 0이 아닙니다.

### <a name="remarks"></a>설명

*pToolTip에서*다시 전달되는 도구 설명 컨트롤을 삭제하려면 [CTooltipManager::DeleteToolTip을](#deletetooltip) 호출해야 합니다.

[CTooltipManager는](../../mfc/reference/ctooltipmanager-class.md) *nType이* 지정하는 툴팁 유형을 기반으로 생성하는 각 도구 설명의 시각적 표시 매개변수를 설정합니다. 하나 이상의 도구 설명 형식에 대한 매개 변수를 변경하려면 [CTooltipManager::SetTooltipParams](#settooltipparams)를 호출합니다.

유효한 도구 설명 유형은 다음 표에 나열됩니다.

|공구 팁 유형|제어 범주|예제 유형|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|버튼입니다.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|캡션 막대입니다.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|다른 범주에 맞지 않는 모든 컨트롤입니다.|없음|
|AFX_TOOLTIP_TYPE_DOCKBAR|도킹 가능한 창입니다.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|텍스트 상자입니다.|없음|
|AFX_TOOLTIP_TYPE_MINIFRAME|미니프레임.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|플래너.|없음|
|AFX_TOOLTIP_TYPE_RIBBON|리본 바입니다.|CMFC리본바, CMFC리본패널메뉴바|
|AFX_TOOLTIP_TYPE_TAB|탭 컨트롤입니다.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|도구 모음입니다.|CMFC툴바, CMFC팝메뉴바|
|AFX_TOOLTIP_TYPE_TOOLBOX|도구 상자입니다.|없음|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>C툴팁매니저::DeleteToolTip

도구 설명 컨트롤을 삭제합니다.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>매개 변수

*pTool팁*<br/>
【인, 아웃】 삭제할 도구 설명에 대한 포인터에 대한 참조입니다.

### <a name="remarks"></a>설명

[CTooltipManager::CreateToolTool팁에](#createtooltip)의해 만들어진 각 [CToolTipCtrl 클래스에](../../mfc/reference/ctooltipctrl-class.md) 대해 이 메서드를 호출합니다. 부모 컨트롤은 처리기에서 `OnDestroy` 이 메서드를 호출해야 합니다. 프레임워크에서 도구 설명을 올바르게 제거하려면 이 방법을 선택해야 합니다. 이 메서드는 반환 하기 전에 *pToolTip을* NULL로 설정 합니다.

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::setTooltipParams

지정된 Windows 컨트롤 유형에 대한 도구 설명 컨트롤의 모양을 사용자 지정합니다.

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>매개 변수

*n유형*<br/>
【인】 컨트롤 유형을 지정합니다.

*pRTC*<br/>
【인】 사용자 지정 도구 설명의 런타임 클래스입니다.

*pParams*<br/>
【인】 도구 설명 매개 변수입니다.

### <a name="remarks"></a>설명

이 메서드는 도구 설명끝을 만들 때 [CToolTipManager에서](../../mfc/reference/ctooltipmanager-class.md) 사용하는 런타임 클래스 및 초기 매개 변수를 설정합니다. 컨트롤이 [CTooltipManager::CreateToolTip을](#createtooltip) 호출하고 *nType으로*표시된 형식 중 하나인 도구 설명 형식을 전달하는 경우 도구 설명 관리자는 *pRTC에서* 지정한 런타임 클래스의 인스턴스인 도구 설명 컨트롤을 만들고 *pParams에* 의해 지정된 매개 변수를 새 도구 설명에 전달합니다.

이 메서드를 호출하면 모든 기존 도구 설명 소유자가 AFX_WM_UPDATETOOLTIPS 메시지를 수신하고 [CTooltipManager::CreateToolTip](#createtooltip)를 사용하여 도구 설명서를 다시 만들어야 합니다.

*n유형은* [CTooltipManager::CreateToolTip에서](#createtooltip) 사용하는 유효한 도구 설명 형식의 조합이거나 AFX_TOOLTIP_TYPE_ALL 수 있습니다. AFX_TOOLTIP_TYPE_ALL 통과하면 모든 도구 설명 유형이 영향을 받습니다.

### <a name="example"></a>예제

다음 예제에서는 `SetTooltipParams` `CTooltipManager` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText

도구 설명에 대한 텍스트와 설명을 설정합니다.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>매개 변수

*Pti*<br/>
【인】 TOOLINFO 개체에 대한 포인터입니다.

*pTool팁*<br/>
【인, 아웃】 텍스트와 설명을 설정할 도구 설명 컨트롤에 대한 포인터입니다.

*nType*<br/>
【인】 이 도구 설명이 연결된 컨트롤 유형을 지정합니다.

*strText*<br/>
【인】 도구 설명 텍스트로 설정할 텍스트입니다.

*lpszDescr*<br/>
【인】 도구 설명 설명에 대한 포인터입니다. NULL일 수 있습니다.

### <a name="remarks"></a>설명

*nType* 값은 도구 설명팁을 만들 때 [CTooltipManager::CreateToolTip의](#createtooltip) *nType* 매개 변수와 동일한 값이어야 합니다.

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::업데이트도구 팁

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴팁Ctrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFC툴팁정보 클래스](../../mfc/reference/cmfctooltipinfo-class.md)
