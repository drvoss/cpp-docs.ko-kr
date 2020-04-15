---
title: 모양, ATL 컨트롤 마법사
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 3484fb5d0f919af0dfd18b584e96d4675e2baea8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319404"
---
# <a name="appearance-atl-control-wizard"></a>모양, ATL 컨트롤 마법사

마법사의 이 페이지를 사용하여 컨트롤에 대한 추가 사용자 요소 옵션을 식별합니다. 이 페이지는 [옵션, ATL 제어 마법사](../../atl/reference/options-atl-control-wizard.md) 페이지의 **컨트롤 유형에서** **표준 컨트롤로** 식별된 컨트롤에 사용할 수 있습니다.

## <a name="uielement-list"></a>UIElement 목록

- **상태 보기**

   컨테이너 내에서 컨트롤의 모양을 설정합니다.

  - **불투명**: [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) 열거판에서 VIEWSTATUS_OPAQUE 비트를 설정하고 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) 메서드에 전달된 전체 컨트롤 사각형을 그립니다. 컨트롤이 완전히 불투명하게 나타나고 컨테이너가 컨트롤 경계 뒤에 표시되지 않습니다.

      이 설정을 사용하면 컨테이너가 컨트롤을 더 빠르게 그릴 수 있습니다. 이 옵션을 선택하지 않으면 컨트롤에 투명 부품이 포함될 수 있습니다.

      불투명 컨트롤만 단단한 배경을 가질 수 있습니다.

  - **솔리드 배경**: 뷰상태 열거에서 VIEWSTATUS_SOLIDBKGND 비트를 설정합니다. 컨트롤의 배경은 패턴이 없는 단색으로 나타납니다.

      이 옵션은 **불투명** 옵션도 선택한 경우에만 사용할 수 있습니다.

- **에 따라 컨트롤 추가**

   컨트롤을 구현하는 클래스에 [CContainedWindow](ccontainedwindowt-class.md) 데이터 멤버를 추가하여 Windows 컨트롤 형식을 기반으로 컨트롤을 설정합니다. 또한 컨트롤에 대 한 Windows 메시지를 처리 하는 메시지 맵 및 메시지 처리기 기능을 추가 합니다. 목록에서 만들려는 Windows 컨트롤 유형(있는 경우)을 선택합니다.

  - **단추**

  - **ListBox**

  - **SysAnimate32**

  - **SysListView32**

  - **ComboBox**

  - **Richedit**

  - **SysDateTimePick32**

  - **SysMonthCal32**

  - **ComboBoxEx32**

  - **ScrollBar**

  - **SysHeader32**

  - **SysTabControl32**

  - **편집**

  - **정적**

  - **SysIPAddress32**

  - **SysTreeView32**

- **기타 상태**

   컨트롤에 대한 추가 모양 및 동작 옵션을 설정합니다.

  - **런타임시 보이지 않음**: 컨트롤을 런타임에 보이지 않게 설정합니다. 보이지 않는 컨트롤을 사용하여 시간 간격으로 이벤트를 발생시등 백그라운드에서 작업을 수행할 수 있습니다.

  - **단추와 같은 역할**: [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) 열거형의 OLEMISC_ACTSLIKEBUTTON 비트를 설정하여 컨트롤이 단추처럼 작동하도록 합니다. 컨테이너가 컨트롤의 클라이언트 사이트를 기본 단추로 표시한 경우 이 옵션을 선택하면 단추 컨트롤이 두꺼운 프레임으로 자신을 그려 기본 단추로 표시할 수 있습니다. 자세한 내용은 [CComControlBase::GetAmbientDisplayADefault를](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) 참조하십시오.

  - **레이블과 같은 작동**: OLEMISC 열거형에서 OLEMISC_ACTSLIKELABEL 비트를 설정하여 컨트롤이 컨테이너의 기본 레이블을 대체할 수 있도록 합니다. 컨테이너는 이 플래그로 수행할 작업을 결정합니다( 이 경우).

- **기타**

   컨트롤에 대한 추가 동작 옵션을 설정합니다.

  - **정규화된 DC**: 자체 그리기를 호출할 때 정규화된 장치 컨텍스트를 만들도록 컨트롤을 설정합니다. 이 작업은 컨트롤의 모양을 표준화하지만 그리기의 효율성이 낮습니다.

  - **창만**: 컨트롤이 창이 없음을 지정합니다. 이 옵션을 선택하지 않으면 창없는 개체를 지원하는 컨테이너에서 컨트롤이 자동으로 창없는 지이고 창없는 개체를 지원하지 않는 컨테이너에서 자동으로 창이 지정됩니다. 이 옵션을 선택하면 창없는 개체를 지원하는 컨테이너에서도 컨트롤이 창을 강제로 창을 만듭니다.

  - **삽입 가능**: Word 및 Excel과 같은 응용 프로그램의 **개체 삽입** 대화 상자에 컨트롤이 표시되도록 이 옵션을 선택합니다. 그런 다음 이 대화 상자를 통해 포함된 개체를 지원하는 모든 응용 프로그램에서 컨트롤을 삽입할 수 있습니다.

## <a name="see-also"></a>참고 항목

[ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT 샘플: 표준 Windows 컨트롤을 수퍼클래스](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
