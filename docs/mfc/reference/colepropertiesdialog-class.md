---
title: COlePropertiesDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
ms.openlocfilehash: f065894ff49af755ab4020f71b0213b19db49054
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374889"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog 클래스

Windows 공용 OLE 개체 속성 대화 상자를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COlePropertiesDialog : public COleDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COle속성대화문::COle속성대화문](#colepropertiesdialog)|`COlePropertiesDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[코올프로퍼티디언: :D오모달](#domodal)|대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[COlePropertiesDialog::온도 스케일](#onapplyscale)|문서 항목의 크기 조정이 변경된 경우 프레임워크에서 호출합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[COlePropertiesDialog::m_gp](#m_gp)|개체의 "일반" 페이지를 초기화하는 `COlePropertiesDialog` 데 사용되는 구조입니다.|
|[COlePropertiesDialog::m_lp](#m_lp)|개체의 "링크" 페이지를 초기화하는 `COlePropertiesDialog` 데 사용되는 구조입니다.|
|[COlePropertiesDialog::m_op](#m_op)|개체를 초기화하는 `COlePropertiesDialog` 데 사용되는 구조입니다.|
|[COlePropertiesDialog::m_psh](#m_psh)|추가 사용자 지정 속성 페이지를 추가 하는 데 사용 되는 구조입니다.|
|[COlePropertiesDialog::m_vp](#m_vp)|개체의 "보기" 페이지를 사용자 지정하는 `COlePropertiesDialog` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

일반적인 OLE 개체 속성 대화 상자는 Windows 표준과 일치하는 방식으로 OLE 문서 항목의 속성을 표시하고 수정하는 쉬운 방법을 제공합니다. 이러한 속성에는 문서 항목으로 표시되는 파일에 대한 정보, 아이콘 및 이미지 크기 조정 을 표시하는 옵션 및 항목링크에 대한 정보(항목이 연결된 경우)가 포함됩니다.

개체를 `COlePropertiesDialog` 사용하려면 먼저 생성기를 `COlePropertiesDialog` 사용하여 개체를 만듭니다. 대화 상자를 생성한 후 멤버 `DoModal` 함수를 호출하여 대화 상자를 표시하고 사용자가 항목의 모든 속성을 수정할 수 있도록 합니다. `DoModal`사용자가 확인(IDOK) 또는 취소(IDCANCEL) 단추를 선택했는지 여부를 반환합니다. 확인 및 취소 버튼 외에도 적용 버튼이 있습니다. 사용자가 적용을 선택하면 문서 항목의 속성에 대한 모든 변경 내용이 항목에 적용되고 해당 이미지가 자동으로 업데이트되지만 활성 상태로 유지됩니다.

[m_psh](#m_psh) 데이터 멤버는 `PROPSHEETHEADER` 구조에 대한 포인터이며 대부분의 경우 명시적으로 액세스할 필요가 없습니다. 한 가지 예외는 기본 일반, 보기 및 링크 페이지를 초과하는 추가 속성 페이지가 필요한 경우입니다. 이 경우 멤버 함수를 `m_psh` 호출하기 전에 사용자 지정 `DoModal` 페이지를 포함하도록 데이터 멤버를 수정할 수 있습니다.

OLE 대화 상자에 대한 자세한 내용은 [OLE의 문서 대화 상자를](../../mfc/dialog-boxes-in-ole.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePropertiesDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

## <a name="colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COle속성대화문::COle속성대화문

`COlePropertiesDialog` 개체를 만듭니다.

```
COlePropertiesDialog(
    COleClientItem* pItem,
    UINT nScaleMin = 10,
    UINT nScaleMax = 500,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
속성에 액세스하는 문서 항목에 대한 포인터입니다.

*n스케일민*<br/>
문서 항목 이미지의 최소 배율 백분율입니다.

*앤스케일맥스*<br/>
문서 항목 이미지의 최대 배율 백분율입니다.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자에 대한 포인터입니다.

### <a name="remarks"></a>설명

문서 항목에 대한 크기 조정을 `COlePropertiesDialog` 구현하기 위해 공통 OLE 개체 속성 대화 상자 클래스를 파생합니다. 이 클래스의 인스턴스에서 구현한 모든 대화 상자는 문서 항목의 크기 조정을 지원하지 않습니다.

기본적으로 일반적인 OLE 개체 속성 대화 상자에는 세 개의 기본 페이지가 있습니다.

- 일반

   이 페이지에는 선택한 문서 항목으로 표시되는 파일에 대한 시스템 정보가 포함되어 있습니다. 이 페이지에서 사용자는 선택한 항목을 다른 유형으로 변환할 수 있습니다.

- 보기

   이 페이지에는 항목을 표시하고, 아이콘을 변경하고, 이미지의 배율을 변경하는 옵션이 포함되어 있습니다.

- 링크

   이 페이지에는 연결된 항목의 위치를 변경하고 연결된 항목을 업데이트하는 옵션이 포함되어 있습니다. 이 페이지에서 사용자는 선택한 항목의 링크를 끊을 수 있습니다.

기본적으로 제공된 페이지 이상으로 페이지를 추가하려면 -derived 클래스의 생성자에서 나가기 전에 [m_psh](#m_psh) 멤버 변수를 수정합니다. `COlePropertiesDialog` 이것은 생성자의 고급 `COlePropertiesDialog` 구현입니다.

## <a name="colepropertiesdialogdomodal"></a><a name="domodal"></a>코올프로퍼티디언: :D오모달

이 멤버 함수를 호출하여 Windows 공통 OLE 개체 속성 대화 상자를 표시하고 사용자가 문서 항목의 다양한 속성을 보거나 변경할 수 있도록 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL이 성공하면 그렇지 않으면 0. IDOK 및 IDCANCEL은 사용자가 확인 또는 취소 단추를 선택했는지 여부를 나타내는 상수입니다.

IDCANCEL가 반환되면 Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 호출하여 오류가 발생했는지 확인할 수 있습니다.

## <a name="colepropertiesdialogm_gp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp

OLE 개체 속성 대화 상자의 일반 페이지를 초기화하는 데 사용되는 [OLEUIGNRLPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuignrlpropsw)형식의 구조입니다.

```
OLEUIGNRLPROPS m_gp;
```

### <a name="remarks"></a>설명

이 페이지에서는 포함의 유형과 크기를 보여 주며 사용자가 대화 상자 변환에 액세스할 수 있도록 합니다. 이 페이지에는 개체가 링크인 경우 링크 대상도 표시됩니다.

`OLEUIGNRLPROPS` 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

## <a name="colepropertiesdialogm_lp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp

OLE 개체 속성 대화 상자의 링크 페이지를 초기화하는 데 사용되는 [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw)형식의 구조입니다.

```
OLEUILINKPROPS m_lp;
```

### <a name="remarks"></a>설명

이 페이지는 연결된 항목의 위치를 표시하고 사용자가 항목에 대한 링크를 업데이트하거나 중단할 수 있도록 합니다.

`OLEUILINKPROPS` 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

## <a name="colepropertiesdialogm_op"></a><a name="m_op"></a>COlePropertiesDialog::m_op

일반적인 OLE 개체 속성 대화 상자를 초기화하는 데 사용되는 [OLEUIOBJECTPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiobjectpropsw)형식의 구조입니다.

```
OLEUIOBJECTPROPS m_op;
```

### <a name="remarks"></a>설명

이 구조에는 일반, 링크 및 보기 페이지를 초기화하는 데 사용되는 멤버가 포함되어 있습니다.

자세한 내용은 Windows SDK의 OLEUIOBJECTPROPS 및 [OLEUILINKPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuilinkpropsw) 구조를 참조하십시오.

## <a name="colepropertiesdialogm_psh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh

멤버가 대화 상자 개체의 특성을 저장하는 [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)형식의 구조입니다.

```
PROPSHEETHEADER m_psh;
```

### <a name="remarks"></a>설명

개체를 생성한 `COlePropertiesDialog` 후 `m_psh` `DoModal` 멤버 함수를 호출하기 전에 대화 상자의 다양한 측면을 설정하는 데 사용할 수 있습니다.

데이터 멤버를 `m_psh` 직접 수정하는 경우 기본 동작을 재정의합니다.

`PROPSHEETHEADER` 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

## <a name="colepropertiesdialogm_vp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp

OLE 개체 속성 대화 상자의 보기 페이지를 초기화하는 데 사용되는 [OLEUIVIEWPROPS](/windows/win32/api/oledlg/ns-oledlg-oleuiviewpropsw)형식의 구조입니다.

```
OLEUIVIEWPROPS m_vp;
```

### <a name="remarks"></a>설명

이 페이지에서는 사용자가 개체의 "콘텐츠" 보기와 "상징적" 보기 사이를 전환하고 컨테이너 내에서 크기를 변경할 수 있습니다. 또한 개체가 아이콘으로 표시될 때 사용자가 아이콘 변경 대화 상자에 액세스할 수 있습니다.

`OLEUIVIEWPROPS` 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

## <a name="colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::온도 스케일

크기 조정 값이 변경되고 확인 또는 적용이 선택된 경우 프레임워크에서 호출합니다.

```
virtual BOOL OnApplyScale(
    COleClientItem* pItem,
    int nCurrentScale,
    BOOL bRelativeToOrig);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
속성에 액세스하는 문서 항목에 대한 포인터입니다.

*n전류 스케일*<br/>
대화 상자 눈금의 숫자 값입니다.

*b친척오리그*<br/>
크기 조정이 문서 항목의 원래 크기에 적용되는지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

처리된 경우 비영점; 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다. 크기 조정 컨트롤을 사용하려면 이 함수를 재정의해야 합니다.

> [!NOTE]
> 일반적인 OLE 개체 속성 대화 상자가 표시 되기 전에 프레임 *워크는 pItem에* 대 한 NULL및 a -1 *nCurrentScale에*대 한이 함수를 호출 합니다. 이 작업은 크기 조정 컨트롤을 사용하도록 설정해야 하는지 여부를 결정하기 위해 수행됩니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 CIRC](../../overview/visual-cpp-samples.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDialog 클래스](../../mfc/reference/coledialog-class.md)<br/>
[CPropertyPage 클래스](../../mfc/reference/cpropertypage-class.md)
