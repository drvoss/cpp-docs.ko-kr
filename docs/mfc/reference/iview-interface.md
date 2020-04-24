---
title: IView 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: dfe77699a51ad2670c703d02e13e9062e76debcd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751287"
---
# <a name="iview-interface"></a>IView 인터페이스

[CWinFormsView가](../../mfc/reference/cwinformsview-class.md) 관리되는 컨트롤에 보기 알림을 보내는 데 사용하는 여러 메서드를 구현합니다.

## <a name="syntax"></a>구문

```
interface class IView
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IView::온인스로뷰](#onactivateview)|뷰가 활성화되거나 비활성화될 때 MFC에서 호출합니다.|
|[IView::초기 업데이트](#oninitialupdate)|뷰가 문서에 처음 연결되지만 뷰가 처음 표시되기 전에 프레임워크에서 호출됩니다.|
|[아이뷰::온업데이트](#onupdate)|뷰의 문서가 수정된 후 MFC에서 호출합니다. 이 기능을 사용하면 뷰가 수정 사항을 반영하도록 디스플레이를 업데이트할 수 있습니다.|

## <a name="remarks"></a>설명

`IView`공통 보기 알림을 `CWinFormsView` 호스팅된 관리 되는 컨트롤에 전달 하는 데 사용 하는 여러 메서드를 구현 합니다. 다음은 [초기 업데이트](#oninitialupdate), [OnUpdate](#onupdate) 및 [OnActivateView](#onactivateview)입니다.

`IView`[CView와](../../mfc/reference/cview-class.md)유사하지만 관리되는 보기 및 컨트롤에서만 사용됩니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="requirements"></a>요구 사항

헤더: afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="iviewonactivateview"></a><a name="onactivateview"></a>IView::온인스로뷰

뷰가 활성화되거나 비활성화될 때 MFC에서 호출합니다.

```cpp
void OnActivateView(bool activate);
```

## <a name="parameters"></a>매개 변수

*활성화*<br/>
뷰가 활성화 또는 비활성화되고 있는지 여부를 나타냅니다.

## <a name="iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::초기 업데이트

뷰가 문서에 처음 연결되지만 뷰가 처음 표시되기 전에 프레임워크에서 호출됩니다.

```cpp
void OnInitialUpdate();
```

## <a name="iviewonupdate"></a><a name="onupdate"></a>아이뷰::온업데이트

뷰의 문서가 수정된 후 MFC에서 호출합니다.

```cpp
void OnUpdate();
```

## <a name="remarks"></a>설명

이 기능을 사용하면 뷰에서 수정 사항을 반영하도록 디스플레이를 업데이트할 수 있습니다.

## <a name="see-also"></a>참조

[CWinForms뷰 클래스](../../mfc/reference/cwinformsview-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)
