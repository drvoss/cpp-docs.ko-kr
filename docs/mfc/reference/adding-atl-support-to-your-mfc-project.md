---
title: MFC 프로젝트에 ATL 지원 추가
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 05c4e8ba54d9a573b422f136c9e8cf69e48d1c9a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371677"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC 프로젝트에 ATL 지원 추가

이미 MFC 기반 응용 프로그램을 만든 경우 IDE를 사용하여 ATL(활성 템플릿 라이브러리)에 대한 지원을 쉽게 추가할 수 있습니다.

> [!NOTE]
> 이 지원은 MFC 실행 파일 또는 DLL 프로젝트에 추가된 단순 COM 개체에만 적용됩니다. MFC 프로젝트에 다른 COM 개체(ActiveX 컨트롤 포함)를 추가할 수 있지만 개체가 예상대로 작동하지 않을 수 있습니다.

::: moniker range=">=vs-2019"

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 **추가**를 클릭한 다음, **새 항목**을 클릭합니다.

1. 왼쪽 창에서 **ATL을** 선택한 다음 중앙 창에서 **ATL 지원을** 선택합니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-add-atl-support-to-your-mfc-project"></a>MFC 프로젝트에 ATL 지원을 추가하려면

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 에 **추가를**클릭한 다음 **클래스 추가**를 클릭합니다.

1. 왼쪽 창에서 **ATL을** 선택한 다음 중앙 창에서 **MFC 프로젝트에 ATL 지원 추가를** 선택합니다.

::: moniker-end

ATL 지원 추가가 MFC 프로젝트의 코드를 변경하는 방법에 대한 자세한 내용은 [ATL 마법사에서 추가한 ATL 지원에 대한 세부 정보를](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[코드 마법사에서 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
