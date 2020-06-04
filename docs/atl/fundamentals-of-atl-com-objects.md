---
title: ATL COM 개체의 기본 사항
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 651413534ed44143e2a0fdaf00bdabd6e5d57010
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319550"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM 개체의 기본 사항

다음 그림에서는 ATL COM 개체를 정의하는 데 사용되는 클래스와 인터페이스 간의 관계를 설명합니다.

![ATL 구조](../atl/media/vc307y1.gif "ATL 구조")

> [!NOTE]
> 이 `CComObject` 다이어그램은 멤버 `CYourClass` `CComAggObject` 변수로 포함되는 반면에서 파생된 `CComPolyObject` 것을 보여 주며 이를 보여 `CYourClass` 주며 이 다이어그램은

ATL COM 개체를 정의하는 방법에는 세 가지가 있습니다. 표준 옵션은 에서 `CComObject` `CYourClass`파생된 클래스를 사용하는 것입니다. 두 번째 옵션은 클래스를 사용하여 집계된 `CComAggObject` 개체를 만드는 것입니다. 세 번째 옵션은 클래스를 사용하는 것입니다. `CComPolyObject` `CComPolyObject`하이브리드 역할을 합니다: 처음 만들어지는 `CComObject` 방법에 `CComAggObject` 따라 클래스 또는 클래스로 작동할 수 있습니다. `CComPolyObject` 클래스를 사용하는 방법에 대한 자세한 내용은 [CComPolyObject 클래스를](../atl/reference/ccompolyobject-class.md)참조하십시오.

표준 ATL COM을 사용하는 경우 외부 개체와 내부 개체의 두 오브젝트를 사용합니다. 외부 클라이언트는 외부 개체에 정의된 래퍼 함수를 통해 내부 개체의 기능에 액세스합니다. 외부 개체는 형식입니다. `CComObject`

집계된 개체를 사용하는 경우 외부 개체는 내부 개체의 기능에 대한 래퍼를 제공하지 않습니다. 대신 외부 개체는 외부 클라이언트에서 직접 액세스하는 포인터를 제공합니다. 이 시나리오에서는 외부 개체는 `CComAggObject`형식입니다. 내부 개체는 외부 개체의 멤버 변수이며 형식입니다. `CYourClass`

클라이언트는 내부 개체와 상호 작용하기 위해 외부 개체를 통과할 필요가 없으므로 집계된 개체가 일반적으로 더 효율적입니다. 또한 외부 개체는 집계된 개체의 인터페이스를 클라이언트에서 직접 사용할 수 있다는 점을 감안할 때 집계된 개체의 기능을 알 필요가 없습니다. 그러나 모든 개체를 집계할 수 있는 것은 아닙니다. 개체를 집계하려면 집계를 염두에 두고 설계해야 합니다.

ATL은 다음 두 단계로 [I알 수 없음을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다.

- [CComObject,](../atl/reference/ccomobject-class.md) [CComAggObject](../atl/reference/ccomaggobject-class.md)또는 [CComPolyObject는](../atl/reference/ccompolyobject-class.md) 메서드를 `IUnknown` 구현합니다.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx는](../atl/reference/ccomobjectrootex-class.md) 의 참조 개수 및 외부 포인터를 `IUnknown`관리합니다.

ATL COM 개체의 다른 측면은 다른 클래스에서 처리됩니다.

- [CComCoClass는](../atl/reference/ccomcoclass-class.md) 개체의 기본 클래스 팩터리 및 집계 모델을 정의합니다.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 개체에 `IDispatch Interface` 있는 모든 이중 인터페이스 부분의 기본 구현을 제공 합니다.

- [ISupportErrorInfoImpl은](../atl/reference/isupporterrorinfoimpl-class.md) 오류 `ISupportErrorInfo` 정보가 호출 체인을 올바르게 전파할 수 있도록 하는 인터페이스를 구현합니다.

## <a name="in-this-section"></a>섹션 내용

[CComObjectRootEx 구현](../atl/implementing-ccomobjectrootex.md)<br/>
구현을 위한 예제 `CComObjectRootEx`COM 맵 항목 표시.

[CComObject, CComAggObject 및 CComPolyObject 구현](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
DECLARE_ **\*_AGGREGATABLE** 매크로의 `CComObject`사용에 미치는 영향에 `CComAggObject`대해 `CComPolyObject`설명합니다.

[IDispatch 및 IErrorInfo 지원](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
`IDispatch` 및 `IErrorInfo` 인터페이스를 지원하는 데 사용할 ATL 구현 클래스를 나열합니다.

[IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)<br/>
클래스에 대한 연결 지점을 구현하는 단계에 대해 설명합니다.

[기본 클래스 팩터리 및 집계 모델 변경](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
기본 클래스 팩터리 및 집계 모델을 변경하는 데 사용할 매크로를 표시합니다.

[집계된 개체 만들기](../atl/creating-an-aggregated-object.md)<br/>
집계된 개체를 만들기 위한 단계를 나열합니다.

## <a name="related-sections"></a>관련 단원

[ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM 개체 를 만드는 것에 대한 정보를 제공합니다.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.

## <a name="see-also"></a>참고 항목

[개념](../atl/active-template-library-atl-concepts.md)
