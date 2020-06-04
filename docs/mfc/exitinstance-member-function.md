---
title: ExitInstance 멤버 함수
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: c76f588b22ad8ffd1d3dae954c5113feffb62a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405822"
---
# <a name="exitinstance-member-function"></a>ExitInstance 멤버 함수

[CWinApp](../mfc/reference/cwinapp-class.md) 클래스의 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 멤버 함수는 사용자가 응용 프로그램을 종료하는 경우와 같이 응용 프로그램 복사본의 종료 시마다 호출됩니다.
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 멤버 함수는 사용자가 응용 프로그램을 종료하는 경우와 같이 응용 프로그램 복사본의 종료 시마다 호출됩니다.

그래픽 장치 인터페이스(GDI) 메모리 해제나 프로그램 실행 중 사용된 메모리 할당 해제와 같은 별도의 정리 작업이 필요한 경우 `ExitInstance`를 재정의합니다. 문서나 뷰와 같은 표준 항목의 정리는 프레임워크에서 제공되기도 하지만, 해당 개체에 대한 별도의 정리 작업 수행을 위한 다른 재정의 가능 함수를 사용합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
