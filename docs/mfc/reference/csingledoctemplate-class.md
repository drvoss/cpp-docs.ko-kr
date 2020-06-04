---
title: CSingleDocTemplate 클래스
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 5a014b35a6cd2d12367e190e4d6dd689e28eae66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318342"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate 클래스

SDI(단일 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSingleDoc템플릿::CSingleDocTemplate](#csingledoctemplate)|`CSingleDocTemplate` 개체를 생성합니다.|

## <a name="remarks"></a>설명

SDI 응용 프로그램은 주 프레임 창을 사용하여 문서를 표시합니다. 한 번에 하나의 문서만 열 수 있습니다.

문서 템플릿은 세 가지 유형의 클래스 간의 관계를 정의합니다.

- 에서 파생되는 문서 클래스입니다. `CDocument`

- 위에 나열된 문서 클래스의 데이터를 표시하는 뷰 클래스입니다. 에서 이 클래스를 `CView` `CScrollView` `CFormView` `CEditView`파생할 수 있습니다. (직접 사용할 `CEditView` 수도 있습니다.)

- 뷰를 포함하는 프레임 창 클래스입니다. SDI 문서 템플릿의 경우 에서 이 `CFrameWnd`클래스를 파생할 수 있습니다. 주 프레임 창의 동작을 사용자 지정할 필요가 없는 `CFrameWnd` 경우 고유한 클래스를 파생하지 않고 직접 사용할 수 있습니다.

SDI 응용 프로그램은 일반적으로 한 가지 유형의 `CSingleDocTemplate` 문서를 지원하므로 개체가 하나만 있습니다. 한 번에 하나의 문서만 열 수 있습니다.

생성자 이외의 멤버 함수를 `CSingleDocTemplate` 호출할 필요가 없습니다. 프레임워크는 개체를 내부적으로 처리합니다. `CSingleDocTemplate`

사용에 `CSingleDocTemplate`대한 자세한 내용은 [문서 템플릿 및 문서/보기 작성 프로세스를](../../mfc/document-templates-and-the-document-view-creation-process.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a>CSingleDoc템플릿::CSingleDocTemplate

`CSingleDocTemplate` 개체를 생성합니다.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
문서 유형에 사용된 리소스의 ID를 지정합니다. 여기에는 메뉴, 아이콘, 액셀러레이터 테이블 및 문자열 리소스가 포함될 수 있습니다.

문자열 리소스는 '\n' 문자로 구분된 최대 7개의 하위 문자열로 구성됩니다(하위 문자열이 포함되지 않은 경우 '\n' 문자는 자리 표시자로 필요하지만 후행 '\n' 문자는 필요하지 않습니다.) 이러한 하위 문자열은 문서 형식을 설명합니다. 하위 문자열에 대한 자세한 내용은 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)을 참조하십시오. 이 문자열 리소스는 응용 프로그램의 리소스 파일에서 찾을 수 있습니다. 다음은 그 예입니다.

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

문자열 편집기에서 이 문자열을 편집할 수 있습니다. 전체 문자열은 7개의 개별 항목이 아니라 문자열 편집기의 단일 항목으로 나타납니다.

이러한 리소스 유형에 대한 자세한 내용은 [문자열 편집기](../../windows/string-editor.md)를 참조하십시오.

*pDoc클래스*<br/>
문서 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CDocument`문서를 나타내기 위해 정의한 -파생 클래스입니다.

*pFrame클래스*<br/>
프레임 창 `CRuntimeClass` 클래스의 개체를 가리킵니다. 이 클래스는 `CFrameWnd`-derived 클래스일 수도 `CFrameWnd` 있고 주 프레임 창에 대한 기본 동작을 원하는 경우 그 자체일 수도 있습니다.

*pView클래스*<br/>
뷰 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CView`문서를 표시하도록 정의하는 -derive 클래스입니다.

### <a name="remarks"></a>설명

개체를 `CSingleDocTemplate` 동적으로 할당하고 응용 `CWinApp::AddDocTemplate` 프로그램 `InitInstance` 클래스의 멤버 함수에서 전달합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 도크툴](../../overview/visual-cpp-samples.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate 클래스](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
