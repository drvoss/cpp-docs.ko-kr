---
title: IDispEventImpl 지원
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: 31beff30a067416f71029c18051f214c8d4429de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329319"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl 지원

템플릿 클래스 [IDispEventImpl은](../atl/reference/idispeventimpl-class.md) ATL 클래스의 연결 점 싱크에 대한 지원을 제공하는 데 사용할 수 있습니다. 연결 점 싱크를 사용하면 클래스에서 외부 COM 개체에서 발생한 이벤트를 처리할 수 있습니다. 이러한 연결 점 싱크는 클래스에서 제공하는 이벤트 싱크 맵과 함께 매핑됩니다.

클래스에 대한 연결 점 싱크를 제대로 구현하려면 다음 단계를 완료해야 합니다.

- 각 외부 개체에 대한 형식 라이브러리 가져오기

- `IDispEventImpl` 인터페이스 선언

- 이벤트 싱크 맵 선언

- 연결 지점에 대한 조언 및 조언 취소

연결 점 싱크를 구현하는 단계는 모두 클래스의 헤더 파일(.h)만 수정하여 수행됩니다.

## <a name="importing-the-type-libraries"></a>형식 라이브러리 가져오기

처리하려는 이벤트가 있는 각 외부 개체에 대해 형식 라이브러리를 가져와야 합니다. 이 단계에서는 처리할 수 있는 이벤트를 정의하고 이벤트 싱크 맵을 선언할 때 사용되는 정보를 제공합니다. [#import](../preprocessor/hash-import-directive-cpp.md) 지시문을 사용하여 이 작업을 수행할 수 있습니다. 클래스의 `#import` 헤더 파일(.h)에 지원할 각 디스패치 인터페이스에 필요한 지시서 줄을 추가합니다.

다음 예제에서는 외부 COM 서버의 형식`MSCAL.Calendar.7`라이브러리 (를 가져옵니다.

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> 지원할 각 외부 `#import` 유형 라이브러리에 대해 별도의 문이 있어야 합니다.

## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl 인터페이스 선언

각 디스패치 인터페이스의 형식 라이브러리를 가져왔으니 각 외부 `IDispEventImpl` 디스패치 인터페이스에 대해 별도의 인터페이스를 선언해야 합니다. 각 외부 개체에 대한 `IDispEventImpl` 인터페이스 선언을 추가하여 클래스의 선언을 수정합니다. 매개 변수에 대한 자세한 내용은 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)을 참조하십시오.

다음 코드는 클래스에서 `DCalendarEvents` `CMyCompositCtrl2`구현된 COM 개체에 대해 인터페이스에 대해 두 개의 연결 지점 싱크를 선언합니다.

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>이벤트 싱크 맵 선언

이벤트 알림을 적절한 함수에 의해 처리하려면 클래스에서 각 이벤트를 올바른 처리기로 라우팅해야 합니다. 이는 이벤트 싱크 맵을 선언함으로써 달성됩니다.

ATL은 이 매핑을 더 쉽게 만드는 여러 매크로, [BEGIN_SINK_MAP,](reference/composite-control-macros.md#begin_sink_map) [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)및 [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)제공합니다. 표준 형식은 다음과 같습니다.

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

다음 예제는 두 개의 이벤트 처리기를 사용 하 고 이벤트 싱크 맵을 선언 합니다.

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

구현이 거의 완료되었습니다. 마지막 단계는 외부 인터페이스의 조언과 조언에 관한 것입니다.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>IDispEventImpl 인터페이스에 대한 조언 및 조언 불문

마지막 단계는 적절한 시간에 모든 연결 지점을 조언(또는 해제)하는 메서드를 구현하는 것입니다. 외부 클라이언트와 개체 간의 통신이 수행되기 전에 이 조언을 수행해야 합니다. 개체가 표시되기 전에 개체에서 지원하는 각 외부 디스패치 인터페이스가 나가는 인터페이스에 대해 쿼리됩니다. 연결이 설정되고 나가는 인터페이스에 대한 참조가 개체의 이벤트를 처리하는 데 사용됩니다. 이 절차를 "조언"이라고 합니다.

개체가 외부 인터페이스로 완료되면 나가는 인터페이스가 클래스에서 더 이상 사용되지 않는다는 알림을 받아야 합니다. 이 프로세스를 "권장되지 않는"이라고 합니다.

COM 개체의 고유한 특성으로 인해 이 절차는 구현 간에 세부 사항및 실행 간에 다릅니다. 이러한 세부 정보는 이 항목의 범위를 벗어나지 않으며 다루지 않습니다.

## <a name="see-also"></a>참고 항목

[ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)
