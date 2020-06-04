---
title: Windows 메시지 매크로
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: a5a6d45c64d6123128ae362c1ef5643392439f41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329404"
---
# <a name="windows-messages-macros"></a>Windows 메시지 매크로

이 매크로는 창 메시지를 전달합니다.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|창을 통해 받은 메시지를 처리를 위해 다른 창으로 전달하는 데 사용합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG

이 매크로는 창에서 받은 메시지를 처리를 위해 다른 창으로 전달합니다.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Return Value

메시지가 처리된 경우 0이 아님을 0입니다.

### <a name="remarks"></a>설명

WM_FORWARDMSG 사용하여 창에서 받은 메시지를 처리를 위해 다른 창으로 전달합니다. LPARAM 및 WPARAM 매개 변수는 다음과 같이 사용됩니다.

|매개 변수|사용|
|---------------|-----------|
|Wparam|사용자가 정의한 데이터|
|Lparam|메시지에 대한 `MSG` 정보가 포함된 구조에 대한 포인터|

### <a name="example"></a>예제

다음 예제에서는 `m_hWndOther` 이 메시지를 받는 다른 창을 나타냅니다.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
