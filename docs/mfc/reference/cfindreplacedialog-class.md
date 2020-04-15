---
title: CFindReplaceDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: 7a12d0520d070d74afd9fa91e828970d14c82700
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373853"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog 클래스

응용 프로그램에서 표준 문자열 찾기/바꾸기 대화 상자를 구현할 수 있습니다.

## <a name="syntax"></a>구문

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|이 함수를 호출하여 개체를 생성합니다. `CFindReplaceDialog`|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFindReplaceDialog::Create](#create)|`CFindReplaceDialog` 대화 상자를 만들고 표시합니다.|
|[CFindReplaceDialog::FindNext](#findnext)|이 함수를 호출하여 사용자가 find 문자열의 다음 발생을 찾을지 여부를 확인합니다.|
|[CFind대체대화상자::GetFindString](#getfindstring)|이 함수를 호출하여 현재 찾기 문자열을 검색합니다.|
|[CFindReplaceDialog::GetNotifier](#getnotifier)|등록된 메시지 처리기에서 구조를 검색하려면 이 함수를 `FINDREPLACE` 호출합니다.|
|[CFind대체 대화 상자::GetReplaceString](#getreplacestring)|이 함수를 호출하여 현재 바꾸기 문자열을 검색합니다.|
|[CFind대체대화문::이터미터팅](#isterminating)|이 함수를 호출하여 대화 상자가 종료되는지 확인합니다.|
|[CFind대체대화상자::매치케이스](#matchcase)|이 함수를 호출하여 사용자가 찾기 문자열의 대/소문자를 정확히 일치할지 여부를 확인합니다.|
|[CFind대체디아로그::매치홀워드](#matchwholeword)|이 함수를 호출하여 사용자가 전체 단어만 일치시킬지 여부를 확인합니다.|
|[CFindReplaceDialog::ReplaceAll](#replaceall)|이 함수를 호출하여 사용자가 문자열의 모든 발생을 대체할지 여부를 확인합니다.|
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|이 함수를 호출하여 사용자가 현재 단어를 대체할지 여부를 결정합니다.|
|[CFind대체대화상자::검색다운](#searchdown)|이 함수를 호출하여 사용자가 아래쪽 방향으로 검색을 진행하도록 원하는지 여부를 확인합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFind대체디아로그::m_fr](#m_fr)|개체를 사용자 지정하는 `CFindReplaceDialog` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

다른 Windows 공통 대화 상자와 `CFindReplaceDialog` 달리 개체는 모덜리스되어 사용자가 화면에 있는 동안 다른 창과 상호 작용할 수 있습니다. `CFindReplaceDialog` 개체에는 대화 상자 찾기 및 대화 상자 찾기/바꾸기의 두 가지 종류가 있습니다. 대화 상자를 통해 사용자가 문자열을 입력하고 검색/바꿀 수 있지만 검색 또는 대체 함수는 수행하지 않습니다. 응용 프로그램에 이러한 것을 추가해야 합니다.

개체를 `CFindReplaceDialog` 생성하려면 제공된 생성자(인수가 없음)를 사용합니다. 모덜리스 대화 상자이므로 스택이 아닌 **새** 연산자를 사용하여 힙에 개체를 할당합니다.

`CFindReplaceDialog` 개체를 생성 한 후에는 [create member](#create) 함수를 호출하여 대화 상자를 만들고 표시 해야합니다.

`Create`를 호출하기 전에 [m_fr](#m_fr) 구조체를 사용하여 대화 상자를 초기화합니다. 구조는 `m_fr` [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)형식입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

부모 창에서 찾기/바꾸기 요청에 대한 알림을 얻으려면 Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) 기능을 사용하고 등록된 메시지를 처리하는 프레임 창에서 [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) 메시지 맵 매크로를 사용해야 합니다.

사용자가 `IsTerminating` 멤버 함수를 사용하여 대화 상자를 종료하기로 결정했는지 여부를 확인할 수 있습니다.

`CFindReplaceDialog`COMMDLG에 의존합니다. Windows 버전 3.1 이상과 함께 제공되는 DLL 파일입니다.

대화 상자를 사용자 지정하려면 에서 `CFindReplaceDialog`클래스를 파생합니다. 처리되지 않은 모든 메시지는 기본 클래스에 전달되어야 합니다.

후크 기능을 사용자 지정할 필요는 없습니다.

사용에 `CFindReplaceDialog`대한 자세한 내용은 [일반적인 대화 상자 클래스를](../../mfc/common-dialog-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>CFind대체대화상자::CFindReplaceDialog

`CFindReplaceDialog` 개체를 생성합니다.

```
CFindReplaceDialog();
```

### <a name="remarks"></a>설명

개체는 `CFindReplaceDialog` 모덜리스 대화 상자이므로 **새** 연산자를 사용하여 힙에서 개체를 생성해야 합니다.

소멸 하는 동안 프레임 워크는 대화 상자에 대 한 포인터에서 **이 삭제를** 수행 하려고 합니다. 스택에서 대화 상자를 만든 경우 **이** 포인터가 존재하지 않으며 정의되지 않은 동작이 발생할 수 있습니다.

`CFindReplaceDialog` 개체 생성에 대한 자세한 내용은 [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) 개요를 참조하십시오. [CFindReplaceDialog::멤버 만들기](#create) 함수를 사용하여 대화 상자를 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a>CFind대체 대화상자::만들기

의 값에 따라 대화 상자 찾기 또는 찾기/바꾸기 상자 `bFindDialogOnly`개체를 만들고 표시합니다.

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*bFindDialogOnly*<br/>
이 매개변수를 TRUE로 설정하여 **대화 상자 찾기를** 표시합니다. **찾기/바꾸기** 대화 상자를 표시하려면 FALSE로 설정합니다.

*lpszFindWhat*<br/>
대화 상자가 나타나면 기본 검색 문자열에 대한 포인터입니다. NULL인 경우 대화 상자에 기본 검색 문자열이 없습니다.

*lpszReplaceWith*<br/>
대화 상자가 나타날 때 기본 대체 문자열에 대한 포인터입니다. NULL인 경우 대화 상자에 기본 대체 문자열이 없습니다.

*dwFlags*<br/>
비트OR 연산자를 사용하여 결합된 대화 상자의 설정을 사용자 지정하는 데 사용할 수 있는 하나 이상의 플래그입니다. 기본값은 FR_DOWN 검색이 아래쪽 방향으로 진행되도록 지정합니다. 이러한 플래그에 대한 자세한 내용은 Windows SDK의 [FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew) 구조를 참조하십시오.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대한 포인터입니다. 찾기/바꾸기 작업이 요청되었음을 나타내는 특수 메시지를 받게 됩니다. NULL이면 응용 프로그램의 기본 창이 사용됩니다.

### <a name="return-value"></a>Return Value

대화 상자 개체가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

부모 창에서 찾기/바꾸기 요청에 대한 알림을 얻으려면 반환 값이 응용 프로그램의 인스턴스에 고유한 메시지 번호인 Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) 함수를 사용해야 합니다. 프레임 창에는 등록된 메시지를 처리하는 콜백 함수(다음 `OnFindReplace` 예제)를 선언하는 메시지 맵 항목이 있어야 합니다. 다음 코드 조각은 다음 `CMyRichEditView`프레임 창 클래스에 대해 이 작업을 수행하는 방법의 예입니다.

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

`OnFindReplace` 함수 내에서 [CFindReplaceDialog::FindNext](#findnext) 및 [CFindReplaceDialog::IsTermating](#isterminating) 메서드를 사용 하 여 사용자의 의도를 해석 하 고 찾기/바꾸기 작업에 대 한 코드를 만듭니다.

### <a name="example"></a>예제

  [CFindReplaceDialog::CFindReplaceDialog의](#cfindreplacedialog)예제를 참조하십시오.

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a>CFind대체대화상자::찾기다음

콜백 함수에서 이 함수를 호출하여 사용자가 검색 문자열의 다음 발생을 찾을지 여부를 확인합니다.

```
BOOL FindNext() const;
```

### <a name="return-value"></a>Return Value

사용자가 검색 문자열의 다음 발생을 찾으려는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>CFind대체대화상자::GetFindString

콜백 함수에서 이 함수를 호출하여 찾을 기본 문자열을 검색합니다.

```
CString GetFindString() const;
```

### <a name="return-value"></a>Return Value

찾을 기본 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>CFind대체디아로그::GetNotifier

이 함수를 호출하여 현재 바꾸기 대화 상자찾기에 대한 포인터를 검색합니다.

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*lParam*<br/>
*lparam* 값은 프레임 창의 `OnFindReplace` 멤버 함수에 전달되었습니다.

### <a name="return-value"></a>Return Value

현재 대화 상자에 대한 포인터입니다.

### <a name="remarks"></a>설명

콜백 함수 내에서 현재 대화 상자에 액세스하고, 멤버 함수를 호출하고, `m_fr` 구조체에 액세스하는 데 사용해야 합니다.

### <a name="example"></a>예제

[참조 CFindReplaceDialog::찾기대체](#create) 처리기를 등록하는 방법의 예는 찾기 바꾸기 대화 상자에서 알림을 수신합니다.

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>CFind대체 대화 상자::GetReplaceString

이 함수를 호출하여 현재 바꾸기 문자열을 검색합니다.

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>Return Value

찾은 문자열을 대체할 기본 문자열입니다.

### <a name="example"></a>예제

  [CFindReplaceDialog::GetFindString에](#getfindstring)대 한 예제를 참조 하십시오.

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a>CFind대체대화문::이터미터팅

콜백 함수 내에서 이 함수를 호출하여 사용자가 대화 상자를 종료하기로 결정했는지 확인합니다.

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>Return Value

사용자가 대화 상자를 종료하기로 결정한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수가 0이 아닌 함수를 반환하는 경우 현재 대화 상자의 `DestroyWindow` 멤버 함수를 호출하고 대화 상자 포인터 변수를 NULL로 설정해야 합니다. 선택적으로 마지막으로 입력한 찾기/바꾸기 텍스트를 저장하고 이를 사용하여 다음 찾기/바꾸기 대화 상자를 초기화할 수도 있습니다.

### <a name="example"></a>예제

  [CFindReplaceDialog::GetFindString에](#getfindstring)대 한 예제를 참조 하십시오.

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a>CFind대체디아로그::m_fr

개체를 사용자 `CFindReplaceDialog` 지정하는 데 사용됩니다.

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>설명

`m_fr`[는 FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)형식의 구조입니다. 해당 멤버는 대화 상자 개체의 특성을 저장합니다. 개체를 생성한 `CFindReplaceDialog` 후 대화 `m_fr` 상자에서 다양한 값을 수정하는 데 사용할 수 있습니다.

이 구조에 대한 자세한 `FINDREPLACE` 내용은 Windows SDK의 구조를 참조하십시오.

### <a name="example"></a>예제

  [CFindReplaceDialog::CFindReplaceDialog의](#cfindreplacedialog)예제를 참조하십시오.

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a>CFind대체대화상자::매치케이스

이 함수를 호출하여 사용자가 찾기 문자열의 대/소문자를 정확히 일치할지 여부를 확인합니다.

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>Return Value

사용자가 검색 문자열의 대/소문자와 정확히 일치하는 검색 문자열의 발생을 찾으려는 경우 Nonzero; 그렇지 않으면 0.

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>CFind대체디아로그::매치홀워드

이 함수를 호출하여 사용자가 전체 단어만 일치시킬지 여부를 확인합니다.

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>Return Value

사용자가 검색 문자열의 전체 단어만 일치하도록 하려는 경우 Nonzero입니다. 그렇지 않으면 0.

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a>CFind대체디아로그::모두 바꾸기

이 함수를 호출하여 사용자가 문자열의 모든 발생을 대체할지 여부를 확인합니다.

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>Return Value

사용자가 replace 문자열과 일치하는 모든 문자열을 교체하도록 요청한 경우 Nonzero입니다. 그렇지 않으면 0.

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>CFind대체대화기록::현재 대체

이 함수를 호출하여 사용자가 현재 단어를 대체할지 여부를 결정합니다.

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>Return Value

사용자가 현재 선택한 문자열을 바꾸기 문자열로 교체하도록 요청한 경우 Nonzero; 그렇지 않으면 0.

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a>CFind대체대화상자::검색다운

이 함수를 호출하여 사용자가 아래쪽 방향으로 검색을 진행하도록 원하는지 여부를 확인합니다.

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>Return Value

사용자가 하향 방향으로 검색을 진행하려는 경우 0이 아닙니다. 사용자가 위쪽 방향으로 검색을 진행하려는 경우 0입니다.

## <a name="see-also"></a>참고 항목

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
