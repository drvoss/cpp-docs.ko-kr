---
title: 컴파일러 오류 C2307
ms.date: 11/04/2016
f1_keywords:
- C2307
helpviewer_keywords:
- C2307
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
ms.openlocfilehash: a9d5addc18dd548e584a1cceed8b880cb62ed40d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206281"
---
# <a name="compiler-error-c2307"></a>컴파일러 오류 C2307

증분 컴파일을 사용 하도록 설정한 경우 ' pragma ' pragma는 함수 외부에 있어야 합니다.

증분 컴파일을 사용 하는 경우 함수 사이에 `data_seg` pragma를 넣어야 합니다.
