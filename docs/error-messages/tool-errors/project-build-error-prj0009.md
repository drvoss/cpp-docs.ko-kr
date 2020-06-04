---
title: 프로젝트 빌드 오류 PRJ0009
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: d02325504b04a13cd15dee0bd70891bf5a63b62e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192966"
---
# <a name="project-build-error-prj0009"></a>프로젝트 빌드 오류 PRJ0009

빌드 로그를 쓰기용으로 열 수 없습니다.

**파일이 다른 프로세스에 의해 열리지 않고 쓰기 방지 되어 있지 않은지 확인 하십시오.**

**빌드 로깅** 속성을 **예** 로 설정 하 고 빌드 또는 다시 빌드를 수행 하면 C++ Visual에서 전용 모드로 빌드 로그를 열 수 없습니다.

**도구** 메뉴에서 **옵션 명령을** 클릭 하 고 **프로젝트** 폴더에서 **VC + + 빌드** 를 선택 하 여 **옵션** 대화 상자를 열고 **빌드 로깅** 설정을 검사 합니다. 빌드 파일은 Buildlog.htm 이라고 하며 중간 디렉터리 $ (IntDir)에 기록 됩니다.

이 오류의 가능한 원인은 다음과 같습니다.

- 두 개의 시각적 개체 C++ 프로세스를 실행 하 고 동시에 동일한 프로젝트의 동일한 구성을 빌드 하려고 합니다.

- 빌드 로그 파일은 파일을 잠그는 프로세스에서 열립니다.

- 사용자에 게 파일을 만들 수 있는 권한이 없습니다.

- 현재 사용자에 게 Buildlog.htm 파일에 대 한 쓰기 권한이 없습니다.
