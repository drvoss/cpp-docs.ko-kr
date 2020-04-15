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
ms.openlocfilehash: f1b59516d5bba13b6f5e006f91d8ebd560543b05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372154"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>보관을 통해 CObject 저장 및 로드

아카이브를 `CObject`통해 s를 저장하고 로드하려면 추가적인 고려가 필요합니다. 경우에 `Serialize` 따라 개체가 `CArchive` `Serialize` 호출의 ** < ** **>>** 매개 변수인 개체의 함수를 `CArchive`호출해야 합니다. 명심해야 할 중요한 사실은 `CArchive` **>>** 연산자가 `CObject` 저장 아카이브에 `CRuntimeClass` 의해 파일에 이전에 기록된 정보를 기반으로 메모리에 대한 생성을 한다는 것입니다.

따라서 `CArchive` ** < ** 및 **>>** 연산자 사용 여부와 `Serialize`호출은 이전에 저장된 `CRuntimeClass` 정보를 기반으로 개체를 동적으로 재구성하기 위해 로드 아카이브가 *필요한지* 여부에 따라 달라집니다. 다음과 `Serialize` 같은 경우 함수를 사용합니다.

- 개체를 역직렬화할 때 개체의 정확한 클래스를 미리 알 수 있습니다.

- 개체를 역직렬화할 때 이미 메모리가 할당되어 있습니다.

> [!CAUTION]
> `Serialize` 함수를 사용하여 개체를 로드하는 경우 `Serialize` 함수를 사용하여 개체도 저장해야 합니다. `CArchive` **<<** 연산자 사용을 사용하여 저장한 다음 `Serialize` 함수를 사용하여 `Serialize` 로드하거나 함수를 `CArchive >>` 사용하여 저장한 다음 연산자사용을 사용하여 로드하지 마십시오.

다음 예제에서는 사례를 보여 줍니다.

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

간단히 말하지만 serializable `CObject` 클래스가 포함된 멤버를 정의하는 경우 해당 개체에 `CArchive` ** < ** 대해 및 연산자 `Serialize` 및 **>>** 연산자는 사용하지 *말고* 함수를 호출해야 합니다. 또한 serializable 클래스가 `CObject` a(또는 에서 `CObject`파생된 개체)에 대한 포인터를 멤버로 정의하지만 자체 생성자에서 이 다른 `Serialize`개체를 생성하는 경우에도 호출해야 합니다.

## <a name="see-also"></a>참고 항목

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
