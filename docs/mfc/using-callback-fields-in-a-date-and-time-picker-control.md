---
title: 날짜 및 시간 선택 컨트롤에서 콜백 필드 사용
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 50350e51b6747d8c010db9d0dcaa9dff2e56e1f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366563"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤에서 콜백 필드 사용

날짜 및 시간 선택기 필드를 정의하는 표준 형식 문자 외에도 사용자 지정 형식 문자열의 특정 부분을 콜백 필드로 지정하여 출력을 사용자 지정할 수 있습니다. 콜백 필드를 선언하려면 형식 문자열의 본문에 하나 이상의 "X" 문자(ASCII Code 88)를 포함합니다. 예를 들어 다음 문자열 "'yy'/'MM'dd'(Day 'X')'는 날짜 및 시간 선택기 컨트롤이 날짜 및 시간 선택기 컨트롤을 연도 다음에 월, 날짜 및 마지막으로 연도의 날짜로 표시하도록 합니다.

> [!NOTE]
> 콜백 필드의 X 수가 표시될 문자 수와 일치하지 않습니다.

"X" 문자를 반복하여 사용자 지정 문자열에서 여러 콜백 필드를 구분할 수 있습니다. 따라서 형식 문자열 "XXdddMMMdd", "yyyXXX"에는 "XX"와 "XXX"라는 두 개의 고유한 콜백 필드가 포함되어 있습니다.

> [!NOTE]
> 콜백 필드는 유효한 필드로 처리되므로 응용 프로그램이 DTN_WMKEYDOWN 알림 메시지를 처리할 수 있도록 준비해야 합니다.

날짜 및 시간 선택기 컨트롤에 콜백 필드를 구현하는 것은 세 부분으로 구성됩니다.

- 사용자 지정 형식 문자열 초기화

- DTN_FORMATQUERY 알림 처리

- DTN_FORMAT 알림 처리

## <a name="initializing-the-custom-format-string"></a>사용자 지정 형식 문자열 초기화

에 대한 호출을 사용하여 `CDateTimeCtrl::SetFormat`사용자 지정 문자열을 초기화합니다. 자세한 내용은 [날짜 및 시간 선택기 컨트롤에서 사용자 지정 형식 문자열 사용을](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)참조하십시오. 사용자 지정 형식 문자열을 `OnInitDialog` 설정하는 일반적인 장소는 포함된 대화 상자 `OnInitialUpdate` 클래스또는 포함된 뷰 클래스의 함수에 있습니다.

## <a name="handling-the-dtn_formatquery-notification"></a>DTN_FORMATQUERY 알림 처리

컨트롤이 형식 문자열을 구문 분석하고 콜백 필드가 발생하면 응용 프로그램은 DTN_FORMAT 보내고 알림 메시지를 DTN_FORMATQUERY. 콜백 필드 문자열이 알림에 포함되어 있으므로 쿼리중인 콜백 필드를 확인할 수 있습니다.

DTN_FORMATQUERY 알림은 현재 콜백 필드에 표시될 문자열의 픽셀에서 허용되는 최대 크기를 검색하기 위해 전송됩니다.

이 값을 올바르게 계산하려면 컨트롤의 표시 글꼴을 사용하여 필드를 대체할 문자열의 높이와 너비를 계산해야 합니다. 문자열의 실제 계산은 [GetTextExtentPoint32](/windows/win32/api/wingdi/nf-wingdi-gettextextentpoint32w) Win32 함수를 호출하여 쉽게 얻을 수 있습니다. 크기가 결정되면 값을 응용 프로그램에 다시 전달하고 처리기 함수를 종료합니다.

다음 예제는 콜백 문자열의 크기를 제공하는 한 가지 방법입니다.

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

현재 콜백 필드의 크기가 계산되면 필드에 대한 값을 제공해야 합니다. 이 작업은 DTN_FORMAT 알림에 대한 처리기에서 수행됩니다.

## <a name="handling-the-dtn_format-notification"></a>DTN_FORMAT 알림 처리

DTN_FORMAT 알림은 대체할 문자 문자열을 요청하기 위해 응용 프로그램에서 사용됩니다. 다음 예제에서는 한 가지 가능한 메서드를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
> **NMDATETIMEFORMAT** 구조에 대한 포인터는 알림 처리기의 첫 번째 매개 변수를 적절한 형식으로 캐스팅하여 찾을 수 있습니다.

## <a name="see-also"></a>참고 항목

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
