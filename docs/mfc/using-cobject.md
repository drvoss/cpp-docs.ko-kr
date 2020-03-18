---
title: CObject 사용
ms.date: 11/04/2016
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: b5399f02819407a529fd5ec66d4f5acbb16ca002
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441929"
---
# <a name="using-cobject"></a>CObject 사용

[CObject](../mfc/reference/cobject-class.md) 는 대부분의 MFC 라이브러리 (MFC)에 대 한 루트 기본 클래스입니다. `CObject` 클래스에는 serialization 지원, 런타임 클래스 정보 및 개체 진단 출력을 포함 하 여 고유한 프로그램 개체에 통합 하려는 많은 유용한 기능이 포함 되어 있습니다. `CObject`에서 클래스를 파생 하는 경우 클래스는 이러한 `CObject` 기능을 이용할 수 있습니다.

## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요

- [CObject에서 클래스 파생](../mfc/deriving-a-class-from-cobject.md)

- [파생 클래스에 대 한 런타임 클래스 정보, 동적 생성 및 serialization에 대 한 지원 추가](../mfc/specifying-levels-of-functionality.md)

- [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)

- [동적으로 개체 만들기](../mfc/dynamic-object-creation.md)

- [진단 목적을 위해 개체의 데이터를 덤프 합니다.](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))

- 개체의 내부 상태를 확인 합니다 ( [MFC ASSERT_VALID 및 CObject:: AssertValid](reference/diagnostic-services.md#assert_valid)참조).

- [클래스가 영구적 저장소로 serialize 되도록 합니다.](../mfc/serialization-in-mfc.md)

- [CObject 질문과 대답](../mfc/cobject-class-frequently-asked-questions.md) 목록 보기

## <a name="see-also"></a>참고 항목

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass 구조체](../mfc/reference/cruntimeclass-structure.md)<br/>
[파일](../mfc/files-in-mfc.md)<br/>
[직렬화](../mfc/serialization-in-mfc.md)
