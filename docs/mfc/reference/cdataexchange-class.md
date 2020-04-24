---
title: CDataExchange 클래스
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: fd1bce7de7ac323dc3099ab4938306768eb95a35
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754627"
---
# <a name="cdataexchange-class"></a>CDataExchange 클래스

Microsoft Foundation 클래스에서 사용되는 DDX(대화 상자 데이터 교환) 및 DDV(대화 상자 데이터 유효성 검사) 루틴을 지원합니다.

## <a name="syntax"></a>구문

```
class CDataExchange
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C데이터 교환::CDataExchange](#cdataexchange)|`CDataExchange` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C데이터 교환::실패](#fail)|유효성 검사가 실패할 때 호출됩니다. 포커스를 이전 컨트롤에 다시 설정하고 예외를 throw합니다.|
|[C데이터익스체인지::P레파레Ctrl](#preparectrl)|데이터 교환 또는 유효성 검사에 대해 지정된 컨트롤을 준비합니다. 비편집 컨트롤에 사용합니다.|
|[CDataExchange::P레파레에이트트Ctrl](#prepareeditctrl)|데이터 교환 또는 유효성 검사를 위해 지정된 편집 컨트롤을 준비합니다.|
|[CDataExchange::P레파레올레Ctrl](#prepareolectrl)|데이터 교환 또는 유효성 검사를 위해 지정된 OLE 컨트롤을 준비합니다. 비편집 컨트롤에 사용합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX 및 DDV 방향에 플래그를 표시합니다.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|데이터 교환이 이루어지는 대화 상자 또는 창입니다.|

## <a name="remarks"></a>설명

`CDataExchange`기본 클래스가 없습니다.

사용자 지정 데이터 형식 또는 컨트롤에 대한 데이터 교환 루틴을 작성하거나 사용자 고유의 데이터 유효성 검사 루틴을 작성하는 경우 이 클래스를 사용합니다. 사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 대화 [상자를](../../mfc/dialog-boxes.md)참조하십시오.

개체는 `CDataExchange` DDX 및 DDV가 수행되는 데 필요한 컨텍스트 정보를 제공합니다. DDX가 데이터 멤버의 대화 상자 컨트롤의 초기 값을 채우는 데 사용되는 경우 *m_bSaveAndValidate* 플래그는 FALSE입니다. m_bSaveAndValidate *플래그는* 대화 상자 컨트롤의 현재 값을 데이터 멤버로 설정하는 데 사용되고 DDV를 사용하여 데이터 값의 유효성을 검사하는 경우 TRUE입니다. DDV 유효성 검사가 실패하면 DDV 프로시저에 입력 오류를 설명하는 메시지 상자가 표시됩니다. 그런 다음 DDV `Fail` 프로시저가 호출되어 잘못된 컨트롤에 포커스를 재설정하고 예외를 throw하여 유효성 검사 프로세스를 중지합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDataExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a>C데이터 교환::CDataExchange

이 멤버 함수를 `CDataExchange` 호출하여 개체를 생성합니다.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>매개 변수

*pDlgWnd*<br/>
컨트롤을 포함 하는 부모 창에 대 한 포인터입니다. 일반적으로 이것은 [CDialog](../../mfc/reference/cdialog-class.md)-파생 개체입니다.

*bSaveAndValidate*<br/>
TRUE이면 이 개체는 데이터의 유효성을 검사한 다음 컨트롤의 데이터를 멤버에 씁니다. FALSE인 경우 이 개체는 데이터를 멤버에서 컨트롤로 이동합니다.

### <a name="remarks"></a>설명

창의 `CDataExchange` [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수에 전달할 데이터 교환 개체에 추가 정보를 저장하려면 개체를 직접 구성합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a>C데이터 교환::실패

대화 상자 데이터 유효성 검사(DDV) 작업이 실패할 때 프레임워크는 이 멤버 함수를 호출합니다.

```cpp
void Fail();
```

### <a name="remarks"></a>설명

`Fail`(복원할 컨트롤이 있는 경우) 유효성 검사가 실패한 컨트롤에 포커스 와 선택을 복원합니다. `Fail`그런 다음 유효성 검사 프로세스를 중지하려면 [CUserException](../../mfc/reference/cuserexception-class.md) 형식의 예외를 throw합니다. 예외로 인해 오류를 설명하는 메시지 상자가 표시됩니다. DDV 유효성 검사가 실패하면 사용자는 잘못된 컨트롤에 데이터를 다시 입력할 수 있습니다.

사용자 지정 DDV 루틴의 구현자는 유효성 검사가 실패할 때 해당 루틴에서 호출할 `Fail` 수 있습니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate

이 플래그는 대화 상자 데이터 교환(DDX) 작업의 방향을 나타냅니다.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>설명

개체가 사용자가 컨트롤을 `CDataExchange` 편집한 후 대화 상자 컨트롤에서 대화 클래스 데이터 멤버로 데이터를 이동하는 데 사용되는 경우 플래그는 0이 아닙니다. 개체가 대화 클래스 데이터 멤버에서 대화 상자 컨트롤을 초기화하는 데 사용되는 경우 플래그는 0입니다.

대화 상자 데이터 유효성 검사(DDV) 중에도 플래그가 0이 아닙니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd

대화 상자 데이터 교환(DDX) 또는 유효성 검사(DDV)가 이루어지는 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터가 포함되어 있습니다.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>설명

이 개체는 일반적으로 [CDialog](../../mfc/reference/cdialog-class.md) 개체입니다. 사용자 지정 DDX 또는 DDV 루틴의 구현자는 이 포인터를 사용하여 작동 중인 컨트롤이 포함된 대화 상자 창에 대한 액세스를 얻을 수 있습니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a>C데이터익스체인지::P레파레Ctrl

프레임워크는 이 멤버 함수를 호출하여 DDX(대화 상자) 및 유효성 검사(DDV)에 대해 지정된 컨트롤을 준비합니다.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX 또는 DDV에 대해 제조될 컨트롤의 ID입니다.

### <a name="return-value"></a>Return Value

DDX 또는 DDV에 대해 준비중인 컨트롤의 HWND.

### <a name="remarks"></a>설명

편집 컨트롤대신 [준비편집Ctrl을](#prepareeditctrl) 사용합니다. 이 멤버 함수를 다른 모든 컨트롤에 사용합니다.

준비는 클래스에 컨트롤의 HWND를 `CDataExchange` 저장하는 것으로 구성됩니다. 프레임워크는 이 핸들을 사용하여 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 조정된 컨트롤에 포커스를 복원합니다.

사용자 지정 DDX 또는 DDV 루틴의 `PrepareCtrl` 구현자는 DDX를 통해 데이터를 교환하거나 DDV를 통해 데이터를 검증하는 모든 비편집 컨트롤을 호출해야 합니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a>CDataExchange::P레파레에이트트Ctrl

프레임워크는 이 멤버 함수를 호출하여 대화 상자 데이터 교환(DDX) 및 유효성 검사(DDV)에 대해 지정된 편집 컨트롤을 준비합니다.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX 또는 DDV에 대해 준비될 편집 컨트롤의 ID입니다.

### <a name="return-value"></a>Return Value

DDX 또는 DDV에 대해 준비중인 편집 컨트롤의 HWND입니다.

### <a name="remarks"></a>설명

편집하지 않은 모든 컨트롤에 대신 [PrepareCtrl을](#preparectrl) 사용합니다.

준비는 두 가지로 구성됩니다. 먼저 `PrepareEditCtrl` 컨트롤의 HWND를 클래스에 `CDataExchange` 저장합니다. 프레임워크는 이 핸들을 사용하여 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 조정된 컨트롤에 포커스를 복원합니다. 둘째, `PrepareEditCtrl` `CDataExchange` 클래스에 플래그를 설정하여 데이터를 교환하거나 유효성을 검사하는 컨트롤이 편집 컨트롤임을 나타냅니다.

사용자 지정 DDX 또는 DDV 루틴의 `PrepareEditCtrl` 구현자는 DDX를 통해 데이터를 교환하거나 DDV를 통해 데이터를 검증하는 모든 편집 컨트롤을 호출해야 합니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a>CDataExchange::P레파레올레Ctrl

프레임워크는 이 멤버 함수를 호출하여 대화 상자 데이터 교환(DDX) 및 유효성 검사(DDV)에 대해 지정된 OLE 컨트롤을 준비합니다.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>매개 변수

*nIDC*<br/>
DDX 또는 DDV에 대해 준비되는 OLE 컨트롤의 ID입니다.

### <a name="return-value"></a>Return Value

OLE 제어 사이트에 대한 포인터입니다.

### <a name="remarks"></a>설명

대신 편집 컨트롤에 대 한 [PrepareEdItCtrl를](#prepareeditctrl) 사용 하거나 다른 모든 비 OLE 컨트롤에 대 한 [PrepareCtrl.](#preparectrl)

사용자 지정 DDX 또는 DDV 루틴의 `PrepareOleCtrl` 구현자는 DDX를 통해 데이터를 교환하거나 DDV를 통해 데이터를 검증하는 모든 OLE 컨트롤을 호출해야 합니다.

사용자 고유의 DDX 및 DDV 루틴 작성에 대한 자세한 내용은 [기술 참고 26을](../../mfc/tn026-ddx-and-ddv-routines.md)참조하십시오. DDX 및 DDV에 대한 개요는 [대화 상자 교환 및 유효성 검사 및](../../mfc/dialog-data-exchange-and-validation.md) 대화 상자 [항목을](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 뷰렉스](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
