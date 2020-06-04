---
title: AsyncStatusInternal 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 0eadd1e3a287feecd36b00b231b42c31218352c1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214151"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 열거형

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>주의

비동기 작업의 상태에 대 한 내부 열거와 `Windows::Foundation::AsyncStatus` 열거형 사이의 매핑을 지정 합니다.

## <a name="members"></a>멤버

`_Created`<br/>
`::Windows::Foundation::AsyncStatus::Created`와 같습니다.

`_Started`<br/>
`::Windows::Foundation::AsyncStatus::Started`와 같습니다.

`_Completed`<br/>
`::Windows::Foundation::AsyncStatus::Completed`와 같습니다.

`_Cancelled`<br/>
`::Windows::Foundation::AsyncStatus::Cancelled`와 같습니다.

`_Error`<br/>
`::Windows::Foundation::AsyncStatus::Error`와 같습니다.

## <a name="requirements"></a>요구 사항

**헤더:** async. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
