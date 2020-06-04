---
title: 링커 도구 오류 LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 7712747deb865ec62fa007fcd95ad09630d00cea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194501"
---
# <a name="linker-tools-error-lnk2039"></a>링커 도구 오류 LNK2039

다른 .obj에 정의 된 '\<형식 > '을 (를) 가져오는 중입니다. 이를 가져오거나 정의 해야 합니다.

Ref 클래스 ' <`type`> '은 (는) 지정 된 .obj 파일에서 가져오지만 다른 .obj 파일에도 정의 되어 있습니다. 이 조건은 런타임 오류 또는 기타 예기치 않은 동작을 일으킬 수 있습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 다른 .obj 파일에 '`type`'을 정의해야 하는지 여부 및 .winmd 파일에서 가져와야 하는지 여부를 확인합니다.

1. 정의 또는 가져오기를 제거합니다.

## <a name="see-also"></a>참고 항목

[링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[링커 도구 오류 LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
