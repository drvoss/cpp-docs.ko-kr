---
title: "Simpleactivationfactory:: Activateinstance 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance 메서드

지정된 된 인터페이스의 인스턴스를 만듭니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>매개 변수

*ppvObject*  
이 작업이 완료 될 때, 지정 된 개체의 인스턴스로에 대 한 포인터는 `Base` 클래스 템플릿 매개 변수입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

경우 &#95; &#95; WRL_STRICT &#95; #95 정의 assert 오류가 면 내보내집니다 클래스 템플릿 매개 변수에서 지정 된 기본 클래스에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md), WinRt 또는 WinRtClassicComMix 구성 되지 않았습니다 또는 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)