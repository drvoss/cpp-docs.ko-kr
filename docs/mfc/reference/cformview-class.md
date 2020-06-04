---
title: CFormView 클래스
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: a9b897c661731878f0bf78c9d04ae7c4ba28cd42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373795"
---
# <a name="cformview-class"></a>CFormView 클래스

폼 뷰에 사용되는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CFormView : public CScrollView
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|`CFormView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|초기화하는 동안 동기화에 사용됩니다.|

## <a name="remarks"></a>설명

폼 뷰는 기본적으로 컨트롤을 포함하는 뷰입니다. 이러한 컨트롤은 대화 상자 템플릿 리소스에 따라 배치됩니다. 애플리케이션에서 폼을 사용하려면 `CFormView`를 사용합니다. 이러한 뷰는 필요에 따라 [CScrollView](../../mfc/reference/cscrollview-class.md) 기능을 사용하여 스크롤을 지원합니다.

[양식 기반 응용 프로그램을 만드는](../../mfc/reference/creating-a-forms-based-mfc-application.md)경우 해당 뷰 클래스를 기반으로 `CFormView`하여 양식 기반 응용 프로그램으로 만들 수 있습니다.

문서 보기 기반 응용 프로그램에 새 [양식 항목을](../../mfc/form-views-mfc.md) 삽입할 수도 있습니다. 애플리케이션이 초기에 폼을 지원하지 않은 경우에도 새 폼을 삽입하면 Visual C++에서 이 지원 기능을 추가합니다.

폼 기반 애플리케이션을 만들 때는 MFC 애플리케이션 마법사 및 클래스 추가 명령을 사용하는 것이 좋습니다. 이러한 메서드를 사용하지 않고 양식 기반 응용 프로그램을 만들어야 하는 경우 [양식 기반 응용 프로그램 만들기](../../mfc/reference/creating-a-forms-based-mfc-application.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cformviewcformview"></a><a name="cformview"></a>C폼 뷰::C폼뷰

`CFormView` 개체를 생성합니다.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null-종단 문자열을 포함합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

### <a name="remarks"></a>설명

에서 `CFormView`파생된 형식의 개체를 만들 때 생성자 중 하나를 호출하여 뷰 개체를 만들고 뷰의 기반이 되는 대화 상자 리소스를 식별합니다. 리소스를 이름으로(문자열을 생성자에게 인수로 전달) 또는 ID(서명되지 않은 정수를 인수로 전달)로 식별할 수 있습니다.

양식 보기 창 및 자식 컨트롤이 호출될 때까지 `CWnd::Create` 만들어지지 않습니다. `CWnd::Create`문서 템플릿에 의해 구동되는 문서 및 뷰 생성 프로세스의 일부로 프레임워크에서 호출됩니다.

> [!NOTE]
> 파생 클래스는 자체 생성자(생성자)를 제공해야 *합니다.* 생성자에서 생성자, `CFormView::CFormView`와 리소스 이름 또는 ID를 이전 클래스 개요에 표시된 인수로 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>CFormView::이시니트Dlg 완료

MFC에서 다른 작업을 수행하기 전에 초기화가 완료되었는지 확인하는 데 사용됩니다.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Return Value

이 대화 상자에 대한 초기화 함수가 완료된 경우 true입니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 뷰렉스](../../overview/visual-cpp-samples.md)<br/>
[C스크롤뷰 클래스](../../mfc/reference/cscrollview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)<br/>
[C스크롤뷰 클래스](../../mfc/reference/cscrollview-class.md)
