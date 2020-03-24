---
title: 링커 도구 경고 LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: fda1fdb03a7629894f846bb20ed84df519239327
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183308"
---
# <a name="linker-tools-warning-lnk4102"></a>링커 도구 경고 LNK4102

삭제 중인 ' name ' 소멸자 내보내기 이미지가 올바르게 실행 되지 않을 수 있습니다.

프로그램에서 삭제 소멸자를 내보내려고 했습니다. 결과 삭제는 DLL 경계를 넘어 수행 되어 프로세스가 소유 하지 않은 메모리를 확보할 수 있습니다. 지정 된 기호가 .def 파일에 나열 되지 않으며, 기호가 링커 명령줄에서 **/import** 또는 **/export** 옵션의 인수로 나열 되지 않는지 확인 합니다.

C 런타임 라이브러리를 다시 작성 하는 경우이 메시지를 무시할 수 있습니다.
