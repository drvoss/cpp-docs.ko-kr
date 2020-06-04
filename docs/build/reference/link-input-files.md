---
title: LINK 입력 파일
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: aec71d4622821618f377953d36a9676e2233eefc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328199"
---
# <a name="link-input-files"></a>LINK 입력 파일

링커에 개체, 가져오기 및 표준 라이브러리, 리소스, 모듈 정의 및 명령 입력이 포함된 파일을 제공합니다. LINK는 파일 확장프로그램을 사용하여 파일의 내용에 대해 가정하지 않습니다. 대신 LINK는 각 입력 파일을 검사하여 파일의 종류를 결정합니다.

명령줄의 개체 파일은 명령줄에 표시되는 순서대로 처리됩니다. 라이브러리는 다음 주의 사항과 함께 명령줄 순서로 검색됩니다: 라이브러리에서 개체 파일을 가져올 때 확인되지 않은 기호는 먼저 해당 라이브러리에서 검색된 다음 명령줄 및 [/DEFAULTLIB(기본 라이브러리 지정)](defaultlib-specify-default-library.md) 지시문에서 다음 라이브러리를 검색한 다음 명령줄의 시작 부분에 있는 라이브러리에 대해서도 검색됩니다.

> [!NOTE]
> LINK는 더 이상 응답 파일 및 주문 파일에서 주석의 시작으로 세미콜론(또는 다른 문자)을 허용하지 않습니다. 세미콜론은 모듈 정의 파일(.def)에서 주석의 시작으로만 인식됩니다.

LINK는 다음과 같은 유형의 입력 파일을 사용합니다.

- [.obj 파일](dot-obj-files-as-linker-input.md)

- [.netmodule 파일](netmodule-files-as-linker-input.md)

- [.lib 파일](dot-lib-files-as-linker-input.md)

- [.exp 파일](dot-exp-files-as-linker-input.md)

- [.def 파일](dot-def-files-as-linker-input.md)

- [.pdb 파일](dot-pdb-files-as-linker-input.md)

- [.res 파일](dot-res-files-as-linker-input.md)

- [.exe 파일](dot-exe-files-as-linker-input.md)

- [.txt 파일](dot-txt-files-as-linker-input.md)

- [.ilk 파일](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
