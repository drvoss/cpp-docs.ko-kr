---
title: MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 2704e04df3792edfee6c39f597fcbe71b6ce51b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374494"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC 대화 상자에서 Windows Form 사용자 정의 컨트롤 호스팅

MFC는 특별한 종류의 ActiveX 컨트롤로 Windows Forms 컨트롤을 호스팅하고 ActiveX 인터페이스 및 <xref:System.Windows.Forms.Control> 클래스의 속성 및 메서드를 사용하여 컨트롤과 통신합니다. .NET Framework 속성 및 메서드를 사용하여 컨트롤에서 작동하는 것이 좋습니다.

MFC와 함께 사용되는 Windows 양식을 보여 주는 샘플 응용 프로그램에 대한 자세한 내용은 [MFC 및 Windows 양식 통합을](https://www.microsoft.com/download/details.aspx?id=2113)참조하십시오.

> [!NOTE]
> 현재 릴리스에서 개체는 Windows Forms 컨트롤을 `CDialogBar` 호스트할 수 없습니다.

## <a name="in-this-section"></a>섹션 내용

[방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[방법: Windows 양식으로 DDX/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>참조

[CWinFormsControl 클래스](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog 클래스](../mfc/reference/cdialog-class.md) &#124; [CWnd 클래스](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>참고 항목

[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[윈도우 양식/MFC 프로그래밍 차이](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
