---
title: CMFC이미지에디터디아로그 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 23c2a919428689fe107b82041bd87b758ede2bc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367473"
---
# <a name="cmfcimageeditordialog-class"></a>CMFC이미지에디터디아로그 클래스

클래스는 `CMFCImageEditorDialog` 이미지 편집기 대화 상자를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC이미지편집기::CMFC이미지에디터디아로그](#cmfcimageeditordialog)|`CMFCImageEditorDialog` 개체를 생성합니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCImageEditorDialog` 다음을 포함하는 대화 상자를 제공합니다.

- 이미지의 개별 픽셀을 수정하는 데 사용하는 그림 영역입니다.

- 그리기 도구를 사용하여 그림 영역의 픽셀을 수정합니다.

- 그리기 도구에서 사용되는 색상을 지정하는 색상 팔레트입니다.

- 편집 효과를 표시하는 미리 보기 영역입니다.

다음 그림에서는 이미지 편집기 대화 상자를 보여 주며, 이미지 편집기 대화 상자가 있습니다.

![CMFCImageEditorDialog 대화 상자](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog 대화 상자")

객체를 `CMFCImageEditorDialog` 사용하는 한 가지 방법은 `CBitmap` 편집할 이미지를 전달하는 것입니다. 이미지 편집 영역의 크기가 제한되어 있고 영역에 맞게 논리적 픽셀 크기가 조정되므로 큰 이미지를 만들지 마십시오. 메서드를 `DoModal` 호출하여 모달 대화 상자를 시작합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximageeditordialog.h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFC이미지편집기::CMFC이미지에디터디아로그

`CMFCImageEditorDialog` 개체를 생성합니다.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
이미지에 대한 포인터입니다.

*pParent*<br/>
현재 이미지 편집기 대화 상자의 상위 창에 대한 포인터입니다.

*엔비트픽셀*<br/>
단일 픽셀의 색상을 나타내는 데 사용되는 비트 수이며, 이를 색상 깊이라고도 합니다.  *nBitsPixel* 매개 변수가 -1이면 색상 깊이는 *pBitmap* 매개 변수에 의해 지정된 이미지에서 파생됩니다. 기본값은 -1입니다.

### <a name="return-value"></a>Return Value

이미지를 수정하려면 이미지 포인터를 `CMFCImageEditorDialog` 생성자로 전달합니다. 그런 다음 `DoModal` 메서드를 호출하여 모달 대화 상자를 엽니다. 메서드가 `DoModal` 반환되면 비트맵에 새 이미지가 포함됩니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 `CMFCImageEditorDialog` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)
