---
title: 코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: b49c1b6f21dfe5270e40649241812320303ad411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370910"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행

DDX 기능에 익숙한 경우 [멤버 추가 변수 마법사의](../ide/add-member-variable-wizard.md) Control 속성을 사용하여 형식 에 대한 안전한 액세스를 만들 수 있습니다. 이 방법은 코드 마법사없이 컨트롤을 만드는 것보다 쉽습니다.

컨트롤의 값에 대한 액세스만 하려는 경우 DDX가 컨트롤값을 제공합니다. 컨트롤의 값에 액세스하는 것 이상을 수행하려면 멤버 변수 추가 마법사를 사용하여 대화 상자 클래스에 적절한 클래스의 멤버 변수를 추가합니다. 이 멤버 변수를 Control 속성에 연결합니다.

멤버 변수에는 Value 속성 대신 Control 속성이 있을 수 있습니다. Value 속성은 컨트롤에서 반환되는 데이터 유형(예: 또는 `CString` **int)을**나타냅니다. Control 속성을 사용하면 형식이 MFC의 컨트롤 클래스 중 하나인 데이터 멤버를 통해 `CButton` `CEdit`컨트롤에 직접 액세스할 수 있습니다.

> [!NOTE]
> 지정된 컨트롤의 경우 원하는 경우 Value 속성과 Control 속성이 있는 하나의 멤버 변수가 여러 개 있는 여러 멤버 변수를 가질 수 있습니다. 컨트롤 또는 다른 창에 연결된 여러 개체가 메시지 맵에 모호해지므로 컨트롤에 매핑된 MFC 개체는 하나만 있을 수 있습니다.

이 개체를 사용하여 컨트롤 개체에 대한 멤버 함수를 호출할 수 있습니다. 이러한 호출은 대화 상자의 컨트롤에 영향을 미칩니다. 예를 들어 형식의 변수 *m_Checkbox*로 표시되는 확인란 `CButton`컨트롤의 경우 다음을 호출할 수 있습니다.

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

여기서 멤버 변수 *m_Checkbox* 코드 마법사 가 `GetMyCheckbox` 없는 컨트롤에 대한 형식 안전 액세스에 표시된 멤버 함수와 동일한 [용도로 사용됩니다.](../mfc/type-safe-access-to-controls-without-code-wizards.md) 확인란이 자동 확인란이 아닌 경우에도 단추를 클릭할 때 BN_CLICKED 제어 알림 메시지에 대한 대화 상자 클래스의 처리기가 필요합니다.

컨트롤에 대한 자세한 내용은 [컨트롤](../mfc/controls-mfc.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[대화 상자에서 컨트롤에 대한 형식 안전 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC에서 대화 상자를 통해 작업](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-without-code-wizards.md)
