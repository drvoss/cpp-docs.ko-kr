---
title: 'TN024: MFC에서 정의한 메시지 및 리소스'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 24bcacd46b839babe9c9c89facb1cc56d18c0ee5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370361"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC에서 정의한 메시지 및 리소스

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 는 MFC에서 사용하는 내부 Windows 메시지 및 리소스 형식에 대해 설명합니다. 이 정보는 프레임워크의 구현에 대해 설명하고 응용 프로그램을 디버깅하는 데 도움이 됩니다. 모험을 위해 이 모든 정보가 공식적으로 지원되지 않더라도 고급 구현에 이 정보 중 일부를 사용할 수 있습니다.

이 메모에는 MFC 개인 구현 세부 정보가 포함되어 있습니다. 모든 내용은 향후 변경될 수 있습니다. MFC 개인 Windows 메시지는 한 응용 프로그램의 범위에서만 의미가 있지만 나중에 시스템 전체 메시지를 포함하도록 변경됩니다.

MFC 개인 Windows 메시지 및 리소스 유형의 범위는 Microsoft Windows에서 따로 설정한 예약된 "시스템" 범위에 있습니다. 현재 범위의 모든 숫자가 사용되는 것은 아니며 나중에 범위의 새 숫자가 사용될 수 있습니다. 현재 사용 중인 숫자는 변경될 수 있습니다.

MFC 전용 Windows 메시지는 0x360->0x37F 범위에 있습니다.

MFC 개인 리소스 유형은 0xF0->0xFF 범위에 있습니다.

**MFC 개인 윈도우 메시지**

이러한 Windows 메시지는 창 개체 간에 비교적 느슨한 결합이 필요하고 C++ 가상 함수가 적절하지 않은 C++ 가상 함수 대신 사용됩니다.

이러한 개인 Windows 메시지 및 관련 매개 변수 구조는 MFC 개인 헤더 'AFXPRIV'에 선언됩니다. H'. 이 헤더를 포함하는 코드는 문서화되지 않은 동작에 의존할 수 있으며 이후 버전의 MFC에서 중단될 수 있습니다.

드문 경우지만 이러한 메시지 중 하나를 처리해야 하는 경우 ON_MESSAGE 메시지 맵 매크로를 사용하고 일반 LRESULT/WPARAM/LPARAM 형식으로 메시지를 처리해야 합니다.

**WM_QUERYAFXWNDPROC**

이 메시지는 생성되는 창으로 전송됩니다. 이는 WndProc가 AfxWndProc인지 여부를 결정하는 방법으로 생성 프로세스 초기에 **전송됩니다. AfxWndProc은** 1을 반환합니다.

|||
|-|-|
|wParam|사용되지 않음|
|lParam|사용되지 않음|
|다음을 반환합니다.|**1 AfxWndProc에** 의해 처리된 경우|

**WM_SIZEPARENT**

이 메시지는 프레임 의 측면 주위에 컨트롤 막대를`CFrameWnd::OnSize` 재배치하기 `CWnd::RepositionBars`위해 크기 조정 (호출 `CFrameWnd::RecalcLayout` 호출) 동안 바로 자식에게 프레임 창에 의해 전송됩니다. AFX_SIZEPARENTPARAMS 구조에는 부모의 현재 사용 가능한 클라이언트 사각형과 다시 그리기를 최소화하기 위해 호출할 `DeferWindowPos` HDWP(NULL일 수 있음)가 포함되어 있습니다.

|||
|-|-|
|wParam|사용되지 않음|
|lParam|AFX_SIZEPARENTPARAMS 구조의 주소|
|다음을 반환합니다.|사용되지 않음 (0)|

메시지를 무시하면 창이 레이아웃에 참여하지 않는다는 것을 나타냅니다.

**WM_SETMESSAGESTRING**

이 메시지는 상태 표시줄의 메시지 줄을 업데이트하도록 요청하는 프레임 창으로 전송됩니다. 문자열 ID 또는 LPCSTR을 지정할 수 있지만 둘 다 지정할 수는 없습니다.

|||
|-|-|
|wParam|문자열 ID(또는 0)|
|lParam|문자열(또는 NULL)에 대한 LPCSTR|
|다음을 반환합니다.|사용되지 않음 (0)|

**WM_IDLEUPDATECMDUI**

