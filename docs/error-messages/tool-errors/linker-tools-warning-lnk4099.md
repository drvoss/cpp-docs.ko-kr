---
title: 링커 도구 경고 LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: b1f330924b8e47e0649268142106a050c83cb20a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183321"
---
# <a name="linker-tools-warning-lnk4099"></a>링커 도구 경고 LNK4099

' Filename ' PDB가 ' object/library ' 또는 ' path '에 없습니다. 디버그 정보가 없는 것 처럼 개체를 링크 합니다.

링커가 .pdb 파일을 찾을 수 없습니다. `object/library`를 포함 하는 디렉터리에 복사 합니다.

개체 파일과 연결 된 .pdb 파일의 이름을 찾으려면 다음을 수행 합니다.

1. [Lib](../../build/reference/lib-reference.md) **/extract:** `objectname` **.obj** `xyz`를 사용 하 여 라이브러리에서 개체 파일을 추출 **합니다.**

1. **Dumpbin/section:. debug $ T/rawdata** `objectname`를 사용 하 여 .pdb 파일의 경로를 **확인 합니다.**

또한 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)로 컴파일하면 pdb를 사용할 필요가 없습니다. 연결 하려는 개체에 대 한 .pdb 파일이 없는 경우에는 [/debug](../../build/reference/debug-generate-debug-info.md) 링커 옵션을 제거 합니다.
