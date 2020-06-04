---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화'
ms.date: 09/12/2018
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
ms.openlocfilehash: 987cde2117307cdb5940a31e6f01efb15c527b84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364591"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화

이 문서에서는 ActiveX 제어 인터페이스를 지역화하기 위한 절차에 대해 설명합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

ActiveX 컨트롤을 국제 시장에 적용하려면 컨트롤을 지역화할 수 있습니다. Windows는 독일어, 프랑스어 및 스웨덴어를 포함한 기본 영어 외에도 많은 언어를 지원합니다. 인터페이스가 영어로만 되어 있는 경우 컨트롤에 문제가 발생할 수 있습니다.

일반적으로 ActiveX 컨트롤은 항상 주변 LocaleID 속성을 기반으로 해야 합니다. 이때 다음과 같은 세 가지 방법을 사용할 수 있습니다.

- 주변 LocaleID 속성의 현재 값을 기반으로 항상 필요에 따라 리소스를 로드합니다. MFC ActiveX 컨트롤 샘플 [지역화는](../overview/visual-cpp-samples.md) 이 전략을 사용합니다.

- 앰비언트 LocaleID 속성을 기반으로 첫 번째 컨트롤이 인스턴스화될 때 리소스를 로드하고 다른 모든 인스턴스에 이러한 리소스를 사용합니다. 이 문서에서는 이 전략을 보여 줍니다.

    > [!NOTE]
    >  이후의 인스턴스에 다른 로캘이 있는 경우 경우에 따라 제대로 작동하지 않습니다.

- 알림 `OnAmbientChanged` 함수를 사용하여 컨테이너의 로캘에 적합한 리소스를 동적으로 로드합니다.

    > [!NOTE]
    >  컨트롤에는 효과가 있지만 런타임 DLL은 주변 LocaleID 속성이 변경될 때 자체 리소스를 동적으로 업데이트하지 않습니다. 또한 ActiveX 컨트롤용 런타임 DLL은 스레드 로캘을 사용하여 리소스에 대한 로캘을 결정합니다.

이 문서의 나머지 부분에서는 두 가지 지역화 전략에 대해 설명합니다. 첫 번째 전략은 [컨트롤의 프로그래밍 가능성](#_core_localizing_your_control.92.s_programmability_interface) 인터페이스(속성, 메서드 및 이벤트의 이름)를 지역화합니다. 두 번째 전략은 컨테이너의 주변 LocaleID 속성을 사용하여 [컨트롤의 사용자 인터페이스를 지역화합니다.](#_core_localizing_the_control.92.s_user_interface) 제어 지역화 데모는 MFC ActiveX 컨트롤 샘플 [지역화](../overview/visual-cpp-samples.md)를 참조하십시오.

## <a name="localizing-the-controls-programmability-interface"></a><a name="_core_localizing_your_control.92.s_programmability_interface"></a>컨트롤의 프로그래밍 가능성 인터페이스 지역화

컨트롤의 프로그래밍 가능성 인터페이스(컨트롤을 사용하는 응용 프로그램을 작성하는 프로그래머가 사용하는 인터페이스)를 지역화할 때 컨트롤의 수정된 버전을 만들어야 합니다. 지원하려는 각 언어에 대한 IDL 파일(제어 유형 라이브러리를 빌드하기 위한 스크립트)입니다. 컨트롤 속성 이름을 지역화하는 데 필요한 유일한 위치입니다.

지역화된 컨트롤을 개발할 때 로캘 ID를 형식 라이브러리 수준에서 특성으로 포함합니다. 예를 들어 프랑스어 지역화된 속성 이름이 있는 형식 라이브러리를 제공하려는 경우 샘플의 복사본을 만듭니다. IDL 파일, 그리고 그것을 SAMPLEFR 호출합니다. Idl. 다음과 유사한 파일에 로캘 ID 특성(프랑스어의 로캘 ID는 0x040c)을 추가합니다.

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR에서 속성 이름을 변경합니다. 프랑스어 등가물로 IDL을 사용한 다음 MKTYPLIB를 사용합니다. EXE는 프랑스어 형 라이브러리, SAMPLEFR을 생성합니다. Tlb.

여러 지역화된 형식 라이브러리를 만들려면 지역화된 모든 을 추가할 수 있습니다. 프로젝트에 IDL 파일이 자동으로 빌드됩니다.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>을 추가하려면 . ActiveX 제어 프로젝트에 대한 IDL 파일

1. 컨트롤 프로젝트를 열려 있는 경우 **프로젝트** 메뉴에서 **기존 항목 추가를**클릭합니다.

   **기존 항목 추가** 대화 상자가 나타납니다.

1. 필요한 경우 볼 드라이브및 디렉토리를 선택합니다.

1. **형식** 파일 상자에서 **모든 파일\*(. ) 을 선택합니다.\***

1. 파일 목록 상자에서 을 두 번 클릭합니다. 프로젝트에 삽입할 IDL 파일입니다.

1. 필요한 모든 것을 추가하면 **열기를** 클릭합니다. IDL 파일.

파일이 프로젝트에 추가되었기 때문에 프로젝트의 나머지 부분을 빌드할 때 파일이 빌드됩니다. 지역화된 형식 라이브러리는 현재 ActiveX 제어 프로젝트 디렉터리에 있습니다.

코드 내에서 내부 속성 이름(일반적으로 영어)은 항상 사용되며 지역화되지 않습니다. 여기에는 제어 디스패치 맵, 속성 교환 기능 및 속성 페이지 데이터 교환 코드가 포함됩니다.

하나의 형식 라이브러리(. TLB) 파일은 제어 구현의 리소스에 바인딩될 수 있습니다() OCX) 파일. 일반적으로 표준화된(일반적으로 영어) 이름이 있는 버전입니다. 지역화된 버전의 컨트롤을 제공하려면 을 발송해야 합니다. OCX(이미 기본값에 바인딩된. TLB 버전) 및 . 적절한 로캘에 대한 TLB입니다. 즉, . OCX는 올바른 이후, 영어 버전에 필요합니다. TLB는 이미 그것에 묶여 있다. 다른 로캘의 경우 지역화된 형식 라이브러리도 와 함께 제공되어야 합니다. Ocx.

