---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍'
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: 9620f4d47197147db4972c9f2024f6018a705902
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371181"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍

이 문서에서는 포함된 ActiveX 컨트롤의 노출된 [메서드](../mfc/mfc-activex-controls-methods.md) 및 [속성에](../mfc/mfc-activex-controls-properties.md) 액세스하는 프로세스에 대해 설명합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

기본적으로 다음 단계를 따릅니다.

1. 갤러리를 사용하여 [ActiveX 컨트롤을 ActiveX 컨테이너 프로젝트에 삽입합니다.](../mfc/inserting-a-control-into-a-control-container-application.md)

1. ActiveX 컨트롤 래퍼 클래스와 동일한 형식의 [멤버 변수(또는](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) 다른 액세스 형식)를 정의합니다.

1. 래퍼 클래스의 미리 정의된 멤버 함수를 사용하여 [ActiveX 컨트롤을 프로그래밍합니다.](#_core_programming_the_activex_control)

이 설명에서는 ActiveX 제어 지원을 통해 대화 상자 기반 프로젝트(컨테이너라는 이름)를 만들었다고 가정합니다. Circ 샘플 컨트롤인 Circ가 결과 프로젝트에 추가됩니다.

Circ 컨트롤이 프로젝트(1단계)에 삽입되면 Circ 컨트롤의 인스턴스를 응용 프로그램의 기본 대화 상자에 삽입합니다.

## <a name="procedures"></a>프로시저

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>대화 상자 템플릿에 Circ 컨트롤을 추가하려면

1. ActiveX 제어 컨테이너 프로젝트를 로드합니다. 이 예제에서는 `Container` 프로젝트를 사용합니다.

1. 리소스 보기 탭을 클릭합니다.

1. 대화 상자 폴더를 **엽니다.**

1. 기본 대화 상자 템플릿을 두 번 클릭합니다. 이 예제에서는 **IDD_CONTAINER_DIALOG.**

1. 도구 상자에서 서커스 컨트롤 아이콘을 클릭합니다.

1. 대화 상자 내의 지점을 클릭하여 Circ 컨트롤을 삽입합니다.

1. **파일** 메뉴에서 **모두 저장을** 선택하여 모든 수정 사항을 대화 상자 템플릿에 저장합니다.

## <a name="modifications-to-the-project"></a>프로젝트 수정

컨테이너 응용 프로그램이 Circ 컨트롤에 액세스할 수 있도록 Visual C++는`CCirc`래퍼 클래스 () 구현 파일()을 자동으로 추가합니다. CPP)를 컨테이너 프로젝트 및 래퍼 클래스 헤더(. H) 대화 상자 헤더 파일에 파일:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a>래퍼 클래스 헤더(. H) 파일

Circ 컨트롤에 대한 속성(및 메서드 호출)을 얻고 `CCirc` 설정하려면 래퍼 클래스는 노출된 모든 메서드 및 속성에 대한 선언을 제공합니다. 이 예제에서는 이러한 선언이 CIRC에서 찾을 수 있습니다. H. 다음 샘플은 ActiveX `CCirc` 컨트롤의 노출된 인터페이스를 정의하는 클래스의 일부입니다.

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

그런 다음 일반 C++ 구문을 사용하여 응용 프로그램의 다른 프로시저에서 이러한 함수를 호출할 수 있습니다. 이 멤버 함수 세트를 사용하여 컨트롤의 메서드 및 속성에 액세스하는 방법에 대한 자세한 내용은 [ActiveX 컨트롤 프로그래밍](#_core_programming_the_activex_control)섹션을 참조하십시오.

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a>프로젝트에 대한 멤버 변수 수정

ActiveX 컨트롤이 프로젝트에 추가되고 대화 상자 컨테이너에 포함되면 프로젝트의 다른 부분에서 액세스할 수 있습니다. 컨트롤에 액세스하는 가장 쉬운 방법은 대화 상자 `CContainerDlg` 클래스(2단계)의 멤버 [변수를 만드는](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) 것입니다. 그런 다음 멤버 변수를 사용하여 언제든지 포함된 컨트롤에 액세스할 수 있습니다.

멤버 **변수 추가** 대화 상자에서 *m_circctl* 멤버 변수를 프로젝트에 추가하면 헤더 파일에 다음 줄도 추가됩니다. H) `CContainerDlg` 클래스의:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

또한 **DDX_Control** 대한 호출이 `CContainerDlg`다음의 `DoDataExchange`구현에 자동으로 추가됩니다.

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a>액티브X 컨트롤 프로그래밍

이 시점에서 대화 상자 템플릿에 ActiveX 컨트롤을 삽입 하 고 그것에 대 한 멤버 변수를 만들었습니다. 이제 일반적인 C++ 구문을 사용하여 포함된 컨트롤의 속성 및 메서드에 액세스할 수 있습니다.

(래퍼 클래스 헤더에서) 언급 한 대로 [(. H) 파일),](#_core_the_wrapper_class_header_28h29_file)헤더 파일(. H) 래퍼 `CCirc` 클래스의 경우 CIRC입니다. H에는 노출된 속성 값을 얻고 설정하는 데 사용할 수 있는 멤버 함수 목록이 포함되어 있습니다. 노출된 메서드에 대한 멤버 함수도 사용할 수 있습니다.

컨트롤의 속성을 수정하는 일반적인 장소는 주 `OnInitDialog` 대화 상자 클래스의 멤버 함수에 있습니다. 이 함수는 대화 상자가 나타나기 직전에 호출되며 컨트롤을 포함하여 내용을 초기화하는 데 사용됩니다.

다음 코드 예제에서는 *m_circctl* 멤버 변수를 사용하여 포함된 Circ 컨트롤의 캡션 및 CircleShape 속성을 수정합니다.

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>참고 항목

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
