---
title: 링커 도구 오류 LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 845c796ee9611e921e2fd1707b9bb956ab62a5ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195268"
---
# <a name="linker-tools-error-lnk1140"></a>링커 도구 오류 LNK1140

프로그램 데이터베이스용 모듈이 너무 많습니다. /PDB: NONE 링크

프로젝트에 4096 개 이상의 모듈이 포함 되어 있습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. [/Pdb: NONE](../../build/reference/pdb-use-program-database.md)을 사용 하 여 다시 연결 합니다.

1. 디버깅 정보를 사용 하지 않고 일부 모듈을 컴파일합니다.

1. 모듈 수를 줄입니다.
