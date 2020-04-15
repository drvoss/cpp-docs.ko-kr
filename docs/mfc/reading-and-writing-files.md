---
title: 파일 읽기 및 쓰기
ms.date: 11/04/2016
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
ms.openlocfilehash: 6c4b2b21bbfa19fb73997f8475cfa9a4047dc0ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371796"
---
# <a name="reading-and-writing-files"></a>파일 읽기 및 쓰기

C 런타임 라이브러리 파일 처리 기능을 사용한 경우 MFC 읽기 및 쓰기 작업이 익숙한 것처럼 보입니다. 이 문서에서는 개체에서 직접 읽고 `CFile` 쓰는 것을 설명합니다. [CArchive](../mfc/reference/carchive-class.md) 클래스를 통해 버퍼링된 파일 I/O를 수행할 수도 있습니다.

#### <a name="to-read-from-and-write-to-the-file"></a>파일을 읽고 쓰려면

1. `Read` 및 `Write` 멤버 함수를 사용하여 파일의 데이터를 읽고 씁니다.

     또는

1. 멤버 `Seek` 함수는 파일 내의 특정 오프셋으로 이동할 수도 있습니다.

`Read`버퍼에 대한 포인터와 읽을 바이트 수를 가져와 읽은 실제 바이트 수를 반환합니다. 파일 끝(EOF)에 도달했기 때문에 필요한 바이트 수를 읽을 수 없는 경우 실제 읽은 바이트 수가 반환됩니다. 읽기 오류가 발생하면 예외가 throw됩니다. `Write``Read`과 유사하지만 기록된 바이트 수는 반환되지 않습니다. 지정된 모든 바이트를 쓰지 않는 것을 포함하여 쓰기 오류가 발생하면 예외가 throw됩니다. 유효한 `CFile` 개체가 있는 경우 다음 예제와 같이 개체를 읽거나 쓸 수 있습니다.

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> 일반적으로 **try**/**catch** 예외 처리 블록 내에서 입력/출력 작업을 수행해야 합니다. 자세한 내용은 [예외 처리(MFC)를](../mfc/exception-handling-in-mfc.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[파일](../mfc/files-in-mfc.md)
