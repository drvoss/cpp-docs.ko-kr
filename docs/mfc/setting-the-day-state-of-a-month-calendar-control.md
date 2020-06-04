---
title: MonthCalendar 컨트롤의 일 상태 설정
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: 9892f2d853687787dd76428fc9bc95f3a4f74565
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365422"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>MonthCalendar 컨트롤의 일 상태 설정

월 달력 컨트롤의 특성 중 하나는 매월 각 일에 대해 컨트롤의 일 상태라고 하는 정보를 저장하는 기능입니다. 이 정보는 현재 표시된 월의 특정 날짜를 강조하는 데 사용됩니다.

> [!NOTE]
> 객체에는 `CMonthCalCtrl` 일 상태 정보를 표시할 MCS_DAYSTATE 스타일이 있어야 합니다.

일 상태 정보는 32비트 데이터 유형인 **월데이스테이트로**표현됩니다. **월데이스테이트** 비트 필드(1~31)의 각 비트는 한 달의 일 의 상태를 나타냅니다. 비트가 켜지면 해당 날이 굵게 표시됩니다. 그렇지 않으면 강조없이 표시됩니다.

월 달력 컨트롤의 일 상태를 설정 하는 두 가지 방법이 있습니다: 명시적으로 [CMonthCalCtrl::SetDayState에](../mfc/reference/cmonthcalctrl-class.md#setdaystate) 대 한 호출 또는 MCN_GETDAYSTATE 알림 메시지를 처리 하 여.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지 처리

MCN_GETDAYSTATE 메시지는 표시되는 월 내의 일을 표시하는 방법을 결정하기 위해 컨트롤에 의해 전송됩니다.

> [!NOTE]
> 컨트롤은 이전 및 다음 달을 캐시하므로 표시되는 달과 관련하여 새 월을 선택할 때마다 이 알림을 받게 됩니다.

이 메시지를 제대로 처리하려면 요청되는 월 일 수의 상태 정보를 결정하고, 적절한 값으로 **MONTHDAYSTATE** 구조의 배열을 초기화하고, 관련 구조 멤버를 새 정보로 초기화해야 합니다. 필요한 단계를 자세히 설명하는 다음 절차는 *m_monthcal* 라는 `CMonthCalCtrl` 개체와 **MONTHDAYSTATE** 개체, *mdState의*배열이 있다고 가정합니다.

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지를 처리하려면

1. 클래스 [마법사를](reference/mfc-class-wizard.md)사용하여 *m_monthcal* 개체에 MCN_GETDAYSTATE 메시지에 대한 알림 처리기를 [추가합니다(함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)참조).

1. 처리기 본문에 다음 코드를 추가합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   이 예제에서는 *pNMHDR* 포인터를 적절한 유형으로 변환한 다음 요청되는 수개월의 정보()를`pDayState->cDayState`결정합니다. 매월 현재 비트필드()가`pDayState->prgDayState[i]`초기화되고 필요한 날짜가 설정됩니다(이 경우 매월 15일).

## <a name="see-also"></a>참고 항목

[CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
