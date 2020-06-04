---
title: 파일 열기
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: 6119bf922b05c30a14d8421800e3931c4a038779
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375956"
---
# <a name="opening-files"></a>파일 열기

MFC에서 파일을 여는 가장 일반적인 방법은 2단계 프로세스입니다.

#### <a name="to-open-a-file"></a>파일을 열려면

1. 경로 또는 사용 권한 플래그를 지정하지 않고 파일 개체를 만듭니다.

   일반적으로 스택 프레임에서 [CFile](../mfc/reference/cfile-class.md) 변수를 선언하여 파일 개체를 만듭니다.

1. 파일 개체에 대해 [Open](../mfc/reference/cfile-class.md#open) 멤버 함수를 호출하여 경로 및 권한 플래그를 제공합니다.

   파일을 성공적으로 `Open` 열면 반환 값이 0이 아니거나 지정된 파일을 열 수 없는 경우 0이 됩니다. 멤버 `Open` 함수는 다음과 같이 프로토타입화됩니다.

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   열린 플래그는 파일에 대해 원하는 읽기 전용과 같은 권한을 지정합니다. 가능한 플래그 값은 `CFile` 클래스 내에서 행해진 상수로 정의되므로`CFile::` `CFile::modeRead`에서와 같이 "로 한정됩니다. 파일을 `CFile::modeCreate` 만들려면 플래그를 사용합니다.

다음 예제에서는 읽기/쓰기 권한이 있는 새 파일을 만드는 방법을 보여 주며(이전 파일을 동일한 경로로 대체).

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> 이 예제는 파일을 만들고 엽니다. 문제가 있는 경우 `Open` 호출은 여기에 `CFileException` 표시된 대로 마지막 매개 변수에 있는 개체를 반환할 수 있습니다. TRACE 매크로는 파일 이름과 실패 이유를 나타내는 코드를 모두 인쇄합니다. 더 자세한 `AfxThrowFileException` 오류 보고가 필요한 경우 함수를 호출할 수 있습니다.

## <a name="see-also"></a>참고 항목

[CFile 클래스](../mfc/reference/cfile-class.md)<br/>
[CFile::열기](../mfc/reference/cfile-class.md#open)<br/>
[파일](../mfc/files-in-mfc.md)
