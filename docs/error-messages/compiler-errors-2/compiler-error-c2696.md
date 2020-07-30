---
title: 컴파일러 오류 C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: f6af217dbcd871ac4edd1852042144802388545b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216091"
---
# <a name="compiler-error-c2696"></a>컴파일러 오류 C2696

관리 되는 형식 ' type '의 임시 개체를 만들 수 없습니다.

**`const`** 관리 되지 않는 프로그램의에 대 한 참조로 인해 컴파일러가 생성자를 호출 하 고 스택에 임시 개체를 만듭니다. 그러나 스택에 관리 되는 클래스를 만들 수는 없습니다.

C2696는 사용 되지 않는 컴파일러 옵션 **/clr: oldSyntax**를 사용 하는 경우에만 연결할 수 있습니다.
