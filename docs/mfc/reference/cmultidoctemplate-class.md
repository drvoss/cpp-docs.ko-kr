---
title: CMultiDocTemplate 클래스
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 3b3f239b05b1cf7661929333e2d616acce6bedb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319738"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate 클래스

MDI(다중 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` 개체를 생성합니다.|

## <a name="remarks"></a>설명

MDI 응용 프로그램은 주 프레임 창을 사용자가 문서를 표시하는 0개 이상의 문서 프레임 창을 열 수 있는 작업 영역으로 사용합니다. MDI에 대한 자세한 설명은 *소프트웨어 설계에 대한 Windows 인터페이스 지침을*참조하십시오.

문서 템플릿은 세 가지 유형의 클래스 간의 관계를 정의합니다.

- [CDocument에서](../../mfc/reference/cdocument-class.md)파생된 문서 클래스입니다.

- 위에 나열된 문서 클래스의 데이터를 표시하는 뷰 클래스입니다. [CView](../../mfc/reference/cview-class.md)에서 `CScrollView` `CFormView` `CEditView`이 클래스를 파생할 수 있습니다. (직접 사용할 `CEditView` 수도 있습니다.)

- 뷰를 포함하는 프레임 창 클래스입니다. MDI 문서 템플릿의 경우 `CMDIChildWnd`에서 이 클래스를 파생하거나 문서 프레임 창의 동작을 사용자 지정할 필요가 없는 경우 자신의 클래스를 파생하지 않고 [CMDIChildWnd를](../../mfc/reference/cmdichildwnd-class.md) 직접 사용할 수 있습니다.

MDI 응용 프로그램은 둘 이상의 문서 유형을 지원할 수 있으며 서로 다른 유형의 문서를 동시에 열 수 있습니다. 응용 프로그램에는 지원하는 각 문서 유형에 대해 하나의 문서 템플릿이 있습니다. 예를 들어 MDI 응용 프로그램이 스프레드시트와 텍스트 문서를 모두 `CMultiDocTemplate` 지원하는 경우 응용 프로그램에두 개의 개체가 있습니다.

응용 프로그램은 사용자가 새 문서를 만들 때 문서 템플릿을 사용합니다. 응용 프로그램이 둘 이상의 문서 유형을 지원하는 경우 프레임워크는 문서 템플릿에서 지원되는 문서 형식의 이름을 가져옵니다. 사용자가 문서 형식을 선택하면 응용 프로그램은 문서 클래스 개체, 프레임 창 개체 및 뷰 개체를 만들어 서로 연결합니다.

생성자 이외의 멤버 함수를 `CMultiDocTemplate` 호출할 필요가 없습니다. 프레임워크는 개체를 내부적으로 처리합니다. `CMultiDocTemplate`

자세한 `CMultiDocTemplate`내용은 문서 [템플릿 및 문서/보기 작성 프로세스를](../../mfc/document-templates-and-the-document-view-creation-process.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate

`CMultiDocTemplate` 개체를 생성합니다.

```
CMultiDocTemplate(
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
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

문자열은 '\n' 문자로 시작합니다. 이는 첫 번째 하위 문자열이 MDI 응용 프로그램에 사용되지 않으므로 포함되지 않기 때문입니다. 문자열 편집기에서 이 문자열을 편집할 수 있습니다. 전체 문자열은 7개의 개별 항목이 아니라 문자열 편집기의 단일 항목으로 나타납니다.

이러한 리소스 유형에 대한 자세한 내용은 [리소스 편집기](../../windows/resource-editors.md)를 참조하십시오.

*pDoc클래스*<br/>
문서 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CDocument`문서를 나타내기 위해 정의한 -파생 클래스입니다.

*pFrame클래스*<br/>
프레임 창 `CRuntimeClass` 클래스의 개체를 가리킵니다. 이 클래스는 `CMDIChildWnd`-derived 클래스일 수도 `CMDIChildWnd` 있고 문서 프레임 창에 대한 기본 동작을 원하는 경우 그 자체일 수도 있습니다.

*pView클래스*<br/>
뷰 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CView`문서를 표시하도록 정의하는 -derive 클래스입니다.

### <a name="remarks"></a>설명

응용 프로그램이 지원하는 `CMultiDocTemplate` 각 문서 형식에 대해 하나의 개체를 `CWinApp::AddDocTemplate` 동적으로 할당하고 각 개체를 응용 프로그램 클래스의 `InitInstance` 멤버 함수에서 전달합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

다음은 두 번째 예제입니다.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate 클래스](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
