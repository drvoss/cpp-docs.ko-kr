---
title: CWinForms뷰 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
ms.openlocfilehash: 6eb6b9e385e9dbc96eb3b62ffb80909e54569e97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369599"
---
# <a name="cwinformsview-class"></a>CWinForms뷰 클래스

Windows Forms 컨트롤을 MFC 뷰로 호스팅하기 위한 일반 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CWinFormsView : public CView;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C윈폼뷰::CWinForms뷰](#cwinformsview)|`CWinFormsView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinForms보기::Getcontrol](#getcontrol)|Windows 양식 컨트롤에 대한 포인터를 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|속성||
|----------|-|
|[CWinForms보기::연산자 제어^](#operator_control)|Windows 양식 컨트롤에 대한 포인터로 형식을 캐스팅합니다.|

## <a name="remarks"></a>설명

MFC는 `CWinFormsView` 클래스를 사용하여 MFC 보기 내에서 .NET 프레임워크 Windows Forms 컨트롤을 호스트합니다. 컨트롤은 네이티브 뷰의 자식이며 MFC 뷰의 전체 클라이언트 영역을 차지합니다. 결과는 `CFormView` 보기와 유사하므로 Windows Forms 디자이너와 런타임을 활용하여 풍부한 양식 기반 뷰를 만들 수 있습니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

> [!NOTE]
> MFC Windows Forms 통합은 MFC(AFXDLL가 정의된 프로젝트)와 동적으로 연결되는 프로젝트에서만 작동합니다.

> [!NOTE]
> CWinFormsView MFC 스플리터 창 [(CSplitterWnd 클래스)를](../../mfc/reference/csplitterwnd-class.md)지원 하지 않습니다. 현재 는 Windows 양식 스플리터 컨트롤만 지원됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>C윈폼뷰::CWinForms뷰

`CWinFormsView` 개체를 생성합니다.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>매개 변수

*p관리뷰타입*<br/>
Windows Forms 사용자 컨트롤의 데이터 형식에 대한 포인터입니다.

### <a name="example"></a>예제

다음 `CUserView` 예제에서 클래스는 생성자에서 `CWinFormsView` 상속 하 `UserControl1` 고 `CWinFormsView` 생성자의 형식을 전달 합니다. `UserControl1`는 ControlLibrary1.dll에서 사용자 지정 빌드된 컨트롤입니다.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a>CWinForms보기::Getcontrol

Windows 양식 컨트롤에 대한 포인터를 검색합니다.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Return Value

`System.Windows.Forms.Control` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

Windows 양식을 사용하는 방법의 예는 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a>CWinForms보기::연산자 제어^

Windows 양식 컨트롤에 대한 포인터로 형식을 캐스팅합니다.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>설명

이 연산자는 형식의 `CWinFormsView` <xref:System.Windows.Forms.Control>Windows Forms 컨트롤에 대한 포인터를 허용하는 함수에 뷰를 전달할 수 있습니다.

### <a name="example"></a>예제

  [참조 CWinFormsView::GetControl.](#getcontrol)

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinForms제어 클래스](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinForms디아로그 클래스](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)
