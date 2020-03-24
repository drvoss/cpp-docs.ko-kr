---
title: 링커 도구 경고 LNK4020
ms.date: 05/29/2018
f1_keywords:
- LNK4020
helpviewer_keywords:
- LNK4020
ms.openlocfilehash: e818909cc0b590b0f7727846cfd7b469e8bc0e3f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194228"
---
# <a name="linker-tools-warning-lnk4020"></a>링커 도구 경고 LNK4020

> '*filename*'의 형식 레코드가 손상 되었습니다. 디버거에서 일부 기호 및 형식을 액세스 하지 못할 수 있습니다.

PDB 파일 파일 *이름* 에 손상 된 유형 레코드가 있습니다.

이 문제는 다른 빌드 문제에 대 한 보조 경우가 종종 있습니다. 첫 번째 보고 된 빌드 문제인 경우를 제외 하 고 다른 오류 및 경고를 먼저 처리 합니다. 이 문제가 처음으로 보고 되는 경우 빌드 디렉터리를 정리 하 고 프로젝트를 다시 빌드해야 할 수 있습니다. 병렬 빌드 프로세스를 사용 하는 경우 빌드를 serialize 할 때 오류가 계속 발생 하는지 확인 합니다.
