---
title: 표준 Windows 메시지에 대한 처리기
ms.date: 11/04/2016
f1_keywords:
- afx_msg
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
ms.openlocfilehash: 9a136caf3a1d22151cb9cfd48e1cd3f999ab51ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370496"
---
# <a name="handlers-for-standard-windows-messages"></a>표준 Windows 메시지에 대한 처리기

표준 Windows 메시지 **(WM_)에**대한 기본 `CWnd`처리기는 클래스에서 미리 정의됩니다. 이 클래스 라이브러리는 메시지 이름을 기반으로 이러한 처리기의 이름을 지정합니다. 예를 들어 **WM_PAINT** 메시지의 처리기는 `CWnd` 다음과 같이 선언됩니다.

`afx_msg void OnPaint();`

**afx_msg** 키워드는 처리기를 다른 `CWnd` 멤버 함수와 구별하여 C++ **가상** 키워드의 효과를 제안합니다. 하지만 이러한 함수는 실제로 가상이 아니며, 대신 메시지 맵을 통해 구현됩니다. 메시지 맵은 C++ 언어의 확장이 아닌 표준 전처리기 매크로에만 의존합니다. **afx_msg** 키워드는 전처리 후 공백으로 확인됩니다.

기본 클래스에 정의된 처리기를 재정의하려면 단순히 파생된 클래스의 동일 프로토타입으로 함수를 정의하고 처리기에 대한 메시지-맵 항목을 만듭니다. 처리기는 클래스의 기본 클래스에서 동일한 이름의 모든 처리기를 "재정의"합니다.

이부 경우에는 기본 클래스 및 Windows가 해당 메시지에 대해 작업을 수행할 수 있도록 처리기가 기본 클래스에서 재정의된 처리기를 호출해야 합니다. 재정의에서 기본 클래스 처리기를 호출 하는 위치는 상황에 따라 달라집니다. 경우에 따라 기본 클래스 처리기를 먼저 호출하거나, 마지막으로 호출해야 합니다. 메시지를 직접 처리하지 않도록 선택한 일부 경우에는 기본 클래스 처리기를 조건에 따라 호출합니다. 또한 기본 클래스 처리기를 호출한 후, 기본 클래스 처리기에서 반환된 값 또는 상태에 따라 고유 처리기 코드를 조건에 따라 실행해야 할 수도 있습니다.

> [!CAUTION]
> 인수를 기본 클래스 처리기에 전달하려는 경우에는 처리기에 전달된 인수를 수정하는 것이 안전하지 않습니다. 예를 들어 `OnChar` 처리기의 *nChar* 인수를 수정하려는 유혹이 있을 수 있습니다(예: 대문자로 변환). 이 동작은 매우 모호하지만 이 효과를 수행해야 하는 `CWnd` 경우 `SendMessage` 대신 멤버 함수를 사용합니다.

[클래스 마법사가](reference/mfc-class-wizard.md) 지정된 메시지에 대한 처리기 함수의 스켈레톤을 쓰는 경우 지정된 메시지를 `OnCreate` 재정의하는 적절한 방법을 결정하는 방법은 WM_CREATE 처리기입니다. **WM_CREATE** 다음 예제는 처리기가 먼저 base 클래스 처리기를 호출하고 -1을 반환하지 않는 조건에서만 진행하는 것이 좋습니다.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

일반적으로 이러한 처리기의 이름은 접두사 "On"으로 시작합니다. 이러한 처리기 중 일부는 인수를 사용하지 않으며, 다른 일부는 인수를 사용합니다. 일부는 또한 **void**이외의 반환 유형이 있습니다. 모든 **WM_** 메시지에 대한 기본 처리기는 이름이 "On"으로 `CWnd` 시작하는 클래스의 멤버 함수로 *MFC 참조에* 문서화됩니다. 의 `CWnd` 멤버 함수 선언은 **afx_msg**접두사입니다.

## <a name="see-also"></a>참고 항목

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
