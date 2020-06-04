---
title: 다른 테이블에 해당 행에 대 한 참조가 포함 되어 있는 경우 열을 업데이트 합니다.
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 95cddfd5f030c7bd8d1220cf040de4bc5a883226
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209484"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>다른 테이블에 행에 대한 참조가 들어 있는 경우의 열 업데이트

일부 공급자는 행에서 변경된 열을 감지할 수 있지만, 대부분의 공급자는 그렇게 하지 못합니다. 따라서, 업데이트하려는 행에 대한 참조가 있는 경우, 열을 업데이트하면 오류가 발생할 수 있습니다. 이 문제를 해결하려면, 변경하려는 열만 들어 있는 개별 접근자를 만드십시오. `SetData`에 해당 접근자의 수를 전달 합니다.

## <a name="see-also"></a>참고 항목

[접근자 사용](../../data/oledb/using-accessors.md)
