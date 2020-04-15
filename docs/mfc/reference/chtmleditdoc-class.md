---
title: CHtmlEditDoc 클래스
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: 8b500f651da1a73040fdb0469f2f023babe25e85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352168"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc 클래스

[CHtmlEditView를](../../mfc/reference/chtmleditview-class.md)사용하면 MFC 문서 보기 아키텍처의 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|`CHtmlEditDoc` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|이 문서에 `CHtmlEditView` 연결된 개체를 검색합니다.|
|[CHtmlEditDoc::수정되었습니다.](#ismodified)|연결된 뷰의 WebBrowser 컨트롤에 사용자가 수정한 문서가 포함되어 있는지 여부를 반환합니다.|
|[CHtmlEditDoc::오픈URL](#openurl)|URL을 엽니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc

`CHtmlEditDoc` 개체를 생성합니다.

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a>CHtmlEditDoc::GetView

이 문서에 첨부된 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) 개체를 검색합니다.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Return Value

문서의 개체에 대한 `CHtmlEditView` 포인터를 반환합니다.

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a>CHtmlEditDoc::수정되었습니다.

연결된 뷰의 WebBrowser 컨트롤에 사용자가 수정한 문서가 포함되어 있는지 여부를 반환합니다.

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a>CHtmlEditDoc::오픈URL

URL을 엽니다.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
열려는 URL입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="see-also"></a>참고 항목

[HTML편집 샘플](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