이 메시지는 유휴 시간에 전송되어 업데이트 명령 UI 처리기의 유휴 시간 업데이트를 구현합니다. 창(일반적으로 컨트롤 바)이 메시지를 처리하는 경우 `CCmdUI` 개체(또는 파생 클래스의 개체)를 만들고 `CCmdUI::DoUpdate` 창의 각 "항목"을 호출합니다. 그러면 명령 처리기 체인의 개체에 대한 ON_UPDATE_COMMAND_UI 처리기가 확인됩니다.

|||
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|사용되지 않음 (0)|
|다음을 반환합니다.|사용되지 않음 (0)|

*bDisableIfNoHandler는* ON_UPDATE_COMMAND_UI ON_COMMAND 처리기가 없는 경우 UI 개체를 사용하지 않도록 설정하는 데 0이 아닙니다.

**WM_EXITHELPMODE**

이 메시지는 컨텍스트에 `CFrameWnd` 민감한 도움말 모드를 종료하는 에 게시됩니다. 이 메시지의 수신은 에서 시작된 모달 루프를 `CFrameWnd::OnContextHelp`종료합니다.

|||
|-|-|
|wParam|사용되지 않음 (0)|
|lParam|사용되지 않음 (0)|
|다음을 반환합니다.|사용되지 않음|

**WM_INITIALUPDATE**

이 메시지는 초기 업데이트를 수행하는 것이 안전할 때 문서 템플릿에서 프레임 창의 모든 하위 하위 항목에 전송됩니다. 호출에 `CView::OnInitialUpdate` 매핑되지만 다른 원샷 업데이트를 `CWnd`위해 다른 파생 클래스에서 사용할 수 있습니다.

|||
|-|-|
|wParam|사용되지 않음 (0)|
|lParam|사용되지 않음 (0)|
|다음을 반환합니다.|사용되지 않음 (0)|

**WM_RECALCPARENT**

이 메시지는 레이아웃 재계산을 강제로 (일반적으로 `GetParent`부모가 호출합니다) `RecalcLayout`부모 창 (통해 얻은)에 대한 뷰에 의해 전송됩니다. 이는 뷰의 총 크기가 증가함에 따라 프레임크기가 커지는 OLE 서버 응용 프로그램에서 사용됩니다.

부모 창이 이 메시지를 처리하는 경우 TRUE를 반환하고 lParam에서 전달된 RECT를 클라이언트 영역의 새 크기로 채워야 합니다. 서버 개체가 `CScrollView` 활성화되어 있을 때 스크롤 막대(추가될 때 창 외부에 배치)를 올바르게 처리하는 데 사용됩니다.

|||
|-|-|
|wParam|사용되지 않음 (0)|
|lParam|LPRECT rectClient, NULL일 수 있습니다.|
|다음을 반환합니다.|TRUE 새 클라이언트 사각형반환 하는 경우, FALSE 그렇지 않으면|

**WM_SIZECHILD**

이 메시지는 사용자가 `COleResizeBar` 크기 조정 핸들을 사용하여 크기 조정 막대의 크기를 조정할 때 소유자 창(via)으로 `GetOwner`전송됩니다. `COleIPFrameWnd`사용자가 요청한 대로 프레임 창의 위치를 변경하려고 시도하여 이 메시지에 응답합니다.

크기 조정 막대가 포함된 프레임 창을 기준으로 클라이언트 좌표에 지정된 새 사각형은 lParam으로 가리키고 있습니다.

|||
|-|-|
|wParam|사용되지 않음 (0)|
|lParam|LPRECT 렉트뉴|
|다음을 반환합니다.|사용되지 않음 (0)|

**WM_DISABLEMODAL**

이 메시지는 비활성화되는 프레임 창이 소유한 모든 팝업 창으로 전송됩니다. 프레임 창은 결과를 사용하여 팝업 창을 사용하지 않도록 설정할지 여부를 결정합니다.

프레임이 모달 상태가 될 때 팝업 창에서 특수 처리를 수행하거나 특정 팝업 창이 비활성화되지 않도록 하려면 이 방법을 사용할 수 있습니다. 예를 들어, 프레임 창이 모달 상태로 전환될 때 도구 설명은 이 메시지를 사용하여 자신을 파괴합니다.

