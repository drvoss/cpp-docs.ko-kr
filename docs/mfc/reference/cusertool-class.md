---
title: CUserTool 클래스
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: 183b30961e4a7d3079fa0d035a4ddc38bc2eebac
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752024"
---
# <a name="cusertool-class"></a>CUserTool 클래스

사용자 도구는 외부 애플리케이션을 실행하는 메뉴 항목입니다. **사용자 지정** 대화 [상자(CMFCToolBarsCustomizeDialog 클래스)의](../../mfc/reference/cmfctoolbarscustomizedialog-class.md) **도구** 탭을 사용하면 사용자가 사용자 도구를 추가하고 각 사용자 도구에 대한 이름, 명령, 인수 및 초기 디렉터리를 지정할 수 있습니다.

## <a name="syntax"></a>구문

```
class CUserTool : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CUserTool::복사아이콘토클립보드](#copyicontoclipboard)||
|[CUserTool::DrawToolIcon](#drawtoolicon)|지정된 사각형에 사용자 도구 아이콘을 그립니다.|
|[CUserTool::GetCommand](#getcommand)|사용자 도구와 연결된 명령의 텍스트가 포함된 문자열을 반환합니다.|
|[CUserTool::GetCommandId](#getcommandid)|사용자 도구의 메뉴 항목의 명령 ID를 반환합니다.|
|[CUserTool::호출](#invoke)|사용자 도구와 연결된 명령을 실행합니다.|
|[CUserTool::직렬화](#serialize)|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CUserTool::설정 명령](#setcommand)|사용자 도구와 연결된 명령을 설정합니다.|
|[CUserTool::settoolicon](#settoolicon)|도구와 연결된 응용 프로그램에서 사용자 도구아이콘을 로드합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CUserTool::로드디폴티콘](#loaddefaulticon)|사용자 도구의 기본 아이콘을 로드합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|사용자 도구에 대한 명령줄 인수입니다.|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|사용자 도구의 초기 디렉터리입니다.|
|[CUserTool::m_strLabel](#m_strlabel)|도구의 메뉴 항목에 표시되는 도구 이름입니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 사용자 도구를 사용하도록 설정하는 방법에 대한 자세한 내용은 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CUserToolsManager` 개체에서 도구를 만들고, 멤버 변수를 `m_strLabel` 설정하고, 사용자 도구가 실행되는 응용 프로그램을 설정하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxusertool.h

## <a name="cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::복사아이콘토클립보드

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon

지정된 사각형의 가운데에 사용자 도구 아이콘을 그립니다.

```cpp
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectImage*<br/>
【인】 아이콘을 표시할 영역의 좌표를 지정합니다.

## <a name="cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::GetCommand

사용자 도구와 연결된 명령의 텍스트가 포함된 문자열을 반환합니다.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Return Value

사용자 도구와 연결된 명령의 텍스트가 포함된 `CString` 개체에 대한 참조입니다.

## <a name="cusertoolgetcommandid"></a><a name="getcommandid"></a>CUserTool::GetCommandId

사용자 도구의 명령 ID를 반환합니다.

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Return Value

이 사용자 도구의 명령 ID입니다.

## <a name="cusertoolinvoke"></a><a name="invoke"></a>CUserTool::호출

사용자 도구와 연결된 명령을 실행합니다.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Return Value

명령이 성공적으로 실행된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

사용자 도구와 연결된 명령을 실행하려면 [ShellExecute를](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) 호출합니다. 명령이 비어 있거나 [ShellExecute가](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) 실패하면 함수가 실패합니다.

## <a name="cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUserTool::로드디폴티콘

사용자 도구의 기본 아이콘을 로드합니다.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Return Value

기본 아이콘을 로드할 수 없는 경우 로드된 아이콘(HICON) 또는 NULL에 대한 핸들입니다.

### <a name="remarks"></a>설명

프레임워크는 도구의 실행 파일에서 사용자 정의 도구에 대한 아이콘을 로드할 수 없는 경우 이 메서드를 호출합니다.

이 메서드를 재정의하여 고유한 기본 도구 아이콘을 제공합니다.

## <a name="cusertoolm_strarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments

사용자 도구에 대한 명령줄 인수입니다.

```
CString m_strArguments;
```

### <a name="remarks"></a>설명

이 문자열은 [CUserTool::Invoke를](#invoke) 호출하거나 사용자가 이 도구와 연결된 명령을 클릭할 때 도구에 전달됩니다.

## <a name="cusertoolm_strinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory

사용자 도구의 초기 디렉터리를 지정합니다.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>설명

이 변수는 [CUserTool::Invoke를](#invoke) 호출하거나 사용자가 이 도구와 연결된 명령을 클릭할 때 도구가 실행되는 초기 디렉터리를 지정합니다.

## <a name="cusertoolm_strlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel

도구의 메뉴 항목에 표시되는 레이블입니다.

```
CString m_strLabel;
```

## <a name="cusertoolserialize"></a><a name="serialize"></a>CUserTool::직렬화

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

[in] *ar*<br/>

### <a name="remarks"></a>설명

## <a name="cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::설정 명령

사용자 도구가 실행되는 응용 프로그램을 설정합니다.

```cpp
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>매개 변수

*lpszCmd*<br/>
【인】 사용자 도구와 연결될 새 응용 프로그램을 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 사용자 도구가 실행되는 새 응용 프로그램을 설정합니다. 메서드는 이전 아이콘을 삭제 하 고 주어진된 응용 프로그램에서 새 아이콘을 로드 합니다. 응용 프로그램에서 아이콘을 로드할 수 없는 경우 [CUserTool::LoadDefaultIcon](#loaddefaulticon)을 호출하여 사용자 도구의 기본 아이콘을 로드합니다.

## <a name="cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::settoolicon

도구가 사용하는 응용 프로그램에서 사용자 도구의 아이콘을 로드합니다.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Return Value

로드된 아이콘의 핸들입니다.

### <a name="remarks"></a>설명

메뉴 항목에 표시할 아이콘을 로드하려면 이 메서드를 호출합니다. 이 메서드는 도구에서 사용하는 실행 파일의 아이콘을 검색합니다. 기본 아이콘이 없는 경우 [CUserTool::LoadDefaultIcon에서](#loaddefaulticon) 제공하는 아이콘이 대신 사용됩니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)<br/>
[CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)
