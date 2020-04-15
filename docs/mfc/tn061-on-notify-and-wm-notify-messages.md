---
title: 'TN061: ON_NOTIFY 및 WM_NOTIFY 메시지'
ms.date: 06/28/2018
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: 845558dad6b9f6e820c759cb83fce2c6cbceaa0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366594"
---
# <a name="tn061-on_notify-and-wm_notify-messages"></a>TN061: ON_NOTIFY 및 WM_NOTIFY 메시지

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트는 새 WM_NOTIFY 메시지에 대한 배경 정보를 제공하며 MFC 응용 프로그램에서 WM_NOTIFY 메시지를 처리하는 권장(가장 일반적인) 방법을 설명합니다.

**Windows 3.x의 알림 메시지**

Windows 3.x에서 컨트롤은 부모에게 메시지를 전송하여 마우스 클릭, 콘텐츠 및 선택 변경 및 제어 백그라운드 페인팅과 같은 이벤트를 부모에게 알립니다. 간단한 알림은 알림 코드(예: BN_CLICKED) 및 제어 ID가 *wParam에* 압축되고 *lParam에서*컨트롤 핸들이 있는 특수 WM_COMMAND 메시지로 전송됩니다. *wParam* 및 *lParam이* 가득 차있기 때문에 추가 데이터를 전달할 수 있는 방법은 없습니다. 예를 들어 BN_CLICKED 알림에서는 단추를 클릭할 때 마우스 커서의 위치에 대한 정보를 보낼 수 없습니다.

Windows 3.x의 컨트롤에서 추가 데이터가 포함된 알림 메시지를 보내야 하는 경우 WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_CHARTOITEM, WM_VKEYTOITEM 등 다양한 특수 목적 메시지를 사용합니다. 이러한 메시지는 메시지를 보낸 컨트롤에 다시 반영될 수 있습니다. 자세한 내용은 [TN062: Windows 컨트롤에 대한 메시지 반사를](../mfc/tn062-message-reflection-for-windows-controls.md)참조하십시오.

**Win32의 알림 메시지**

Windows 3.1에 있는 컨트롤의 경우 Win32 API는 Windows 3.x에서 사용된 대부분의 알림 메시지를 사용합니다. 그러나 Win32는 Windows 3.x에서 지원되는 컨트롤에 여러 가지 정교하고 복잡한 컨트롤을 추가합니다. 이러한 컨트롤은 알림 메시지와 함께 추가 데이터를 보내야 하는 경우가 종종 있습니다. Win32 API의 디자이너는 추가 데이터가 필요한 각 새 알림에 대해 새 **WM_** <strong>\*</strong> 메시지를 추가하는 대신 표준화된 방식으로 추가 데이터를 전달할 수 있는 WM_NOTIFY 하나의 메시지만 추가하기로 결정했습니다.

WM_NOTIFY 메시지에는 *wParam에서* 메시지를 보내는 컨트롤의 ID와 *lParam의*구조에 대한 포인터가 포함되어 있습니다. 이 구조는 **NMHDR** 구조 또는 **NMHDR** 구조를 첫 번째 멤버로 하는 일부 더 큰 구조입니다. **NMHDR** 멤버가 첫 번째이기 때문에 이 구조에 대한 포인터를 **NMHDR에** 대한 포인터또는 캐스팅 방법에 따라 더 큰 구조에 대한 포인터로 사용할 수 있습니다.

대부분의 경우 포인터는 더 큰 구조를 가리키며 사용할 때 포인터를 캐스팅해야 합니다. 일반적인 **알림(이름이 NM_** 시작)과 도구 설명 컨트롤의 TTN_SHOW 및 TTN_POP 알림과 같은 몇 가지 알림에서만 실제로 사용되는 **NMHDR** 구조입니다.

