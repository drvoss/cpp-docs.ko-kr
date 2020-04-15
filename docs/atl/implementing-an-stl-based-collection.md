---
title: C++ 표준 라이브러리 기반 컬렉션 구현
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: e80ce5e7bbc6b9c6be1615dad1ea43c18e03eb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319435"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ 표준 라이브러리 기반 컬렉션 구현

ATL은 `ICollectionOnSTLImpl` 개체에 C++ 표준 라이브러리 기반 컬렉션 인터페이스를 신속하게 구현할 수 있는 인터페이스를 제공합니다. 이 클래스의 작동 방식을 이해하려면 이 클래스를 사용하여 자동화 클라이언트를 대상으로 한 읽기 전용 컬렉션을 구현하는 간단한 예제(아래)를 통해 작업합니다.

샘플 코드는 [ATLCollections 샘플에서 입력합니다.](../overview/visual-cpp-samples.md)

이 절차를 완료하려면 다음을 수행합니다.

- [새 단순 개체를 생성합니다.](#vccongenerating_an_object)

- 생성된 인터페이스에 대한 [IDL 파일을 편집합니다.](#vcconedit_the_idl)

- 컬렉션 항목이 저장되는 방법과 COM 인터페이스를 통해 클라이언트에 노출되는 방법을 설명하는 [5가지 typedefs를 만듭니다.](#vcconstorage_and_exposure_typedefs)

- [복사 정책 클래스에 대해 두 개의 형식 defs를 만듭니다.](#vcconcopy_classes)

- [열거형 및 컬렉션 구현에 대한 형식 defs를 만듭니다.](#vcconenumeration_and_collection)

- [마법사에서 생성된 C++ 코드를 편집하여 컬렉션 형식def를 사용합니다.](#vcconedit_the_generated_code)

- [컬렉션을 채우는 코드를 추가합니다.](#vcconpopulate_the_collection)

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a>새 간단한 개체 생성

응용 프로그램 설정에서 특성 상자를 지우도록 새 프로젝트를 만듭니다. ATL 클래스 추가 대화 상자를 사용하고 간단한 개체 마법사를 `Words`추가하여 . 라는 `IWords` 이중 인터페이스가 생성되는지 확인합니다. 생성된 클래스의 개체는 단어(즉, 문자열)의 컬렉션을 나타내는 데 사용됩니다.

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a>IDL 파일 편집

이제 IDL 파일을 열고 아래와 같이 읽기 `IWords` 전용 컬렉션 인터페이스로 전환하는 데 필요한 세 가지 속성을 추가합니다.

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

이 형식은 자동화 클라이언트를 염두에 두고 설계된 읽기 전용 컬렉션 인터페이스의 표준 양식입니다. 이 인터페이스 정의의 번호가 매겨진 주석은 아래 주석에 해당합니다.

1. 자동화 클라이언트가 을 통해 `_NewEnum` `IDispatch::Invoke`속성에 액세스하기 때문에 컬렉션 인터페이스는 일반적으로 이중입니다. 그러나 자동화 클라이언트는 vtable을 통해 나머지 메서드에 액세스할 수 있으므로 이중 인터페이스는 인터페이스를 분리하는 것이 좋습니다.

1. 이중 인터페이스 또는 dispinterface런 타임에 확장 되지 않습니다 (즉, 추가 메서드 또는 `IDispatch::Invoke`속성을 통해 제공 하지 않습니다)) 정의에 **무분별 한** 특성을 적용 해야 합니다. 이 특성을 사용하면 Automation 클라이언트가 컴파일 시 전체 코드 확인을 수행할 수 있습니다. 이 경우 인터페이스를 확장하면 안 됩니다.

1. 자동화 클라이언트가 이 속성을 사용할 수 있도록 하려면 올바른 DISPID가 중요합니다. (DISPID_NEWENUM 하나의 밑줄만 있습니다.)

1. `Item` 속성의 DISPID로 모든 값을 제공할 수 있습니다. 그러나 `Item` 일반적으로 DISPID_VALUE 사용 하 여 컬렉션의 기본 속성으로 만듭니다. 이렇게 하면 자동화 클라이언트가 명시적으로 이름을 지정하지 않고 속성을 참조할 수 있습니다.

1. `Item` 속성의 반환 값에 사용되는 데이터 형식은 COM 클라이언트와 관련된 한 컬렉션에 저장된 항목의 형식입니다. 인터페이스는 문자열을 반환하므로 표준 COM 문자열 유형인 BSTR을 사용해야 합니다. 곧 보게 될 것처럼 데이터를 내부적으로 다른 형식으로 저장할 수 있습니다.

1. 속성의 DISPID에 사용되는 `Count` 값은 완전히 임의적입니다. 이 속성에 대 한 표준 DISPID 없습니다.

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a>저장 및 노출을 위한 타이프스생성

수집 인터페이스가 정의되면 데이터가 저장되는 방법과 열거체를 통해 데이터가 노출되는 방법을 결정해야 합니다.

이러한 질문에 대한 답변은 새로 만든 클래스의 헤더 파일 상단 근처에 추가할 수 있는 여러 typedefs 형식으로 제공될 수 있습니다.

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

이 경우 **std::string s의 std::vector로** 데이터를 저장합니다. **std::string** **std::vector는** 관리되는 배열처럼 행동하는 C++ 표준 라이브러리 컨테이너 클래스입니다. **std::문자열은** C++ 표준 라이브러리의 문자열 클래스입니다. 이러한 클래스를 사용하면 문자열 컬렉션을 쉽게 작업할 수 있습니다.

Visual Basic 지원은 이 인터페이스의 성공에 필수적이므로 속성에서 `_NewEnum` 반환하는 열거자는 `IEnumVARIANT` 인터페이스를 지원해야 합니다. 이것은 Visual Basic에서 이해하는 유일한 열거자 인터페이스입니다.

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a>복사 정책 클래스에 대한 형식 defs 만들기

지금까지 만든 typedefs는 열거자 및 컬렉션에서 사용할 복사 클래스에 대한 추가 typedefs를 만드는 데 필요한 모든 정보를 제공합니다.

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

이 예제에서는 `GenericCopy` [ATLCollections](../overview/visual-cpp-samples.md) 샘플에서 VCUE_Copy.h 및 VCUE_CopyString.h에 정의된 사용자 지정 클래스를 사용할 수 있습니다. 다른 코드에서 이 클래스를 사용할 수 있지만 사용자 고유의 `GenericCopy` 컬렉션에 사용되는 데이터 형식을 지원하기 위해 추가 전문화 를 정의해야 할 수 있습니다. 자세한 내용은 [ATL 복사 정책 클래스를](../atl/atl-copy-policy-classes.md)참조하십시오.

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a>열거형 및 컬렉션에 대한 형식 defs 만들기

이제 이 상황에 대한 `CComEnumOnSTL` 및 `ICollectionOnSTLImpl` 클래스를 전문으로 하는 데 필요한 모든 템플릿 매개 변수가 typedefs 형식으로 제공되었습니다. 전문화 프로그램의 사용을 단순화하려면 아래와 같이 두 개의 typedefs를 더 만듭니다.

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

이제 `CollectionType` 앞에서 정의한 `ICollectionOnSTLImpl` `IWords` 인터페이스를 구현하고 를 지원하는 `IEnumVARIANT`열거형을 제공하는 전문화 전문화의 동의어입니다.

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a>마법사 생성 코드 편집

이제 아래와 `CWords` 같이 `CollectionType` typedef가 아닌 `IWords`typedef로 표시되는 인터페이스 구현에서 파생되어야 합니다.

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a>컬렉션 채우기 위한 코드 추가

남은 것은 벡터를 데이터로 채우는 것입니다. 이 간단한 예제에서는 클래스에 대 한 생성자의 컬렉션에 몇 가지 단어를 추가할 수 있습니다.

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

이제 선택한 클라이언트로 코드를 테스트할 수 있습니다.

## <a name="see-also"></a>참고 항목

[컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)<br/>
[ATL컬렉션 샘플](../overview/visual-cpp-samples.md)<br/>
[ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md)
