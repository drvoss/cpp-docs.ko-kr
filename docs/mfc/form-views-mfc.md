---
title: 폼 뷰(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
ms.openlocfilehash: 5e8912c9013175fe254b2f4a4a968a67fd071f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365294"
---
# <a name="form-views-mfc"></a>폼 뷰(MFC)

양식 기반 응용 프로그램(뷰 클래스에서 파생되는 응용 `CFormView`프로그램)을 포함하여 MFC 라이브러리를 지원하는 모든 Visual C++ [응용 프로그램에](../mfc/reference/creating-a-forms-based-mfc-application.md) 양식을 추가할 수 있습니다. 양식을 지원하기 위해 응용 프로그램을 처음에 만들지 않은 경우 Visual C++는 새 양식을 삽입할 때 이 지원을 추가합니다. 기본 [문서/보기 아키텍처를](../mfc/document-view-architecture.md)구현하는 SDI 또는 MDI 응용 프로그램에서 사용자가 **새** 명령을 선택할 때(기본적으로 **파일** 메뉴에서) Visual C++는 사용자에게 사용 가능한 양식 중에서 선택하라는 메시지를 표시합니다.

SDI 응용 프로그램을 사용하면 사용자가 **새** 명령을 선택하면 양식의 현재 인스턴스가 계속 실행되지만 선택한 폼이 있는 응용 프로그램의 새 인스턴스가 만들어지지 않으면 만들어집니다. MDI 응용 프로그램에서 는 사용자가 **새** 명령을 선택할 때 양식의 현재 인스턴스가 계속 실행됩니다.

> [!NOTE]
> 대화 상자 클래스를 기반으로 `CDialog` 하는 응용 프로그램과 뷰 클래스가 구현되지 않은 응용 프로그램)에 양식을 삽입할 수 있습니다. 그러나 문서/뷰 아키텍처가 없으면 Visual C++는 **새** **&#124;파일** 기능을 자동으로 구현하지 않습니다. 사용자가 다양한 속성 페이지가 있는 탭된 대화 상자를 구현하는 등 추가 양식을 볼 수 있는 방법을 만들어야 합니다.

응용 프로그램에 새 양식을 삽입할 때 Visual C++는 다음을 수행합니다.

- 선택한`CFormView` `CRecordView` `CDaoRecordView`양식 스타일 클래스 중 하나를 기반으로 클래스를 `CDialog`만듭니다.

- 적절한 스타일로 대화 상자 리소스를 만듭니다(또는 아직 클래스와 연결되지 않은 기존 대화 상자 리소스를 사용할 수 있음).

   기존 대화 상자 리소스를 선택하는 경우 대화 상자에 대한 속성 페이지를 사용하여 이러한 스타일을 설정해야 할 수 있습니다. 대화 상자의 스타일에는 다음이 포함되어야 합니다.

     **WS_CHILD**=켜기

     **WS_BORDER**=꺼져

     **WS_VISIBLE**=꺼져

     **WS_CAPTION**=꺼져

문서/보기 아키텍처를 기반으로 하는 응용 프로그램의 경우 **새 양식** 명령(클래스 보기에서 마우스 오른쪽 단추 클릭)도 있습니다.

- `CDocument`기반 클래스 를 만듭니다.

   새 클래스를 만든 대신 프로젝트에서 기존 `CDocument`기반 클래스를 사용할 수 있습니다.

- 문자열, 메뉴 및 아이콘 `CDocument`리소스를 사용 하 고 문서 템플릿(파생)을 생성합니다.

   템플릿을 기반으로 하는 새 클래스를 만들 수도 있습니다.

- 응용 프로그램 `AddDocumentTemplate` 코드에 호출을 `InitInstance` 추가합니다.

   Visual C++는 사용자가 새 **명령을** 선택할 때 사용 가능한 양식 목록에 양식을 추가하는 각 새 양식에 대해 이 코드를 추가합니다. 이 코드에는 양식의 관련 리소스 ID와 새 양식 개체를 구성하는 연결된 문서, 뷰 및 프레임 클래스의 이름이 포함됩니다.

   문서 템플릿은 문서, 프레임 창 및 보기 간의 연결 역할을 합니다. 단일 문서의 경우 많은 템플릿을 만들 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [양식 기반 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)

- [프로젝트에 폼 삽입](../mfc/inserting-a-form-into-a-project.md)

## <a name="see-also"></a>참고 항목

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
