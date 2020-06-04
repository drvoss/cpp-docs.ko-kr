---
title: CMFC키맵디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 22aa006ce214ca720192bb761e2ff2b35a64fce3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374409"
---
# <a name="cmfckeymapdialog-class"></a>CMFC키맵디아로그 클래스

클래스는 `CMFCKeyMapDialog` 키보드의 키에 명령을 매핑하는 컨트롤을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC키맵디아로그::CMFC키맵디아로그](#cmfckeymapdialog)|`CMFCKeyMapDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC키맵디아로그::DoModal](#domodal)|키보드 매핑 대화 상자를 표시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC키맵 디아로그::형식항목](#formatitem)|키 매핑을 설명하는 문자열을 빌드하기 위해 프레임워크에서 호출합니다. 기본적으로 문자열에는 명령 이름, 사용된 바로 가기 키 및 바로 가기 키 설명이 포함됩니다.|
|[CMFC키맵디아로그::GetCommand키](#getcommandkeys)|지정된 명령과 연결된 바로 가기 키 목록이 포함된 문자열을 검색합니다.|
|[CMFC키맵 디아로그::온인서인스아이템](#oninsertitem)|새 항목이 키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤에 삽입되기 전에 프레임워크에서 호출됩니다.|
|[CMFC키맵디아로그::온프린트헤더](#onprintheader)|새 페이지에서 키보드 맵의 헤더를 인쇄하려면 프레임워크에서 호출합니다.|
|[CMFC키맵 디아로그::온프린트항목](#onprintitem)|키보드 매핑 항목을 인쇄하는 프레임워크에서 호출합니다.|
|[CMFC키맵 디아로그::온셋열](#onsetcolumns)|키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤의 열에 대한 캡션을 설정하기 위해 프레임워크에서 호출합니다.|
|[CMFC키맵디아로그::P린트키맵](#printkeymap)|사용자가 **인쇄** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CMFC키맵 디아로그::세트열너비](#setcolumnswidth)|키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤에서 열의 너비를 설정하기 위해 프레임워크에서 호출합니다.|

## <a name="remarks"></a>설명

클래스를 `CMFCKeyMapDialog` 사용하여 식용 키보드 매핑 대화 상자를 구현합니다. 대화 상자는 목록 보기 컨트롤을 사용하여 키보드 단축키와 관련 명령을 표시합니다.

응용 프로그램에서 `CMFCKeyMapDialog` 클래스를 사용하려면 포인터를 주 프레임 창에 생성자의 `CMFCKeyMapDialog` 매개 변수로 전달합니다. 그런 다음 `DoModal` 메서드를 호출하여 모달 대화 상자를 시작합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxkeymapdialog.h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a>CMFC키맵디아로그::CMFC키맵디아로그

`CMFCKeyMapDialog` 개체를 생성합니다.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>매개 변수

*pWnd부모프레임*<br/>
【인】 개체의 상위 창에 `CMFCKeyMapDialog` 대한 포인터입니다.

*b인가능하게 인쇄*<br/>
【인】 TRUE 가속기 키 목록을 인쇄할 수 있는 경우; 그렇지 않으면 false입니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 `CMFCKeyMapDialog` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 예제는 [Visual Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a>CMFC키맵디아로그::DoModal

키보드 매핑 대화 상자를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL과 같은 서명된 정수는 [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) 메서드에 전달됩니다. 메서드는 차례로 대화 상자를 닫습니다. 자세한 내용은 [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal)을 참조하십시오.

### <a name="remarks"></a>설명

키보드 매핑 대화 상자를 사용하면 다양한 명령 범주에 가속기 키를 선택하고 할당할 수 있습니다. 또한 선택한 가속기 키와 설명을 클립보드에 복사할 수 있습니다.

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a>CMFC키맵 디아로그::형식항목

키 매핑을 설명하는 문자열을 빌드하기 위해 프레임워크에서 호출합니다. 기본적으로 문자열에는 명령 이름, 사용된 바로 가기 키 및 바로 가기 키 설명이 포함됩니다.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
【인】 키 매핑의 내부 목록에서 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

서식이 지정된 항목 텍스트가 포함된 `CString` 개체입니다.

### <a name="remarks"></a>설명

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a>CMFC키맵디아로그::GetCommand키

문자열 값을 검색합니다. 문자열에는 지정된 명령과 연결된 바로 가기 키 목록이 포함되어 있습니다.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
【인】 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령과 연결된 바로 가기 키의 세미콜론 구분(';') 목록입니다.

### <a name="remarks"></a>설명

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a>CMFC키맵 디아로그::온인서인스아이템

새 항목이 키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤에 삽입되기 전에 프레임워크에서 호출됩니다.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>매개 변수

*p 버튼*<br/>
【인】 명령 이름 및 설명에 키보드 키 조합을 매핑하는 데 사용되는 도구 모음 단추에 대한 포인터입니다. 키 맵 항목은 내부 목록 컨트롤에 저장됩니다.

*nItem*<br/>
【인】 내부 목록 컨트롤에 새 키 맵 항목을 삽입할 위치를 지정하는 0기반 인덱스입니다.

### <a name="remarks"></a>설명

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a>CMFC키맵디아로그::온프린트헤더

새 페이지에서 키보드 맵의 헤더를 인쇄하려면 프레임워크에서 호출합니다.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
【인】 프린터의 장치 컨텍스트입니다.

*n페이지*<br/>
【인】 인쇄할 페이지 번호입니다.

*Cx*<br/>
【인】 헤더의 가로 오프셋(픽셀 단위)입니다.

### <a name="return-value"></a>Return Value

성공하면 인쇄된 텍스트의 높이입니다. 자세한 내용은 [CDC::DrawText의](../../mfc/reference/cdc-class.md#drawtext)반환 값 섹션을 참조하십시오.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 사용하여 키보드 맵을 인쇄합니다. 기본적으로 이 메서드는 페이지 번호, 응용 프로그램 이름 및 대화 상자 제목을 인쇄합니다.

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a>CMFC키맵 디아로그::온프린트항목

키보드 매핑 항목을 인쇄하는 프레임워크에서 호출합니다.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
【인】 프린터의 장치 컨텍스트입니다.

*nItem*<br/>
【인】 인쇄할 항목의 0기반 인덱스입니다.

*Y*<br/>
【인】 페이지 상단과 항목의 위치 사이의 세로 간격띄우기입니다.

*Cx*<br/>
【인】 페이지 왼쪽과 항목의 위치 사이의 가로 간격띄우기입니다.

*bCalc높이 높이*<br/>
【인】 TRUE인쇄 항목에 대한 최적의 높이를 계산합니다. 기본 공간에 맞도록 인쇄 항목을 잘립니다.

### <a name="return-value"></a>Return Value

인쇄된 항목의 높이입니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 키 맵 대화 상자 항목을 인쇄합니다. 기본적으로 이 메서드는 항목의 명령 이름, 바로 가기 키 및 명령 설명을 인쇄합니다.

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a>CMFC키맵 디아로그::온셋열

키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤의 열에 대한 캡션을 설정하기 위해 프레임워크에서 호출합니다.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 세 개의 리소스에서 열에 대 한 캡션을 가져옵니다. 명령 열 캡션은 IDS_AFXBARRES_COMMAND, 키 열 캡션은 IDS_AFXBARRES_KEYS, 설명 열 캡션은 IDS_AFXBARRES_DESCRIPTION.

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a>CMFC키맵디아로그::P린트키맵

사용자가 **인쇄** 단추를 클릭할 때 프레임워크에서 호출됩니다.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>설명

메서드는 `PrintKeyMap` 키 맵을 인쇄합니다. 새 인쇄 작업을 시작한 다음 모든 키 매핑이 인쇄될 때까지 [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) 및 [CMFCKeyMapDialog::OnPrintItem](#onprintitem) 메서드를 반복적으로 호출합니다.

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a>CMFC키맵 디아로그::세트열너비

키보드 매핑 컨트롤을 지원하는 내부 목록 컨트롤에서 열의 너비를 설정하기 위해 프레임워크에서 호출합니다.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>설명

이 메서드는 내부 목록 컨트롤의 열을 기본 너비로 설정합니다. 먼저 바로 가기 키 열의 너비가 계산됩니다. 그런 다음 나머지 너비의 3분의 1이 명령 열에 할당되고 나머지 3분의 2가 설명 열에 할당됩니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[C키보드관리자 클래스](../../mfc/reference/ckeyboardmanager-class.md)
