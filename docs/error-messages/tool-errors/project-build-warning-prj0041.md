---
title: 프로젝트 빌드 경고 PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: bb6469b1daf193223a9b3361cc3e4bfb96d0c751
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191936"
---
# <a name="project-build-warning-prj0041"></a>프로젝트 빌드 경고 PRJ0041

' File ' 파일에 대 한 누락 된 종속성 ' 종속성 '을 찾을 수 없습니다. 프로젝트를 빌드할 수는 있지만이 파일이 발견 될 때까지 계속 해 서 오래 된 상태로 표시 될 수 있습니다.

예를 들어, 파일 (리소스 파일 또는 .idl/. m i d 파일)에는 프로젝트 시스템에서 확인할 수 없는 include 문이 포함 되어 있습니다.

프로젝트 시스템에서는 전처리기 문 (예: #if)을 처리 하지 않기 때문에 잘못 된 문은 실제로 빌드의 일부가 아닐 수 있습니다.

이 경고를 해결 하려면 .rc 파일에서 불필요 한 코드를 모두 삭제 하거나 적절 한 이름의 자리 표시자 파일을 추가 합니다.
