---
title: CMFC리본응용프로그램버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: b28d075c5fcc4313e1a62ae731b3fad8ef4d8a12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749935"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFC리본응용프로그램버튼 클래스

애플리케이션 창의 왼쪽 위 모서리에 있는 특수 단추를 구현합니다. 클릭하면 단추는 **열기** , **저장**및 **종료**와 같은 일반적인 **파일**명령이 포함된 메뉴를 엽니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC 리본 응용 프로그램 단추::CMFC 리본 응용 프로그램 단추](#cmfcribbonapplicationbutton)|`CMFCRibbonApplicationButton` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonApplicationButton::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC 리본 응용 프로그램 단추::세트 이미지](#setimage)|리본 응용 프로그램 단추에 이미지를 할당합니다.|

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonApplicationButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 응용 프로그램 단추에 이미지를 할당하는 방법과 해당 도구 설명을 설정하는 방법을 보여 주며, 이 단추를 설정하는 방법을 보여 주며, 이 단추를 설정하는 방법을 보여 주시면 됩니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonBar.h

## <a name="cmfcribbonapplicationbuttoncmfcribbonapplicationbutton"></a><a name="cmfcribbonapplicationbutton"></a>CMFC 리본 응용 프로그램 단추::CMFC 리본 응용 프로그램 단추

[CMFC리본응용프로그램단추](../../mfc/reference/cmfcribbonapplicationbutton-class.md) 개체를 생성하고 초기화합니다.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>매개 변수

*uiBmpResID*<br/>
응용 프로그램 단추에 표시할 이미지의 리소스 ID입니다.

*hBmp*<br/>
응용 프로그램 단추에 표시할 비트맵에 대한 핸들입니다.

### <a name="remarks"></a>설명

리본 응용 프로그램 단추는 응용 프로그램 창의 왼쪽 위 모서리에 있는 특수 단추입니다. 사용자가 이 단추를 클릭하면 응용 프로그램은 일반적으로 **열기,** **저장**및 **종료**와 같은 일반적인 **파일** 명령이 포함된 메뉴를 엽니다.

## <a name="cmfcribbonapplicationbuttonsetimage"></a><a name="setimage"></a>CMFC 리본 응용 프로그램 단추::세트 이미지

응용 프로그램 단추에 이미지를 할당합니다.

```cpp
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>매개 변수

*uiBmpResID*<br/>
【인】 응용 프로그램 단추에 표시할 이미지의 리소스 ID입니다.

*hBmp*<br/>
【인】 응용 프로그램 단추에 표시할 비트맵에 대한 핸들입니다.

### <a name="remarks"></a>설명

단추를 만든 후 리본 응용 프로그램 단추에 새 이미지를 할당하려면 이 메서드를 사용합니다. 응용 프로그램 단추는 응용 프로그램 창의 왼쪽 위 모서리에 있습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
