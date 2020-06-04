---
title: 'MFC ActiveX 컨트롤: Serialize'
ms.date: 09/12/2018
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
ms.openlocfilehash: d804486b612906f537b6ed1665dfc0cec5149826
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364546"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX 컨트롤: Serialize

이 문서에서는 ActiveX 컨트롤을 직렬화하는 방법에 대해 설명합니다. 직렬화는 디스크 파일과 같은 영구 저장소 매체를 읽거나 쓰는 프로세스입니다. Microsoft 파운데이션 클래스(MFC) 라이브러리는 클래스의 `CObject`직렬화를 위한 기본 제공 지원을 제공합니다. `COleControl`속성 교환 메커니즘을 사용하여 ActiveX 컨트롤로 이 지원을 확장합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

ActiveX 컨트롤에 대한 직렬화는 [COleControl::DoPropExchange를](../mfc/reference/colecontrol-class.md#dopropexchange)재정의하여 구현됩니다. 컨트롤 개체를 로드하고 저장하는 동안 호출되는 이 함수는 멤버 변수 또는 멤버 변수로 구현된 모든 속성을 변경 알림과 함께 저장합니다.

다음 항목에서는 ActiveX 컨트롤 직렬화와 관련된 주요 문제를 다룹니다.

- 컨트롤 `DoPropExchange` 개체를 직렬화하는 함수 구현

- [직렬화 프로세스 사용자 지정](#_core_customizing_the_default_behavior_of_dopropexchange)

- [버전 지원 구현](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>DoPropExchange 함수 구현

ActiveX 컨트롤 마법사를 사용하여 제어 프로젝트를 생성하면 [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)의 기본 구현을 포함하여 여러 기본 처리기 함수가 컨트롤 클래스에 자동으로 추가됩니다. 다음 예제에서는 ActiveX 컨트롤 마법사로 만든 클래스에 추가된 코드를 보여 주며,

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

속성을 영구적으로 만들려면 속성 교환 `DoPropExchange` 함수에 호출을 추가하여 수정합니다. 다음 예제에서는 CircleShape 속성의 기본값이 **TRUE인**사용자 지정 부울 CircleShape 속성의 직렬화를 보여 줍니다.

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

다음 표에는 컨트롤의 속성을 직렬화하는 데 사용할 수 있는 속성 교환 함수가 나열되어 있습니다.

|부동산 교환 기능|용도|
|---------------------------------|-------------|
|**PX_Blob () )**|BLOB(이진 대문자) 데이터 속성을 직렬화합니다.|
|**PX_Bool ()**|부울 형식 속성을 직렬화합니다.|
|**PX_Color () )**|형식 색상 속성을 직렬화합니다.|
|**PX_Currency () )**|유형 **CY(통화)** 속성을 직렬화합니다.|
|**PX_Double () )**|형식 **이중** 속성을 직렬화합니다.|
|**PX_Font ()**|글꼴 유형 속성을 직렬화합니다.|
|**PX_Float () )**|형식 **float** 속성을 직렬화합니다.|
|**PX_IUnknown ()**|형식의 `LPUNKNOWN`속성을 직렬화합니다.|
|**PX_Long ()**|형식 **long** 속성을 직렬화합니다.|
|**PX_Picture () )**|유형 그림 속성을 직렬화합니다.|
|**PX_Short () )**|형식 **짧은** 속성을 직렬화합니다.|
|**PXstring () )**|형식 `CString` 속성을 직렬화합니다.|
|**PX_ULong () )**|형식 **ULONG** 속성을 직렬화합니다.|
|**PX_UShort ()**|**USHORT** 형식 속성을 직렬화합니다.|

이러한 속성 교환 함수에 대한 자세한 내용은 *MFC 참조에서* [OLE 컨트롤의 지속성을](../mfc/reference/persistence-of-ole-controls.md) 참조하십시오.

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>DoPropExchange의 기본 동작 사용자 지정

(이전 항목에 `DoPropertyExchange` 도시 된 대로)의 기본 구현 기본 `COleControl`클래스에 대 한 호출을 만듭니다. 이렇게 하면 컨트롤의 사용자 지정 속성만 직렬화하는 것보다 더 많은 저장소 공간을 사용하는 `COleControl`에서 자동으로 지원되는 속성 집합을 직렬화합니다. 이 호출을 제거하면 개체가 중요하게 간주하는 속성만 직렬화할 수 있습니다. 컨트롤에 대 한 호출을 명시적으로 **PX_** 추가 하지 않는 한 컨트롤을 저장 하거나 로드 할 때 컨트롤이 구현 된 모든 stock 속성 상태 직렬화 되지 않습니다.

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>버전 지원 구현

버전 지원을 사용하면 수정된 ActiveX 컨트롤을 사용하여 새 영구 속성을 추가할 수 있으며 이전 버전의 컨트롤에서 만든 영구 상태를 검색하고 로드할 수 있습니다. 컨트롤의 버전을 영구 데이터의 일부로 사용할 수 있도록 하려면 컨트롤 `DoPropExchange` 함수에서 [COleControl::ExchangeVersion을](../mfc/reference/colecontrol-class.md#exchangeversion) 호출합니다. ActiveX 컨트롤 마법사를 사용하여 ActiveX 컨트롤을 만든 경우 이 호출이 자동으로 삽입됩니다. 버전 지원이 필요하지 않은 경우 제거할 수 있습니다. 그러나 제어 크기의 비용은 버전 지원에서 제공하는 추가 유연성을 위해 매우 작습니다(4바이트).

ActiveX 컨트롤 마법사로 컨트롤을 만들지 않은 경우 `COleControl::ExchangeVersion` `DoPropExchange` 함수 시작 시 다음 줄을 삽입하여 다음 을 `COleControl::DoPropExchange`호출합니다( 호출 전) :

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

모든 **DWORD를** 버전 번호로 사용할 수 있습니다. ActiveX 컨트롤 마법사에서 생성한 `_wVerMajor` 프로젝트가 기본값으로 사용됩니다. `_wVerMinor` 이러한 상수는 프로젝트의 ActiveX 제어 클래스의 구현 파일에 정의된 전역 상수입니다. `DoPropExchange` 함수의 나머지 부분에서 는 언제든지 [CPropExchange::GetVersion를](../mfc/reference/cpropexchange-class.md#getversion) 호출하여 저장하거나 검색하는 버전을 검색할 수 있습니다.

다음 예제에서는 이 샘플 컨트롤의 버전 1에는 "ReleaseDate" 속성만 있습니다. 버전 2는 "OriginalDate" 속성을 추가합니다. 컨트롤이 이전 버전에서 영구 상태를 로드하도록 지시되면 새 속성에 대한 멤버 변수를 기본값으로 초기화합니다.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

기본적으로 컨트롤은 이전 데이터를 최신 형식으로 "변환"합니다. 예를 들어 컨트롤의 버전 2가 버전 1에 의해 저장된 데이터를 로드하는 경우 다시 저장될 때 버전 2 형식을 작성합니다. 컨트롤이 마지막 읽기 형식으로 데이터를 저장하도록 하려면 **FALSE를** 호출할 `ExchangeVersion`때 세 번째 매개 변수로 전달합니다. 이 세 번째 매개 변수는 선택 사항이며 기본적으로 **TRUE입니다.**

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
