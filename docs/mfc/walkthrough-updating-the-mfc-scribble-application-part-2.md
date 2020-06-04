---
title: '연습: MFC 자유 곡선 애플리케이션 업데이트(파트 2)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: bc204a152168accf3731eede8ca9ef960ab121d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360222"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>연습: MFC 자유 곡선 애플리케이션 업데이트(파트 2)

이 연습의 [1부에서는](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) 클래식 스크리블 응용 프로그램에 Office 유창한 리본을 추가하는 방법을 보여 주어 도보였습니다. 이 부분에서는 메뉴및 명령 대신 사용자가 사용할 수 있는 리본 패널과 컨트롤을 추가하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>사전 요구 사항

[Visual C++ 샘플](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a>섹션

이 연습 부분에는 다음 단원이 있습니다.

- [리본에 새 패널 추가](#addnewpanel)

- [리본에 도움말 패널 추가](#addhelppanel)

- [리본에 펜 패널 추가](#addpenpanel)

- [리본에 색상 단추 추가](#addcolorbutton)

- [문서 클래스에 색상 멤버 추가](#addcolormember)

- [펜 초기화 및 환경 설정 저장](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a>리본에 새 패널 추가

이 단계는 도구 모음및 상태 표시줄의 가시성을 제어하는 두 개의 확인란이 포함된 **보기** 패널과 MDI(다중 문서 인터페이스) 창의 생성 및 배열을 제어하는 수직 방향 분할 단추를 포함하는 **창** 패널을 추가하는 방법을 보여 줍니다.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>리본 막대에 보기 패널 및 창 패널을 추가하려면

1. 상태 표시줄과 도구 모음을 전환하는 두 개의 확인란이 있는 패널을 `View`만듭니다.

   1. 도구 **상자에서** **패널을** **홈** 범주로 드래그합니다. 그런 다음 두 **개의 확인란을** 패널로 드래그합니다.

   1. 패널을 클릭하여 해당 속성을 수정합니다. **캡션을** `View`로 변경합니다.

   1. 첫 번째 확인란을 클릭하여 해당 속성을 수정합니다. **ID를** `ID_VIEW_TOOLBAR` 로 변경하고 `Toolbar` **캡션을** 로 변경합니다.

   1. 두 번째 확인란을 클릭하여 해당 속성을 수정합니다. **ID를** `ID_VIEW_STATUS_BAR` 로 변경하고 `Status Bar` **캡션을** 로 변경합니다.

1. 분할 단추가 `Window` 있는 패널을 만듭니다. 사용자가 분할 단추를 클릭하면 바로 가기 메뉴에 Scribble 응용 프로그램에 이미 정의된 세 가지 명령이 표시됩니다.

   1. 도구 **상자에서** **패널을** **홈** 범주로 드래그합니다. 그런 다음 **단추를** 패널로 끕습니다.

   1. 패널을 클릭하여 해당 속성을 수정합니다. **캡션을** `Window`로 변경합니다.

   1. 이 단추를 클릭합니다. **캡션을** `Windows`에서 **키로** `w`변경하고 큰 `1`이미지 **인덱스를** 에서 로 변경하고 모드를 로 **분할합니다.** `False` 그런 다음 **메뉴 항목** 옆의 타원(... ) 을 클릭하여 항목 **편집기** 대화 상자를 엽니다.**...**

   1. 세 번 **추가를** 클릭하여 세 개의 단추를 추가합니다.

   1. 첫 번째 단추를 클릭한 `New Window`다음 **캡션을** 로 및 **ID를** 로 변경합니다. `ID_WINDOW_NEW`

   1. 두 번째 단추를 클릭한 `Cascade`다음 **캡션을** 로 및 **ID를** 로 변경합니다. `ID_WINDOW_CASCADE`

   1. 세 번째 단추를 클릭한 `Tile`다음 **캡션을** 로 및 **ID를** 로 변경합니다. `ID_WINDOW_TILE_HORZ`

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. **보기** 및 **창** 패널이 표시되어야 합니다. 단추를 클릭하여 올바르게 작동하는지 확인합니다.

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a>리본에 도움말 패널 추가

이제 Scribble 응용 프로그램에 정의된 두 메뉴 항목을 **도움말 항목** 및 **스크리블 정보라는**이름의 리본 단추에 할당할 수 있습니다. 단추는 **도움말**입니다라는 새 패널에 추가됩니다.

### <a name="to-add-a-help-panel"></a>도움말 패널을 추가하려면

1. 도구 **상자에서** **패널을** **홈** 범주로 드래그합니다. 그런 다음 두 개의 단추를 패널로 **끕습니다.**

1. 패널을 클릭하여 해당 속성을 수정합니다. **캡션을** `Help`로 변경합니다.

1. 첫 번째 단추를 클릭합니다. **캡션을** `Help Topics`로 변경하고 `ID_HELP_FINDER` **ID를** 로 변경합니다.

1. 두 번째 단추를 클릭합니다. **캡션을** `About Scribble...`로 변경하고 `ID_APP_ABOUT` **ID를** 로 변경합니다.

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 두 개의 리본 버튼이 포함된 **도움말** 패널이 표시되어야 합니다.

   > [!IMPORTANT]
   > **도움말 항목** 단추를 클릭하면 Scribble 응용 프로그램은 .chmyour_project_name라는 압축된 *your_project_name*HTML(.chm) 도움말 파일을 엽니다. 따라서 프로젝트의 이름이 Scribble이 아닌 경우 도움말 파일의 이름을 프로젝트 이름으로 바여야 합니다.

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a>리본에 펜 패널 추가

이제 패널을 추가하여 펜의 두께와 색상을 제어하는 단추를 표시합니다. 이 패널에는 굵게 펜과 얇은 펜 사이를 전환하는 확인란이 포함되어 있습니다. 해당 기능은 낙서 응용 프로그램의 **굵은 선** 메뉴 항목과 유사합니다.

원래 낙서 응용 프로그램을 사용하면 사용자가 메뉴에서 펜 너비를 클릭할 때 나타나는 대화 상자에서 **펜 너비를** 선택할 수 있습니다. 리본 막대에는 새 컨트롤을 위한 충분한 공간이 있으므로 리본에 두 개의 콤보 상자를 사용하여 대화 상자를 바꿀 수 있습니다. 하나의 콤보 박스는 얇은 펜의 폭을 조정하고 다른 콤보 상자는 두꺼운 펜의 너비를 조정합니다.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>리본에 펜 패널과 콤보 상자를 추가하려면

1. 도구 **상자에서** **패널을** **홈** 범주로 드래그합니다. 그런 다음 **확인란과** 두 개의 콤보 상자를 패널로 **드래그합니다.**

1. 패널을 클릭하여 해당 속성을 수정합니다. **캡션을** `Pen`로 변경합니다.

1. 확인란을 선택합니다. **캡션을** `Use Thick`로 변경하고 `ID_PEN_THICK_OR_THIN` **ID를** 로 변경합니다.

1. 첫 번째 콤보 상자를 클릭합니다. **캡션을** `Thin Pen` **에서** 로 `ID_PEN_THIN_WIDTH`변경하고 `Drop List`의 경우 를 **'를 입력합니다.'** 및 **에 대한** `2` **텍스트** `1;2;3;4;5;6;7;8;9;`

1. 두 번째 콤보 상자를 클릭합니다. **캡션을** `Thick Pen` **에서** 로 `ID_PEN_THICK_WIDTH`변경하고 `Drop List`의 경우 를 **'를 입력합니다.'** 및 **에 대한** `5` **텍스트** `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`

1. 새 콤보 상자는 기존 메뉴 항목과 일치하지 않으므로 모든 펜 옵션에 대해 메뉴 항목을 만들어야 합니다.

   1. 리소스 **보기** 창에서 **IDR_SCRIBBTYPE** 메뉴 리소스를 엽니다.

   1. **펜** 메뉴를 열려면 펜을 클릭합니다. 그런 다음 여기 `Thi&n Pen`를 입력하고 입력을 **클릭합니다.**

   1. **속성** 창을 열기 위해 입력한 텍스트를 마우스 오른쪽 단추로 클릭한 `ID_PEN_THIN_WIDTH`다음 ID 속성을 로 변경합니다.

   1. 모든 펜 메뉴 항목에 대한 이벤트 처리기를 만듭니다. 만든 Thi **&n 펜** 메뉴 항목을 마우스 오른쪽 단추로 클릭한 다음 **이벤트 처리기 추가를**클릭합니다. **이벤트 처리기 마법사가** 표시됩니다.

   1. 마법사의 **클래스 목록** 상자에서 **CScribbleDoc을** 선택한 다음 추가 및 **편집을**클릭합니다. 명령은 .라는 `CScribbleDoc::OnPenThinWidth`이벤트 처리기를 만듭니다.

   1. 다음 코드를 `CScribbleDoc::OnPenThinWidth`에 추가합니다.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 다음으로 두꺼운 펜에 대한 메뉴 항목 및 이벤트 처리기를 만듭니다.

   1. 리소스 **보기** 창에서 **IDR_SCRIBBTYPE** 메뉴 리소스를 엽니다.

   1. **펜** 메뉴를 열려면 펜을 클릭합니다. 그런 다음 여기 `Thic&k Pen`를 입력하고 입력을 **클릭합니다.**

   1. **속성** 창을 표시하려면 입력한 텍스트를 마우스 오른쪽 단추로 클릭합니다. ID 속성을 로 `ID_PEN_THICK_WIDTH`변경합니다.

   1. 만든 **굵은 펜** 메뉴 항목을 마우스 오른쪽 단추로 클릭한 다음 **이벤트 처리기 추가를**클릭합니다. **이벤트 처리기 마법사가** 표시됩니다.

   1. 마법사의 **클래스 목록** 상자에서 **CScribbleDoc을** 선택한 다음 추가 및 **편집을**클릭합니다. 명령은 .라는 `CScribbleDoc::OnPenThickWidth`이벤트 처리기를 만듭니다.

   1. 다음 코드를 `CScribbleDoc::OnPenThickWidth`에 추가합니다.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 새 단추와 콤보 상자가 표시되어야 합니다. 다른 펜 너비를 사용하여 낙서해 보십시오.

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a>펜 패널에 색상 단추 추가

그런 다음 사용자가 색상으로 낙서할 수 있는 [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) 개체를 추가합니다.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>펜 패널에 색상 단추를 추가하려면

1. 색상 단추를 추가하기 전에 색상 단추에 대한 메뉴 항목을 만듭니다. 리소스 **보기** 창에서 **IDR_SCRIBBTYPE** 메뉴 리소스를 엽니다. **펜** 메뉴를 클릭하여 펜 메뉴를 엽니다. 그런 다음 여기 `&Color`를 입력하고 입력을 **클릭합니다.** **속성** 창을 표시하려면 입력한 텍스트를 마우스 오른쪽 단추로 클릭합니다. ID를 `ID_PEN_COLOR`로 변경합니다.

1. 이제 색상 단추를 추가합니다. 도구 **상자에서**색상 **단추를** **펜** 패널로 드래그합니다.

1. 색상 단추를 클릭합니다. **캡션을** `Color` **에서** 로 `ID_PEN_COLOR`변경하고 의 `True`경우 를 " 에서 단순 `False` **보기** 로 , 큰 이미지 **인덱스를** 에서 로, `1`모드를 로 **분할합니다.**

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 새 색상 버튼이 **펜** 패널에 표시되어야 합니다. 그러나 아직 이벤트 처리기가 없기 때문에 사용할 수 없습니다. 다음 단계에서는 색상 단추에 대한 이벤트 처리기를 추가하는 방법을 보여 주며,

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a>문서 클래스에 색상 멤버 추가

원래 낙서 응용 프로그램에는 컬러 펜이 없으므로 구현을 작성해야 합니다. 문서의 펜 색상을 저장하려면 문서 클래스에 새 멤버를 `CscribbleDoc`추가합니다.

### <a name="to-add-a-color-member-to-the-document-class"></a>문서 클래스에 색상 멤버를 추가하려면

1. `CScribbleDoc` scribdoc.h에서, 수업에서, 섹션을 `// Attributes` 찾을 수 있습니다. 데이터 멤버 정의 후 다음 코드 `m_nThickWidth` 줄을 추가합니다.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. 모든 문서에는 사용자가 이미 그린 스톡 목록이 포함되어 있습니다. 모든 스트로크는 개체에 `CStroke` 의해 정의됩니다. 클래스에는 `CStroke` 펜 색상에 대한 정보가 포함되어 있지 않으므로 클래스를 수정해야 합니다. scribdoc.h에서 `CStroke` 클래스에서 `m_nPenWidth` 데이터 멤버의 정의 다음에 다음 코드 줄을 추가합니다.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. scribdoc.h에서 매개 변수가 너비와 색상을 지정하는 새 `CStroke` 생성자도 추가합니다. 문 다음에 다음 코드 `CStroke(UINT nPenWidth);` 줄을 추가합니다.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. scribdoc.cpp에서 새 `CStroke` 생성자의 구현을 추가합니다. `CStroke::CStroke(UINT nPenWidth)` 생성자 구현 후 다음 코드를 추가합니다.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. 메서드의 두 번째 `CStroke::DrawStroke` 줄을 다음과 같이 변경합니다.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. 문서 클래스의 기본 펜 색상을 설정합니다. scribdoc.cpp에서 문 다음에 다음 `CScribbleDoc::InitDocument`줄을 `m_nThickWidth = 5;` 추가합니다.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. scribdoc.cpp에서 `CScribbleDoc::NewStroke` 메서드의 첫 번째 줄을 다음으로 변경합니다.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. `CScribbleDoc::ReplacePen` 메서드의 마지막 줄을 다음으로 변경합니다.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. 이전 단계에서 `m_penColor` 멤버를 추가했습니다. 이제 멤버를 설정하는 색상 단추에 대한 이벤트 처리기를 만듭니다.

   1. 리소스 **보기** 창에서 IDR_SCRIBBTYPE 메뉴 리소스를 엽니다.

   1. **색상** 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 **이벤트 처리기 추가를**클릭합니다. **이벤트 처리기 마법사가** 나타납니다.

   1. 마법사의 **클래스 목록** 상자에서 **CScribbleDoc을** 선택한 다음 추가 및 **편집** 단추를 클릭합니다. 명령이벤트 처리기 스텁을 `CScribbleDoc::OnPenColor` 만듭니다.

1. 이벤트 처리기의 `CScribbleDoc::OnPenColor` 스텁을 다음 코드로 바꿉니다.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 이제 색상 버튼을 누르고 펜의 색상을 변경할 수 있습니다.

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a>펜 초기화 및 환경 설정 저장

다음으로 펜의 색상과 너비를 초기화합니다. 마지막으로 파일에서 색상 도면을 저장하고 로드합니다.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>리본 막대에서 컨트롤을 초기화하려면

1. 리본 막대의 펜을 초기화합니다.

   명령문 다음에 scribdoc.cpp에 `CScribbleDoc::InitDocument` 다음 코드를 추가합니다. `m_sizeDoc = CSize(200,200)`

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. 컬러 드로잉을 파일에 저장합니다. `CStroke::Serialize` 명령문 다음에 scribdoc.cpp에 다음 문을 추가합니다. `ar << (WORD)m_nPenWidth;`

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. 마지막으로 파일에서 색상 드로잉을 로드합니다. `CStroke::Serialize` 메서드에서 문 다음에 다음 코드 줄을 `m_nPenWidth = w;` 추가합니다.

   ```cpp
   ar >> m_penColor;
   ```

1. 이제 색상을 낙서하고 도면을 파일에 저장합니다.

## <a name="conclusion"></a>결론

MFC 낙서 응용 프로그램을 업데이트했습니다. 기존 응용 프로그램을 수정할 때 이 연습을 지침으로 사용합니다.

## <a name="see-also"></a>참고 항목

[연습](../mfc/walkthroughs-mfc.md)<br/>
[연습: MFC 자유 곡선 애플리케이션 업데이트(1부)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
