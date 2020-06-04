---
title: 일반 창 만들기 시퀀스
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: fb10ced78e230316a6e2982f24c1fb6e2e52ed8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364267"
---
# <a name="general-window-creation-sequence"></a>일반 창 만들기 시퀀스

하위 창과 같은 사용자 고유의 창을 만들 때 프레임워크는 [문서/보기 만들기에](../mfc/document-view-creation.md)설명된 것과 거의 동일한 프로세스를 사용합니다.

MFC에서 제공하는 모든 창 클래스는 [2 단계 구조를](../mfc/one-stage-and-two-stage-construction-of-objects.md)사용합니다. 즉, C++ **새** 연산자 호출 하는 동안 생성자는 C ++ 개체를 할당 하 고 초기화 하지만 해당 Windows 창을 만들지 않습니다. 나중에 창 개체의 멤버 [만들기](../mfc/reference/cwnd-class.md#create) 함수를 호출하여 수행됩니다.

멤버 `Create` 함수는 Windows 창을 만들고 `HWND` m_hWnd C++ 개체의 공용 데이터 [멤버에](../mfc/reference/cwnd-class.md#m_hwnd)저장합니다. `Create`생성 매개 변수에 대한 완전한 유연성을 제공합니다. 호출하기 `Create`전에 프레임의 아이콘 및 클래스 스타일을 설정하기 위해 전역 함수 [AfxRegisterWndClass에](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 창 클래스를 등록할 수 있습니다.

프레임 창의 `Create` [경우.](../mfc/reference/cframewnd-class.md#loadframe) `LoadFrame`더 적은 매개 변수를 사용하여 Windows 창을 만듭니다. 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 비롯한 리소스에서 많은 기본값을 가져옵니다.

> [!NOTE]
> LoadFrame에서 로드하려면 아이콘, 가속기 테이블 및 메뉴 리소스에 **IDR_MAINFRAME**와 같은 공통 리소스 ID가 있어야 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [창 개체](../mfc/window-objects.md)

- [창 "클래스" 등록](../mfc/registering-window-classes.md)

- [창 개체 파괴](../mfc/destroying-window-objects.md)

- [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>참고 항목

[창 만들기](../mfc/creating-windows.md)
