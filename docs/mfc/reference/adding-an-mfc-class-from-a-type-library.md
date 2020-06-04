---
title: 형식 라이브러리에서 MFC 클래스 추가
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: bf9c763a215a4880d5b0ad206f6a347341fea9eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371716"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>형식 라이브러리에서 MFC 클래스 추가

사용 가능한 형식 라이브러리의 인터페이스에서 MFC 클래스를 만들려면 이 마법사를 사용합니다. MFC 클래스를 [MFC 애플리케이션](../../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md) 또는 [MFC ActiveX 컨트롤](../../mfc/reference/creating-an-mfc-activex-control.md)에 추가할 수 있습니다.

> [!NOTE]
> 형식 라이브러리에서 클래스를 추가하려면 자동화를 사용하도록 설정한 MFC 프로젝트를 만들 필요가 없습니다.

형식 라이브러리에는 구성 요소에 의해 노출되는 인터페이스에 대한 이진 설명이 포함되어 있으며, 메서드는 매개 변수 및 반환 형식과 함께 정의합니다. Type lib 마법사에서 클래스 추가의 **사용 가능한 형식 라이브러리** 목록에 표시하려면 형식 라이브러리를 등록해야 합니다. 자세한 내용은 MSDN 라이브러리의 "분산 COM 내부: 형식 라이브러리 및 언어 통합"을 참조하십시오.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>형식 라이브러리에서 MFC 클래스를 추가하려면

1. 솔루션 **탐색기** 또는 [클래스 보기에서](/visualstudio/ide/viewing-the-structure-of-code)클래스를 추가할 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 **추가**를 클릭한 다음, **클래스 추가**를 클릭합니다.

1. 클래스 [추가](../../ide/add-class-dialog-box.md) 대화 상자에서 템플릿 창에서 **Typelib에서 MFC 클래스를**클릭한 다음 **열기를** 클릭하여 [Typelib 마법사에서 클래스 추가를](../../mfc/reference/add-class-from-typelib-wizard.md)표시합니다.

마법사에서 형식 라이브러리에 두 개 이상의 클래스를 추가할 수 있습니다. 마찬가지로 단일 마법사 세션에서 두 개 이상의 형식 라이브러리의 클래스를 추가할 수 있습니다.

마법사는 선택한 형식 라이브러리에서 추가하는 각 인터페이스에 대해 [COleDispatchDriver에서](../../mfc/reference/coledispatchdriver-class.md)파생된 MFC 클래스를 만듭니다. `COleDispatchDriver`OLE 자동화의 클라이언트 측면을 구현합니다.

## <a name="see-also"></a>참고 항목

[자동화 클라이언트](../../mfc/automation-clients.md)<br/>
[자동화 클라이언트: 형식 라이브러리 사용](../../mfc/automation-clients-using-type-libraries.md)
