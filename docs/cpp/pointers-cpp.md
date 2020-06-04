---
title: 포인터(C++)
ms.date: 11/19/2019
description: Microsoft C++의 원시 포인터 및 스마트 포인터에 대해
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 485cee667fa288bff76fdeac7c9f229355c276d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371911"
---
# <a name="pointers-c"></a>포인터(C++)

포인터는 개체의 메모리 주소를 저장하는 변수입니다. 포인터는 세 가지 주요 목적으로 C와 C++에서 광범위하게 사용됩니다.

- 힙에 새 개체를 할당하려면
- 다른 함수에 함수를 전달하기 위해
- 어레이 또는 기타 데이터 구조의 요소를 반복할 수 있습니다.

C 스타일 프로그래밍에서는 *원시 포인터가* 이러한 모든 시나리오에 사용됩니다. 그러나 원시 포인터는 많은 심각한 프로그래밍 오류의 원인입니다. 따라서 상당한 성능 이점을 제공하고 개체를 삭제하는 *소유 포인터인* 포인터에 대한 모호성이 없는 경우를 제외하고는 사용하지 않는 것이 좋습니다. 현대 C++는 개체 할당을 위한 *스마트 포인터,* 데이터 구조를 탐색하기 위한 *이터레이터* 및 함수 전달을 위한 *람다 식을* 제공합니다. 원시 포인터 대신 이러한 언어 및 라이브러리 시설을 사용하면 프로그램을 더 안전하고 디버깅하기 쉬우며 이해 및 유지 관리가 간단해집니다. 자세한 내용은 [스마트 포인터,](smart-pointers-modern-cpp.md) [이터레이터](../standard-library/iterators.md)및 [Lambda 식을](lambda-expressions-in-cpp.md) 참조하십시오.

## <a name="in-this-section"></a>섹션 내용

- [원시 포인터](raw-pointers.md)
- [Const 및 휘발성 포인터](const-and-volatile-pointers.md)
- [연산자 신규 및 삭제](new-and-delete-operators.md)
- [스마트 포인터](smart-pointers-modern-cpp.md)
- [방법: unique_ptr 인스턴스 만들기 및 사용](how-to-create-and-use-unique-ptr-instances.md)
- [방법: shared_ptr 인스턴스 만들기 및 사용](how-to-create-and-use-shared-ptr-instances.md)
- [방법: 인스턴스 만들기 및 사용 weak_ptr](how-to-create-and-use-weak-ptr-instances.md)
- [방법: CComPtr 및 CComQIPtr 인스턴스 생성 및 사용](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>참고 항목

[반복기](../standard-library/iterators.md)</br>
[람다 식](lambda-expressions-in-cpp.md)
