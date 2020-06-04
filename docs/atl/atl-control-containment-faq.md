---
title: ATL 컨트롤 포함 FAQ
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 36ff3381447b46b28908522d65be9f34fe23addf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317395"
---
# <a name="atl-control-containment-faq"></a>ATL 컨트롤 포함 FAQ

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>어떤 ATL 클래스가 ActiveX 컨트롤 포함에 도움이 되나요?

ATL의 제어 호스팅 코드는 ATL 클래스를 사용할 필요가 없습니다. **"AtlAxWin80"** 창을 만들고 필요한 경우 제어 호스팅 API를 사용할 수 있습니다(자세한 내용은 **ATL 제어 호스팅 API를**참조하십시오. 그러나 다음 클래스를 사용하면 제약 기능을 더 쉽게 사용할 수 있습니다.

|클래스|Description|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|**"AtlAxWin80"** 창을 래핑하여 창을 만들고, 컨트롤을 만들고/또는 창에 컨트롤을 연결하고, 호스트 개체에서 인터페이스 포인터를 검색하는 메서드를 제공합니다.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|**"AtlAxWinLic80"** 창을 래핑하여 창을 만들고, 컨트롤을 만들고/또는 사용이 허가된 컨트롤을 창에 연결하고, 호스트 개체에서 인터페이스 포인터를 검색하는 방법을 제공합니다.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|대화 상자 리소스를 기반으로 ActiveX 컨트롤 클래스의 기본 클래스 역할을 합니다. 이러한 컨트롤에는 다른 ActiveX 컨트롤이 포함될 수 있습니다.|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|대화 상자 리소스를 기반으로 대화 클래스에 대 한 기본 클래스 역할을 합니다. 이러한 대화 상자에는 ActiveX 컨트롤이 포함될 수 있습니다.|
|[CWindow](../atl/reference/cwindow-class.md)|호스트 창의 ID를 감안할 때 컨트롤에 인터페이스 포인터를 반환하는 [메서드인 GetDlgControl을](../atl/reference/cwindow-class.md#getdlgcontrol)제공합니다. 또한 일반적으로 Windows API 래퍼에 `CWindow` 의해 노출되어 창 관리가 더 쉬워집니다.|

## <a name="what-is-the-atl-control-hosting-api"></a>ATL 컨트롤 호스팅 API란 무엇인가요?

ATL의 제어 호스팅 API는 모든 창이 ActiveX 제어 컨테이너역할을 할 수 있도록 하는 함수 집합입니다. 이러한 함수는 소스 코드로 사용할 수 있고 ATL90.dll에서 노출되므로 정적으로 또는 동적으로 프로젝트에 연결될 수 있습니다. 컨트롤 호스팅 함수는 아래 표에 나와 있습니다.

|함수|Description|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|호스트 개체를 만들고 제공된 창에 연결한 다음 기존 컨트롤을 연결합니다.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|호스트 개체를 만들고 제공된 창에 연결한 다음 컨트롤을 로드합니다.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|라이센스가 부여된 ActiveX 컨트롤을 만들고 초기화하며 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)과 유사한 지정된 창에서 호스트합니다.|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|호스트 개체를 만들고 제공된 창에 연결한 다음 컨트롤을 로드합니다(이벤트 싱크를 설정할 수도 있음).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|라이센스가 부여된 ActiveX 컨트롤을 만들고 초기화하며 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)과 유사한 지정된 창에서 호스트합니다.|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|대화 상자 리소스에서 모덜리스 대화 상자를 만들고 창 핸들을 반환합니다.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|대화 상자 리소스에서 모달 대화 상자를 만듭니다.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|창에서 호스트된 컨트롤의 **IUnknown** 인터페이스 포인터를 반환합니다.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|창에 연결된 호스트 개체의 **IUnknown** 인터페이스 포인터를 반환합니다.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|컨트롤 호스팅 코드를 초기화합니다.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|컨트롤 호스팅 코드를 초기화하지 않습니다.|

처음 `HWND` 세 함수의 매개 변수는 거의 모든 형식의 기존 창이어야 합니다. 이러한 세 가지 함수 중 일부를 명시적으로 호출하는 경우(일반적으로 필요하지 않음) 이미 호스트 역할을 하는 창에 핸들을 전달하지 마십시오(이 경우 기존 호스트 개체는 해제되지 않음).

