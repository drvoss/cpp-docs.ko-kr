---
title: 컴파일러 오류 C2558
ms.date: 11/04/2016
f1_keywords:
- C2558
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
ms.openlocfilehash: 93b6e414f26c56702a1c7ac12863cbcd5063b570
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177497"
---
# <a name="compiler-error-c2558"></a>컴파일러 오류 C2558

'identifier' : 복사 생성자를 사용할 수 없거나 복사 생성자가 'explicit'으로 선언되었습니다.

복사 생성자는 형식이 같은 다른 개체로부터 개체를 초기화하며 (개체의 복사본을 만듭니다.) 생성자를 정의 하지 않으면 컴파일러가 기본 복사 생성자를 생성 합니다.

### <a name="to-fix-this-error"></a>이 오류를 해결하려면

1. 복사 생성자가 `private`인 클래스를 복사하려고 하면 문제가 발생할 수 있습니다. 대부분의 경우 `private` 복사 생성자를 포함하는 클래스는 복사해서는 안 됩니다. 일반적인 프로그래밍 기술에서는 `private` 복사 생성자를 선언하여 클래스를 직접 사용하지 못하도록 합니다. 이 클래스 자체만으로는 사용될 수 없습니다. 제대로 작동하려면 또 다른 클래스가 필요합니다.

   `private` 복사 생성자를 포함하는 클래스를 사용해도 안전하다고 판단되는 경우 `private` 생성자가 있는 클래스에서 새 클래스를 파생시킨 다음 새 클래스에서 사용할 수 있는 `public` 또는 `protected` 복사 생성자를 만듭니다. 원본 클래스 대신 파생 클래스를 사용하십시오.

1. 복사 생성자가 explicit인 클래스를 복사하려고 하면 문제가 발생할 수 있습니다. 복사 생성자를 `explicit`으로 선언하면 클래스 개체를 함수에 전달하거나 함수로부터 반환할 수 없습니다. 명시적 생성자에 대 한 자세한 내용은 [사용자 정의 형식 변환](../../cpp/user-defined-type-conversions-cpp.md)을 참조 하세요.

1. `const` 참조 매개 변수를 사용하지 않는 복사 생성자를 사용하여 `const`로 선언된 클래스 인스턴스를 복사하려고 하면 문제가 발생할 수 있습니다. non-const 형식 참조 대신에 `const` 형식 참조를 사용하여 복사 생성자를 선언합니다.
