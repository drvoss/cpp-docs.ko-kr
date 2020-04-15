---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스'
ms.date: 11/19/2018
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: aaab4ae3bb13790784a66d53b41dbc3a7cdaec89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364614"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스

ActiveX 컨트롤의 선택적 기능인 라이선스 지원을 사용하면 컨트롤을 사용하거나 배포할 수 있는 사람을 제어할 수 있습니다. 라이선스 문제에 대한 추가 설명은 [기존 ActiveX 컨트롤 업그레이드시](../mfc/upgrading-an-existing-activex-control.md)라이선스 문제를 참조하십시오.

> [!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

이 문서는 다음 항목을 설명합니다.

- [ActiveX 제어 라이선싱 개요](#_core_overview_of_activex_control_licensing)

- [라이센스가 부여된 컨트롤 만들기](#_core_creating_a_licensed_control)

- [라이선싱 지원](#_core_licensing_support)

- [ActiveX 컨트롤의 라이선스 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control)

라이선스를 구현하는 ActiveX 컨트롤을 사용하면 컨트롤 개발자로서 다른 사용자가 ActiveX 컨트롤을 사용하는 방법을 결정할 수 있습니다. 컨트롤 구매자에게 컨트롤 및 을 제공합니다. LIC 파일, 구매자가 컨트롤을 배포할 수 있지만. 제어를 사용하는 응용 프로그램과 함께 LIC 파일입니다. 이렇게 하면 해당 응용 프로그램의 사용자가 컨트롤에 대한 라이선스를 먼저 부여하지 않고 컨트롤을 사용하는 새 응용 프로그램을 작성할 수 없습니다.

## <a name="overview-of-activex-control-licensing"></a><a name="_core_overview_of_activex_control_licensing"></a>ActiveX 제어 라이선싱 개요

ActiveX 컨트롤에 대한 라이선싱 지원을 제공하기 위해 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) 클래스는 `IClassFactory2` `IClassFactory2::RequestLicKey`인터페이스의 `IClassFactory2::GetLicInfo` `IClassFactory2::CreateInstanceLic`여러 기능에 대한 구현을 제공합니다. 컨테이너 응용 프로그램 개발자가 컨트롤의 인스턴스를 만들기 위해 `GetLicInfo` 요청을 하면 컨트롤이 있는지 확인하기 위해 호출이 이루어집니다. LIC 파일이 있습니다. 컨트롤에 라이선스가 부여된 경우 컨트롤의 인스턴스를 만들고 컨테이너에 배치할 수 있습니다. 개발자가 컨테이너 응용 프로그램 생성을 완료한 후 이번에는 `RequestLicKey`다른 함수 호출이 만들어집니다. 이 함수는 라이센스 키(간단한 문자열)를 컨테이너 응용 프로그램에 반환합니다. 그러면 반환된 키가 응용 프로그램에 포함됩니다.

아래 그림은 컨테이너 응용 프로그램을 개발하는 동안 사용할 ActiveX 컨트롤의 라이센스 확인을 보여 줍니다. 앞에서 설명한 것처럼 컨테이너 응용 프로그램 개발자는 적절한 . 컨트롤의 인스턴스를 만들기 위해 개발 컴퓨터에 설치된 LIC 파일입니다.

![허가된 ActiveX 컨트롤이 개발 시 확인됨](../mfc/media/vc374d1.gif "허가된 ActiveX 컨트롤이 개발 시 확인됨") <br/>
개발 도중 사용이 허가된 ActiveX 컨트롤 확인

다음 그림에 표시된 다음 프로세스는 최종 사용자가 컨테이너 응용 프로그램을 실행할 때 발생합니다.

응용 프로그램이 시작되면 일반적으로 컨트롤의 인스턴스를 만들어야 합니다. 컨테이너는 매개 변수로 포함된 `CreateInstanceLic`라이센스 키를 전달하여 호출하여 이 작업을 수행합니다. 그런 다음 포함된 라이센스 키와 컨트롤의 라이선스 키 복사본 간에 문자열 비교가 이루어집니다. 일치가 성공하면 컨트롤의 인스턴스가 만들어지고 응용 프로그램이 정상적으로 계속 실행됩니다. 을 참조하십시오. 제어 사용자의 컴퓨터에 LIC 파일이 있을 필요가 없습니다.

![허가된 ActiveX 컨트롤이 실행 시 확인됨](../mfc/media/vc374d2.gif "허가된 ActiveX 컨트롤이 실행 시 확인됨") <br/>
실행 도중 사용이 허가된 ActiveX 컨트롤 확인

제어 라이선스는 컨트롤 구현 DLL의 특정 코드와 라이센스 파일의 두 가지 기본 구성 요소로 구성됩니다. 코드는 두 개의 함수 호출과 문자열 문자열로 구성되며, 이 에 따라 저작권 고지가 포함된 "라이센스 문자열"이라고 합니다. 이러한 호출 및 라이센스 문자열은 컨트롤 구현() CPP) 파일. ActiveX 컨트롤 마법사에서 생성한 라이센스 파일은 저작권 문이 있는 텍스트 파일입니다. 프로젝트 이름을 사용하여 명명됩니다. LIC 확장, 예를 들어 샘플. Lic. 디자인 타임 사용이 필요한 경우 라이센스 컨트롤과 함께 사용이 허가되어야 합니다.

## <a name="creating-a-licensed-control"></a><a name="_core_creating_a_licensed_control"></a>라이센스가 부여된 컨트롤 만들기

ActiveX 컨트롤 마법사를 사용하여 제어 프레임워크를 만들면 라이선스 지원을 쉽게 포함할 수 있습니다. 컨트롤에 런타임 라이선스가 있어야 한다고 지정하면 ActiveX 컨트롤 마법사가 라이선스를 지원하기 위해 컨트롤 클래스에 코드를 추가합니다. 코드는 라이센스 확인을 위해 키 및 라이센스 파일을 사용하는 기능으로 구성됩니다. 이러한 함수는 컨트롤 라이선스를 사용자 지정하도록 수정할 수도 있습니다. 라이선스 사용자 지정에 대한 자세한 내용은 이 문서의 후반부에서 [ActiveX 컨트롤의 라이선스 사용자 지정을](#_core_customizing_the_licensing_of_an_activex_control) 참조하세요.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>컨트롤 프로젝트를 만들 때 ActiveX 제어 마법사를 사용하여 라이선스 에 대한 지원을 추가하려면

1. [MFC ActiveX 컨트롤 만들기의](../mfc/reference/creating-an-mfc-activex-control.md)지침을 사용합니다. ActiveX 제어 마법사의 **응용 프로그램 설정** 페이지에는 런타임 라이선스를 사용하여 컨트롤을 만드는 옵션이 포함되어 있습니다.

이제 ActiveX 컨트롤 마법사에서 기본 라이선스 지원이 포함된 ActiveX 제어 프레임워크를 생성합니다. 라이선스 코드에 대한 자세한 설명은 다음 항목을 참조하십시오.

## <a name="licensing-support"></a><a name="_core_licensing_support"></a>라이선싱 지원

ActiveX 컨트롤 마법사를 사용하여 ActiveX 컨트롤 에 라이선싱 지원을 추가하는 경우 ActiveX 제어 마법사는 라이센싱 기능을 선언하고 구현하는 코드를 컨트롤 헤더 및 구현 파일에 추가합니다. 이 코드는 `VerifyUserLicense` [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) `GetLicenseKey` 에 있는 기본 구현을 재정의하는 멤버 함수와 멤버 함수로 구성됩니다. 이러한 함수는 제어 라이센스를 검색하고 확인합니다.

> [!NOTE]
> 세 번째 멤버 `VerifyLicenseKey` 함수는 ActiveX 컨트롤 마법사에서 생성되지 않지만 라이선스 키 확인 동작을 사용자 지정하도록 재정의할 수 있습니다.

이러한 멤버 함수는 다음과 같습니다.

- [사용자 라이선스 확인](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   제어 라이센스 파일이 있는지 시스템을 확인하여 컨트롤이 설계 시간 사용을 허용하는지 확인합니다. 이 함수는 처리 `IClassFactory2::GetLicInfo` 및 의 일부로 `IClassFactory::CreateInstanceLic`프레임 워크에 의해 호출 됩니다.

- [GetLicense키](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   컨트롤 DLL에서 고유한 키를 요청합니다. 이 키는 컨테이너 응용 프로그램에 포함되며 나중에 `VerifyLicenseKey`와 함께 컨트롤의 인스턴스를 만드는 데 사용됩니다. 이 함수는 처리의 `IClassFactory2::RequestLicKey`일부로 프레임워크에서 호출됩니다.

- [라이센스 키 확인](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   포함된 키와 컨트롤의 고유 키가 동일한지 확인합니다. 이렇게 하면 컨테이너에서 해당 사용에 대 한 컨트롤의 인스턴스를 만들 수 있습니다. 이 함수는 처리의 `IClassFactory2::CreateInstanceLic` 일부로 프레임워크에서 호출되며 라이센스 키에 대한 사용자 지정 확인을 제공하기 위해 재정의할 수 있습니다. 기본 구현은 문자열 비교를 수행합니다. 자세한 내용은 [이 문서의 후반부에서 ActiveX 컨트롤의 라이선스 사용자 지정을](#_core_customizing_the_licensing_of_an_activex_control)참조하십시오.

### <a name="header-file-modifications"></a><a name="_core_header_file_modifications"></a>헤더 파일 수정

ActiveX 컨트롤 마법사는 컨트롤 헤더 파일에 다음 코드를 배치합니다. 이 예제에서는 컨트롤의 `CSampleCtrl`존재를 확인하는 `factory` 두 개의 멤버 함수가 선언됩니다. LIC 파일 및 컨트롤을 포함하는 응용 프로그램에서 사용할 라이센스 키를 검색하는 다른:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

### <a name="implementation-file-modifications"></a><a name="_core_implementation_file_modifications"></a>구현 파일 수정

ActiveX 컨트롤 마법사는 컨트롤 구현 파일에 다음 두 문을 배치하여 라이센스 파일 이름과 라이센스 문자열을 선언합니다.

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
> 어떤 방식으로든 수정하는 `szLicString` 경우 컨트롤의 첫 번째 줄도 수정해야 합니다. LIC 파일 또는 라이선스가 제대로 작동하지 않습니다.

ActiveX 컨트롤 마법사는 컨트롤 구현 파일에 다음 코드를 배치하여 `VerifyUserLicense` `GetLicenseKey` 컨트롤 클래스 및 함수를 정의합니다.

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

마지막으로 **ActiveX 컨트롤 마법사는** 컨트롤 프로젝트를 수정합니다. IDL 파일입니다. 다음 예제와 같이 **라이선스가 부여된** 키워드가 컨트롤의 공동 클래스 선언에 추가됩니다.

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

## <a name="customizing-the-licensing-of-an-activex-control"></a><a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX 컨트롤의 라이선스 사용자 지정

을 통해 `VerifyLicenseKey` 컨트롤 팩터리 클래스의 가상 멤버 함수로 선언되므로 컨트롤의 라이선스 동작을 사용자 지정할 수 있습니다. `GetLicenseKey` `VerifyUserLicense`

예를 들어 `VerifyUserLicense` 또는 `VerifyLicenseKey` 멤버 함수를 재정의하여 컨트롤에 대한 여러 수준의 라이선스를 제공할 수 있습니다. 이 함수 내에서 검색한 라이선스 수준에 따라 사용자에게 노출되는 속성이나 메서드를 조정할 수 있습니다.

컨트롤 생성이 `VerifyLicenseKey` 실패했다는 것을 사용자에게 알리는 사용자 지정된 메서드를 제공하는 함수에 코드를 추가할 수도 있습니다. 예를 들어 멤버 `VerifyLicenseKey` 함수에서 컨트롤을 초기화하지 못했고 그 이유를 알리는 메시지 상자를 표시할 수 있습니다.

> [!NOTE]
> ActiveX 제어 라이센스 확인을 사용자 지정하는 또 다른 방법은 등록 데이터베이스에서 `AfxVerifyLicFile`호출하는 대신 특정 레지스트리 키를 확인하는 것입니다. 기본 구현의 예는 이 문서의 [구현 파일 수정](#_core_implementation_file_modifications) 섹션을 참조하십시오.

라이선스 문제에 대한 추가 설명은 [기존 ActiveX 컨트롤 업그레이드시](../mfc/upgrading-an-existing-activex-control.md)라이선스 문제를 참조하세요.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)
