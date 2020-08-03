---
title: 내부 링크
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: 3709ca815877b98fe5dfe6e5b2eca6b5c627641b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229599"
---
# <a name="internal-linkage"></a>내부 링크

개체 또는 함수의 파일 범위 식별자 선언에 *storage-class-specifier* **`static`** 이 있으면 식별자에 내부 링크가 있고 그렇지 않으면 식별자에 외부 링크가 있습니다. *storage-class-specifier* 비터미널에 대한 설명은 [스토리지 클래스](../c-language/c-storage-classes.md)를 참조하세요.

변환 단위 안에서 내부 링크가 있는 식별자의 각 인스턴스는 같은 식별자 또는 함수를 나타냅니다. 내부적으로 연결된 식별자는 변환 단위마다 다릅니다.

## <a name="see-also"></a>참조

[extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)
