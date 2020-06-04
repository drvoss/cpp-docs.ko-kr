---
title: ATL 복사 정책 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: f40f31124d4547076249a7459ac4b63cc25305d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317388"
---
# <a name="atl-copy-policy-classes"></a>ATL 복사 정책 클래스

복사 정책 클래스는 데이터를 초기화, 복사 및 삭제하는 데 사용되는 [유틸리티 클래스입니다.](../atl/utility-classes.md) 복사 정책 클래스를 사용하면 모든 데이터 유형에 대한 복사 의미 체계를 정의하고 서로 다른 데이터 형식 간의 변환을 정의할 수 있습니다.

ATL은 다음 템플릿의 구현에서 복사 정책 클래스를 사용합니다.

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

ATL 개발자는 템플릿 인수로 전달할 수 있는 복사 정책 클래스의 데이터를 복사하거나 변환하는 데 필요한 정보를 캡슐화하여 이러한 클래스를 극도로 재사용할 수 있도록 했습니다. 예를 들어 임의의 데이터 형식을 사용하여 컬렉션을 구현해야 하는 경우 제공해야 하는 모든 것이 적절한 복사 정책입니다. 컬렉션을 구현하는 코드를 터치할 필요가 없습니다.

## <a name="definition"></a>정의

정의에 따라 다음과 같은 정적 함수를 제공하는 클래스는 복사 정책 클래스입니다.

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

형식 `DestinationType` 및 *SourceType을* 각 복사 정책에 대한 임의의 데이터 유형으로 바꿀 수 있습니다.

> [!NOTE]
> 임의의 데이터 형식에 대해 복사 정책 클래스를 정의할 수 있지만 ATL 코드에서 클래스를 사용하면 의미가 있는 형식을 제한해야 합니다. 예를 들어 ATL의 컬렉션 또는 열거체 구현과 함께 복사 정책 `DestinationType` 클래스를 사용하는 경우 COM 인터페이스 메서드에서 매개 변수로 사용할 수 있는 형식이어야 합니다.

**초기화를** 사용하여 데이터를 초기화하고, **복사하여** 데이터를 복사하고, **데이터를 해제하기** 위해 삭제합니다. 초기화, 복사 및 소멸의 정확한 의미는 복사 정책 클래스의 도메인이며 관련된 데이터 형식에 따라 달라집니다.

복사 정책 클래스의 사용 및 구현에는 두 가지 요구 사항이 있습니다.

- **복사할** 첫 번째 매개 변수는 **init을**사용하여 이전에 초기화한 데이터에 대한 포인터만 수신해야 합니다.

- **destroy는** 이전에 **초기화했거나** **복사본을**통해 복사한 데이터에 대한 포인터만 받아야 합니다.

## <a name="standard-implementations"></a>표준 구현

ATL은 `_Copy` 다음 및 `_CopyInterface` 템플릿 클래스의 형태로 두 개의 복사 정책 클래스를 제공합니다.

- 이 `_Copy` 클래스는 단일 템플릿 매개 변수만 제공하여 둘 다 `DestinationType` 및 *SourceType*을 지정하기 때문에 데이터 형식 간에 변환되지 않는 균일한 복사만 허용합니다. 이 템플릿의 일반 구현에는 초기화 또는 `memcpy` 소멸 코드가 없으며 데이터를 복사하는 데 사용됩니다. ATL은 또한 VARIANT, `_Copy` LPOLESTR, 올버브 및 CONNECTDATA 데이터 유형에 대한 전문화도 제공합니다.

- 클래스는 `_CopyInterface` 표준 COM 규칙에 따라 인터페이스 포인터를 복사하기 위한 구현을 제공합니다. 이 클래스는 다시 한 번 균일 한 복사만 허용하므로 `AddRef` 간단한 할당 및 복사 를 수행하기 위한 호출을 사용합니다.

## <a name="custom-implementations"></a>사용자 지정 구현

일반적으로 이기종 복사(즉, 데이터 형식 간의 변환)에 대해 고유한 복사 정책 클래스를 정의해야 합니다. 사용자 지정 복사 정책 클래스의 몇 가지 예에서는 [ATLCollections](../overview/visual-cpp-samples.md) 샘플에서 VCUE_Copy.h 및 VCUE_CopyString.h 파일을 살펴봅니다. 이러한 파일에는 두 개의 `GenericCopy` 템플릿 `MapCopy`복사 정책 클래스와 다양한 `GenericCopy` 데이터 형식에 대한 여러 특수화가 포함되어 있습니다.

### <a name="genericcopy"></a>제네릭 복사

`GenericCopy`을 사용하면 *SourceType* 및 `DestinationType` 템플릿 인수를 지정할 수 있습니다. 다음은 VCUE_Copy.h의 클래스의 `GenericCopy` 가장 일반적인 형태입니다.

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h에는 이 클래스의 `GenericCopy<BSTR>` `GenericCopy<VARIANT, BSTR>`다음 전문화 항목도 포함되어 `GenericCopy<BSTR, VARIANT>`있습니다. VCUE_CopyString.h는 **std:::string**s: `GenericCopy<std::string>`및 `GenericCopy<VARIANT, std::string>`. `GenericCopy<BSTR, std::string>` 당신은 당신의 `GenericCopy` 자신의 추가 전문화를 제공함으로써 향상시킬 수 있습니다.

### <a name="mapcopy"></a>맵복사

`MapCopy`복사할 데이터가 C++ 표준 라이브러리 스타일 맵에 저장된다고 가정하므로 데이터가 저장되는 맵 유형과 대상 유형을 지정할 수 있습니다. 클래스의 구현은 *MapType* 클래스에서 제공하는 typedefs를 사용하여 원본 데이터의 형식을 확인하고 적절한 `GenericCopy` 클래스를 호출합니다. 이 클래스의 전문화는 필요하지 않습니다.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리 기반 컬렉션 구현](../atl/implementing-an-stl-based-collection.md)<br/>
[ATL컬렉션 샘플](../overview/visual-cpp-samples.md)
