---
title: 파일 상태 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 23c626940e700d3e9827ef6a7cf849d970e40d5d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619780"
---
# <a name="accessing-file-status"></a>파일 상태 액세스

`CFile`은 파일 존재 여부, 생성/수정 날짜 및 시간, 논리적 크기와 경로 등을 비롯한 파일 상태도 가져올 수 있습니다.

### <a name="to-get-file-status"></a>파일 상태를 가져오려면

1. [CFile](reference/cfile-class.md) 클래스를 사용 하 여 파일에 대 한 정보를 가져오고 설정 합니다. 한 가지 유용한 응용 프로그램은 `CFile` 정적 멤버 함수 **GetStatus** 를 사용 하 여 파일이 있는지 확인 하는 것입니다. 지정 된 파일이 없는 경우 **GetStatus** 는 0을 반환 합니다.

따라서 다음 예제와 같이 **GetStatus** 의 결과를 사용 하 여 파일을 열 때 **CFile:: modeCreate** 플래그를 사용할지 여부를 결정할 수 있습니다.

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

관련 정보는 [Serialization](serialization-in-mfc.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[Files](files-in-mfc.md)
