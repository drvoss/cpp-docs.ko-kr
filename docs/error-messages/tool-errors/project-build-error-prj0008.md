---
title: 프로젝트 빌드 오류 PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 7d1c11ab7539f25d371c0bfbd2853b6155c9661c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192958"
---
# <a name="project-build-error-prj0008"></a>프로젝트 빌드 오류 PRJ0008

' File ' 파일을 삭제할 수 없습니다.

**파일이 다른 프로세스에 의해 열리지 않고 쓰기 방지 되어 있지 않은지 확인 하십시오.**

다시 빌드 또는 정리 중에는 C++ [일반 구성 설정 속성 페이지](../../build/reference/general-property-page-project.md)에서 **정리 시 삭제할 확장** 속성의 와일드 카드 사양을 만족 하는 모든 파일 뿐만 아니라 빌드에 대해 알려진 모든 중간 파일 및 출력 파일을 삭제 합니다.

시각적 개체 C++ 에서 파일을 삭제할 수 없는 경우이 오류가 표시 됩니다. 오류를 해결 하려면 빌드를 수행 하는 사용자를 위해 파일과 해당 디렉터리를 쓰기 가능 하도록 설정 합니다.
