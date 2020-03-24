---
title: 프로젝트 빌드 오류 PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 3675c3796ae37df848e458aa2db665d8c4aa7766
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192512"
---
# <a name="project-build-error-prj0030"></a>프로젝트 빌드 오류 PRJ0030

매크로 확장 오류입니다. 재귀 평가는 $ (매크로)에 대해 32 수준을 초과 했습니다.

이 오류는 매크로에서 재귀로 인해 발생 합니다. 예를 들어 **중간 디렉터리** 속성 ( [일반 속성 페이지 (프로젝트)](../../build/reference/general-property-page-project.md)참조)을 $ (IntDir)로 설정 하는 경우 재귀가 발생 합니다.

이 오류를 해결 하려면을 정의 하는 데 사용 되는 매크로를 기준으로 매크로 또는 속성을 정의 하지 마십시오.
