---
title: COleDB레코드뷰 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: de9c602cb747ee3d4449df479530e55ce907cb8a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366098"
---
# <a name="coledbrecordview-class"></a>COleDB레코드뷰 클래스

컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.

## <a name="syntax"></a>구문

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[COleDB레코드뷰::콜레DB레코드뷰](#coledbrecordview)|`COleDBRecordView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleDB레코드뷰::온겟로우셋](#ongetrowset)|표준 HRESULT 값을 반환합니다.|
|[COleDB레코드뷰::온무](#onmove)|데이터 원본의 현재 레코드(더티인 경우)를 업데이트한 다음 지정된 레코드(다음, 이전, 첫 번째 또는 마지막)로 이동합니다.|

## <a name="remarks"></a>설명

뷰는 객체에 직접 연결된 `CRowset` 양식 보기입니다. 뷰는 대화 상자 템플릿 리소스에서 만들어지며 대화 `CRowset` 상자 템플릿의 컨트롤에 개체의 필드를 표시합니다. 개체는 `COleDBRecordView` 대화 상자 데이터 교환(DDX) 및 `CRowset`에 기본 제공된 탐색 기능을 사용하여 양식의 컨트롤과 행 집합 필드 간의 데이터 이동을 자동화합니다. `COleDBRecordView`또한 첫 번째, 다음, 이전 또는 마지막 레코드로 이동하기 위한 기본 구현과 현재 보기중인 레코드를 업데이트하기 위한 인터페이스를 제공합니다.

DDX 함수를 `COleDbRecordView` 사용하여 데이터베이스 레코드 집합에서 직접 데이터를 얻고 대화 상자 컨트롤에 표시할 수 있습니다. `COleDbRecordView`의 `DDX_Field*` 함수가 `DDX_*` 아닌 메서드(예: `DDX_Text` `DDX_FieldText`)를 사용해야 합니다. `DDX_FieldText`형식(for) `COleDbRecordView` `DDX_FieldText` `CRecordset*` `CRecordView`또는 `CDaoRecordset*` (for)의 `CDaoRecordView`추가 인수를 취하기 때문에 작동하지 않습니다.

> [!NOTE]
> OLE DB 소비자 템플릿 클래스가 아닌 DAO(데이터 액세스 개체) 클래스로 작업하는 경우 대신 [클래스 CDaoRecordView를](../../mfc/reference/cdaorecordview-class.md) 사용합니다. 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

`COleDBRecordView`은 레코드 뷰가 사용자 인터페이스를 업데이트할 수 있도록 행 집합에서 사용자의 위치를 추적합니다. 사용자가 행 집합의 양쪽 끝으로 이동하면 레코드 보기는 메뉴 항목 또는 도구 모음 단추와 같은 사용자 인터페이스 개체를 비활성화하여 동일한 방향으로 더 멀리 이동합니다.

행 집합 클래스에 대한 자세한 내용은 [OLE DB 소비자 템플릿 사용](../../data/oledb/ole-db-consumer-templates-cpp.md) 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>요구 사항

**헤더:** afxoledb.h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a>COleDB레코드뷰::콜레DB레코드뷰

`COleDBRecordView` 개체를 생성합니다.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null-종단 문자열을 포함합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

### <a name="remarks"></a>설명

에서 `COleDBRecordView`파생된 형식의 개체를 만들 때 생성자 중 하나를 호출하여 뷰 개체를 만들고 뷰의 기반이 되는 대화 상자 리소스를 식별합니다. 리소스를 이름으로(문자열을 생성자에게 인수로 전달) 또는 ID(서명되지 않은 정수를 인수로 전달)로 식별할 수 있습니다.

> [!NOTE]
> 파생 클래스는 자체 생성자(생성자)를 제공해야 *합니다.* 생성자에서 생성자, 를 호출 `COleDBRecordView::COleDBRecordView`합니다.

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a>COleDB레코드뷰::온겟로우셋

레코드 뷰와 연결된 **CRowset<>** 개체에 대한 핸들을 반환합니다.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

행 집합 개체를 생성하거나 가져오고 핸들을 반환하려면 이 멤버 함수를 재정의해야 합니다. ClassWizard를 사용 하 여 레코드 보기 클래스를 선언 하는 경우 마법사는 기본 재정의를 작성 합니다. ClassWizard의 기본 구현은 레코드 뷰에 저장된 행 집합 핸들이 있는 경우 반환합니다. 그렇지 않으면 ClassWizard로 지정한 형식의 행 집합 개체를 `Open` 생성하고 해당 멤버 함수를 호출하여 테이블을 열거나 쿼리를 실행한 다음 개체에 대한 핸들을 반환합니다.

> [!NOTE]
> MFC 7.0 이전의 `OnGetRowset` 경우 에 `CRowset`대한 포인터를 반환했습니다. 호출하는 `OnGetRowset`코드가 있는 경우 반환 형식을 템플릿화된 클래스 **CRowset<>** 변경해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

자세한 정보 및 예제는 [레코드 보기: 레코드 보기 사용](../../data/using-a-record-view-mfc-data-access.md)문서를 참조하십시오.

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a>COleDB레코드뷰::온무

행 집합의 다른 레코드로 이동하고 해당 필드를 레코드 뷰의 컨트롤에 표시합니다.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>매개 변수

*니드무브커드*<br/>
다음 표준 명령 ID 값 중 하나입니다.

- ID_RECORD_FIRST — 레코드 집합의 첫 번째 레코드로 이동합니다.

- ID_RECORD_LAST — 레코드 집합의 마지막 레코드로 이동합니다.

- ID_RECORD_NEXT — 레코드 집합의 다음 레코드로 이동합니다.

- ID_RECORD_PREV — 레코드 집합의 이전 레코드로 이동합니다.

### <a name="return-value"></a>Return Value

이동이 성공한 경우 0이 아닙니다. 그렇지 않으면 이동 요청이 거부된 경우 0입니다.

### <a name="remarks"></a>설명

기본 구현은 레코드 `Move` 뷰와 `CRowset` 연결된 개체의 적절한 멤버 함수를 호출합니다.

기본적으로 사용자가 `OnMove` 레코드 보기에서 변경한 경우 데이터 원본의 현재 레코드를 업데이트합니다.

응용 프로그램 마법사는 첫 번째 레코드, 마지막 레코드, 다음 레코드 및 이전 레코드 메뉴 항목이 있는 메뉴 리소스를 만듭니다. 도킹 가능한 도구 모음 옵션을 선택하면 응용 프로그램 마법사에서 이러한 명령에 해당하는 단추가 있는 도구 모음도 만듭니다.

레코드 집합의 마지막 레코드를 지나이동하면 레코드 뷰가 계속해서 마지막 레코드를 표시합니다. 첫 번째 레코드를 뒤로 이동하면 레코드 뷰가 첫 번째 레코드를 계속 표시합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)
