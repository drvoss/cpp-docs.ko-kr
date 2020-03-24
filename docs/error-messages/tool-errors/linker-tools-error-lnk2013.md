---
title: 링커 도구 오류 LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 6ad3f40f06e64422b393edb457a0dcf419828b6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194748"
---
# <a name="linker-tools-error-lnk2013"></a>링커 도구 오류 LNK2013

픽스업 형식 픽스업 오버플로가 발생 했습니다. 대상 ' 기호 이름 '이 범위를 벗어났습니다.

대상 기호가 명령 위치에서 너무 멀리 떨어져 있으므로 링커가 필요한 주소 또는 오프셋을 지정 된 명령에 맞출 수 없습니다.

여러 이미지를 만들거나 [/order](../../build/reference/order-put-functions-in-order.md) 옵션을 사용 하 여이 문제를 해결할 수 있습니다. 그러면 명령과 대상이 서로 가까이 배치 됩니다.

기호 이름이 사용자 정의 기호 (컴파일러에서 생성 된 기호가 아님) 인 경우 다음 작업을 시도 하 여 오류를 해결할 수도 있습니다.

- 정적 함수를 비정적으로 변경 합니다.

- 정적 함수를 포함 하는 코드 섹션의 이름을 호출자와 동일 하 게 바꿉니다.

`DUMPBIN /SYMBOLS`를 사용 하 여 함수가 정적 인지 확인 합니다.