처음 7개의 함수는 [AtlAxWinInit을](reference/composite-control-global-functions.md#atlaxwininit) 암시적으로 호출합니다.

> [!NOTE]
> 제어 호스팅 API는 ActiveX 제어 억제에 대한 ATL의 지원의 토대를 형성합니다. 그러나 ATL의 래퍼 클래스를 활용하거나 완전히 사용하는 경우 일반적으로 이러한 함수를 직접 호출할 필요가 거의 없습니다. 자세한 내용은 [ActiveX 제어 억제를 용이하게 하는 ATL 클래스를](which-atl-classes-facilitate-activex-control-containment-q.md)참조하십시오.

## <a name="what-is-atlaxwin100"></a>AtlAxWin100이란 무엇인가요?

`AtlAxWin100`는 ATL의 제어 호스팅 기능을 제공하는 데 도움이 되는 창 클래스의 이름입니다. 이 클래스의 인스턴스를 만들 때 창 프로시저는 컨트롤 호스팅 API를 자동으로 사용하여 창과 연결된 호스트 개체를 만들고 창 제목으로 지정한 컨트롤로 로드합니다.

## <a name="when-do-i-need-to-call-atlaxwininit"></a>언제 AtlAxWinInit를 호출해야 하나요?

[AtlAxWinInit은](reference/composite-control-global-functions.md#atlaxwininit) **"AtlAxWin80"** 창 클래스(사용자 지정 창 메시지 몇 개)를 등록하므로 호스트 창을 만들기 전에 이 함수를 호출해야 합니다. 그러나 호스팅 API(및 이를 사용하는 클래스)가 이 함수를 호출하는 경우가 많기 때문에 항상 이 함수를 명시적으로 호출할 필요는 없습니다. 이 함수를 두 번 이상 호출하는 데 아무런 해가 없습니다.

## <a name="what-is-a-host-object"></a>호스트 개체란 무엇인가요?

호스트 개체는 특정 창에 대해 ATL에서 제공하는 ActiveX 컨트롤 컨테이너를 나타내는 COM 개체입니다. 호스트 개체는 컨테이너 창을 서브클래스하여 컨트롤에 메시지를 반영하고, 컨트롤에서 사용할 필수 컨테이너 인터페이스를 제공하며, [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) 및 [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) 인터페이스를 노출하여 컨트롤 환경을 구성할 수 있도록 합니다.

호스트 개체를 사용하여 컨테이너의 주변 속성을 설정할 수 있습니다.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>하나의 창에서 여러 개의 컨트롤을 호스트할 수 있나요?

단일 ATL 호스트 창에서 두 개 이상의 컨트롤을 호스트할 수 없습니다. 각 호스트 창은 한 번에 정확히 하나의 컨트롤을 유지하도록 설계되었습니다(메시지 리플렉션 및 제어별 주변 속성을 처리하기 위한 간단한 메커니즘을 허용합니다). 그러나 사용자가 단일 창에서 여러 컨트롤을 표시해야 하는 경우 해당 창의 자식으로 여러 호스트 창을 만드는 것은 간단한 문제입니다.

## <a name="can-i-reuse-a-host-window"></a>호스트 창을 다시 사용할 수 있나요?

호스트 창을 다시 사용하지 않는 것이 좋습니다. 코드의 견고성을 보장하려면 호스트 창의 수명을 단일 컨트롤의 수명과 연결해야 합니다.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>언제 AtlAxWinTerm을 호출해야 하나요?

[AtlAxWinTerm은](reference/composite-control-global-functions.md#atlaxwinterm) **"AtlAxWin80"** 창 클래스를 등록 취소합니다. 기존 호스트 창이 모두 소멸된 후 이 함수를 호출해야 합니다(호스트 창을 더 이상 만들 필요가 없는 경우). 이 함수를 호출하지 않으면 프로세스가 종료되면 창 클래스가 자동으로 등록 취소됩니다.

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅

이 섹션의 샘플에서는 AXHost를 만드는 방법과 다양한 ATL 함수를 사용하여 ActiveX 컨트롤을 호스트하는 방법을 보여 주며, 이를 보여 주실 수 있습니다. 또한 호스트되는 컨트롤에서 컨트롤 및 싱크 이벤트에 액세스하는 [방법(IDispEventImpl](../atl/reference/idispeventimpl-class.md)사용)을 보여 주기도 합니다. 샘플은 주 창 또는 자식 창에서 Calendar 컨트롤을 호스트합니다.

기호의 정의를 `USE_METHOD` 확인합니다. 이 기호의 값을 1에서 8 사이로 변경할 수 있습니다. 기호 값은 컨트롤을 만들 방법을 결정합니다.

- 의 짝수 번호 `USE_METHOD`값의 경우 호출은 호스트를 만드는 창을 하위 클래스로 만들고 이를 컨트롤 호스트로 변환합니다. 홀수 번호 값의 경우 코드는 호스트 역할을 하는 자식 창을 만듭니다.

- 1에서 `USE_METHOD` 4 사이의 값의 경우 호스트를 만드는 호출에서 이벤트의 컨트롤 및 가라앉는 에 대한 액세스가 수행됩니다. 5에서 8 사이의 값은 인터페이스에 대한 호스트를 쿼리하고 싱크를 후크합니다.

다음은 요약입니다.

|USE_METHOD|호스트|액세스 및 이벤트 싱킹 제어|기능 시연|
|-----------------|----------|--------------------------------------|---------------------------|
|1|자식 창|1단계|만들기제어LicEx|
|2|기본 창|1단계|AtlAxCreateControlLicEx|
|3|자식 창|1단계|만들기제어Ex|
|4|기본 창|1단계|AtlAxCreateControlEx|
|5|자식 창|여러 단계|컨트롤릭 만들기|
|6|기본 창|여러 단계|AtlAxCreateControlLic|
|7|자식 창|여러 단계|CreateControl|
|8|기본 창|여러 단계|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>참고 항목

[컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T 클래스](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHost윈도우인터페이스](../atl/reference/iaxwinhostwindowlic-interface.md)
