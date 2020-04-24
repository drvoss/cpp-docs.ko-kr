---
title: CMFCAcceleratorKeyAssignCtrl 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: 2021a2069885c6314859a65d528cf03712c524b6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751741"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl 클래스

클래스는 `CMFCAcceleratorKeyAssignCtrl` ALT, 제어 및 SHIFT와 같은 추가 시스템 단추를 지원하기 위해 [CEdit 클래스를](../../mfc/reference/cedit-class.md) 확장합니다.

## <a name="syntax"></a>구문

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCAccelerator키시그함Ctrl:::CMFCAcceleratorKey시인Ctrl](#cmfcacceleratorkeyassignctrl)|`CMFCAcceleratorKeyAssignCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|`CMFCAcceleratorKeyAssignCtrl` 개체에서 누른 바로 가기 키에 대한 `ACCEL` 구조체를 검색합니다.|
|[CMFCAcceleratorKey시사인Ctrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|바로 가기 키가 정의되었는지 여부를 확인합니다.|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/win32/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|바로 가기 키를 다시 설정합니다.|

## <a name="remarks"></a>설명

이 클래스는 액셀러레이터 키라고도 하는 바로 가기 키를 지원하여 `CEdit` 클래스의 기능을 확장합니다. 클래스는 `CMFCAcceleratorKeyAssignCtrl` [CEdit 클래스로](../../mfc/reference/cedit-class.md) 작동하며 시스템 단추도 인식할 수 있습니다.

이 클래스는 실제 바로 가기 키 조합을 문자열 값에 매핑합니다. 예를 들어 키 조합 ALT + B가 문자열 "Alt + B"에 매핑된다고 가정하겠습니다. 사용자가 `CMFCAcceleratorKeyAssignCtrl` 개체에서 이 키를 조합을 누르면 "Alt + B"가 사용자에게 표시됩니다. 바로 가기 키와 문자열 형식 간의 매핑에 대한 자세한 내용은 [CMFCAcceleratorKey 키 클래스를](../../mfc/reference/cmfcacceleratorkey-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCAcceleratorKeyAssignCtrl` 개체를 생성하고 해당 `ResetKey` 메서드를 사용하여 바로 가기 키를 다시 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxacceleratorkeyassignctrl.h

## <a name="cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a>CMFCAccelerator키시그함Ctrl:::CMFCAcceleratorKey시인Ctrl

[CMFCAcceleratorKey할당Ctrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 개체를 생성합니다.

```
CMFCAcceleratorKeyAssignCtrl();
```

## <a name="cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a>CMFCAccelerator키시사인Ctrl::GetAccel

[CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 개체에서 누른 바로 가기 키에 대한 `ACCEL`구조를 검색합니다.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Return Value

바로 `ACCEL` 가기 키를 설명하는 구조입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 `ACCEL` 사용자가 개체에 입력한 바로 가기 `CMFCAcceleratorKeyAssignCtrl` 키에 대한 구조를 검색합니다.

## <a name="cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a>CMFCAcceleratorKey시사인Ctrl::IsFocused

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a>CMFCAcceleratorKey할당Ctrl::IsKey정의

바로 가기 키가 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 개체에 정의되었는지 여부를 결정합니다.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Return Value

사용자가 이미 바로 가기 키를 정의하는 키의 유효한 조합을 눌렀다면 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 사용하여 사용자가 개체에 유효한 바로 `CMFCAcceleratorKeyAssignCtrl` 가기 키를 입력했는지 여부를 확인합니다. 바로 가기 키가 있는 경우 [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) 메서드를 `ACCEL` 사용하여 이 바로 가기 키와 연결된 구조를 가져올 수 있습니다.

## <a name="cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCAcceleratorKey할당Ctrl::PreTranslateMessage

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

[in] *pMsg*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a>CMFCAcceleratorKey할당Ctrl::재설정키

바로 가기 키를 다시 설정합니다.

```cpp
void ResetKey();
```

### <a name="remarks"></a>설명

이 함수는 편집 제어 텍스트를 지웁히 바웁습니다. 여기에는 사용자가 누른 모든 바로 가기 키가 포함됩니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey 클래스](../../mfc/reference/cmfcacceleratorkey-class.md)
