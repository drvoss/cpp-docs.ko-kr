---
title: CMFC속성그리드파일속성 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 0ce3321968f0c29ce3b946f6127e4435b531c422
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360577"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFC속성그리드파일속성 클래스

클래스는 `CMFCPropertyGridFileProperty` 파일 선택 대화 상자를 여는 속성 목록 제어 항목을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC속성그리드파일속성::CMFCPropertyGridFile속성](#cmfcpropertygridfileproperty)|`CMFCPropertyGridFileProperty` 개체를 생성합니다.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|`CMFCPropertyGridFileProperty::OnClickButton`|[(CMFCPropertyGrid속성 재정의::클릭 단추.)](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|

### <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a>CMFC속성그리드파일속성::CMFCPropertyGridFile속성

`CMFCPropertyGridFileProperty` 개체를 생성합니다.

```
CMFCPropertyGridFileProperty(
    const CString& strName,
    BOOL bOpenFileDialog,
    const CString& strFileName,
    LPCTSTR lpszDefExt=NULL,
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,
    LPCTSTR lpszFilter=NULL,
    LPCTSTR lpszDescr=NULL,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
【인】 속성 이름입니다.

*bOpenFile 디아로그*<br/>
【인】 파일 **열기** 대화 상자를 열려면 TRUE; FALSE를 사용하여 **파일 저장** 대화 상자를 엽니다.

*strFileName*<br/>
【인】 초기 파일 이름입니다.

*lpsz데프엑스트*<br/>
【인】 하나 이상의 파일 이름 확장자의 문자열입니다. 기본값은 NULL입니다.

*dwFlags*<br/>
【인】 대화 상자 플래그입니다. 기본값은 OFN_HIDEREADONLY와 OFN_OVERWRITEPROMPT의 비트 조합(OR)입니다.

*lpsz필터*<br/>
【인】 하나 이상의 파일 필터 문자열입니다. 기본값은 NULL입니다.

*lpszDescr*<br/>
【인】 속성 항목 설명입니다. 기본값은 NULL입니다.

*dwData*<br/>
【인】 속성 항목과 연결된 응용 프로그램 별 데이터입니다. 예를 들어 32비트 정수 또는 다른 데이터에 대한 포인터입니다. 기본값은 0입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

사용 가능한 플래그의 전체 목록은 [OPENFILENAME 구조를](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 `CMFCPropertyGridFileProperty` 클래스의 생성자를 사용하여 개체를 만드는 방법을 보여 줍니다. 이 예제는 [Visual Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC프로퍼티그리드트럴 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFC프로퍼티그리드프로퍼티 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)
