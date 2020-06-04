---
title: C레코드뷰 클래스
ms.date: 11/04/2016
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
helpviewer_keywords:
- CRecordView [MFC], CRecordView
- CRecordView [MFC], IsOnFirstRecord
- CRecordView [MFC], IsOnLastRecord
- CRecordView [MFC], OnGetRecordset
- CRecordView [MFC], OnMove
- CRecordView [MFC], OnMove
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
ms.openlocfilehash: b706a80f91a3c952d80da13f453a807c775b9405
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368348"
---
# <a name="crecordview-class"></a>C레코드뷰 클래스

컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CRecordView : public CFormView
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[C레코드 뷰::C레코드뷰](#crecordview)|`CRecordView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C레코드 뷰::이온퍼스트레코드](#isonfirstrecord)|현재 레코드가 연결된 레코드 집합의 첫 번째 레코드인 경우 비영을 반환합니다.|
|[C레코드 뷰::이온라스트레코드](#isonlastrecord)|현재 레코드가 연결된 레코드 집합의 마지막 레코드인 경우 비영을 반환합니다.|
|[C레코드 뷰::온겟레코드 세트](#ongetrecordset)|`CRecordset`에서 파생 된 클래스의 개체에 대 한 포인터를 반환 합니다. ClassWizard는 이 함수를 재정의하고 필요한 경우 레코드 집합을 만듭니다.|
|[C레코드 뷰::이동 중](#onmove)||

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C레코드 뷰::이동 중](#onmove)|현재 레코드가 변경된 경우 데이터 원본에서 업데이트한 다음 지정된 레코드(다음, 이전, 첫 번째 또는 마지막)로 이동합니다.|

## <a name="remarks"></a>설명

뷰는 객체에 직접 연결된 `CRecordset` 양식 보기입니다. 뷰는 대화 상자 템플릿 리소스에서 만들어지며 대화 `CRecordset` 상자 템플릿의 컨트롤에 개체의 필드를 표시합니다. 개체는 `CRecordView` 대화 상자 데이터 교환(DDX) 및 RFX(레코드 필드 교환)를 사용하여 양식의 컨트롤과 레코드 집합 필드 간의 데이터 이동을 자동화합니다. `CRecordView`또한 첫 번째, 다음, 이전 또는 마지막 레코드로 이동하기 위한 기본 구현과 현재 보기중인 레코드를 업데이트하기 위한 인터페이스를 제공합니다.

> [!NOTE]
> ODBC(개방형 데이터베이스 연결) 클래스가 아닌 DAO(데이터 액세스 개체) 클래스로 작업하는 경우 대신 [클래스 CDaoRecordView를](../../mfc/reference/cdaorecordview-class.md) 사용합니다. 자세한 내용은 [문서 개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)을 참조하십시오.

레코드 보기를 만드는 가장 일반적인 방법은 응용 프로그램 마법사를 사용 하 여 입니다. 응용 프로그램 마법사는 레코드 뷰 클래스와 해당 관련 레코드 집합 클래스를 스켈레톤 시작 응용 프로그램의 일부로 만듭니다. 응용 프로그램 마법사를 사용하여 레코드 보기 클래스를 만들지 않으면 나중에 ClassWizard를 사용하여 레코드 뷰 클래스를 만들 수 있습니다. 단일 양식만 필요한 경우 응용 프로그램 마법사 접근 방식이 더 쉽습니다. ClassWizard를 사용하면 개발 프로세스의 나중에 레코드 보기를 사용하도록 결정할 수 있습니다. ClassWizard를 사용하여 레코드 보기와 레코드 집합을 별도로 만든 다음 연결하는 것이 레코드 집합 클래스 및 의 이름을 지정하는 데 더 많은 제어를 제공하므로 가장 유연한 방법입니다. H/. CPP 파일. 이 방법을 사용하면 동일한 레코드 집합 클래스에서 여러 레코드 보기를 가질 수도 있습니다.

최종 사용자가 레코드 보기에서 레코드로 쉽게 이동할 수 있도록 응용 프로그램 마법사는 첫 번째 레코드, 다음 레코드, 이전 레코드 또는 마지막 레코드로 이동하기 위한 메뉴(및 선택적으로 도구 모음) 리소스를 만듭니다. ClassWizard를 사용하여 레코드 뷰 클래스를 만드는 경우 메뉴 및 비트맵 편집기를 사용하여 이러한 리소스를 직접 만들어야 합니다.

레코드에서 레코드로 이동하기 위한 기본 구현에 `IsOnLastRecord` 대한 자세한 내용은 레코드 보기를 [사용하여](../../data/using-a-record-view-mfc-data-access.md)문서를 참조하고 참조합니다. `IsOnFirstRecord`

`CRecordView`은 레코드 뷰가 사용자 인터페이스를 업데이트할 수 있도록 레코드 집합에서 사용자의 위치를 추적합니다. 사용자가 레코드 집합의 양쪽 끝으로 이동하면 레코드 보기는 메뉴 항목 또는 도구 모음 단추와 같은 사용자 인터페이스 개체를 비활성화하여 동일한 방향으로 더 멀리 이동합니다.

레코드 보기 및 레코드 집합 클래스를 선언하고 사용하는 자세한 내용은 레코드 [보기](../../data/record-views-mfc-data-access.md)문서의 "레코드 보기 디자인 및 만들기"를 참조하십시오. 레코드 뷰의 작동 방식과 이를 사용하는 방법에 대한 자세한 내용은 [레코드 보기 사용](../../data/using-a-record-view-mfc-data-access.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CRecordView`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

## <a name="crecordviewcrecordview"></a><a name="crecordview"></a>C레코드 뷰::C레코드뷰

에서 `CRecordView`파생된 형식의 개체를 만들 때 생성자의 두 형식 중 하나를 호출하여 뷰 개체를 초기화하고 뷰의 기반이 되는 대화 상자 리소스를 식별합니다.

```
explicit CRecordView(LPCTSTR lpszTemplateName);
explicit CRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null-종단 문자열을 포함합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

### <a name="remarks"></a>설명

리소스를 이름으로 식별(문자열을 생성자에게 인수로 전달) 또는 ID(서명되지 않은 정수를 인수로 전달)로 식별할 수 있습니다. 리소스 ID를 사용하는 것이 좋습니다.

> [!NOTE]
> 파생 클래스는 자체 생성자(생성자)를 제공해야 *합니다.* 파생 클래스의 생성자에서 아래 예제와 `CRecordView::CRecordView` 같이 리소스 이름 또는 ID를 인수로 생성자 호출합니다.

`CRecordView::OnInitialUpdate``DoDataExchange`호출합니다. `UpdateData` 이 초기 `DoDataExchange` 호출은 `CRecordView` ClassWizard에서 만든 `CRecordset` 필드 데이터 멤버에 (간접적으로) 컨트롤을 연결합니다. 이러한 데이터 멤버는 기본 클래스 `CFormView::OnInitialUpdate` 멤버 함수를 호출할 때까지 사용할 수 없습니다.

> [!NOTE]
> ClassWizard를 사용하는 경우 마법사는 **열거형** 값을 `CRecordView::IDD`정의하고 클래스 선언에서 지정하고 생성자의 멤버 초기화 목록에 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]

## <a name="crecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>C레코드 뷰::이온퍼스트레코드

이 멤버 함수를 호출하여 현재 레코드가 이 레코드 보기와 연결된 레코드 집합 개체의 첫 번째 레코드인지 확인합니다.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Return Value

현재 레코드가 레코드 집합의 첫 번째 레코드인 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 ClassWizard에서 작성한 기본 명령 업데이트 처리기의 구현을 작성하는 데 유용합니다.

사용자가 첫 번째 레코드로 이동하면 프레임워크는 첫 번째 레코드 또는 이전 레코드로 이동하기 위해 가지고 있는 모든 사용자 인터페이스 개체를 비활성화합니다.

## <a name="crecordviewisonlastrecord"></a><a name="isonlastrecord"></a>C레코드 뷰::이온라스트레코드

이 멤버 함수를 호출하여 현재 레코드가 이 레코드 보기와 연결된 레코드 집합 개체의 마지막 레코드인지 확인합니다.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Return Value

현재 레코드가 레코드 집합의 마지막 레코드인 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 ClassWizard가 레코드에서 레코드로 이동하기 위한 사용자 인터페이스를 지원하기 위해 작성하는 기본 명령 업데이트 처리기의 고유한 구현을 작성하는 데 유용합니다.

> [!CAUTION]
> 이 함수의 결과는 사용자가 레코드 집합을 지나갈 때까지 뷰가 레코드 집합의 끝을 감지할 수 없다는 점을 제외하고는 신뢰할 수 있습니다. 레코드 뷰가 다음 레코드 또는 마지막 레코드로 이동하기 위해 사용자 인터페이스 개체를 비활성화해야 함을 알기 전에 사용자는 마지막 레코드를 넘어이동해야 합니다. 사용자가 마지막 레코드를 지나 이동한 다음 마지막 레코드(또는 그 이전)로 다시 이동하면 레코드 보기는 레코드 집합에서 사용자의 위치를 추적하고 사용자 인터페이스 개체를 올바르게 비활성화할 수 있습니다. `IsOnLastRecord`ID_RECORD_LAST 명령을 처리하는 구현 함수를 `OnRecordLast`호출한 후에도 신뢰할 수 `CRecordset::MoveLast`ID_RECORD_LAST.

## <a name="crecordviewongetrecordset"></a><a name="ongetrecordset"></a>C레코드 뷰::온겟레코드 세트

레코드 뷰와 `CRecordset`연결된 -derive된 개체에 대한 포인터를 반환합니다.

```
virtual CRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Return Value

개체가 `CRecordset`성공적으로 생성된 경우 -derived 개체에 대한 포인터입니다. 그렇지 않으면 NULL 포인터입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 생성하거나 가져오고 포인터를 반환하려면 이 멤버 함수를 재정의해야 합니다. ClassWizard를 사용 하 여 레코드 보기 클래스를 선언 하는 경우 마법사는 기본 재정의를 작성 합니다. ClassWizard의 기본 구현은 레코드 뷰에 저장된 레코드 집합 포인터가 있는 경우 반환합니다. 그렇지 않은 경우 ClassWizard로 지정한 형식의 레코드 집합 개체를 생성하고 해당 멤버 함수를 `Open` 호출하여 테이블을 열거나 쿼리를 실행한 다음 개체에 대한 포인터를 반환합니다.

자세한 정보 및 예제는 [레코드 보기: 레코드 보기 사용](../../data/using-a-record-view-mfc-data-access.md)문서를 참조하십시오.

## <a name="crecordviewonmove"></a><a name="onmove"></a>C레코드 뷰::이동 중

이 멤버 함수를 호출하여 레코드 집합의 다른 레코드로 이동하고 해당 필드를 레코드 뷰의 컨트롤에 표시합니다.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>매개 변수

*니드무브커드*<br/>
다음 표준 명령 ID 값 중 하나입니다.

- ID_RECORD_FIRST 레코드 집합의 첫 번째 레코드로 이동합니다.

- ID_RECORD_LAST 레코드 집합의 마지막 레코드로 이동합니다.

- ID_RECORD_NEXT 레코드 집합의 다음 레코드로 이동합니다.

- ID_RECORD_PREV 레코드 집합의 이전 레코드로 이동합니다.

### <a name="return-value"></a>Return Value

이동이 성공한 경우 0이 아닙니다. 그렇지 않으면 이동 요청이 거부된 경우 0입니다.

### <a name="remarks"></a>설명

기본 구현은 레코드 `Move` 뷰와 `CRecordset` 연결된 개체의 적절한 멤버 함수를 호출합니다.

기본적으로 사용자가 `OnMove` 레코드 보기에서 변경한 경우 데이터 원본의 현재 레코드를 업데이트합니다.

응용 프로그램 마법사는 첫 번째 레코드, 마지막 레코드, 다음 레코드 및 이전 레코드 메뉴 항목이 있는 메뉴 리소스를 만듭니다. 도킹 가능한 도구 모음 옵션을 선택하면 응용 프로그램 마법사에서 이러한 명령에 해당하는 단추가 있는 도구 모음도 만듭니다.

레코드 집합의 마지막 레코드를 지나이동하면 레코드 뷰가 계속해서 마지막 레코드를 표시합니다. 첫 번째 레코드를 뒤로 이동하면 레코드 뷰가 첫 번째 레코드를 계속 표시합니다.

> [!CAUTION]
> 호출은 `OnMove` 레코드 집합에 레코드가 없는 경우 예외를 throw합니다. 해당 이동 작업 전에 적절한 `OnUpdateRecordFirst` `OnUpdateRecordLast`사용자 `OnUpdateRecordNext`인터페이스 `OnUpdateRecordPrev` 업데이트 처리기 함수(또는)를 호출하여 레코드 집합에 레코드가 있는지 확인합니다.

## <a name="see-also"></a>참고 항목

[CFormView 클래스](../../mfc/reference/cformview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)