컨트롤의 클라이언트가 지역화된 형식 라이브러리를 찾을 수 있도록 하려면 로캘별 을 등록합니다. Windows 시스템 레지스트리의 TypeLib 섹션 아래에 있는 TLB 파일입니다. [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) 함수의 세 번째 매개 변수(일반적으로 선택 사항)는 이 목적을 위해 제공됩니다. 다음 예제는 ActiveX 컨트롤에 대 한 프랑스어 형식 라이브러리를 등록 합니다.

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

컨트롤이 등록되면 함수가 `AfxOleRegisterTypeLib` 지정된 을 자동으로 찾습니다. 컨트롤과 동일한 디렉터리에서 TLB 파일을 Windows 등록 데이터베이스에 등록합니다. . TLB 파일을 찾을 수 없습니다.

## <a name="localizing-the-controls-user-interface"></a><a name="_core_localizing_the_control.92.s_user_interface"></a>컨트롤의 사용자 인터페이스 지역화

컨트롤의 사용자 인터페이스를 지역화하려면 컨트롤의 모든 사용자 표시 리소스(예: 속성 페이지 및 오류 메시지)를 언어별 리소스 DLL에 배치합니다. 그런 다음 컨테이너의 주변 LocaleID 속성을 사용하여 사용자의 로캘에 적합한 DLL을 선택할 수 있습니다.

다음 코드 예제에서는 특정 로캘에 대한 리소스 DLL을 찾고 로드하는 한 가지 방법을 보여 줍니다. 이 예제에서 `GetLocalizedResourceHandle` 호출되는 이 멤버 함수는 ActiveX 컨트롤 클래스의 멤버 함수일 수 있습니다.

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

스위치 문의 각 경우에 하위 언어 ID를 검사하여 보다 전문적인 지역화를 제공할 수 있습니다. 이 함수의 데모에 대 `GetResourceHandle` 한 MFC ActiveX 컨트롤 샘플 [지역화에서](../overview/visual-cpp-samples.md)함수를 참조 하십시오.

컨트롤이 먼저 컨테이너에 자신을 로드할 때 [COleControl::AmbientLocaleID를](../mfc/reference/colecontrol-class.md#ambientlocaleid) 호출하여 로캘 ID를 검색할 수 있습니다. 그런 다음 컨트롤은 반환된 로캘 `GetLocalizedResourceHandle` ID 값을 함수에 전달하여 적절한 리소스 라이브러리를 로드할 수 있습니다. 컨트롤은 결과 핸들(있는 경우)을 [AfxSetResourceHandle에](../mfc/reference/application-information-and-management.md#afxsetresourcehandle)전달해야 합니다.

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

위의 코드 샘플을 [COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite)의 재정의와 같은 컨트롤의 멤버 함수에 배치합니다. 또한 *m_hResDLL* 컨트롤 클래스의 멤버 변수여야 합니다.

컨트롤의 속성 페이지를 지역화하는 데 유사한 논리를 사용할 수 있습니다. 속성 페이지를 지역화하려면 다음 샘플과 유사한 코드를 속성 페이지의 구현 파일에 [추가합니다(COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)의 재정의)

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
