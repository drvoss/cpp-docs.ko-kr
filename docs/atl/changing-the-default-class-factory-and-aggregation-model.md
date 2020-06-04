---
title: 기본 클래스 팩터리 및 집계 모델 변경
ms.date: 11/04/2016
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
ms.openlocfilehash: 94f9ecd85e09cb3916b518d71b904961042142e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223159"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>기본 클래스 팩터리 및 집계 모델 변경

ATL은 개체에 대한 기본 클래스 팩터리 및 집계 모델을 정의하기 위해 [CComCoClass](../atl/reference/ccomcoclass-class.md)를 사용합니다. `CComCoClass`는 다음 두 매크로를 지정합니다.

- [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) 클래스 팩터리를 [CComClassFactory](../atl/reference/ccomclassfactory-class.md)가 되도록 선언합니다.

- [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) 개체를 집계될 수 있도록 선언 합니다.


클래스 정의에서 다른 매크로를 지정하여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 들어 `CComClassFactory` 대신 [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md)를 사용하려면 [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로를 지정합니다.

[!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]

클래스 팩터리를 정의 하는 다른 두 매크로 [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 하 고 [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton)합니다.

ATL은 또한 **typedef** 매커니즘을 사용하여 기본 동작을 구현합니다. 예를 들어 DECLARE_AGGREGATABLE 매크로는 **typedef**를 사용하여 `_CreatorClass`라는 형식을 정의한 다음 ATL 전체에서 참조합니다. 파생된 클래스에서, 기본 클래스의 **typedef**와 동일한 이름을 사용하는 **typedef**의 경우, ATL은 해당 정의를 사용하고 기본 동작을 재정의합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)<br/>
[집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)