|||
|-|-|
|wParam|사용되지 않음 (0)|
|lParam|사용되지 않음 (0)|
|다음을 반환합니다.|0이 아닌 창을 사용하지 않도록 설정하지 **않음,** 0은 창이 비활성화됨을 나타냅니다.|

**WM_FLOATSTATUS**

이 메시지는 프레임이 다른 최상위 프레임 창에서 활성화되거나 비활성화될 때 프레임 창이 소유한 모든 팝업 창으로 전송됩니다. 이는 MFS_SYNCACTIVE `CMiniFrameWnd`구현하여 이러한 팝업 창의 활성화를 최상위 프레임 창의 활성화와 동기화하는 데 사용됩니다.

|||
|-|-|
|wParam|"Admin"<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|사용되지 않음 (0)|

FS_SYNCACTIVE 설정되고 창이 부모 프레임과 활성화를 동기화하는 경우 반환 값은 0이 아닌 값이어야 합니다. `CMiniFrameWnd`스타일이 MFS_SYNCACTIVE 설정되면 0이 아닌 반환됩니다.

자세한 내용은 `CMiniFrameWnd`의 구현을 참조하십시오.

## <a name="wm_activatetoplevel"></a>WM_ACTIVATETOPLEVEL

이 메시지는 "최상위 그룹"의 창이 활성화되거나 비활성화될 때 최상위 창으로 전송됩니다. 창은 최상위 창(상위 또는 소유자 없음)이거나 이러한 창이 소유한 경우 최상위 그룹의 일부입니다. 이 메시지는 WM_ACTIVATEAPP 사용에서 비슷하지만 다른 프로세스에 속하는 창이 단일 창 계층 구조(OLE 응용 프로그램에서 일반적)에 혼합되어 있는 상황에서 작동합니다.

## <a name="wm_commandhelp-wm_helphittest-wm_exithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

이러한 메시지는 상황에 맞는 도움말의 구현에 사용됩니다. 자세한 내용은 [기술 참고 28을](../mfc/tn028-context-sensitive-help-support.md) 참조하십시오.

## <a name="mfc-private-resource-formats"></a>MFC 개인 리소스 형식

현재 MFC는 RT_TOOLBAR 및 RT_DLGINIT 두 가지 개인 리소스 형식을 정의합니다.

## <a name="rt_toolbar-resource-format"></a>RT_TOOLBAR 리소스 형식

AppWizard에서 제공하는 기본 도구 모음은 MFC 4.0에 도입된 RT_TOOLBAR 사용자 지정 리소스를 기반으로 합니다. 도구 모음 편집기에서 이 리소스를 편집할 수 있습니다.

## <a name="rt_dlginit-resource-format"></a>RT_DLGINIT 리소스 형식

하나의 MFC 개인 리소스 형식은 추가 대화 상자 초기화 정보를 저장하는 데 사용됩니다. 여기에는 콤보 상자에 저장된 초기 문자열이 포함됩니다. 이 리소스의 형식은 수동으로 편집하도록 설계되지 않았지만 Visual C++에서 처리합니다.

Visual C++ 및 이 RT_DLGINIT 리소스는 리소스의 정보를 사용하는 API 대안이 있기 때문에 MFC의 관련 기능을 사용할 필요가 없습니다. Visual C++를 사용하면 장기적으로 응용 프로그램을 훨씬 쉽게 작성, 유지 관리 및 번역할 수 있습니다.

RT_DLGINIT 리소스의 기본 구조는 다음과 같습니다.

```
+---------------+    \
| Control ID    |   UINT             |
+---------------+    |
| Message #     |   UINT             |
+---------------+    |
|length of data |   DWORD            |
+---------------+    |   Repeated
|   Data        |   Variable Length  |   for each control
|   ...         |   and Format       |   and message
+---------------+    /
|     0         |   BYTE
+---------------+
```

반복 된 섹션에는 메시지를 보낼 제어 ID, 보낼 메시지 # (일반 Windows 메시지) 및 데이터의 가변 길이가 포함 됩니다. Windows 메시지는 다음과 같은 형태로 전송됩니다.

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

이것은 모든 Windows 메시지와 데이터 콘텐츠를 허용하는 매우 일반적인 형식입니다. Visual C++ 리소스 편집기와 MFC는 제한된 Windows 메시지 하위 집합만 지원합니다 CB_ADDSTRING.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
