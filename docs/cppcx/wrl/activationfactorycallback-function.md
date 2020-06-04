---
title: ActivationFactoryCallback 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 0be4bebcc561cdf1df3f2502c8cc1927bdc65564
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214216"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback 함수

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>매개 변수

*activationId*<br/>
런타임 클래스 이름을 지정 하는 문자열에 대 한 핸들입니다.

*ppFactory*<br/>
이 작업이 완료 되 면 매개 변수 *activationId*에 해당 하는 활성화 팩터리가 활성화 됩니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 오류 Hresult는 CLASS_E_CLASSNOTAVAILABLE E_INVALIDARG 됩니다.

## <a name="remarks"></a>주의

지정 된 활성화 ID에 대 한 활성화 팩터리를 가져옵니다.

Windows 런타임는이 콜백 함수를 호출 하 여 해당 런타임 클래스 이름으로 지정 된 개체를 요청 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** module .h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
