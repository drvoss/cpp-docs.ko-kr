---
title: '방법: Windows Forms에서 DDX-DDV 데이터 바인딩 수행'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 31629a4db2559112ba49f5c069b08de7abdfc2db
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754355"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) [CWinFormsControl::CreateManagedControl을](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) 호출하여 리소스 제어 ID와 일치하는 컨트롤을 만듭니다. 마법사에서 `DDX_ManagedControl` 생성된 코드에서 컨트롤에 사용하는 경우 동일한 `CreateManagedControl` 컨트롤에 대해 명시적으로 호출해서는 안 됩니다. `CWinFormsControl`

`DDX_ManagedControl` [CWnd::DoDataExchange에서](../mfc/reference/cwnd-class.md#dodataexchange) 호출하여 리소스 아이디에서 컨트롤을 만듭니다. 데이터 교환의 경우 Windows Forms 컨트롤에서 DDX/DDV 함수를 사용할 필요가 없습니다. 대신 다음 예제와 같이 대화(또는 보기) `DoDataExchange` 클래스의 메서드에서 관리되는 컨트롤의 속성에 액세스하는 코드를 배치할 수 있습니다.

다음 예제에서는 기본 C++ 문자열을 .NET 사용자 컨트롤에 바인딩하는 방법을 보여 주며 있습니다.

## <a name="example"></a>예제

다음은 .NET 사용자 컨트롤의 사용자 정의 `m_str` `NameText` 속성을 가진 MFC 문자열의 DDX/DDV 데이터 바인딩의 예입니다.

[CDialog::OnInitDialog가](../mfc/reference/cdialog-class.md#oninitdialog) 처음으로 호출될 `CMyDlg::DoDataExchange` 때 컨트롤이 만들어지므로 참조하는 `m_UserControl` 모든 `DDX_ManagedControl` 코드는 호출 후에 와야 합니다.

대화 [상자에서 사용자 컨트롤 및 호스트 만들기에서](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)만든 MFC01 응용 프로그램에서 이 코드를 구현할 수 있습니다.

CMFC01Dlg 선언에 다음 코드를 넣습니다.

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>예제

CMFC01Dlg의 구현에 다음 코드를 넣습니다.

```cpp
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
{
   CDialog::DoDataExchange(pDX);
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);

   if (pDX->m_bSaveAndValidate) {
      m_str = m_MyControl->textBox1->Text;
   } else
   {
      m_MyControl->textBox1->Text = gcnew System::String(m_str);
   }
}
```

## <a name="example"></a>예제

이제 확인 단추를 클릭하기 위한 처리기 메서드를 추가합니다. 리소스 보기 탭을 **클릭합니다.** 리소스 보기에서 를 두 `IDD_MFC01_DIALOG`번 클릭합니다. 대화 상자 리소스가 리소스 편집기에 나타납니다. 그런 다음 확인 버튼을 두 번 클릭합니다.

다음과 같이 처리기를 정의합니다.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>예제

그리고 BOOL CMFC01Dlg의 구현에 다음 줄을 추가::OnInitDialog().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

이제 애플리케이션을 빌드 및 실행할 수 있습니다. 응용 프로그램이 닫히면 텍스트 상자의 텍스트가 팝업 메시지 상자에 표시됩니다.

## <a name="see-also"></a>참조

[CWinForms제어 클래스](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
