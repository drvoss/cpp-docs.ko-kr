---
title: CMFC데스크탑경고폰드정보 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: f51c1b75e0c096a34b190e36e097aaca4109b5f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367584"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFC데스크탑경고폰드정보 클래스

클래스는 `CMFCDesktopAlertWndInfo` [CMFCDesktopAlertWnd 클래스와](../../mfc/reference/cmfcdesktopalertwnd-class.md)함께 사용됩니다. 바탕 화면 경고 창이 표시될 경우 표시되는 컨트롤을 지정합니다.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC데스크톱경고폰드정보::연산자=](#operator_eq)||

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC데스크톱경고폰드정보::m_hIcon](#m_hicon)|표시되는 아이콘에 대한 핸들입니다.|
|[CMFC데스크톱경고폰드정보::m_nURLCmdID](#m_nurlcmdid)|데스크톱 경고 창의 링크와 연결된 명령 ID입니다.|
|[CMFC데스크톱경고폰드정보:m_strText](#m_strtext)|바탕 화면 경고 창에 표시되는 텍스트입니다.|
|[CMFC데스크톱경고폰드정보::m_strURL](#m_strurl)|데스크톱 경고 창에 표시되는 링크입니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCDesktopAlertWndInfo` [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 메서드로 전달되어 데스크톱 경고 창의 기본 대화 상자에 표시되는 요소를 지정합니다. 기본 대화 상자에는 다음 세 가지 항목이 포함될 수 있습니다.

- [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)를 호출하여 설정되는 아이콘입니다.

- [CMFCDesktopAlertWndInfo:m_strText](#m_strtext)를 호출하여 설정되는 레이블 또는 문자 메시지입니다.

- [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)를 호출하여 설정되는 링크입니다. 링크를 클릭할 때 실행되는 명령을 설정하려면 [CMFCDesktopAlertWndInfo:m_nURLCmdID](#m_nurlcmdid).

기본 대화 상자가 충분하지 않으면 사용자 지정 대화 상자를 만들어 이 클래스를 사용하는 대신 [CMFCDesktopAlertWnd:만들기](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 메서드에 전달할 수 있습니다. 자세한 내용은 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 다양한 멤버를 `CMFCDesktopAlertWndInfo` 사용하는 방법을 보여 줍니다. 이 예제에서는 핸들을 표시되는 아이콘, 데스크톱 경고 창에 표시되는 텍스트, 데스크톱 경고 창에 표시되는 링크 및 데스크톱 경고 창의 링크와 연결된 명령 ID로 핸들을 설정하는 방법을 보여 줍니다. 이 예제는 [데스크톱 경고 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDesktopAlertDialog.h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>CMFC데스크톱경고폰드정보::연산자=

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>매개 변수

【인】 *src*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a>CMFC데스크톱경고폰드정보::m_hIcon

표시되는 아이콘에 대한 핸들입니다.

```
HICON m_hIcon;
```

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a>CMFC데스크톱경고폰드정보::m_nURLCmdID

데스크톱 경고 창의 링크와 연결된 명령 ID입니다.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>설명

명령 ID는 사용자가 [CMFCDesktopAlertWndInfo:m_strURL](#m_strurl)에 의해 지정된 링크를 클릭할 때 팝업 창의 소유자에게 전송됩니다.

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a>CMFC데스크톱경고폰드정보:m_strText

바탕 화면 경고 창에 표시되는 텍스트입니다.

```
CString m_strText;
```

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a>CMFC데스크톱경고폰드정보::m_strURL

데스크톱 경고 창에 표시되는 링크입니다.

```
CString m_strURL;
```

### <a name="remarks"></a>설명

사용자가 링크를 클릭하면 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) 명령 ID가 있는 명령이 팝업 창의 소유자에게 전송됩니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFC데스크톱경고::만들기](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFC데스크탑경고디아로그 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)
