---
title: CCmdUI 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 105aa7ad6c5cc6a5563dbde8145327a2b3d066a1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447147"
---
# <a name="the-ccmdui-class"></a>CCmdUI 클래스

업데이트 명령을 해당 처리기로 라우팅하는 경우 프레임 워크는 `CCmdUI` 개체 또는 `CCmdUI`파생 클래스의 개체에 대 한 포인터를 처리기에 전달 합니다. 이 개체는 메뉴 항목 또는 도구 모음 단추나 명령을 생성 한 다른 사용자 인터페이스 개체를 나타냅니다. 업데이트 처리기는 포인터를 통해 `CCmdUI` 구조체의 멤버 함수를 호출 하 여 사용자 인터페이스 개체를 업데이트 합니다. 예를 들어 다음은 모두 지우기 메뉴 항목에 대 한 업데이트 처리기입니다.

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

이 처리기는 메뉴 항목에 대 한 액세스 권한이 있는 개체의 `Enable` 멤버 함수를 호출 합니다. `Enable`는 항목을 사용할 수 있도록 합니다.

## <a name="see-also"></a>참고 항목

[방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)
