---
title: '방법: 형식이 안전한 컬렉션 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: 1901100996a776244b57efe0951795ceec3c630a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377257"
---
# <a name="how-to-make-a-type-safe-collection"></a>방법: 형식이 안전한 컬렉션 만들기

이 문서에서는 사용자 고유의 데이터 형식에 대해 형식 이 안전한 컬렉션을 만드는 방법을 설명합니다. 다룰 주제는 다음과 같습니다.

- [형식 안전성에 템플릿 기반 클래스 사용](#_core_using_template.2d.based_classes_for_type_safety)

- [도우미 기능 구현](#_core_implementing_helper_functions)

- [템플릿이 아닌 컬렉션 클래스 사용](#_core_using_nontemplate_collection_classes)

Microsoft 재단 클래스 라이브러리는 C++ 템플릿을 기반으로 미리 정의된 형식 안전 컬렉션을 제공합니다. 템플릿이기 때문에 이러한 클래스는 형식 캐스팅 및 이 목적을 위해 비템플릿 클래스를 사용하는 데 관련된 기타 추가 작업 없이 형식 안전성과 사용 편의성을 제공하는 데 도움이 됩니다. MFC 샘플 [COLLECT는](../overview/visual-cpp-samples.md) MFC 응용 프로그램에서 템플릿 기반 컬렉션 클래스의 사용을 보여 줍니다. 일반적으로 새 컬렉션 코드를 작성할 때마다 이러한 클래스를 사용합니다.

## <a name="using-template-based-classes-for-type-safety"></a><a name="_core_using_template.2d.based_classes_for_type_safety"></a>형식 안전을 위해 템플릿 기반 클래스 사용

#### <a name="to-use-template-based-classes"></a>템플릿 기반 클래스를 사용하려면

1. 컬렉션 클래스 형식의 변수를 선언합니다. 다음은 그 예입니다.

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. 컬렉션 개체의 멤버 함수를 호출합니다. 다음은 그 예입니다.

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. 필요한 경우 [도우미 함수및](../mfc/reference/collection-class-helpers.md) [직렬화요소를](../mfc/reference/collection-class-helpers.md#serializeelements)구현합니다. 이러한 함수 구현에 대한 자세한 내용은 [도우미 기능 구현을](#_core_implementing_helper_functions)참조하십시오.

이 예제에서는 정수 목록의 선언을 보여 주십습니다. 1단계의 첫 번째 매개 변수는 목록의 요소로 저장된 데이터 유형입니다. 두 번째 매개 변수는 데이터를 컬렉션 클래스의 멤버 함수(예: `Add` 및)에 `GetAt`전달하고 반환하는 방법을 지정합니다.

## <a name="implementing-helper-functions"></a><a name="_core_implementing_helper_functions"></a>도우미 기능 구현

템플릿 기반 컬렉션 `CArray` `CList`클래스는 `CMap` 파생 컬렉션 클래스에 필요에 따라 사용자 지정할 수 있는 5개의 전역 도우미 함수를 사용합니다. 이러한 도우미 기능에 대한 자세한 내용은 *MFC 참조의* [컬렉션 클래스 도우미를](../mfc/reference/collection-class-helpers.md) 참조하십시오. 템플릿 기반 컬렉션 클래스의 대부분의 용도에 는 직렬화 함수의 구현이 필요합니다.

### <a name="serializing-elements"></a><a name="_core_serializing_elements"></a>요소 직렬화

의 `CArray` `CList`에서 `CMap` 및 `SerializeElements` 클래스는 컬렉션 요소를 저장하거나 아카이브에서 읽도록 호출합니다.

`SerializeElements` 도우미 함수의 기본 구현은 개체에서 아카이브로 비트를 쓰거나 개체가 아카이브에서 저장되거나 아카이브에서 검색되는지 여부에 따라 아카이브에서 개체로 비트 읽기를 수행합니다. 이 `SerializeElements` 작업이 적절하지 않은 경우 재정의합니다.

컬렉션에서 `CObject` 파생된 개체를 저장하고 `IMPLEMENT_SERIAL` 컬렉션 요소 클래스의 구현에서 매크로를 사용하는 경우 다음과 같은 `CArchive` `CObject`기능을 기본으로 하는 직렬화 기능을 활용할 수 있습니다.

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

각 `CArchive` `CPerson` 개체에 대해 호출(또는 `CObject::Serialize` 해당 함수의 재정의)에 대한 오버로드된 삽입 연산자입니다.

## <a name="using-nontemplate-collection-classes"></a><a name="_core_using_nontemplate_collection_classes"></a>템플릿이 아닌 컬렉션 클래스 사용

MFC는 MFC 버전 1.0에 도입된 컬렉션 클래스도 지원합니다. 이러한 클래스는 템플릿을 기반으로 하지 않습니다. 지원되는 `CObject*`형식 의 데이터를 포함하는 `UINT`데 `DWORD`사용할 `CString`수 있습니다. 이러한 미리 정의된 컬렉션(예: `CObList`)을 사용하여 `CObject`에서 파생된 모든 개체의 컬렉션을 보유할 수 있습니다. MFC는 또한 `UINT` *와 같은 기본 형식 및 void 포인터를`void`보유하는 다른 미리 정의된 컬렉션을 제공합니다. 그러나 일반적으로 보다 구체적인 클래스와 해당 파생 상품의 개체를 보유하도록 고유한 형식 안전 컬렉션을 정의하는 것이 유용한 경우가 많습니다. 템플릿을 기반으로 하지 않는 컬렉션 클래스를 사용하면 템플릿 기반 클래스를 사용하는 것보다 더 많은 작업이 수행됩니다.

템플릿이 아닌 컬렉션을 사용하여 형식 이용성 컬렉션을 만드는 방법에는 두 가지가 있습니다.

1. 필요한 경우 형식 캐스팅과 함께 템플릿이 아닌 컬렉션을 사용합니다. 이것은 더 쉬운 방법입니다.

1. 템플릿이 아닌 형식 이안전 컬렉션에서 파생및 확장합니다.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>형식 캐스팅이 있는 템플릿이 아닌 컬렉션을 사용하려면

1. 에 직접 와 같은 `CWordArray`템플릿이 아닌 클래스 중 하나를 사용합니다.

   예를 들어 32비트 `CWordArray` 값을 만들고 추가한 다음 검색할 수 있습니다. 더 이상 할 일은 없습니다. 미리 정의된 기능만 사용합니다.

   에서 파생된 모든 개체를 보유하는 것과 같이 `CObList`미리 `CObject`정의된 컬렉션을 사용할 수도 있습니다. 컬렉션은 `CObList` `CObject`에 대한 포인터를 보유하도록 정의됩니다. 목록에서 개체를 검색할 때 `CObList` 함수가 포인터를 에 반환하기 때문에 결과를 적절한 유형으로 캐스팅해야 할 `CObject`수 있습니다. 예를 들어 컬렉션에 `CPerson` 개체를 `CObList` 저장하는 경우 개체에 대한 포인터로 `CPerson` 검색된 요소를 캐스팅해야 합니다. 다음 예제에서는 `CObList` 컬렉션을 사용하여 `CPerson` 개체를 보유합니다.

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   미리 정의된 컬렉션 형식을 사용하고 필요에 따라 캐스팅하는 이 기술은 많은 컬렉션 요구에 적합할 수 있습니다. 추가 기능 또는 더 많은 형식 안전이 필요한 경우 템플릿 기반 클래스를 사용하거나 다음 절차를 따르십시오.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>템플릿이 아닌 형식 이안전 컬렉션을 파생하고 확장하려면

1. 미리 정의된 비템플릿 클래스 중 하나에서 사용자 고유의 컬렉션 클래스를 파생합니다.

   클래스를 파생할 때 형식이 안전한 래퍼 함수를 추가하여 기존 함수에 형식이 안전한 인터페이스를 제공할 수 있습니다.

   예를 들어 개체를 `CObList` 보유할 `CPerson` 목록에서 목록을 파생한 경우 아래와 `AddHeadPerson` 같이 `GetHeadPerson`래퍼 함수 및 을 추가할 수 있습니다.

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   이러한 래퍼 함수는 파생 된 목록에서 개체를 `CPerson` 추가 하 고 검색 하는 형식 안전 방법을 제공 합니다. 함수의 `GetHeadPerson` 경우 형식 캐스팅을 캡슐화하는 것만으로 볼 수 있습니다.

   또한 형식이 안전한 래퍼에서 기존 기능을 래핑하는 대신 컬렉션의 기능을 확장하는 새 기능을 정의하여 새 기능을 추가할 수도 있습니다. 예를 들어 [CObject 컬렉션의 모든 개체 삭제](../mfc/deleting-all-objects-in-a-cobject-collection.md) 문서에서는 목록에 포함된 모든 개체를 삭제하는 함수를 설명합니다. 이 함수는 파생 클래스에 멤버 함수로 추가할 수 있습니다.

## <a name="see-also"></a>참고 항목

[컬렉션](../mfc/collections.md)
