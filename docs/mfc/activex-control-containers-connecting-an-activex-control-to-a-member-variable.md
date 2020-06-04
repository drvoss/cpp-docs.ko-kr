---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤을 멤버 변수에 연결'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
ms.openlocfilehash: 620a9ec58b3a5a8fcdac63626b81fbc4620de399
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371614"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤을 멤버 변수에 연결

컨트롤 컨테이너 응용 프로그램 내에서 ActiveX 컨트롤에 액세스하는 가장 쉬운 방법은 ActiveX 컨트롤을 컨트롤을 포함하는 대화 상자 클래스의 멤버 변수와 연결하는 것입니다.

> [!NOTE]
> 이것은 컨테이너 클래스 내에서 포함된 컨트롤에 액세스하는 유일한 방법은 아니지만 이 문서의 목적상 충분합니다.

### <a name="adding-a-member-variable-to-the-dialog-class"></a>대화 상자 클래스에 멤버 변수 추가

1. 클래스 보기에서 기본 대화 상자 클래스를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다. `CContainerDlg`)을 입력합니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **변수 추가**를 클릭합니다.

1. 멤버 변수 추가 마법사에서 **컨트롤 변수를**클릭합니다.

1. 컨트롤 **ID** 목록 상자에서 포함된 ActiveX 컨트롤의 제어 ID를 선택합니다. `IDC_CIRCCTRL1`)을 입력합니다.

1. 변수 **이름** 상자에 이름을 입력합니다.

   예를 들어, *m_circctl*.

1. **완료를** 클릭하여 선택 사항을 수락하고 멤버 추가 변수 마법사를 종료합니다.

## <a name="see-also"></a>참고 항목

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
