---
title: CPropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: f46566eb562f1515e98aedf938ca68b225ee1b67
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751107"
---
# <a name="cpropertypage-class"></a>CPropertyPage 클래스

속성 시트(탭 대화 상자라고도 함)의 개별 페이지를 나타냅니다.

## <a name="syntax"></a>구문

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C속성 페이지::C속성 페이지](#cpropertypage)|`CPropertyPage` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPropertyPage::취소닫기](#canceltoclose)|확인 단추를 변경하여 닫기를 읽고 모달 속성 시트 페이지에서 복구할 수 없는 변경 후 취소 단추를 사용하지 않도록 설정합니다.|
|[CPropertyPage::생성](#construct)|`CPropertyPage` 개체를 생성합니다. 런타임에 매개 변수를 지정하거나 배열을 사용하는 경우 사용합니다. `Construct`|
|[CPropertyPage::GetPSP](#getpsp)|`CPropertyPage` 개체와 연결된 Windows [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) 구조를 검색합니다.|
|[CPropertyPage::적용 중](#onapply)|지금 적용 단추를 클릭하면 프레임워크에서 호출됩니다.|
|[CPropertyPage::OnCancel](#oncancel)|취소 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::온킬액티브](#onkillactive)|현재 페이지가 더 이상 활성 페이지가 아니면 프레임워크에서 호출됩니다. 여기에서 데이터 유효성 검사를 수행합니다.|
|[CPropertyPage::OnOK](#onok)|확인, 지금 적용 또는 닫기 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::온쿼리취소](#onquerycancel)|취소 단추를 클릭하고 취소가 발생하기 전에 프레임워크에서 호출합니다.|
|[CPropertyPage::온리셋](#onreset)|취소 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::시작 활성](#onsetactive)|페이지가 활성 페이지로 만들어지면 프레임워크에서 호출됩니다.|
|[CPropertyPage::온위저드백](#onwizardback)|마법사 형식 속성 시트를 사용하는 동안 뒤로 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::온위저피니](#onwizardfinish)|마법사 형식 속성 시트를 사용하는 동안 완료 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::온위저즈넥스트](#onwizardnext)|마법사 형식 속성 시트를 사용하는 동안 다음 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CPropertyPage::쿼리 형제](#querysiblings)|메시지를 속성 시트의 각 페이지로 전달합니다.|
|[C속성 페이지::집합수정](#setmodified)|지금 적용 버튼을 활성화하거나 비활성화하려면 전화를 걸수 있습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|윈도우 [소품 페이지](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) 구조입니다. 기본 속성 페이지 매개 변수에 대한 액세스를 제공합니다.|

## <a name="remarks"></a>설명

표준 대화 상자와 마찬가지로 속성 시트의 `CPropertyPage` 각 페이지에 대해 클래스를 파생합니다. -derived 개체를 사용 `CPropertyPage`하려면 먼저 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) 개체를 만든 다음 속성 시트에 들어가는 각 페이지에 대 한 개체를 만듭니다. 시트의 각 페이지에 대해 [CPropertySheet::AddPage를](../../mfc/reference/cpropertysheet-class.md#addpage) 호출한 다음 모달 속성 시트에 [대해 CPropertySheet::DoModal또는](../../mfc/reference/cpropertysheet-class.md#domodal) [CPropertySheet::모덜리스](../../mfc/reference/cpropertysheet-class.md#create) 속성 시트에 대해 만들기를 호출하여 속성 시트를 표시합니다.

장치 설정 또는 뉴스레터 만들기와 같은 작업 단계를 안내하는 속성 페이지 시퀀스가 있는 속성 시트로 구성된 마법사라는 탭 대화 상자 유형을 만들 수 있습니다. 마법사 유형 탭 대화 상자에서 속성 페이지에는 탭이 없으며 한 번에 하나의 속성 페이지만 표시됩니다. 또한 확인 및 지금 적용 버튼 대신 마법사 유형 탭 대화 상자에 뒤로 버튼, 다음 또는 완료 버튼 및 취소 버튼이 있습니다.

속성 시트를 마법사로 설정하는 방법에 대한 자세한 내용은 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)을 참조하십시오. 개체 사용에 `CPropertyPage` 대한 자세한 내용은 [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>CPropertyPage::취소닫기

복구할 수 없는 변경이 모달 속성 시트 페이지의 데이터에 대해 변경된 후 이 함수를 호출합니다.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>설명

이 함수는 확인 버튼을 닫고 취소 단추를 비활성화하도록 변경합니다. 이렇게 변경하면 변경 사항이 영구적이며 수정을 취소할 수 없음을 사용자에게 알릴 수 있습니다.

모덜리스 속성 시트에는 `CancelToClose` 기본적으로 취소 단추가 없기 때문에 멤버 함수는 모덜리스 속성 시트에서 아무 것도 수행하지 않습니다.

### <a name="example"></a>예제

  [CPropertyPage::쿼리 형제에](#querysiblings)대 한 예제를 참조 합니다.

## <a name="cpropertypageconstruct"></a><a name="construct"></a>CPropertyPage::생성

이 멤버 함수를 `CPropertyPage` 호출하여 개체를 생성합니다.

```cpp
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지에 사용된 템플릿의 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 배치할 이름의 ID입니다. 0이면 이 페이지의 대화 상자 템플릿에서 이름이 이동됩니다.

*lpszTemplateName*<br/>
템플릿 리소스의 이름인 null-종료된 문자열을 포함합니다.

*니드헤더타이틀*<br/>
속성 페이지 헤더의 제목 위치에 배치할 이름의 ID입니다. 기본적으로 0입니다.

*니디헤더자막*<br/>
속성 페이지 헤더의 자막 위치에 배치할 이름의 ID입니다. 기본적으로 0입니다.

### <a name="remarks"></a>설명

다음 조건이 모두 충족되면 개체가 표시됩니다.

- 페이지가 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)를 사용하여 속성 시트에 추가되었습니다.

- 속성 시트의 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 또는 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출되었습니다.

- 사용자가 이 페이지를 선택했습니다(탭에 탭).

다른 `Construct` 클래스 생성자 중 하나가 호출되지 않은 경우 호출합니다. 멤버 `Construct` 함수는 매개 변수 문을 비워 두었다가 코드의 어느 지점에서나 여러 매개 변수 및 생성을 지정할 수 있으므로 유연합니다.

배열로 `Construct` 작업할 때 사용해야 하며 데이터 `Construct` 멤버에 적절한 값이 할당되도록 배열의 각 멤버를 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

## <a name="cpropertypagecpropertypage"></a><a name="cpropertypage"></a>C속성 페이지::C속성 페이지

`CPropertyPage` 개체를 생성합니다.

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지에 사용된 템플릿의 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 배치할 이름의 ID입니다. 0이면 이 페이지의 대화 상자 템플릿에서 이름이 이동됩니다.

*dwSize*<br/>
*lpsz템플릿이름* 이 페이지의 템플릿 이름이 포함된 문자열을 가리킵니다. NULL이 될 수 없습니다.

*니드헤더타이틀*<br/>
속성 페이지 헤더의 제목 위치에 배치할 이름의 ID입니다.

*니디헤더자막*<br/>
속성 페이지 헤더의 자막 위치에 배치할 이름의 ID입니다.

### <a name="remarks"></a>설명

다음 조건이 모두 충족되면 개체가 표시됩니다.

- 페이지가 [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)를 사용하여 속성 시트에 추가되었습니다.

- 속성 시트의 [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) 또는 [만들기](../../mfc/reference/cpropertysheet-class.md#create) 함수가 호출되었습니다.

- 사용자가 이 페이지를 선택했습니다(탭에 탭).

여러 매개 변수가 있는 경우(예: 배열을 사용하는 경우) `CPropertyPage` [대신 CPropertySheet:Construct를](../../mfc/reference/cpropertysheet-class.md#construct) 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

## <a name="cpropertypagegetpsp"></a><a name="getpsp"></a>CPropertyPage::GetPSP

`CPropertyPage` 개체와 연결된 Windows [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) 구조를 검색합니다.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Return Value

구조에 대한 `PROPSHEETPAGE` 참조입니다.

## <a name="cpropertypagem_psp"></a><a name="m_psp"></a>CPropertyPage::m_psp

`m_psp`[PROPSHEETPAGE의](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)특성을 저장하는 구조입니다.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>설명

이 구조를 사용하여 생성된 후 속성 페이지의 모양을 초기화합니다.

멤버 목록을 포함하여 이 구조에 대한 자세한 `PROPSHEETPAGE` 내용은 Windows SDK를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

## <a name="cpropertypageonapply"></a><a name="onapply"></a>CPropertyPage::적용 중

사용자가 확인 또는 지금 적용 단추를 선택할 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Return Value

변경이 수락되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

프레임워크가 이 함수를 호출하면 속성 시트의 모든 속성 페이지에 대한 변경 내용이 `OnApply` 허용되고 속성 시트는 포커스를 유지하고 TRUE(값 1)를 반환합니다. 프레임워크에서 호출하기 전에 `OnApply` [SetModified를](#setmodified) 호출하고 해당 매개 변수를 TRUE로 설정해야 합니다. 이렇게 하면 사용자가 속성 페이지에서 변경하는 즉시 지금 적용 버튼이 활성화됩니다.

이 멤버 함수를 재정의하여 사용자가 지금 적용 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다. 재정의 할 때 함수는 변경 내용을 수락하기 위해 TRUE를 반환하고 FALSE는 변경 사항이 적용되지 않도록해야합니다.

호출의 `OnApply` `OnOK`기본 구현 .

사용자가 속성 시트에서 지금 적용 또는 확인 단추를 누를 때 전송되는 알림 메시지에 대한 자세한 내용은 Windows SDK의 [PSN_APPLY](/windows/win32/Controls/psn-apply) 참조하세요.

### <a name="example"></a>예제

  [CPropertyPage::OnOK](#onok)에 대한 예제를 참조하십시오.

## <a name="cpropertypageoncancel"></a><a name="oncancel"></a>CPropertyPage::OnCancel

이 멤버 함수는 취소 단추를 선택할 때 프레임워크에서 호출됩니다.

```
virtual void OnCancel();
```

### <a name="remarks"></a>설명

단추 취소 작업을 수행하려면 이 멤버 함수를 재정의합니다. 기본값은 변경된 내용을 무효화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

## <a name="cpropertypageonkillactive"></a><a name="onkillactive"></a>CPropertyPage::온킬액티브

이 멤버 함수는 페이지가 더 이상 활성 페이지가 아니면 프레임워크에서 호출됩니다.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Return Value

데이터가 성공적으로 업데이트된 경우 비영( Nonzero) 0.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 특수 데이터 유효성 검사 작업을 수행합니다.

이 멤버 함수의 기본 구현은 속성 페이지의 컨트롤에서 속성 페이지의 멤버 변수로 설정을 복사합니다. 대화 상자 데이터 유효성 검사(DDV) 오류로 인해 데이터가 성공적으로 업데이트되지 않은 경우 페이지는 포커스를 유지합니다.

이 멤버 함수가 성공적으로 반환되면 프레임워크는 페이지의 [OnOK](#onok) 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

## <a name="cpropertypageonok"></a><a name="onok"></a>CPropertyPage::OnOK

이 멤버 함수는 프레임워크에서 OnKillActive 를 호출한 직후 사용자가 확인 또는 지금 적용 단추를 선택할 때 프레임워크에서 [호출됩니다.](#onkillactive)

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

사용자가 확인 또는 지금 적용 단추중 하나를 선택하면 프레임워크는 속성 페이지에서 [PSN_APPLY](/windows/win32/Controls/psn-apply) 알림을 받습니다. 속성 페이지가 해당 경우 알림을 보내지 않기 때문에 `OnOK` [CPropertySheet::PressButton을](../../mfc/reference/cpropertysheet-class.md#pressbutton) 호출하는 경우 호출이 수행되지 않습니다.

사용자가 전체 속성 시트를 해제할 때 현재 활성 페이지에 특정한 추가 동작을 구현하기 위해 이 멤버 함수를 재정의합니다.

이 멤버 함수의 기본 구현은 데이터가 `OnKillActive` 함수에서 업데이트되었다는 것을 반영하기 위해 페이지를 "정리"로 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

## <a name="cpropertypageonquerycancel"></a><a name="onquerycancel"></a>CPropertyPage::온쿼리취소

이 멤버 함수는 사용자가 취소 단추를 클릭하고 취소 작업이 수행되기 전에 프레임워크에서 호출됩니다.

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Return Value

취소 작업을 방지하려면 FALSE를 반환하거나 TRUE를 허용합니다.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 사용자가 취소 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다.

TRUE를 반환하는 `OnQueryCancel` 기본 구현입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

## <a name="cpropertypageonreset"></a><a name="onreset"></a>CPropertyPage::온리셋

사용자가 취소 단추를 선택할 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual void OnReset();
```

### <a name="remarks"></a>설명

프레임워크가 이 함수를 호출하면 사용자가 이전에 지금 적용 단추를 선택한 모든 속성 페이지의 변경 내용이 삭제되고 속성 시트에 포커스가 유지됩니다.

이 멤버 함수를 재정의하여 사용자가 취소 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다.

기본 구현은 `OnReset` 아무 것도 하지 않습니다.

### <a name="example"></a>예제

  [CPropertyPage::OnCancel](#oncancel)에 대한 예제를 참조하십시오.

## <a name="cpropertypageonsetactive"></a><a name="onsetactive"></a>CPropertyPage::시작 활성

이 멤버 함수는 사용자가 페이지를 선택하고 활성 페이지가 될 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Return Value

페이지가 성공적으로 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

페이지가 활성화될 때 작업을 수행하도록 이 멤버 함수를 재정의합니다. 이 멤버 함수의 재정의는 일반적으로 데이터 멤버를 업데이트한 후 기본 버전을 호출하여 새 데이터로 페이지 컨트롤을 업데이트할 수 있도록 합니다.

기본 구현은 이전에 만들지 않은 경우 페이지에 대한 창을 만들고 활성 페이지로 만듭니다.

### <a name="example"></a>예제

  [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)에 대한 예제를 참조하십시오.

## <a name="cpropertypageonwizardback"></a><a name="onwizardback"></a>CPropertyPage::온위저드백

사용자가 마법사에서 뒤로 단추를 클릭할 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Return Value

0을 자동으로 다음 페이지로 진행합니다. -1 페이지가 변경 되지 않도록 합니다. 다음 페이지가 아닌 다른 페이지로 이동하려면 표시할 대화 상자의 식별자를 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 뒤로 단추를 누를 때 사용자가 수행해야 하는 일부 작업을 지정합니다.

마법사 유형 속성 시트를 만드는 방법에 대한 자세한 내용은 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

## <a name="cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>CPropertyPage::온위저피니

사용자가 마법사에서 완료 단추를 클릭할 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Return Value

마법사가 완료될 때 속성 시트가 소멸되는 경우 비영입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

사용자가 마법사에서 **완료** 단추를 클릭하면 프레임워크에서 이 함수를 호출합니다. TRUE(영하가 아닌 값)를 `OnWizardFinish` 반환하면 속성 시트가 소멸될 수 있지만 실제로는 소멸되지 않습니다. 속성 `DestroyWindow` 시트를 파기하기 위해 호출합니다. 에서 `DestroyWindow` `OnWizardFinish`호출하지 마십시오. 이렇게 하면 힙이 손상되어 있거나 다른 오류가 발생할 수 있습니다.

이 멤버 함수를 재정의하여 완료 단추를 누를 때 사용자가 수행해야 하는 일부 작업을 지정할 수 있습니다. 이 함수를 재정의할 때 FALSE를 반환하여 속성 시트가 소멸되지 않도록 합니다.

사용자가 마법사 속성 시트에서 완료 단추를 누를 때 전송되는 알림 메시지에 대한 자세한 내용은 Windows SDK의 [PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish) 참조하세요.

마법사 유형 속성 시트를 만드는 방법에 대한 자세한 내용은 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

## <a name="cpropertypageonwizardnext"></a><a name="onwizardnext"></a>CPropertyPage::온위저즈넥스트

사용자가 마법사에서 다음 단추를 클릭할 때 이 멤버 함수는 프레임워크에서 호출됩니다.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Return Value

0을 자동으로 다음 페이지로 진행합니다. -1 페이지가 변경 되지 않도록 합니다. 다음 페이지가 아닌 다른 페이지로 이동하려면 표시할 대화 상자의 식별자를 반환합니다.

### <a name="remarks"></a>설명

다음 단추를 누를 때 사용자가 수행해야 하는 몇 가지 작업을 지정하려면 이 멤버 함수를 재정의합니다.

마법사 유형 속성 시트를 만드는 방법에 대한 자세한 내용은 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

## <a name="cpropertypagequerysiblings"></a><a name="querysiblings"></a>CPropertyPage::쿼리 형제

이 멤버 함수를 호출하여 속성 시트의 각 페이지에 메시지를 전달합니다.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*wParam*<br/>
추가 메시지 종속 정보를 지정합니다.

*lParam*<br/>
추가 메시지 종속 정보 지정

### <a name="return-value"></a>Return Value

속성 시트의 페이지에서 영하지 않은 값 또는 모든 페이지가 0값을 반환하는 경우 0입니다.

### <a name="remarks"></a>설명

페이지가 영하지 않은 값을 반환하는 경우 속성 시트는 후속 페이지로 메시지를 보내지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

## <a name="cpropertypagesetmodified"></a><a name="setmodified"></a>C속성 페이지::집합수정

속성 페이지의 설정을 적절한 외부 개체에 적용해야 하는지 여부에 따라 이 멤버 함수를 호출하여 지금 적용 단추를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>매개 변수

*b 변경되었습니다.*<br/>
TRUE는 속성 페이지 설정이 마지막으로 적용된 이후 수정되었음을 나타냅니다. false는 속성 페이지 설정이 적용되었거나 무시되어야 함을 나타냅니다.

### <a name="remarks"></a>설명

프레임워크는 호출한 속성 페이지즉 "더티"인 페이지를 `SetModified( TRUE )`추적합니다. 페이지 중 하나를 호출하면 `SetModified( TRUE )` 지금 적용 버튼이 항상 활성화됩니다. 페이지 중 하나를 호출할 `SetModified( FALSE )` 때 지금 적용 단추는 비활성화되지만 다른 페이지중 어느 페이지도 "더럽지 않은" 경우에만 사용할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CProperty시트 클래스](../../mfc/reference/cpropertysheet-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
