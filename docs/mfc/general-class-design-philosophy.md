---
title: 일반 클래스 디자인 원칙
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 34a173802e3fa43615c05da4ce747592f851228f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441192"
---
# <a name="general-class-design-philosophy"></a>일반 클래스 디자인 원칙

Microsoft Windows는 C++ 언어가 널리 사용 되기 전까지 설계 되었습니다. 수천 개의 응용 프로그램에서 C 언어 Windows API (응용 프로그래밍 인터페이스)를 사용 하기 때문에 해당 인터페이스는 예측 가능한 미래를 위해 유지 관리 됩니다. 따라서 C++ 모든 Windows 인터페이스는 절차적 C 언어 API 위에 빌드해야 합니다. 이렇게 하면 C++ 응용 프로그램을 C 응용 프로그램과 함께 사용할 수 있습니다.

MFC 라이브러리는 다음과 같은 디자인 목표를 충족 하는 Windows에 대 한 개체 지향 인터페이스입니다.

- Windows 용 응용 프로그램을 작성 하는 데 상당한 노력이 필요 합니다.

- C 언어 API와 비교할 수 있는 실행 속도입니다.

- 최소 코드 크기 오버 헤드입니다.

- Windows C 함수를 직접 호출 하는 기능입니다.

- 기존 C 응용 프로그램을로 쉽게 C++변환할 수 있습니다.

- 기존 C 언어의 Windows 프로그래밍 환경에서 활용 하는 기능

- Windows API를 사용 하는 C++ 것이 아니라 C 보다 더 쉽게 사용할 수 있습니다.

- ActiveX 컨트롤, 데이터베이스 지원, 인쇄, 도구 모음 및 상태 표시줄과 같은 복잡 한 기능의 강력한 추상화를 사용 하는 것이 더 쉽습니다.

- 언어 기능을 효과적 C++ 으로 사용 C++ 하는에 대 한 진정한 Windows API입니다.

MFC 라이브러리의 디자인에 대 한 자세한 내용은 다음을 참조 하세요.

- [응용 프로그램 프레임 워크](../mfc/application-framework.md)

- [C 언어 API와의 관계](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
