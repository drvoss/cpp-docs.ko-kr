---
title: 새 컨트롤 클래스 기반의 변수 선언
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: 994f81524001a80d1cf0dd3783b9de742d61e84d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365841"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>새 컨트롤 클래스 기반의 변수 선언

MFC 컨트롤 클래스를 만든 후에는 변수를 기반으로 선언할 수 있습니다. 새 변수에 대한 컨텍스트를 제공하려면 대화 상자 편집기를 열고 재사용 가능한 컨트롤을 사용할 대화 상자를 편집해야 합니다. 또한 대화 상자에 연결된 클래스가 이미 있어야 합니다. 대화 상자 편집기 사용에 대한 자세한 내용은 [대화 상자 편집기](../../windows/dialog-editor.md)를 참조하십시오.

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>재사용 가능한 클래스를 기반으로 변수를 선언하려면

1. 대화 상자를 편집하는 동안 컨트롤 도구 모음에서 대화 상자로 새 컨트롤의 기본 클래스와 동일한 유형의 컨트롤을 끕을 끕입니다.

1. 삭제된 컨트롤 위에 마우스 포인터를 놓습니다.

1. CTRL 키를 누르는 동안 컨트롤을 두 번 클릭합니다.

   [멤버 가변 대화 상자가](../../ide/add-member-variable-wizard.md) 나타납니다.

1. **액세스** 상자에서 컨트롤에 대한 올바른 액세스를 선택합니다.

1. 컨트롤 **변수** 확인란을 클릭합니다.

1. 변수 **이름** 상자에 이름을 입력합니다.

1. **범주에서** **컨트롤을**클릭합니다.

1. 컨트롤 **ID** 목록에서 추가한 컨트롤을 선택합니다. **변수 유형** 목록에올바른 변수 유형이 표시되고 **컨트롤 유형** 상자에 올바른 컨트롤 유형이 표시되어야 합니다.

1. **주석** 상자에 코드에 표시할 주석을 추가합니다.

1. **확인**을 클릭합니다.

## <a name="see-also"></a>참고 항목

[함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[코드 마법사에서 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
