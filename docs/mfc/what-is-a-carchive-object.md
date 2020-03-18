---
title: CArchive 개체
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 0a78385c81c43a4b0c925bbe89ccd3937873ee8b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446025"
---
# <a name="what-is-a-carchive-object"></a>CArchive 개체

`CArchive` 개체는 `CFile` 개체에서 serialize 할 수 있는 개체를 쓰거나 읽을 수 있는 형식이 안전한 버퍼링 메커니즘을 제공 합니다. 일반적으로 `CFile` 개체는 디스크 파일을 나타냅니다. 그러나 클립보드를 나타내는 메모리 파일 (`CSharedFile` 개체) 일 수도 있습니다.

지정 된 `CArchive` 개체는 데이터를 저장 (쓰기, serialize) 하거나 데이터를 로드 (읽기, deserialize) 하는 것은 불가능 합니다. `CArchive` 개체의 수명은 개체를 파일에 쓰거나 파일에서 개체를 읽을 때 한 번의 통과로 제한 됩니다. 따라서 데이터를 파일에 serialize 한 다음 파일에서 다시 deserialize 하려면 `CArchive` 개체가 연속적으로 두 번 생성 되어야 합니다.

아카이브는 개체를 파일에 저장할 때 개체에 `CRuntimeClass` 이름을 연결 합니다. 그런 다음 다른 아카이브가 파일의 개체를 메모리로 로드할 때 `CObject`파생 개체가 개체의 `CRuntimeClass`에 따라 동적으로 재구성 됩니다. 지정 된 개체는 저장 보관 파일에 의해 파일에 기록 될 때 두 번 이상 참조 될 수 있습니다. 그러나 로드 보관 파일은 개체를 한 번만 다시 생성 합니다. 여러 참조를 고려 하 여 아카이브가 개체에 `CRuntimeClass` 정보를 연결 하는 방법에 대 한 세부 정보는 [기술 참고 2](../mfc/tn002-persistent-object-data-format.md)에 설명 되어 있습니다.

데이터가 보관으로 serialize 될 때 보관은 버퍼가 가득 찼을 때까지 데이터를 누적 합니다. 그런 다음 아카이브는 `CArchive` 개체가 가리키는 `CFile` 개체에 버퍼를 씁니다. 마찬가지로 보관 파일에서 데이터를 읽을 때 파일에서 버퍼로 데이터를 읽은 다음 버퍼에서 deserialize 된 개체로 데이터를 읽습니다. 이렇게 버퍼링 하면 하드 디스크를 물리적으로 읽는 횟수가 줄어들어 응용 프로그램의 성능이 향상 됩니다.

## <a name="see-also"></a>참고 항목

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
