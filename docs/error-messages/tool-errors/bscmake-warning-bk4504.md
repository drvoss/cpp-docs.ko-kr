---
title: BSCMAKE 경고 BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 57858827439ac8cc11e3718d7a484124ae8a6d74
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197446"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE 경고 BK4504

파일에 참조가 너무 많습니다. 이 소스에서 추가 참조를 무시 합니다.

.cpp 파일에는 64,000개 이상의 기호 참조가 포함되어 있습니다. BSCMAKE가 파일에서 64,000개의 참조를 발견하면 모든 추가 참조가 무시됩니다.

이 문제를 해결하려면 파일을 두 개 이상의 파일로 분할해서 각 파일의 기호 참조 수를 64,000개 미만으로 줄이거나 `#pragma component(browser)` 전처리기 지시문을 사용해서 특정 참조에 대해 생성되는 기호를 제한합니다. 자세한 내용은 [구성 요소](../../preprocessor/component.md)를 참조 하세요.
