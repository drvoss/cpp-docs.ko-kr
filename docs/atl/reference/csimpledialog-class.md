---
title: CSimpleDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 345372d71ad96a74bb0ae6dd7e89bdf0724cd822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330829"
---
# <a name="csimpledialog-class"></a>CSimpleDialog 클래스

이 클래스는 기본 모달 대화 상자를 구현합니다.

## <a name="syntax"></a>구문

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>매개 변수

*t_wDlgTemplateID*

대화 상자 템플릿 리소스의 리소스 ID입니다.

*t_bCenter*<br/>
대화 상자 개체가 소유자 창의 가운데에 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|모달 대화 상자를 만듭니다.|

## <a name="remarks"></a>설명

기본 기능이 있는 모달 대화 상자를 구현합니다. `CSimpleDialog`에서는 Windows 공통 컨트롤에 대해서만 지원을 제공합니다. 모달 대화 상자를 만들고 표시하려면 대화 상자에 대한 기존 리소스 템플릿의 이름을 제공하면서 이 클래스의 인스턴스를 만듭니다. 사용자가 미리 정의된 값(예: IDOK 또는 IDCANCEL)으로 컨트롤을 클릭하면 대화 상자 개체가 닫힙니다.

`CSimpleDialog`만 모달 대화 상자를 만들 수 있습니다. `CSimpleDialog`는 기본 메시지 맵을 사용하여 적절한 처리기로 메시지를 전달하는 대화 상자 프로시저를 제공합니다.

자세한 내용은 [대화 상자 구현을](../../atl/implementing-a-dialog-box.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a>CSimpleDialog::DoModal

모달 대화 상자를 호출하고 완료되면 대화 상자 결과를 반환합니다.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
대화 상자의 상위에 대한 핸들입니다. 값이 제공되지 않으면 부모가 현재 활성 창으로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 반환 값은 대화 상자를 해제한 컨트롤의 리소스 ID입니다.

함수가 실패하면 반환 값은 -1입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

이 메서드는 대화 상자가 활성화되어 있는 동안 사용자와의 모든 상호 작용을 처리합니다. 이것이 대화 상자 모달을 만드는 것입니다. 즉, 대화 상자가 닫혀야 사용자가 다른 창과 상호 작용할 수 없습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
