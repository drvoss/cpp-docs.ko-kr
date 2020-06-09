---
title: 재정의 가능 CWinApp 멤버 함수
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 7ae72a52c37582f8398ebc03f404ff105fe14650
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624008"
---
# <a name="overridable-cwinapp-member-functions"></a>재정의 가능 CWinApp 멤버 함수

[CWinApp](reference/cwinapp-class.md) 는 다음과 같은 몇 가지 키 재정의 가능 멤버 함수를 제공 합니다 ( `CWinApp` 가 파생 되는 [CWinThread](reference/cwinthread-class.md)클래스에서이 멤버 재정의 `CWinApp` ).

- [InitInstance](initinstance-member-function.md)

- [실행](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

재정의해야 하는 유일한 `CWinApp` 멤버 함수는 `InitInstance`입니다.

## <a name="see-also"></a>참고 항목

[CWinApp: 애플리케이션 클래스](cwinapp-the-application-class.md)
