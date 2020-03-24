---
title: 컴파일러 경고 (수준 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: 214ccae5d9835bc4a3b66bbbe1cd5ded4bc651cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164146"
---
# <a name="compiler-warning-level-1-c4049"></a>컴파일러 경고 (수준 1) C4049

컴파일러 한계: 줄 번호 내보내기를 종료 하 고 있습니다.

파일에 16777215 (2<sup>24</sup>-1) 이상의 소스 줄이 포함 되어 있습니다. 컴파일러가 16777215에서 번호 매기기를 중지 합니다.

16777215 줄 이후의 코드:

- 이미지는 줄 번호에 대 한 디버그 정보를 포함 하지 않습니다.

- 일부 진단이 잘못 된 줄 번호와 함께 보고 될 수 있습니다.

- .asm 목록 (/FAs)에 잘못 된 줄 번호가 있을 수 있습니다.
