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
ms.openlocfilehash: 74ae94146b1ec711b586ea1fecbbc89a47b40b5e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626275"
---
# <a name="memory-management-resizable-memory-blocks"></a>메모리 관리: 크기 조정 가능한 메모리 블록

[메모리 관리: 예제](memory-management-examples.md)문서에 설명 된 **new** 및 **delete** 연산자는 고정 크기 메모리 블록과 개체를 할당 및 할당 취소 하는 데 유용 합니다. 경우에 따라 응용 프로그램에 크기 조정 가능한 메모리 블록이 필요할 수 있습니다. 표준 C 런타임 라이브러리 함수 [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)및 free를 사용 하 여 힙에서 크기 조정 [가능한](../c-runtime-library/reference/free.md) 메모리 블록을 관리 해야 합니다.

> [!IMPORTANT]
> **New** 및 **delete** 연산자를 동일한 메모리 블록에서 크기 조정 가능한 메모리 할당 함수와 함께 사용 하면 MFC의 디버그 버전에서 메모리가 손상 됩니다. **New**로 할당 된 메모리 블록에 **realloc** 를 사용 하면 안 됩니다. 마찬가지로, **new** 연산자를 사용 하 여 메모리 블록을 할당 하 고 **free**를 사용 하 여 삭제 하거나 **malloc**로 할당 된 메모리 블록에 **delete** 연산자를 사용 해야 합니다.

## <a name="see-also"></a>참고 항목

[메모리 관리: 힙 할당](memory-management-heap-allocation.md)
