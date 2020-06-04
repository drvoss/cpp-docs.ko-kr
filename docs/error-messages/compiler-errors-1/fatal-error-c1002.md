---
title: 심각한 오류 C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: 78edf886f34665f996497abe323a0ea5d3800c2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204934"
---
# <a name="fatal-error-c1002"></a>심각한 오류 C1002

2번 패스에서 컴파일러의 힙 공간이 부족합니다.

기호 또는 복잡 한 식이 너무 많은 프로그램 때문에 두 번째 단계에서 컴파일러에 동적 메모리 공간이 부족 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 소스 파일을 여러 개의 작은 파일로 나눕니다.

1. 식을 더 작은 하위 식으로 나눕니다.

1. 메모리를 사용 하는 다른 프로그램 또는 드라이버를 제거 합니다.
