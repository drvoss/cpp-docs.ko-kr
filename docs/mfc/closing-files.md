---
title: 파일 닫기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 51e51c88260a51ec44f11ecb5c2a88e645194f4e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617227"
---
# <a name="closing-files"></a>파일 닫기

일반적으로 i/o 작업에서 파일을 완료 한 후 파일을 닫아야 합니다.

#### <a name="to-close-a-file"></a>파일을 닫으려면

1. **Close** 멤버 함수를 사용 합니다. 이 함수는 파일 시스템 파일을 닫고 필요한 경우 버퍼를 플러시합니다.

[파일 열기](opening-files.md)에 표시 된 예제와 같이 프레임에서 [CFile](reference/cfile-class.md) 개체를 할당 한 경우 개체가 자동으로 닫히고 범위를 벗어나면 소멸 됩니다. 개체를 삭제 `CFile` 해도 파일 시스템의 물리적 파일은 삭제 되지 않습니다.

## <a name="see-also"></a>참고 항목

[Files](files-in-mfc.md)
