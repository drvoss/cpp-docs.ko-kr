---
title: 링커 도구 오류 LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: 9dcc37bd74a25e29726529346b1578bb8b18ac3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195138"
---
# <a name="linker-tools-error-lnk1200"></a>링커 도구 오류 LNK1200

' filename ' 프로그램 데이터베이스를 읽는 동안 오류가 발생 했습니다.

PDB (프로그램 데이터베이스)를 읽을 수 없습니다.

이 오류는 파일이 손상 된 경우에 발생할 수 있습니다.

`filename` 개체 파일의 PDB 인 경우 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)를 사용 하 여 개체 파일을 다시 컴파일하십시오.

`filename` 주 출력 파일에 대 한 PDB이 고 증분 링크를 실행 하는 동안이 오류가 발생 한 경우에는 PDB를 삭제 하 고 다시 링크 합니다.