**NMHDR** 구조 또는 초기 멤버에는 메시지 및 알림 코드(예: TTN_SHOW)를 보내는 컨트롤의 핸들 및 ID가 포함되어 있습니다. **NMHDR** 구조의 형식은 다음과 같습니다.

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW 메시지의 경우 **코드** 멤버가 TTN_SHOW 설정됩니다.

대부분의 알림은 첫 번째 멤버로 **NMHDR** 구조를 포함하는 더 큰 구조에 대한 포인터를 전달합니다. 예를 들어 목록 보기 컨트롤의 LVN_KEYDOWN 알림 메시지에서 사용되는 구조를 고려해 보며, 이 메시지는 목록 보기 컨트롤에서 키를 누를 때 전송됩니다. 포인터는 아래와 같이 정의된 **LV_KEYDOWN** 구조를 가리킵니다.

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

**NMHDR** 멤버가 이 구조에서 첫 번째이기 때문에 알림 메시지에 전달된 포인터를 **NMHDR에** 대한 포인터 또는 **LV_KEYDOWN**대한 포인터로 캐스팅할 수 있습니다.

**모든 새 Windows 컨트롤에 공통된 알림**

일부 알림은 모든 새 Windows 컨트롤에 공통적입니다. 이러한 알림은 **NMHDR** 구조에 대한 포인터를 전달합니다.

|알림 코드|전송된 이유|
|-----------------------|------------------|
|NM_CLICK|사용자가 컨트롤에서 왼쪽 마우스 단추를 클릭했습니다.|
|NM_DBLCLK|사용자가 컨트롤에서 왼쪽 마우스 버튼을 두 번 클릭했습니다.|
|NM_RCLICK|사용자가 컨트롤에서 오른쪽 마우스 단추를 클릭했습니다.|
|NM_RDBLCLK|사용자가 컨트롤에서 오른쪽 마우스 버튼을 두 번 클릭했습니다.|
|NM_RETURN|컨트롤에 입력 포커스가 있는 동안 사용자가 ENTER 키를 누른 경우|
|NM_SETFOCUS|컨트롤에 입력 포커스가 부여되었습니다.|
|NM_KILLFOCUS|컨트롤이 입력 포커스를 잃었습니다.|
|NM_OUTOFMEMORY|사용 가능한 메모리가 부족하여 컨트롤이 작업을 완료할 수 없습니다.|

## <a name="on_notify-handling-wm_notify-messages-in-mfc-applications"></a><a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a>ON_NOTIFY: MFC 응용 프로그램에서 WM_NOTIFY 메시지 처리

이 `CWnd::OnNotify` 함수는 알림 메시지를 처리합니다. 기본 구현은 메시지 맵에서 호출할 알림 처리기가 확인합니다. 일반적으로 재정의하지 `OnNotify`않습니다. 대신 처리기 함수를 제공하고 해당 처리기에 대한 메시지 맵 항목을 소유자 창 클래스의 메시지 맵에 추가합니다.

ClassWizard는 ClassWizard 속성 시트를 통해 ON_NOTIFY 메시지 맵 항목을 만들고 스켈레톤 처리기 함수를 제공할 수 있습니다. 이를 쉽게 하기 위해 ClassWizard를 사용하는 방법에 대한 자세한 내용은 [메시지 메시지를 함수에 매핑을](../mfc/reference/mapping-messages-to-functions.md)참조하십시오.

ON_NOTIFY 메시지 맵 매크로에는 다음과 같은 구문이 있습니다.

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*<br/>
LVN_KEYDOWN 같은 알림 메시지를 처리할 코드입니다.

*id*<br/>
알림이 전송되는 컨트롤의 자식 식별자입니다.

*멤버Fxn*<br/>
이 알림을 보낼 때 호출할 멤버 함수입니다.

멤버 함수는 다음 프로토타입으로 선언되어야 합니다.

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*pNotifyStruct*<br/>
위의 섹션에 설명된 대로 알림 구조에 대한 포인터입니다.

