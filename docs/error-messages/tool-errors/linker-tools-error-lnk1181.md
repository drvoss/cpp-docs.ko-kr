---
title: 링커 도구 오류 LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: d2b28af52a2ca2263a7bad77c8c69242396ff2b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195255"
---
# <a name="linker-tools-error-lnk1181"></a>링커 도구 오류 LNK1181

' filename ' 입력 파일을 열 수 없습니다.

링커가 없거나 경로를 찾을 수 없기 때문에 `filename`를 찾을 수 없습니다.

오류 LNK1181의 몇 가지 일반적인 원인은 다음과 같습니다.

- `filename` 링커 줄에서 추가 종속성으로 참조 되지만 파일이 존재 하지 않습니다.

- `filename`를 포함 하는 디렉터리를 지정 하는 **/libpath** 문이 없습니다.

위의 문제를 해결 하려면 링커 줄에서 참조 되는 파일이 시스템에 있는지 확인 합니다.  또한 링커 종속 파일을 포함 하는 각 디렉터리에 대해 **/libpath** 문이 있는지 확인 합니다.

자세한 내용은 [링커 입력 파일로 사용할 .Lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)을 참조 하세요.

LNK1181의 또 다른 가능한 원인은 공백이 포함 된 긴 파일 이름을 따옴표로 묶지 않았기 때문입니다.  이 경우 링커에서는 첫 번째 공간까지 파일 이름만 인식 한 다음 .obj의 파일 확장명을 가정 합니다.  이러한 상황을 해결 하는 방법은 긴 파일 이름 (경로 + 파일 이름)을 따옴표로 묶는 것입니다.

[/P (파일에 대 한 전처리)](../../build/reference/p-preprocess-to-a-file.md) 옵션을 사용 하 여 컴파일하면 .obj 파일 생성을 억제 LNK1181 수 있습니다.

## <a name="see-also"></a>참고 항목

[/LIBPATH(추가 Libpath)](../../build/reference/libpath-additional-libpath.md)
