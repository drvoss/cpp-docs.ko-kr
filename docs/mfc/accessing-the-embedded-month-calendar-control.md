---
title: 포함된 MonthCalendar 컨트롤 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: 69270cc5663406f2c5d38ffccdbd35f39298a3d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354190"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>포함된 MonthCalendar 컨트롤 액세스

포함된 월 캘린더 제어 개체는 `CDateTimeCtrl` [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) 멤버 함수를 호출하여 개체에서 액세스할 수 있습니다.

> [!NOTE]
> 포함된 월 달력 컨트롤은 날짜 및 시간 선택기 컨트롤에 **DTS_UPDOWN** 스타일 집합이 없는 경우에만 사용됩니다.

이 기능은 포함된 컨트롤이 표시되기 전에 특정 특성을 수정하려는 경우에 유용합니다. 이렇게 하려면 **DTN_DROPDOWN** 알림을 처리하고, 월 캘린더 [컨트롤(CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)사용)을 검색하고 수정합니다. 안타깝게도 월 달력 컨트롤은 영구적이지 않습니다.

즉, 사용자가 월 캘린더 컨트롤의 표시를 요청하면 새 월 캘린더 컨트롤이 **만들어집니다(DTN_DROPDOWN** 알림 이전). 사용자가 해제하면 컨트롤이 DTN_CLOSEUP **알림** 후 소멸됩니다. 즉, 포함된 컨트롤이 표시되기 전에 수정한 모든 특성은 포함된 컨트롤을 해제할 때 손실됩니다.

다음 예제에서는 **DTN_DROPDOWN** 알림에 대 한 처리기를 사용 하 여이 절차를 보여 줍니다. 코드는 [SetMonthCalColor를](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)호출하여 월 달력 컨트롤의 배경 색을 회색으로 변경합니다. 코드는 다음과 같습니다.

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

앞에서 설명했듯이 포함된 컨트롤이 해제될 때 두 가지 예외를 제외하고 월 달력 컨트롤의 속성에 대한 모든 수정 사항이 손실됩니다. 첫 번째 예외인 월 달력 컨트롤의 색상은 이미 논의되었습니다. 두 번째 예외는 월 달력 컨트롤에서 사용하는 글꼴입니다. [CDateTimeCtrl::SetMonthCalFont를](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont)호출하여 기본 글꼴을 수정할 수 있습니다. 다음 예제(날짜 `m_dtPicker` 및 시간 제어 개체는 위치)에서는 한 가지 가능한 메서드를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

에 대한 호출을 `CDateTimeCtrl::SetMonthCalFont`통해 글꼴이 변경되면 다음에 한 달 달력이 표시될 때 새 글꼴이 저장되고 사용됩니다.

## <a name="see-also"></a>참고 항목

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
