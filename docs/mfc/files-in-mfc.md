---
title: MFC의 파일
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
ms.openlocfilehash: 3a99c4143bbd27ba765b0289b80be8870a940f63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365309"
---
# <a name="files-in-mfc"></a>MFC의 파일

Microsoft 파운데이션 클래스 라이브러리(MFC)에서 클래스 [CFile은](../mfc/reference/cfile-class.md) 일반 파일 I/O 작업을 처리합니다. 이 문서 제품군은 파일을 열고 닫는 방법과 해당 파일에 데이터를 읽고 쓰는 방법을 설명합니다. 또한 파일 상태 작업에 대해서도 설명합니다. 파일에서 데이터를 읽고 쓰는 다른 방법으로 MFC의 개체 기반 직렬화 기능을 사용하는 방법에 대한 설명은 [일련화를](../mfc/serialization-in-mfc.md)참조하십시오.

> [!NOTE]
> MFC `CDocument` 개체를 사용하는 경우 프레임워크는 직렬화 작업을 대부분 수행합니다. 특히 프레임워크는 개체를 `CFile` 만들고 사용합니다. 클래스의 멤버 함수 재정의에 `Serialize` 코드를 작성하기만 `CDocument`하면 됩니다.

클래스는 `CFile` 범용 이진 파일 작업에 대한 인터페이스를 제공합니다. `CStdioFile` 공급보다 `CMemFile` 전문적인 파일 `CFile` 서비스에서 `CSharedFile` 파생된 `CMemFile` 클래스 및 클래스입니다.

MFC 파일 처리에 대한 대안에 대한 자세한 내용은 *런타임 라이브러리 참조의* [파일 처리를](../c-runtime-library/file-handling.md) 참조하십시오.

파생 클래스에 `CFile` 대한 자세한 내용은 [MFC 계층 구조 차트를](../mfc/hierarchy-chart.md)참조하십시오.

## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요

*CFile 사용*

- [CFile으로 파일 열기](../mfc/opening-files.md)

- [CFile을 통해 파일 읽기 및 쓰기](../mfc/reading-and-writing-files.md)

- [CFile으로 파일 닫기](../mfc/closing-files.md)

- [CFile을 통해 파일 상태에 액세스](../mfc/accessing-file-status.md)

*MFC 직렬화(개체 지속성) 사용*

- [직렬화 가능한 클래스 만들기](../mfc/serialization-making-a-serializable-class.md)

- [CArchive 개체를 통해 개체 직렬화](../mfc/serialization-serializing-an-object.md)

- [CArchive 개체 만들기](../mfc/two-ways-to-create-a-carchive-object.md)

- [CArchive <\< 및 >> 연산자 사용](../mfc/using-the-carchive-output-and-input-operators.md)

- [아카이브를 통해 CObject 및 CObject 파생 개체 저장 및 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>참고 항목

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CArchive 클래스](../mfc/reference/carchive-class.md)<br/>
[CObject 클래스](../mfc/reference/cobject-class.md)
