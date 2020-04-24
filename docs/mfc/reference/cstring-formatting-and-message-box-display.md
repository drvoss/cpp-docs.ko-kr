---
title: CString 서식 지정 및 메시지 상자 표시
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: fa1fe8826543834872de5257a0f5d56b2ad9fc1c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752678"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString 서식 지정 및 메시지 상자 표시

개체의 형식 지정 및 구문 분석에는 `CString` 여러 함수가 제공됩니다. `CString` 개체를 조작해야 할 때마다 이러한 함수를 사용할 수 있지만 메시지 상자 텍스트에 나타나는 문자열 서식을 지정하는 데 특히 유용합니다.

이 함수 그룹에는 메시지 상자를 표시하기 위한 전역 루틴도 포함됩니다.

### <a name="cstring-functions"></a>CString 함수

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|지정된 소스 문자열에서 단일 문자로 구분된 하위 문자열을 추출합니다.|
|[AfxFormatString1](#afxformatstring1)|문자열 테이블에 포함된 문자열에서 형식 문자 "%1"에 대해 지정된 문자열을 대체합니다.|
|[AfxFormatString2](#afxformatstring2)|문자열 테이블에 포함된 문자열에서 형식 문자 "%1" 및 "%2"에 대해 두 문자열을 대체합니다.|
|[AfxMessageBox](#afxmessagebox)|메시지 상자를 표시합니다.|

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxextractsubstring"></a><a name="afxextractsubstring"></a>Afx추출서브스트링

이 전역 함수는 지정된 소스 문자열에서 하위 문자열을 추출하는 데 사용할 수 있습니다.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
개별 하위 문자열을 수신하는 [CString](../../atl-mfc-shared/using-cstring.md) 개체에 대한 참조입니다.

*lpsz풀스트링*<br/>
추출할 문자열의 전체 텍스트를 포함하는 문자열입니다.

*아이 서브 스트링*<br/>
*lpszFullString에서*추출할 하위 문자열의 제로 기반 인덱스 .

*chSep*<br/>
하위 문자열을 구분하는 데 사용되는 구분 기호 문자입니다.

### <a name="return-value"></a>Return Value

TRUE 함수가 제공된 인덱스에서 서브스트링을 성공적으로 추출한 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 함수는 알려진 단일 문자가 각 하위 문자열을 구분할 때 소스 문자열에서 여러 하위 문자열을 추출하는 데 유용합니다. 이 함수는 호출될 때마다 *lpszFullString* 매개 변수의 시작 부분에서 검색합니다.

*lpszFullString이* NULL로 설정되거나 함수가 지정된 구분 기호 문자의 *iSubString*+1 발생을 찾지 않고 *lpszFullString의* 끝에 도달하면 이 함수는 FALSE를 반환합니다. *lpszFullString이* NULL로 설정된 경우 *rString* 매개 변수는 원래 값에서 수정되지 않습니다. 그렇지 않으면 지정된 인덱스에 대한 하위 문자열을 추출할 수 없는 경우 *rString* 매개 변수가 빈 문자열로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormat스트링1

*nIDS로*식별된 템플릿 문자열 리소스에서 문자 "%1"의 인스턴스에 대해 *lpsz1로* 가리키는 문자열을 대체합니다.

```cpp
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
대체가 수행된 후 결과 문자열을 포함하는 `CString` 개체에 대한 참조입니다.

*Nids*<br/>
대체가 수행될 템플릿 문자열의 리소스 ID입니다.

*lpsz1*<br/>
템플릿 문자열에서 서식 문자 "%1"을(를) 대체하는 문자열입니다.

### <a name="remarks"></a>설명

새로 형성된 문자열은 *rString에*저장됩니다. 예를 들어 문자열 테이블의 문자열이 "파일 %1을 찾을 수 없습니다"이고 *lpsz1이* "C:\MYFILE"과 같으면 됩니다. TXT", 다음 *rString* 문자열을 포함 합니다 "파일 C:\MYFILE. TXT를 찾을 수 없습니다". 이 함수는 메시지 상자와 다른 창에 서식 지정 문자열을 전송하는 데 유용합니다.

서식 문자 "%1"이(가) 두 번 이상 문자열에 나타나는 경우 대체가 여러 번 수행됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormat스트링2

*nIDS로*식별된 템플릿 문자열 리소스에서 문자 "%1"의 인스턴스에 대해 *lpsz1로* 가리키는 문자열과 문자 "%2"의 모든 인스턴스에 대해 *lpsz2로* 가리키는 문자열을 대체합니다.

```cpp
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
대체가 `CString` 수행된 후 결과 문자열을 포함하는 참조입니다.

*Nids*<br/>
대체가 수행될 템플릿 문자열의 문자열 테이블 ID입니다.

*lpsz1*<br/>
템플릿 문자열에서 서식 문자 "%1"을(를) 대체하는 문자열입니다.

*lpsz2*<br/>
템플릿 문자열의 형식 문자 "%2"를 대체하는 문자열입니다.

### <a name="remarks"></a>설명

새로 형성된 문자열은 *rString에*저장됩니다. 예를 들어 문자열 테이블의 문자열이 "디렉토리 %2에서 찾을 수 없는 파일 %1"인 경우 *lpsz1은* "MYFILE"을 가리킵니다. TXT", 및 *lpsz2는* "C:\MYDIR"을 가리키고, *다음 rString문자열* "파일 MYFILE"을 포함합니다. TXT는 디렉토리 C에서 찾을 수 없습니다:\MYDIR"

형식 문자 "%1" 또는 "%2"가 문자열에 두 번 이상 나타나면 여러 대체가 만들어집니다. 숫자 순서일 필요는 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox

화면에 메시지 상자를 표시합니다.

```
int AfxMessageBox(
    LPCTSTR lpszText,
    UINT nType = MB_OK,
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,
    UINT nType = MB_OK,
    UINT nIDHelp = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
메시지 상자에 `CString` 표시할 메시지를 포함하는 개체 또는 null 종료 문자열을 가리킵니다.

*nType*<br/>
메시지 상자의 스타일입니다. 상자에 메시지 [상자 스타일을](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) 적용합니다.

*니드 도움말*<br/>
메시지에 대한 도움말 컨텍스트 ID; 0은 응용 프로그램의 기본 도움말 컨텍스트가 사용됩니다 나타냅니다.

*니드프롬프트*<br/>
문자열 테이블에서 문자열을 참조하는 데 사용되는 고유 ID입니다.

### <a name="return-value"></a>Return Value

메시지 상자를 표시할 메모리가 충분하지 않으면 0입니다. 그렇지 않으면 다음 값 중 하나가 반환됩니다.

- IDABORT 중단 버튼이 선택되었습니다.

- IDCANCEL 취소 버튼이 선택되었습니다.

- IDIGNORE 무시 버튼이 선택되었습니다.

- IDNO 없음 단추가 선택되었습니다.

- IDOK 확인 버튼이 선택되었습니다.

- IDRETRY 재시도 버튼이 선택되었습니다.

- IDYES 예 버튼이 선택되었습니다.

메시지 상자에 취소 버튼이 있는 경우 ESC 키를 누르거나 취소 단추를 선택하면 IDCANCEL 값이 반환됩니다. 메시지 상자에 취소 버튼이 없는 경우 ESC 키를 누르면 아무런 효과가 없습니다.

[함수 AfxFormatString1](#afxformatstring1) 및 [AfxFormatString2는](#afxformatstring2) 메시지 상자에 나타나는 텍스트 서식을 지정하는 데 유용할 수 있습니다.

### <a name="remarks"></a>설명

이 오버로드 된 함수의 첫 번째 형식은 메시지 상자에 *lpszText로* 가리키는 텍스트 문자열을 표시하고 *nIDHelp를* 사용하여 도움말 컨텍스트를 설명합니다. 도움말 컨텍스트는 사용자가 도움말 키(일반적으로 F1)를 누를 때 연결된 도움말 항목으로 이동하는 데 사용됩니다.

함수의 두 번째 형식은 ID *nIDPrompt가* 있는 문자열 리소스를 사용하여 메시지 상자에 메시지를 표시합니다. 연결된 도움말 페이지는 *nIDHelp*의 값을 통해 찾을 수 있습니다. *nIDHelp의* 기본값을 사용하는 경우(-1), 문자열 리소스 ID, *nIDPrompt는*도움말 컨텍스트에 사용됩니다. 도움말 컨텍스트 정의에 대한 자세한 내용은 [기술 참고 28을](../../mfc/tn028-context-sensitive-help-support.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>참조

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)
