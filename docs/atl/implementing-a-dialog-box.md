---
title: 대화 상자 구현
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 435926b0a0affde03580ceb2b479cb08a17d0454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319484"
---
# <a name="implementing-a-dialog-box"></a>대화 상자 구현

ATL 프로젝트에 대화 상자를 추가하는 방법에는 ATL 대화 상자 마법사를 사용하거나 수동으로 추가하는 두 가지 방법이 있습니다.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL 대화 상자 마법사를 사용하면 대화 상자 추가

클래스 [추가 대화 상자에서](../ide/add-class-dialog-box.md)ATL 대화 상자 개체를 선택하여 ATL 프로젝트에 대화 상자를 추가합니다. ATL 대화 상자 마법사를 적절 하 게 입력 하 고 **완료를**클릭 합니다. 마법사는 [CAxDialogImpl에서](../atl/reference/caxdialogimpl-class.md) 파생된 클래스를 프로젝트에 추가합니다. **보기** 메뉴에서 **리소스 보기를** 열고 대화 상자를 찾은 다음 두 번 클릭하여 리소스 편집기에서 엽니다.

> [!NOTE]
> 대화 상자에서 `CAxDialogImpl`파생된 경우 ActiveX 및 Windows 컨트롤을 모두 호스트할 수 있습니다. 대화 상자 클래스에서 ActiveX 컨트롤 지원의 오버헤드를 원하지 않는 경우 [CSimpleDialog](../atl/reference/csimpledialog-class.md) 또는 [CDialogImpl을](../atl/reference/cdialogimpl-class.md) 대신 사용합니다.

메시지 및 이벤트 처리기를 클래스 보기에서 대화 상자에 추가할 수 있습니다. 자세한 내용은 [ATL 메시지 처리기 추가를](../atl/adding-an-atl-message-handler.md)참조하십시오.

## <a name="adding-a-dialog-box-manually"></a>대화 상자 수동으로 추가

대화 상자를 구현하는 것은 창을 구현하는 것과 유사합니다. [CAxDialogImpl,](../atl/reference/caxdialogimpl-class.md) [CDialogImpl](../atl/reference/cdialogimpl-class.md)또는 [CSimpleDialog에서](../atl/reference/csimpledialog-class.md) 클래스를 파생하고 메시지를 처리하는 [메시지 맵을](../atl/message-maps-atl.md) 선언합니다. 그러나 파생 클래스에서 대화 상자 템플릿 리소스 ID도 지정해야 합니다. 클래스에는 이 값을 유지하기 `IDD` 위해 호출된 데이터 멤버가 있어야 합니다.

> [!NOTE]
> ATL 대화 상자 마법사를 사용하여 대화 상자를 만들면 마법사가 `IDD` 멤버를 **열거형** 유형으로 자동으로 추가합니다.

`CDialogImpl`을 사용하면 Windows 컨트롤을 호스트하는 모달 또는 모덜리스 대화 상자를 구현할 수 있습니다. `CAxDialogImpl`이를 통해 ActiveX 및 Windows 컨트롤을 모두 호스팅하는 모달 또는 모덜리스 대화 상자를 구현할 수 있습니다.

모달 대화 상자를 만들려면 -derived(또는 `CDialogImpl` `CAxDialogImpl`파생된) 클래스의 인스턴스를 만든 다음 [DoModal](../atl/reference/cdialogimpl-class.md#domodal) 메서드를 호출합니다. 모달 대화 상자를 닫려면 메시지 처리기에서 [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) 메서드를 호출합니다. 모덜리스 대화 상자를 만들려면 [Create](../atl/reference/cdialogimpl-class.md#create) `DoModal`대신 만들기 메서드를 호출합니다. 모덜리스 대화 상자를 삭제하려면 [DestroyWindow를](../atl/reference/cdialogimpl-class.md#destroywindow)호출합니다.

가라앉는 이벤트는 [CAxDialogImpl에서](../atl/reference/caxdialogimpl-class.md)자동으로 수행됩니다. `CWindowImpl`-derived 클래스의 처리기와 마찬가지로 대화 상자의 메시지 처리기를 구현합니다. 메시지별 반환 값이 있는 경우 을 로 `LRESULT`반환합니다. 반환된 `LRESULT` 값은 Windows 대화 상자 관리자가 제대로 처리하기 위해 ATL에 의해 매핑됩니다. 자세한 내용은 atlwin.h의 [CDialogImplBaseT::DialogProc의](../atl/reference/cdialogimpl-class.md#dialogproc) 소스 코드를 참조하십시오.

## <a name="example"></a>예제

다음 클래스는 대화 상자를 구현합니다.

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>참고 항목

[창 클래스](../atl/atl-window-classes.md)
