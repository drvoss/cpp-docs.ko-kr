---
title: DHTML 제어 프로젝트의 요소 식별
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 5fabdc815989c21bdf6b0932b9d6826e28d7012a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319499"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>DHTML 제어 프로젝트의 요소 식별

대부분의 DHTML 제어 코드는 ATL 컨트롤에 대해 생성된 코드와 정확히 같습니다. 일반 코드에 대한 기본적인 이해를 위해 [ATL 자습서를](../atl/active-template-library-atl-tutorial.md)통해 작업하고 [ATL 프로젝트](../atl/reference/creating-an-atl-project.md) 만들기 및 [ATL COM 개체의 기본 사항](../atl/fundamentals-of-atl-com-objects.md)만들기 섹션을 읽어보십시오.

DHTML 컨트롤은 다음을 제외한 모든 ATL 컨트롤과 유사합니다.

- 컨트롤이 구현하는 일반 인터페이스 외에도 C++ 코드와 HTML 사용자 인터페이스(UI) 간에 통신하는 데 사용되는 추가 인터페이스를 구현합니다. HTML UI는 이 인터페이스를 사용하여 C++ 코드를 호출합니다.

- 컨트롤 UI에 대 한 HTML 리소스를 만듭니다.

- [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))형식의 스마트 포인터인 `m_spBrowser`멤버 변수를 통해 DHTML 개체 모델에 액세스할 수 있습니다. 이 포인터를 사용하여 DHTML 개체 모델의 모든 부분에 액세스합니다.

다음 그래픽은 DLL, DHTML 컨트롤, 웹 브라우저 및 HTML 리소스 간의 관계를 보여 줍니다.

![DHTML 컨트롤 프로젝트의 요소](../atl/media/vc52en1.gif "DHTML 컨트롤 프로젝트의 요소")

> [!NOTE]
> 이 그래픽의 이름은 자리 표시자입니다. HTML 리소스의 이름과 컨트롤에 노출된 인터페이스는 ATL 제어 마법사에서 할당한 이름을 기반으로 합니다.

이 그래픽에서 요소는 다음과 같습니다.

- **내 DLL** ATL 프로젝트 마법사를 사용하여 만든 DLL입니다.

- **DHTML** 컨트롤`m_spBrowser`() ATL 개체 마법사를 사용 하 여 만든 DHTML 컨트롤입니다. 이 컨트롤은 웹 브라우저 개체의 인터페이스를 통해 웹 브라우저 `IWebBrowser2`개체 및 해당 메서드에 액세스합니다. 컨트롤 자체는 컨트롤에 필요한 다른 표준 인터페이스 외에 다음 두 인터페이스를 노출합니다.

  - `IDHCTL1`컨테이너에서만 사용하기 위해 컨트롤에 의해 노출된 인터페이스입니다.

  - `IDHCTLUI1`C++ 코드와 HTML 사용자 인터페이스 간에 통신하기 위한 디스패치 인터페이스입니다. 웹 브라우저는 컨트롤의 디스패치 인터페이스를 사용하여 컨트롤을 표시합니다. 호출 을 호출 하 여 컨트롤의 사용자 인터페이스에서이 디스패치 인터페이스의 다양 한 메서드를 호출할 수 `window.external`있습니다.이 디스패치 인터페이스에 메서드 이름을 호출 합니다. 이 컨트롤의 UI를 구성하는 HTML 내의 SCRIPT 태그에서 액세스할 `window.external` 수 있습니다. 리소스 파일에서 외부 메서드를 호출하는 방법에 대한 자세한 내용은 [DHTML에서 C++ 코드 호출을](../atl/calling-cpp-code-from-dhtml.md)참조하십시오.

- **IDR_CTL1** HTML 리소스의 리소스 ID입니다. 이 경우 파일 이름은 DHCTL1UI.htm입니다. DHTML 컨트롤은 텍스트 편집기에서 편집할 수 있는 표준 HTML 태그 및 외부 창 디스패치 명령을 포함하는 HTML 리소스를 사용합니다.

- **웹 브라우저** 웹 브라우저는 HTML 리소스의 HTML을 기반으로 컨트롤의 UI를 표시합니다. DHTML 개체 모델에 대한 `IWebBrowser2` 액세스를 허용하기 위해 DHTML 컨트롤에서 웹 브라우저의 인터페이스에 대한 포인터를 사용할 수 있습니다.

ATL 제어 마법사는 HTML 리소스와 .cpp 파일 모두에서 기본 코드가 있는 컨트롤을 생성합니다. 마법사에서 생성된 컨트롤을 컴파일하고 실행한 다음 웹 브라우저 또는 ActiveX 제어 테스트 컨테이너에서 컨트롤을 볼 수 있습니다. 아래 그림은 테스트 컨테이너에 세 개의 버튼이 표시된 기본 ATL DHTML 컨트롤을 보여 주며 있습니다.

![ATL DHTML 제어](../atl/media/vc52en2.gif "ATL DHTML 컨트롤")

DHTML 컨트롤 빌드를 시작하려면 [ATL DHTML 컨트롤 만들기를](../atl/creating-an-atl-dhtml-control.md) 참조하십시오. 테스트 컨테이너에 액세스하는 방법에 대한 자세한 내용은 [테스트 컨테이너를 사용하여 속성 및 이벤트](../mfc/testing-properties-and-events-with-test-container.md) 테스트를 참조하십시오.

## <a name="see-also"></a>참고 항목

[DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)
