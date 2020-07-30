---
title: __based 문법
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 539ccef65477bafe2c46ce328bdaf65f52aff1b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229157"
---
# <a name="__based-grammar"></a>__based 문법

**Microsoft 전용**

기반 주소 지정은 개체가 할당된(정적 및 동적 기반 데이터) 세그먼트를 정밀하게 제어해야 할 때 유용합니다.

32 비트 및 64 비트 컴파일에서 사용할 수 있는 유일한 형태의 주소 지정은 32 비트 또는 64 비트 기반에 대 한 32 비트 또는 64 비트 변위를 포함 하는 형식을 정의 하는 "포인터 기반"입니다 **`void`** .

## <a name="grammar"></a>문법

*기반 범위 한정자*: **__based (**  *기본 식*  **)**

*base-expression*: *variablebased-declaratorsegment-namesegment-캐스트*

*기반 변수*: *식별자*

*기반-추상-선언 자*: *추상-선언 자*

*기본 형식*: *형식-이름*

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[기반 포인터](../cpp/based-pointers-cpp.md)
