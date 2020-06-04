---
title: CMFC마스크편집클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
ms.openlocfilehash: 26617f10605fe2a8a94adcc477cccab7e2ba4919
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754228"
---
# <a name="cmfcmaskededit-class"></a>CMFC마스크편집클래스

클래스는 `CMFCMaskedEdit` 마스크에 대한 사용자 입력의 유효성을 검사하고 템플릿에 따라 유효성이 검사된 결과를 표시하는 마스크된 편집 컨트롤을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|기본 생성자입니다.|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC마스크편집::D사용 가능한 마스크](#disablemask)|사용자 입력의 유효성을 검사하지 않습니다.|
|[CMFC마스크 편집::인에이블겟마스크차스만](#enablegetmaskedcharsonly)|메서드가 `GetWindowText` 마스크된 문자만 검색하는지 여부를 지정합니다.|
|[CMFC마스크 편집::인에이블 마스크](#enablemask)|마스크된 편집 컨트롤을 초기화합니다.|
|[CMFC마스크 편집::인에이블셀렉트바이그룹](#enableselectbygroup)|마스크된 편집 컨트롤이 특정 사용자 입력 그룹 또는 모든 사용자 입력을 선택하는지 여부를 지정합니다.|
|[CMFC마스크 편집::인에이블셋마스크차만](#enablesetmaskedcharsonly)|텍스트가 마스크된 문자에 대해서만 유효성을 검사하는지 또는 전체 마스크에 대해 유효성을 검사하는지 지정합니다.|
|`CMFCMaskedEdit::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC마스크 편집::GetWindow텍스트](#getwindowtext)|마스크된 편집 컨트롤에서 검증된 텍스트를 검색합니다.|
|[CMFC마스크 편집::세트유효차르](#setvalidchars)|사용자가 입력할 수 있는 유효한 문자 문자열을 지정합니다.|
|[CMFC마스크 편집::SetWindow텍스트](#setwindowtext)|마스크된 편집 컨트롤에 프롬프트를 표시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC마스크편집::이스마스크차](#ismaskedchar)|해당 마스크 문자에 대해 지정된 문자의 유효성을 검사하기 위해 프레임워크에서 호출합니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 `CMFCMaskedEdit` 컨트롤을 사용 하려면 다음 단계를 수행 합니다.

1. 창 클래스에 개체를 `CMFCMaskedEdit` 포함합니다.

2. [CMFCMaskedEdit::EnableMask](#enablemask) 메서드를 호출하여 마스크를 지정합니다.

3. [CMFCMaskedEdit::SetValidChars 메서드를](#setvalidchars) 호출하여 유효한 문자 목록을 지정합니다.

4. [CMFCMaskedEdit::SetWindowText](#setwindowtext) 메서드를 호출하여 마스크된 편집 컨트롤의 기본 텍스트를 지정합니다.

5. [CMFCMaskedEdit::GetWindowText](#getwindowtext) 메서드를 호출하여 검증된 텍스트를 검색합니다.

마스크, 유효한 문자 및 기본 텍스트를 초기화하기 위해 하나 이상의 메서드를 호출하지 않으면 마스크된 편집 컨트롤이 표준 편집 컨트롤이 작동하듯이 작동합니다.

## <a name="example"></a>예제

다음 예제에서는 마스크 편집 컨트롤에 대 한 마스크를 만드는 `EnableMask` 메서드를 사용 하 여 마스크(예: 전화 `SetValidChars` 번호)를 설정 하는 방법을 보여 줍니다., 사용자가 입력할 수 있는 유효한 문자의 문자열을 지정 하는 메서드 및 `SetWindowText` 마스크 된 편집 컨트롤에 프롬프트를 표시 하는 메서드입니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxmaskededit.h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a>CMFC마스크편집::D사용 가능한 마스크

사용자 입력의 유효성을 검사하지 않습니다.

```cpp
void DisableMask();
```

### <a name="remarks"></a>설명

사용자 입력 유효성 검사를 사용하지 않도록 설정하면 마스크된 편집 컨트롤이 표준 편집 컨트롤처럼 작동합니다.

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a>CMFC마스크 편집::인에이블겟마스크차스만

메서드가 `GetWindowText` 마스크된 문자만 검색하는지 여부를 지정합니다.

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 [CMFCMaskedEdit::GetWindowText](#getwindowtext) 메서드가 마스크된 문자만 검색하도록 지정합니다. FALSE 메서드가 전체 텍스트를 검색하도록 지정합니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

마스크된 문자를 검색하려면 이 메서드를 사용합니다. 그런 다음 (425) 555-0187과 같은 전화 번호에 해당하는 마스크된 편집 컨트롤을 만듭니다. 메서드를 `GetWindowText` 호출하면 "425550187"을 반환합니다. 마스크된 문자 검색을 사용하지 않도록 `GetWindowText` 설정하면 메서드는 "(425) 555-0187"과 같은 편집 컨트롤에 표시되는 텍스트를 반환합니다.

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a>CMFC마스크 편집::인에이블 마스크

마스크된 편집 컨트롤을 초기화합니다.

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz 마스크*<br/>
【인】 사용자 입력의 각 위치에 나타날 수 있는 문자 유형을 지정하는 마스크 문자열입니다. *lpszInputTemplate* 및 *lpszMask* 매개 변수 문자열의 길이는 동일해야 합니다. 마스크 문자에 대한 자세한 내용은 비고 섹션을 참조하십시오.

*lpsz입력템플릿*<br/>
【인】 사용자 입력의 각 위치에 나타날 수 있는 리터럴 문자를 지정하는 마스크 템플릿 문자열입니다. 밑줄 문자('_')를 문자 자리 표시자로 사용합니다. *lpszInputTemplate* 및 *lpszMask* 매개 변수 문자열의 길이는 동일해야 합니다.

*chMask입력 템플릿*<br/>
【인】 프레임워크가 사용자 입력의 잘못된 각 문자를 대체하는 기본 문자입니다. 이 매개 변수의 기본값은 밑줄('_')입니다.

*lpsz유효*<br/>
【인】 유효한 문자 집합을 포함하는 문자열입니다. NULL은 모든 문자가 유효하다는 것을 나타냅니다. 이 매개 변수의 기본값은 NULL입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 마스크 된 편집 컨트롤에 대 한 마스크를 만듭니다. `CMFCMaskedEdit` 클래스에서 클래스를 파생 하 고 [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) 메서드 사용자 지정 마스크 처리에 대 한 사용자 고유의 코드를 사용 하 여 재정의 합니다.

다음 표에는 기본 마스크 문자가 나열됩니다.

|마스크 캐릭터|정의|
|--------------------|----------------|
|D|자리.|
|d|숫자 또는 공간입니다.|
|+|플러스('+'), 마이너스('-') 또는 공백.|
|C|알파벳 문자입니다.|
|c|알파벳 문자 또는 공간입니다.|
|A|영숫자.|
|a|영숫자 문자 또는 공간.|
|*|인쇄 가능한 문자입니다.|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a>CMFC마스크 편집::인에이블셀렉트바이그룹

마스크된 편집 컨트롤을 통해 사용자가 특정 그룹 입력또는 모든 입력을 선택할 수 있는지 여부를 지정합니다.

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 그룹만 선택합니다. FALSE를 클릭하여 전체 텍스트를 선택합니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 마스크된 편집 컨트롤을 사용하여 사용자가 그룹별로 선택할 수 있는지 또는 전체 텍스트를 선택할 수 있는지 여부를 지정합니다.

기본적으로 그룹별 선택이 활성화됩니다. 이 경우 사용자는 유효한 문자의 연속 그룹만 선택할 수 있습니다.

예를 들어 다음 마스머드 편집 컨트롤을 사용하여 전화 번호의 유효성을 검사할 수 있습니다.

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

그룹별 선택이 활성화된 경우 사용자는 "425", "555" 또는 "0187" 문자열 그룹만 검색할 수 있습니다. 그룹 선택이 비활성화된 경우 사용자는 전화 번호의 전체 텍스트를 검색할 수 있습니다: "(425) 555-0187".

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a>CMFC마스크 편집::인에이블셋마스크차만

텍스트가 마스크된 문자에 대해서만 유효성을 검사하는지 또는 전체 마스크에 대해 유효성을 검사하는지 지정합니다.

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 마스크된 문자에 대해서만 사용자 입력의 유효성을 검사합니다. FALSE는 전체 마스크에 대해 유효성을 검사합니다. 기본값은 TRUE입니다.

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a>CMFC마스크 편집::GetWindow텍스트

마스크된 편집 컨트롤에서 검증된 텍스트를 검색합니다.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>매개 변수

*lpsz스트링부프*<br/>
【아웃】 편집 컨트롤에서 텍스트를 받는 버퍼에 대한 포인터입니다.

*n맥스카운트*<br/>
【인】 수신할 최대 문자 수입니다.

*rstrString*<br/>
【아웃】 편집 컨트롤에서 텍스트를 받는 문자열 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

첫 번째 메서드 오버로드는 *lpszStringBuf* 매개 변수 버퍼에 복사된 문자열의 바이트 수를 반환합니다. 마스크된 편집 컨트롤에 텍스트가 없는 경우 0입니다.

### <a name="remarks"></a>설명

이 메서드는 마스커링된 편집 컨트롤에서 *lpszStringBuf* 버퍼 또는 *rstrString* 문자열에 텍스트를 복사합니다.

이 메서드는 [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)를 재정의합니다.

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a>CMFC마스크편집::이스마스크차

해당 마스크 문자에 대해 지정된 문자의 유효성을 검사하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>매개 변수

*chchar*<br/>
【인】 유효성을 검사할 문자입니다.

*chMaskChar*<br/>
【인】 마스크 문자열의 해당 문자입니다.

### <a name="return-value"></a>Return Value

*true chChar* 매개 변수가 *chMaskChar* 매개 변수에서 허용하는 문자 유형인 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 입력 문자의 유효성을 검사합니다. 마스크 문자에 대한 자세한 내용은 [CMFCMaskedEdit::EnableMask](#enablemask) 메서드를 참조하십시오.

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a>CMFC마스크 편집::세트유효차르

사용자가 입력할 수 있는 유효한 문자 문자열을 지정합니다.

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>매개 변수

*lpsz유효*<br/>
【인】 유효한 입력 문자 집합을 포함하는 문자열입니다. NULL은 모든 문자가 유효하다는 것을 의미합니다. 이 매개 변수의 기본값은 NULL입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 유효한 문자 목록을 정의합니다. 입력 문자가 이 목록에 없는 경우 마스크된 편집 컨트롤은 해당 문자를 허용하지 않습니다.

다음 코드 예제는 육각 숫자만 허용합니다.

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a>CMFC마스크 편집::SetWindow텍스트

마스크된 편집 컨트롤에 프롬프트를 표시합니다.

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*lpszString*<br/>
【인】 프롬프트로 사용되는 null 종료 된 문자열을 가리킵니다.

### <a name="remarks"></a>설명

이 메서드는 컨트롤 텍스트를 설정 합니다.

이 메서드는 [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)를 재정의합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)
