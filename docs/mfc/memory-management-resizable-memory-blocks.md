---
title: '메모리 관리: 크기 조정 가능한 메모리 블록'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: b048b60a5512ecc54750cb980ca67e2373e2c837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364784"
---
# <a name="memory-management-resizable-memory-blocks"></a>메모리 관리: 크기 조정 가능한 메모리 블록

[메모리 관리: 예제에](../mfc/memory-management-examples.md)설명된 새 **및** **삭제** 연산자는 고정 크기 메모리 블록 및 개체를 할당하고 할당하는 데 적합합니다. 경우에 따라 응용 프로그램에 상당한 메모리 블록이 필요할 수 있습니다. 당신은 표준 C 런타임 라이브러리 기능을 사용해야합니다 [malloc,](../c-runtime-library/reference/malloc.md) [realloc,](../c-runtime-library/reference/realloc.md)및 힙에 식용 메모리 블록을 관리 할 [수](../c-runtime-library/reference/free.md) 있습니다.

> [!IMPORTANT]
> **새** 연산자와 **삭제** 연산자와 동일한 메모리 블록에서 조정 가능한 메모리 할당 함수를 혼합하면 MFC의 디버그 버전에서 메모리가 손상됩니다. **새**로 할당된 메모리 블록에 **realloc를** 사용 해서는 안 됩니다. 마찬가지로 **새** 연산자와 함께 메모리 블록을 할당하고 **무료로**삭제하거나 **malloc에**할당된 메모리 블록에서 **삭제** 연산자사용을 사용해서는 안 됩니다.

## <a name="see-also"></a>참고 항목

[메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)
