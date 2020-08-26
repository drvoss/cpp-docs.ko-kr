---
title: FactoryCacheFlags 열거형
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 3381b2bcfcbf298270b547199ae614291855a2f7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843276"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 열거형

팩터리 개체를 캐시하는지 여부를 결정합니다.

## <a name="syntax"></a>구문

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>설명

기본적으로 팩터리 캐싱 정책은 [Module](module-class.md) 개체를 만들 때 [ModuleType](moduletype-enumeration.md) 템플릿 매개 변수로 지정 됩니다. 이 정책을 재정의 하려면 팩터리 개체를 만들 때 **FactoryCacheFlags** 값을 지정 합니다.

| 정책 | 설명 |
|-|-|
|`FactoryCacheDefault`|`Module` 개체의 캐싱 정책이 사용됩니다.|
|`FactoryCacheEnabled`|`ModuleType` 개체를 만드는 데 사용된 `Module` 템플릿 매개 변수에 관계없이 팩터리 캐싱을 사용합니다.|
|`FactoryCacheDisabled`|`ModuleType` 개체를 만드는 데 사용된 `Module` 템플릿 매개 변수에 관계없이 팩터리 캐싱을 사용하지 않습니다.|

## <a name="requirements"></a>요구 사항

**헤더:** .h를 구현 합니다.

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft:: WRL 네임 스페이스](microsoft-wrl-namespace.md)
