---
title: 'MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 5314545a3a903158362dbfa65c4a9a1b2143e86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364549"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환

이 문서에서는 ActiveX 제어 메서드에서 오류 코드를 반환 하는 방법을 설명 합니다.

메서드 내에서 오류가 발생했음을 나타내려면 SCODE(상태 코드)를 매개 변수로 사용하는 [COleControl:ThrowError](../mfc/reference/colecontrol-class.md#throwerror) 멤버 함수를 사용해야 합니다. 미리 정의된 SCODE를 사용하거나 사용자 고유의 SCODE를 정의할 수 있습니다.

> [!NOTE]
> `ThrowError`속성의 Get 또는 Set 함수 또는 자동화 메서드 내에서 오류를 반환하는 수단으로만 사용됩니다. 스택에 적절한 예외 처리기가 있는 유일한 시간입니다.

도우미 함수는 [COleControl::SetNotSupported,](../mfc/reference/colecontrol-class.md#setnotsupported) [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)및 [COleControl::SetNot허용](../mfc/reference/colecontrol-class.md#setnotpermitted)된 것과 같은 가장 일반적인 미리 정의된 SCODEs에 대해 존재합니다.

미리 정의된 SCOD 및 사용자 지정 SCOD중 정의에 대한 지침은 ActiveX [컨트롤의 ActiveX 컨트롤:](../mfc/mfc-activex-controls-advanced-topics.md) 고급 항목의 오류 처리 섹션을 참조하십시오.

코드의 다른 영역에서 예외를 보고하는 방법에 대한 자세한 내용은 ActiveX 컨트롤의 [ActiveX 컨트롤:](../mfc/mfc-activex-controls-advanced-topics.md) 고급 항목에서 [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 오류 처리 섹션을 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
