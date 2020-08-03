---
title: register 스토리지 클래스 지정자
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: 513213222ee2c598455709a0891977a0949c8555
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229560"
---
# <a name="register-storage-class-specifier"></a>register 스토리지 클래스 지정자

**Microsoft 전용**

Microsoft C/C++ 컴파일러는 레지스터 변수에 대한 사용자 요청을 고려하지 않습니다. 하지만 이식성을 위해 **`register`** 키워드와 연결된 다른 모든 의미 체계는 컴파일러에서 적용됩니다. 예를 들어 단항 address-of 연산자( **&** )를 register 개체에 적용할 수 없거나 배열에서 **`register`** 키워드를 사용할 수 없습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[내부 수준 선언에 대한 스토리지 클래스 지정자](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
