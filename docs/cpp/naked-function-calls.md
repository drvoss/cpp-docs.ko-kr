---
title: Naked 함수 호출
ms.date: 11/04/2016
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
ms.openlocfilehash: 9b49d34d7276d3c9260488f23d1821b9708d2481
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227324"
---
# <a name="naked-function-calls"></a>Naked 함수 호출

**Microsoft 전용**

특성을 사용 하 여 선언 된 함수 **`naked`** 는 프롤로그 또는 에필로그 코드 없이 내보내지고 [인라인 어셈블러](../assembler/inline/inline-assembler.md)를 사용 하 여 사용자 지정 프롤로그/에필로그 시퀀스를 작성할 수 있도록 합니다. Naked 함수는 고급 기능으로 제공됩니다. 이 함수를 통해 C/C++ 이외의 컨텍스트에서 호출되는 함수를 선언할 수 있으므로 매개 변수의 위치와 유지되고 있는 레지스터에 대한 다양한 가정을 만들 수 있습니다. 예시에는 인터럽트 처리기와 같은 루틴이 포함됩니다. 이러한 기능은 VxD(가상 디바이스 드라이버) 작성에 특히 유용합니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [naked](../cpp/naked-cpp.md)

- [Naked 함수의 규칙 및 제한 사항](../cpp/rules-and-limitations-for-naked-functions.md)

- [프롤로그/에필로그 코드 작성 시 고려 사항](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[호출 규칙](../cpp/calling-conventions.md)
