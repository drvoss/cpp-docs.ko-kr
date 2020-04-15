---
title: 메시지 맵을 찾을 장소
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: eec0ae43546e3cc0c08e3178c4808e21fa48686a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360158"
---
# <a name="where-to-find-message-maps"></a>메시지 맵을 찾을 장소

응용 프로그램 마법사를 사용하여 새 스켈레톤 응용 프로그램을 만들 때 응용 프로그램 마법사는 작성하는 각 명령 대상 클래스에 대한 메시지 맵을 작성합니다. 여기에는 파생 응용 프로그램, 문서, 보기 및 프레임 창 클래스가 포함됩니다. 이러한 메시지 맵 중 일부는 이미 특정 메시지 및 미리 정의된 명령에 대해 응용 프로그램 마법사에서 제공하는 항목을 가지고 있으며 일부는 추가할 처리기의 자리 표시자일 뿐입니다.

클래스의 메시지 맵은 에 있습니다. 클래스에 대한 CPP 파일입니다. 응용 프로그램 마법사가 만드는 기본 메시지 맵으로 작업하는 경우 [클래스 마법사를](reference/mfc-class-wizard.md) 사용하여 각 클래스가 처리할 메시지 및 명령에 대한 항목을 추가합니다. 일부 항목을 추가한 후 일반적인 메시지 맵은 다음과 같이 보일 수 있습니다.

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

메시지 맵은 매크로 컬렉션으로 구성됩니다. 두 개의 매크로, [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 및 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)메시지 맵을 괄호로 묶습니다. 과 같은 `ON_COMMAND`다른 매크로는 메시지 맵의 내용을 입력합니다.

> [!NOTE]
> 메시지 맵 매크로 뒤에 세미콜론이 따르지 않습니다.

클래스 추가 마법사를 사용하여 새 클래스를 만들 면 클래스에 대한 메시지 맵을 제공합니다. 또는 소스 코드 편집기에서 수동으로 메시지 맵을 만들 수 있습니다.

## <a name="see-also"></a>참고 항목

[프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)
