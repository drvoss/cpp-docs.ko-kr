---
title: 링커 도구 경고 LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: 5de53abc2342e3ed743f6b4abb871e05606dfc37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194280"
---
# <a name="linker-tools-warning-lnk4014"></a>링커 도구 경고 LNK4014

' objectname ' 멤버 개체를 찾을 수 없습니다.

LIB가 라이브러리에서 `objectname`를 찾을 수 없습니다.

**/Remove** 및 **/extract** 옵션에는 파일에 삭제 하거나 복사할 멤버 개체의 전체 이름이 필요 합니다. 전체 이름에는 원래 개체 파일의 경로가 포함 됩니다. 라이브러리에 있는 멤버 개체의 전체 이름을 확인 하려면 DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) 또는 LIB [/list](../../build/reference/managing-a-library.md)를 사용 합니다.
