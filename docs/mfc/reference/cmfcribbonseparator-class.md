---
title: CMFCRibbonSeparator 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: 41a958c78719f6aedf1cc02f8e3ff5a2dbbf0e1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368845"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator 클래스

리본 구분 기호를 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFC리본분리기::CMFC리본분리기](#cmfcribbonseparator)|`CMFCRibbonSeparator` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC리본분리기::애드토리스트박스](#addtolistbox)|**사용자 지정** 대화 상자의 명령 목록에 구분 기호를 **추가합니다.** [(CMFC 리본베이스요소 재정의::추가 목록 상자.)](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox)|
|`CMFCRibbonSeparator::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonSeparator::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|||
|-|-|
|속성|Description|
|[CMFC리본분리기::복사에서](#copyfrom)|다른 개체에서 구분 기호의 멤버 변수를 설정 하는 복사 메서드입니다.|
|[CMFC리본세파레이터::GetRegularSize](#getregularsize)|구분 기호의 크기를 반환합니다.|
|[CMFC리본분리기::이세파레이터](#isseparator)|이 구분 기호인지 여부를 나타냅니다.|
|[CMFC리본세파레이터::이스탭스탑](#istabstop)|탭 중지인지 여부를 나타냅니다.|
|[CMFC리본분리기::온드로우](#ondraw)|리본 또는 빠른 액세스 도구 모음에 구분 기호를 그리는 시스템에 의해 호출됩니다.|
|[CMFC리본세퍼레이터::온드로우온리스트](#ondrawonlist)|명령 목록에 구분 기호를 그리는 시스템에 의해 **호출됩니다.**|

## <a name="remarks"></a>설명

리본 구분 기호는 논리적으로 리본 요소를 구분하는 수직 또는 수평 선입니다. 구분 기호는 리본 컨트롤, 기본 응용 프로그램 메뉴, 리본 상태 표시줄 및 빠른 액세스 도구 모음에 그릴 수 있습니다.

응용 프로그램에서 구분 기호를 사용하려면 새 개체를 생성하고 다음과 같이 기본 응용 프로그램 메뉴에 추가합니다.

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

[CMFC리본 패널::분리자를 추가하여](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) 리본 패널에 구분 기호를 추가합니다. 구분 기호는 메서드에 `AddSeparator` 의해 내부적으로 할당되고 추가됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFC리본세퍼레이터](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFC리본분리기::애드토리스트박스

**사용자 지정** 대화 상자의 명령 목록에 구분 기호를 **추가합니다.**

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>매개 변수

*pWndListBox*<br/>
【인】 구분 기호가 추가되는 **명령** 목록에 대한 포인터입니다.

*bDeep*<br/>
【인】 무시.

### <a name="return-value"></a>Return Value

*pWndListBox에*의해 지정된 목록 상자의 문자열에 대한 0 기반 인덱스 .

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFC리본분리기::CMFC리본분리기

`CMFCRibbonSeparator` 개체를 생성합니다.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>매개 변수

*비쇼리즈*<br/>
【인】 TRUE이면 구분 기호가 수평인 경우 FALSE인 경우 구분 기호는 세로입니다.

### <a name="remarks"></a>설명

수평 구분 기호는 응용 프로그램 메뉴에 사용됩니다. 수직 구분 기호는 도구 모음에 사용됩니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonSeparator` 클래스의 개체를 생성 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFC리본분리기::복사에서

다른 개체에서 구분 기호의 멤버 변수를 설정 하는 복사 메서드입니다.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

*Src*<br/>
【인】 복사할 소스 리본 요소입니다.

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFC리본세파레이터::GetRegularSize

구분 기호의 크기를 반환합니다.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 콘텐츠에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 장치 컨텍스트에서 구분 기호의 크기입니다.

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFC리본분리기::이세파레이터

이 구분 기호인지 여부를 나타냅니다.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Return Value

이 클래스에 대 한 항상 TRUE입니다.

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFC리본세파레이터::이스탭스탑

탭 중지인지 여부를 나타냅니다.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Return Value

이 클래스에 대해 항상 FALSE입니다.

### <a name="remarks"></a>설명

리본 구분 기호는 탭 중지가 아닙니다.

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFC리본분리기::온드로우

리본 또는 빠른 액세스 도구 모음에 구분 기호를 그리는 시스템에 의해 호출됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFC리본세퍼레이터::온드로우온리스트

명령 목록에 구분 기호를 그리는 시스템에 의해 **호출됩니다.**

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pDC*|【인】 장치 컨텍스트에 대한 포인터입니다.|
|*strText*|【인】 목록에 텍스트가 표시됩니다.|
|*nTextOffset*|【인】 경계 사각형의 텍스트와 왼쪽 사이의 간격입니다.|
|*rect*|【인】 경계 사각형을 지정합니다.|
|*bIsSelected*|【인】 무시.|
|*b 강조 표시*|【인】 무시.|

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
