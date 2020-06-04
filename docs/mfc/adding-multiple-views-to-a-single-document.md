---
title: 단일 문서에 뷰 여러 개 추가
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 4fa39a4d9369c84d2cffdaeff28dc9cb2f966b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370862"
---
# <a name="adding-multiple-views-to-a-single-document"></a>단일 문서에 뷰 여러 개 추가

Microsoft 기초 클래스(MFC) 라이브러리로 만든 단일 문서 인터페이스(SDI) 응용 프로그램에서 각 문서 유형은 단일 뷰 유형과 연결됩니다. 경우에 따라 새 보기로 문서의 현재 보기를 전환하는 것이 바람직합니다.

> [!TIP]
> 단일 문서에 대한 여러 뷰 구현에 대한 추가 절차는 [CDocument::AddView](../mfc/reference/cdocument-class.md#addview) 및 [COLLECT](../overview/visual-cpp-samples.md) MFC 샘플을 참조하십시오.

뷰를 기존 MFC 응용 `CView`프로그램에 동적으로 전환하기 위한 새 파생 클래스 및 추가 코드를 추가하여 이 기능을 구현할 수 있습니다.

단계는 다음과 같습니다.

- [기존 응용 프로그램 클래스 수정](#vcconmodifyexistingapplicationa1)

- [새 뷰 클래스 만들기 및 수정](#vcconnewviewclassa2)

- [새 뷰 만들기 및 첨부](#vcconattachnewviewa3)

- [스위칭 기능 구현](#vcconswitchingfunctiona4)

- [뷰 전환지원 추가](#vcconswitchingtheviewa5)

이 항목의 나머지 부분에서는 다음을 가정합니다.

- `CWinApp`-derive된 개체의 이름은 `CMyWinApp`에서 `CMyWinApp` 이며 MYWINAPP에서 선언 되고 정의 *됩니다. H와* *마이위냅. CPP*.

- `CNewView`은 새 `CView`-파생 개체의 이름이며 `CNewView` NEWVIEW에서 선언되고 *정의됩니다. H* 및 *NEWVIEW. CPP*.

## <a name="modify-the-existing-application-class"></a><a name="vcconmodifyexistingapplicationa1"></a>기존 응용 프로그램 클래스 수정

응용 프로그램이 뷰 간에 전환하려면 뷰를 저장하는 멤버 변수와 뷰를 전환하는 방법을 추가하여 응용 프로그램 클래스를 수정해야 합니다.

MYWINAPP의 `CMyWinApp` 선언에 다음 코드를 *추가합니다. H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

새 멤버 변수 `m_pOldView` 및 `m_pNewView`은 현재 뷰와 새로 생성된 뷰를 가리킵니다. 새 메서드`SwitchView`() 사용자가 요청 하면 보기를 전환 합니다. 메서드의 본문에는 이 항목의 이 부분에서 [스위칭 함수 구현에](#vcconswitchingfunctiona4)대해 설명합니다.

응용 프로그램 클래스에 대한 마지막 수정에는 스위칭 함수에 사용되는 Windows**메시지(WM_INITIALUPDATE)를**정의하는 새 헤더 파일이 포함되어야 합니다.

MYWINAPP의 포함 섹션에 다음 줄을 *삽입합니다. CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

변경 내용을 저장하고 다음 단계로 계속합니다.

## <a name="create-and-modify-the-new-view-class"></a><a name="vcconnewviewclassa2"></a>새 뷰 클래스 만들기 및 수정

클래스 보기에서 사용할 수 있는 **새 클래스** 명령을 사용 하 여 새 뷰 클래스를 쉽게 만들 수 있습니다. 이 클래스에 대한 유일한 요구 사항은 `CView`에서 파생된다는 것입니다. 이 새 클래스를 응용 프로그램에 추가합니다. 프로젝트에 새 클래스를 추가하는 방법에 대한 자세한 내용은 [클래스 추가](../ide/adding-a-class-visual-cpp.md)를 참조하십시오.

프로젝트에 클래스를 추가한 후에는 일부 뷰 클래스 멤버의 접근성을 변경해야 합니다.

*NEWVIEW를 수정합니다. H* 생성자 및 소멸자에 **대** 한 **보호** 된 공용에서 액세스 지정기를 변경 하 여. 이렇게 하면 클래스를 동적으로 만들고 소멸하고 표시하기 전에 뷰 모양을 수정할 수 있습니다.

변경 내용을 저장하고 다음 단계로 계속합니다.

## <a name="create-and-attach-the-new-view"></a><a name="vcconattachnewviewa3"></a>새 뷰 만들기 및 첨부

새 뷰를 만들고 연결하려면 응용 프로그램 `InitInstance` 클래스의 함수를 수정해야 합니다. 수정은 새 뷰 개체를 생성한 다음 두 `m_pOldView` 개의 `m_pNewView` 기존 뷰 개체를 모두 초기화하는 새 코드를 추가합니다.

`InitInstance` 함수 내에서 새 뷰가 만들어지므로 새 뷰와 기존 뷰는 응용 프로그램의 수명 동안 유지됩니다. 그러나 응용 프로그램은 새 뷰를 동적으로 쉽게 만들 수 있습니다.

호출 후 다음을 `ProcessShellCommand`통해 이 코드를 삽입합니다.

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

변경 내용을 저장하고 다음 단계로 계속합니다.

## <a name="implement-the-switching-function"></a><a name="vcconswitchingfunctiona4"></a>스위칭 기능 구현

이전 단계에서는 새 뷰 개체를 만들고 초기화한 코드를 추가했습니다. 마지막 주요 조각은 스위칭 `SwitchView`방법을 구현하는 것입니다.

응용 프로그램 클래스 (MYWINAPP)에 대한 구현 파일의*끝에서. CPP)* 다음 메서드 정의를 추가합니다.

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

변경 내용을 저장하고 다음 단계로 계속합니다.

## <a name="add-support-for-switching-the-view"></a><a name="vcconswitchingtheviewa5"></a>뷰 전환지원 추가

마지막 단계는 응용 프로그램이 `SwitchView` 뷰 간에 전환해야 할 때 메서드를 호출하는 코드를 추가하는 것입니다. 이 작업은 사용자가 선택할 수 있는 새 메뉴 항목을 추가하거나 특정 조건이 충족될 때 내부적으로 보기를 전환하여 여러 가지 방법으로 수행할 수 있습니다.

새 메뉴 항목 및 명령 처리기 함수 추가에 대한 자세한 내용은 [명령 및 제어 알림에 대한 처리기를](../mfc/handlers-for-commands-and-control-notifications.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[문서/아키텍처 보기](../mfc/document-view-architecture.md)
