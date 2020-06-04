---
title: 컴파일러 경고 (수준 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 6786d692785dbca575d4b241b7b3e3d40575b686
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198551"
---
# <a name="compiler-warning-level-4-c4092"></a>컴파일러 경고 (수준 4) C4092

sizeof는 ' unsigned long '을 반환 합니다.

`sizeof` 연산자의 피연산자가 너무 크므로 `sizeof` 부호 없는 **long**이 반환 됩니다. 이 경고는 Microsoft 확장 ([/ze](../../build/reference/za-ze-disable-language-extensions.md))에서 발생 합니다. ANSI 호환성 (/Za)에서 결과가 대신 잘립니다.
