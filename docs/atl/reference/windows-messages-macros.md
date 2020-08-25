---
title: Windows 메시지 매크로
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: b4cd3c2eea24449eb17050b147d9c59560d8358f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834442"
---
# <a name="windows-messages-macros"></a>Windows 메시지 매크로

이 매크로는 창 메시지를 전달 합니다.

|Name|설명|
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|창에서 받은 메시지를 처리 하기 위해 다른 창으로 전달 하는 데 사용 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a> WM_FORWARDMSG

이 매크로는 창에서 받은 메시지를 처리 하기 위해 다른 창으로 전달 합니다.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>반환 값

메시지가 처리 되 면 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

WM_FORWARDMSG를 사용 하 여 창에서 받은 메시지를 처리 하기 위해 다른 창으로 전달 합니다. LPARAM 및 WPARAM 매개 변수는 다음과 같이 사용 됩니다.

|매개 변수|사용량|
|---------------|-----------|
|WPARAM|사용자가 정의한 데이터|
|LPARAM|`MSG`메시지에 대 한 정보를 포함 하는 구조체에 대 한 포인터입니다.|

### <a name="example"></a>예제

다음 예제에서는 `m_hWndOther` 이 메시지를 수신 하는 다른 창을 나타냅니다.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
