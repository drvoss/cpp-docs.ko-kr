---
title: 포함된 창 사용
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 5da765eae28d411c98e79af5b9173f48ea66ef8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329303"
---
# <a name="using-contained-windows"></a>포함된 창 사용

ATL 구현 포함 된 창 [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). 포함된 창은 해당 메시지를 자체 클래스에서 처리하는 대신 컨테이너 개체에 위임하는 창을 나타냅니다.

> [!NOTE]
> 포함된 창을 사용하려면 클래스를 `CContainedWindowT` 파생할 필요가 없습니다.

포함된 창을 사용하면 기존 Windows 클래스를 수퍼클래스로 분류하거나 기존 창을 하위 클래스로 분류할 수 있습니다. 기존 Windows 클래스를 수퍼클래스로 지정하는 창을 만들려면 먼저 개체에 `CContainedWindowT` 대한 생성자의 기존 클래스 이름을 지정합니다. 그런 `CContainedWindowT::Create`다음 을 호출합니다. 기존 창을 하위 클래스로 지정하려면 Windows 클래스 이름을 지정할 필요가 없습니다(NULL을 생성자에게 전달). 핸들이 `CContainedWindowT::SubclassWindow` 있는 메서드를 하위 클래스가 되는 창에 호출하기만 하면 됩니다.

일반적으로 포함된 창을 컨테이너 클래스의 데이터 멤버로 사용합니다. 컨테이너가 창일 필요는 없습니다. 그러나 [CMessageMap](../atl/reference/cmessagemap-class.md)에서 파생 되어야 합니다.

포함된 창은 대체 메시지 맵을 사용하여 메시지를 처리할 수 있습니다. 포함된 창이 두 개 이상있는 경우 각각 별도의 포함된 창에 해당하는 여러 대체 메시지 맵을 선언해야 합니다.

## <a name="example"></a>예제

다음은 두 개의 포함된 창이 있는 컨테이너 클래스의 예입니다.

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

포함된 창에 대한 자세한 내용은 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) 샘플을 참조하십시오.

## <a name="see-also"></a>참고 항목

[창 클래스](../atl/atl-window-classes.md)
