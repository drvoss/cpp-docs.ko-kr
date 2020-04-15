---
title: 컴포지트 컨트롤에 기능 추가
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 5de18f863831973af384d2456adb5b2214f0dd68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317423"
---
# <a name="adding-functionality-to-the-composite-control"></a>컴포지트 컨트롤에 기능 추가

복합 컨트롤에 필요한 컨트롤을 삽입한 후 다음 단계에서는 새 기능을 추가해야 합니다. 이 새로운 기능은 일반적으로 두 가지 범주로 나뉩니다.

- 추가 인터페이스를 지원하고 특정 기능을 추가로 사용하여 복합 제어의 동작을 사용자 지정합니다.

- 포함된 ActiveX 컨트롤(또는 컨트롤)의 이벤트를 처리합니다.

이 문서의 목적과 범위를 위해 이 섹션의 나머지 부분에서는 ActiveX 컨트롤의 이벤트를 처리하는 데만 중점을 둡니다.

> [!NOTE]
> Windows 컨트롤의 메시지를 처리해야 하는 경우 ATL의 메시지 처리에 대한 자세한 내용은 [창 구현을](../atl/implementing-a-window.md) 참조하십시오.

대화 상자 리소스에 ActiveX 컨트롤을 삽입한 후 컨트롤을 마우스 오른쪽 단추로 클릭하고 **이벤트 처리기 추가를**클릭합니다. 처리할 이벤트를 선택하고 **추가 및 편집을**클릭합니다. 이벤트 처리기 코드가 컨트롤의 .h 파일에 추가됩니다.

복합 제어의 ActiveX 컨트롤에 대한 연결 지점은 [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)에 대한 호출을 통해 자동으로 연결되고 연결이 끊어집니다.

## <a name="see-also"></a>참고 항목

[복합 컨트롤 기본 사항](../atl/atl-composite-control-fundamentals.md)
