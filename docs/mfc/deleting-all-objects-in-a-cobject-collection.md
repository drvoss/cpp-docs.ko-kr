---
title: CObject 컬렉션의 모든 개체 삭제
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
ms.openlocfilehash: 303b8a566a730c5abd06d51fb7977174e19a6435
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370533"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject 컬렉션의 모든 개체 삭제

이 문서에서는 컬렉션 개체 자체를 삭제하지 않고 컬렉션의 모든 개체를 삭제하는 방법을 설명합니다.

s(또는 파생된 `CObject` `CObject`개체)의 컬렉션에 있는 모든 개체를 삭제하려면 [컬렉션의 모든 멤버에 액세스하는](../mfc/accessing-all-members-of-a-collection.md) 문서에 설명된 반복 기술 중 하나를 사용하여 각 개체를 차례로 삭제합니다.

> [!CAUTION]
> 컬렉션의 개체를 공유할 수 있습니다. 즉, 컬렉션은 개체에 대한 포인터를 유지하지만 프로그램의 다른 부분에는 동일한 개체에 대한 포인터가 있을 수도 있습니다. 모든 부품이 객체 사용을 완료할 때까지 공유되는 객체를 삭제하지 않도록 주의해야 합니다.

이 문서에서는 다음에서 개체를 삭제하는 방법을 보여 주며 있습니다.

- [목록](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [배열](#_core_to_delete_all_elements_in_an_array)

- [지도](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>CObject에 대한 포인터 목록의 모든 개체를 삭제하려면

1. 목록을 `GetHeadPosition` `GetNext` 반복합니다.

1. **delete** 연산자를 사용하여 반복에서 발생하는 각 개체를 삭제합니다.

1. 해당 `RemoveAll` 요소와 연결된 개체가 삭제된 후 목록에서 모든 요소를 제거하는 함수를 호출합니다.

다음 예제에서는 `CPerson` 개체 목록에서 모든 개체를 삭제하는 방법을 보여 주며 있습니다. 목록의 각 개체는 힙에 `CPerson` 원래 할당된 개체에 대한 포인터입니다.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

마지막 함수 호출은 `RemoveAll`목록에서 모든 요소를 제거하는 목록 멤버 함수입니다. 멤버 함수는 `RemoveAt` 단일 요소를 제거합니다.

요소의 개체를 삭제하고 요소 자체를 제거하는 것의 차이점을 확인합니다. 목록에서 요소를 제거하면 개체에 대한 목록의 참조만 제거됩니다. 개체가 여전히 메모리에 있습니다. 개체를 삭제하면 개체가 일시 중지되고 해당 메모리가 회수됩니다. 따라서 목록이 더 이상 존재하지 않는 개체에 액세스하지 않도록 요소의 개체가 삭제된 직후에 요소를 제거하는 것이 중요합니다.

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>배열의 모든 요소를 삭제하려면

1. 배열을 반복하기 위해 인덱스 값을 사용하고 `GetSize` 정수합니다.

1. **delete** 연산자를 사용하여 반복에서 발생하는 각 요소를 삭제합니다.

1. 함수를 `RemoveAll` 호출하여 삭제된 후 배열에서 모든 요소를 제거합니다.

   배열의 모든 요소를 삭제하는 코드는 다음과 같습니다.

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

위의 목록 예제와 마찬가지로 `RemoveAll` 호출하여 배열의 모든 요소를 `RemoveAt` 제거하거나 개별 요소를 제거할 수 있습니다.

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>맵의 모든 요소를 삭제하려면

1. `GetNextAssoc` 배열을 사용하여 `GetStartPosition` 반복합니다.

1. **delete** 연산자를 사용하여 반복에서 발생하는 각 맵 요소의 키 및/또는 값을 삭제합니다.

1. 함수를 `RemoveAll` 호출하여 삭제된 후 맵에서 모든 요소를 제거합니다.

   `CMap` 컬렉션의 모든 요소를 삭제하는 코드는 다음과 같습니다. 맵의 각 요소에는 문자열이 키로, `CPerson` `CObject`개체(파생)가 값으로 있습니다.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

호출하여 `RemoveAll` 맵의 모든 요소를 제거하거나 `RemoveKey` 지정된 키가 있는 개별 요소를 제거할 수 있습니다.

## <a name="see-also"></a>참고 항목

[컬렉션의 모든 멤버에 액세스](../mfc/accessing-all-members-of-a-collection.md)