*result*<br/>
반환하기 전에 설정할 결과 코드에 대한 포인터입니다.

## <a name="example"></a>예제

구성원 함수가 `OnKeydownList1` ID의 `CListCtrl` `IDC_LIST1`LVN_KEYDOWN 메시지를 처리하도록 지정하려면 ClassWizard를 사용하여 다음을 메시지 맵에 추가합니다.

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

위의 예에서 ClassWizard에서 제공하는 함수는 다음과 같이 있습니다.

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard는 적절한 형식의 포인터를 자동으로 제공합니다. *pNMHDR* 또는 *pLVKeyDow*를 통해 알림 구조에 액세스할 수 있습니다.

## <a name="on_notify_range"></a><a name="_mfcnotes_on_notify_range"></a>ON_NOTIFY_RANGE

컨트롤 집합에 대해 동일한 WM_NOTIFY 메시지를 처리해야 하는 경우 ON_NOTIFY 대신 ON_NOTIFY_RANGE 사용할 수 있습니다. 예를 들어 특정 알림 메시지에 대해 동일한 작업을 수행하려는 단추 집합이 있을 수 있습니다.

ON_NOTIFY_RANGE 사용하는 경우 범위의 시작 및 끝 자식 식별자를 지정하여 알림 메시지를 처리할 연속 하위 식별자를 지정합니다.

ClassWizard는 ON_NOTIFY_RANGE 처리하지 않습니다. 메시지를 직접 편집해야 합니다.

ON_NOTIFY_RANGE 메시지 맵 항목 및 기능 프로토타입은 다음과 같습니다.

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*<br/>
LVN_KEYDOWN 같은 알림 메시지를 처리할 코드입니다.

*id*<br/>
연속된 식별자 범위의 첫 번째 식별자입니다.

*idLast*<br/>
연속된 식별자 범위의 마지막 식별자입니다.

*멤버Fxn*<br/>
이 알림을 보낼 때 호출할 멤버 함수입니다.

멤버 함수는 다음 프로토타입으로 선언되어야 합니다.

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*id*<br/>
알림을 보낸 컨트롤의 자식 식별자입니다.

*pNotifyStruct*<br/>
위에서 설명한 대로 알림 구조에 대한 포인터입니다.

*result*<br/>
반환하기 전에 설정할 결과 코드에 대한 포인터입니다.

## <a name="on_notify_ex-on_notify_ex_range"></a><a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a>ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

알림 라우팅에서 메시지를 처리하기 위해 두 개 이상의 개체를 원하는 경우 ON_NOTIFY(또는 ON_NOTIFY_RANGE)이 아닌 ON_NOTIFY_EX(또는 ON_NOTIFY_EX_RANGE)를 사용할 수 있습니다. **EX** 버전과 일반 버전 간의 유일한 차이점은 **EX** 버전에 대해 호출된 멤버 함수가 메시지 처리를 계속할지 여부를 나타내는 **BOOL을** 반환한다는 것입니다. 이 함수에서 **FALSE를** 반환하면 두 개 이상의 개체에서 동일한 메시지를 처리할 수 있습니다.

ClassWizard는 ON_NOTIFY_EX 또는 ON_NOTIFY_EX_RANGE 처리하지 않습니다. 둘 중 하나를 사용하려면 메시지 맵을 직접 편집해야 합니다.

ON_NOTIFY_EX 및 ON_NOTIFY_EX_RANGE 대한 메시지 맵 항목 및 기능 프로토타입은 다음과 같습니다. 매개 변수의 의미는 비**EX** 버전과 동일합니다.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

위의 두 프로토타입의 프로토타입은 동일합니다.

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

두 경우 모두 *id는* 알림을 보낸 컨트롤의 자식 식별자를 보유합니다.

명령 라우팅의 다른 개체가 메시지를 처리할 수 있는 **경우** 알림 메시지가 완전히 처리된 경우 함수가 **TRUE를** 반환해야 합니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
