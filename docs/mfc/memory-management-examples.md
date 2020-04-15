---
title: '메모리 관리: 예'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
ms.openlocfilehash: 3a1e647175b7b5294e672efbf234e3ae2853e411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367843"
---
# <a name="memory-management-examples"></a>메모리 관리: 예

이 문서에서는 MFC가 세 가지 일반적인 메모리 할당 각각에 대해 프레임 할당 및 힙 할당을 수행하는 방법을 설명합니다.

- [바이트 의 배열](#_core_allocation_of_an_array_of_bytes)

- [데이터 구조](#_core_allocation_of_a_data_structure)

- [개체](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a>바이트 배열 할당

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>프레임에 바이트 배열을 할당하려면

1. 다음 코드에 표시된 대로 배열을 정의합니다. 배열변수가 범위를 종료하면 어레이가 자동으로 삭제되고 해당 메모리가 회수됩니다.

   [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>힙에 바이트(또는 기본 데이터 형식)의 배열을 할당하려면

1. 이 예제에 표시된 배열 구문을 사용하여 **새** 연산자 사용:

   [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>힙에서 배열을 할당 하려면

1. 다음과 같이 **삭제** 연산자 사용:

   [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a>데이터 구조 할당

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>프레임에 데이터 구조를 할당하려면

1. 구조 변수를 다음과 같이 정의합니다.

   [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]

   구조가 차지하는 메모리는 해당 범위를 종료할 때 회수됩니다.

#### <a name="to-allocate-data-structures-on-the-heap"></a>힙에 데이터 구조를 할당하려면

1. 다음 예제와 같이 **새** 를 사용하여 힙에 데이터 구조를 할당하고 **삭제하여** 할당 할 수 있습니다.

   [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a>개체 할당

#### <a name="to-allocate-an-object-on-the-frame"></a>프레임에 개체를 할당하려면

1. 다음과 같이 개체를 선언합니다.

   [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]

   개체가 범위를 종료할 때 개체에 대한 소멸자가 자동으로 호출됩니다.

#### <a name="to-allocate-an-object-on-the-heap"></a>힙에 개체를 할당하려면

1. 개체에 대한 포인터를 반환하는 **새** 연산자에서 힙에 개체를 할당합니다. **삭제** 연산자를 사용하여 삭제합니다.

   다음 힙 및 프레임 예제는 `CPerson` 생성자가 인수를 취하지 않는다고 가정합니다.

   [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]

   `CPerson` 생성자의 인수가 **char에**대한 포인터인 경우 프레임 할당에 대한 문은 다음과 같은 것입니다.

   [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]

   힙 할당에 대한 문은 다음과 같은 것입니다.

   [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>참고 항목

[메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)
