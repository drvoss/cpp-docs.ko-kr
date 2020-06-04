---
title: CVSListBox 클래스
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: 4ea48a263a01133419067979ee5fa3e62105c7f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373189"
---
# <a name="cvslistbox-class"></a>CVSListBox 클래스

클래스는 `CVSListBox` 편집 가능한 목록 컨트롤을 지원합니다.

## <a name="syntax"></a>구문

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CVSList상자::CVSListBox](#cvslistbox)|`CVSListBox` 개체를 생성합니다.|
|`CVSListBox::~CVSListBox`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CVSList상자::추가 항목](#additem)|목록 컨트롤에 문자열을 추가합니다. ( `CVSListBoxBase::AddItem`을 재정의합니다.)|
|[CVSListBox::편집항목](#edititem)|목록 컨트롤 항목의 텍스트에서 편집 작업을 시작합니다. ( `CVSListBoxBase::EditItem`을 재정의합니다.)|
|[CVSListBox::GetCount](#getcount)|편집 가능한 목록 컨트롤에서 문자열 수를 검색합니다. ( `CVSListBoxBase::GetCount`을 재정의합니다.)|
|[CVSListBox::겟아이템데이터](#getitemdata)|편집 가능한 목록 제어 항목과 연결된 응용 프로그램별 32비트 값을 검색합니다. ( `CVSListBoxBase::GetItemData`을 재정의합니다.)|
|[CVSListBox:::겟아이템텍스트](#getitemtext)|편집 가능한 목록 컨트롤 항목의 텍스트를 검색합니다. ( `CVSListBoxBase::GetItemText`을 재정의합니다.)|
|[CVSList상자::겟셀아이템](#getselitem)|편집 가능한 목록 컨트롤에서 현재 선택한 항목의 0기준 인덱스를 검색합니다. ( `CVSListBoxBase::GetSelItem`을 재정의합니다.)|
|`CVSListBox::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. 자세한 정보 및 메서드 구문은 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 참조하십시오. ( `CVSListBoxBase::PreTranslateMessage`을 재정의합니다.)|
|[CVSList상자::제거항목](#removeitem)|편집 가능한 목록 컨트롤에서 항목을 제거합니다. ( `CVSListBoxBase::RemoveItem`을 재정의합니다.)|
|[CVSList상자::선택항목](#selectitem)|편집 가능한 목록 컨트롤 문자열을 선택합니다. ( `CVSListBoxBase::SelectItem`을 재정의합니다.)|
|[CVSListBox::셋아이템데이터](#setitemdata)|응용 프로그램별 32비트 값을 편집 가능한 목록 제어 항목과 연결합니다. ( `CVSListBoxBase::SetItemData`을 재정의합니다.)|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CVSList상자::겟리스트Hwnd](#getlisthwnd)|핸들을 현재 포함된 목록 보기 컨트롤로 반환합니다.|

## <a name="remarks"></a>설명

클래스는 `CVSListBox` 사용자가 목록 컨트롤에서 항목을 만들거나 수정, 삭제 또는 다시 정렬할 수 있도록 하는 편집 단추 집합을 제공합니다.

다음은 편집 가능한 목록 컨트롤의 그림입니다. "Item2"라는 제목의 두 번째 목록 항목은 편집을 위해 선택됩니다.

![CVSListBox 컨트롤](../../mfc/reference/media/cvslistbox.png "CVSListBox 컨트롤")

리소스 편집기를 사용하여 편집 가능한 목록 컨트롤을 추가하는 경우 편집기의 **도구 상자** 창에서 미리 정의된 편집 가능한 목록 컨트롤을 제공하지 않습니다. 대신 그룹 상자 컨트롤과 같은 정적 컨트롤을 **추가합니다.** 프레임워크는 정적 컨트롤을 자리 표시자로 사용하여 편집 가능한 목록 컨트롤의 크기와 위치를 지정합니다.

대화 상자 템플릿에서 편집 가능한 목록 컨트롤을 사용하려면 대화 상자 클래스에서 변수를 `CVSListBox` 선언합니다. 변수와 컨트롤 간의 데이터 교환을 지원하려면 대화 `DDX_Control` `DoDataExchange` 상자의 메서드에서 매크로 항목을 정의합니다. 기본적으로 편집 가능한 목록 컨트롤은 편집 버튼 없이 만들어집니다. 상속된 CVSListBoxBase::SetStandardButtons 메서드를 사용하여 편집 단추를 활성화합니다.

자세한 내용은 샘플 디렉토리, `New Controls` 샘플, Page3.cpp 및 Page3.h 파일을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxvslistbox.h

## <a name="cvslistboxadditem"></a><a name="additem"></a>CVSList상자::추가 항목

목록 컨트롤에 문자열을 추가합니다.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*스트리엑스*<br/>
【인】 문자열에 대한 참조입니다.

*dwData*<br/>
【인】 문자열과 연결된 응용 프로그램별 32비트 값입니다. 기본값은 0입니다.

*iIndex*<br/>
【인】 문자열을 보유할 위치의 0기반 인덱스입니다. *iIndex* 매개 변수가 -1이면 문자열이 목록의 끝에 추가됩니다. 기본값은 -1입니다.

### <a name="return-value"></a>Return Value

목록 컨트롤에서 문자열의 위치의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

[CVSListBox::GetItemData](#getitemdata) 메서드를 사용하여 *dwData* 매개 변수에 의해 지정된 값을 검색합니다. 이 값은 응용 프로그램별 정수이거나 다른 데이터에 대한 포인터일 수 있습니다.

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSList상자::CVSListBox

`CVSListBox` 개체를 생성합니다.

```
CVSListBox();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::편집항목

목록 컨트롤 항목의 텍스트에서 편집 작업을 시작합니다.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 제어 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

편집 작업이 성공적으로 시작되는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

사용자는 항목의 레이블을 두 번 클릭하거나 항목에 포커스가 있는 경우 **F2** 또는 **SPACEBAR** 키를 눌러 편집 작업을 시작합니다.

## <a name="cvslistboxgetcount"></a><a name="getcount"></a>CVSListBox::GetCount

편집 가능한 목록 컨트롤에서 문자열 수를 검색합니다.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Return Value

목록 컨트롤의 항목 수입니다.

### <a name="remarks"></a>설명

인덱스가 0을 기준으로 하기 때문에 개수가 마지막 항목의 인덱스 값보다 큰 개수입니다.

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSListBox::겟아이템데이터

편집 가능한 목록 제어 항목과 연결된 응용 프로그램별 32비트 값을 검색합니다.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 편집 가능한 목록 제어 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 항목과 연결된 32비트 값입니다.

### <a name="remarks"></a>설명

[CVSListBox::SetItemData](#setitemdata) 또는 [CVSListBox::AddItem](#additem) 메서드를 사용하여 32비트 값을 목록 제어 항목과 연결합니다. 이 값은 응용 프로그램별 정수이거나 다른 데이터에 대한 포인터일 수 있습니다.

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSListBox:::겟아이템텍스트

편집 가능한 목록 컨트롤 항목의 텍스트를 검색합니다.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 편집 가능한 목록 제어 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 항목의 텍스트를 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSList상자::겟리스트Hwnd

핸들을 현재 포함된 목록 보기 컨트롤로 반환합니다.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Return Value

포함된 목록 보기 컨트롤에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 클래스를 지 `CVSListBox` 원하는 포함 된 목록 보기 컨트롤에 핸들을 검색 합니다.

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a>CVSList상자::겟셀아이템

편집 가능한 목록 컨트롤에서 현재 선택한 항목의 0기준 인덱스를 검색합니다.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 현재 선택한 항목의 0기반 인덱스입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a>CVSList상자::제거항목

편집 가능한 목록 컨트롤에서 항목을 제거합니다.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 편집 가능한 목록 제어 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

TRUE 지정된 항목이 제거된 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a>CVSList상자::선택항목

편집 가능한 목록 컨트롤 문자열을 선택합니다.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>매개 변수

*iItem*<br/>
【인】 편집 가능한 목록 제어 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 항목을 선택 하 고 필요한 경우 항목을 뷰로 스크롤합니다.

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSListBox::셋아이템데이터

응용 프로그램별 32비트 값을 편집 가능한 목록 제어 항목과 연결합니다.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 편집 가능한 목록 제어 항목의 0기반 인덱스입니다.

*dwData*<br/>
【인】 32비트 값입니다. 이 값은 응용 프로그램별 정수이거나 다른 데이터에 대한 포인터일 수 있습니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
