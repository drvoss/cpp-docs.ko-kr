---
title: IID_PPV_ARGS_Helper 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 68dbd0b5b2e9d4fc04821a7e7e0193840b55e312
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077135"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper 함수

지정 된 인수의 형식이 `IUnknown` 인터페이스에서 파생 되는지 확인 합니다.

> [!IMPORTANT]
> 이 템플릿 특수화는 WRL 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다. 대신 [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) 를 사용 해야 합니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인수 *pp*의 유형입니다.

*pp*<br/>
이중 간접 포인터입니다.

## <a name="return-value"></a>반환 값

인수 *pp* 를 **void**포인터로 캐스팅 합니다.

## <a name="remarks"></a>주의

템플릿 매개 변수 *T* 가 `IUnknown`에서 파생 되지 않으면 컴파일 시간 오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h
