---
title: 보관을 통해 CObject 저장 및 로드
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 368421a86d6ff6fc70455edd0ea9a32e05645007
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446370"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>보관을 통해 CObject 저장 및 로드

보관을 통해 `CObject`s를 저장 하 고 로드 하려면 추가 고려 사항이 필요 합니다. 경우에 따라 \<의 **<>>** 또는 **`CArchive`** 연산자를 사용 하는 것과는 반대로, 개체의 `Serialize` 함수를 호출 해야 합니다. 여기서 `CArchive` 개체는 `Serialize` 호출의 매개 변수입니다. 중요 한 점은 `CArchive` **>>** 연산자가 이전에 저장 된 보관 파일에 의해 파일에 기록 된 `CRuntimeClass` 정보를 기반으로 메모리에 `CObject`를 생성 한다는 것입니다.

따라서 `Serialize`를 호출 하는 것과 비교 하 여 `CArchive` **<\<** 및 **>>** 연산자를 사용 하는 경우 이전에 저장 된 `CRuntimeClass` 정보를 기준으로 개체를 동적으로 다시 생성 하려면 로드 보관 파일이 *필요한* 지 여부에 따라 달라 집니다. 다음과 같은 경우 `Serialize` 함수를 사용 합니다.

- 개체를 deserialize 할 때 개체의 정확한 클래스를 미리 알고 있습니다.

- 개체를 deserialize 할 때 해당 개체에 할당 된 메모리가 이미 있습니다.

> [!CAUTION]
>  `Serialize` 함수를 사용 하 여 개체를 로드 하는 경우에도 `Serialize` 함수를 사용 하 여 개체를 저장 해야 합니다. `CArchive` **<<** 연산자를 사용 하 여 저장 한 다음 `Serialize` 함수를 사용 하 여 로드 하거나 `Serialize` 함수를 사용 하 여 저장 한 다음 `CArchive >>` 연산자를 사용 하 여 로드 합니다.

다음 예에서는 사례를 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

요약 하자면, serializable 클래스에서 포함 된 `CObject`를 멤버로 정의 하는 경우 해당 개체에 대 한 `CArchive` **<\<** 및 **>>** 연산자를 사용 *하지* 말고 대신 `Serialize` 함수를 호출 해야 합니다. 또한 serializable 클래스가 `CObject` (또는 `CObject`에서 파생 된 개체)에 대 한 포인터를 멤버로 정의 하지만 자체 생성자에서 다른 개체를 생성 하는 경우 `Serialize`도 호출 해야 합니다.

## <a name="see-also"></a>참고 항목

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
