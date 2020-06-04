---
title: ActivatableClass 매크로
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 7bc3d789d6c0d304aa170d59dff23a97a67061d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214281"
---
# <a name="activatableclass-macros"></a>ActivatableClass 매크로

지정 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다.

## <a name="syntax"></a>구문

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>매개 변수

*className*<br/>
만들 클래스의 이름입니다.

*팩토리에서*<br/>
지정 된 클래스의 인스턴스를 만드는 팩터리입니다.

*serverName*<br/>
모듈에서 팩터리의 하위 집합을 지정 하는 이름입니다.

## <a name="remarks"></a>주의

`#undef` 지시어를 사용 하 여 `__WRL_WINRT_STRICT__` 매크로 정의가 제거 되지 않도록 하는 경우를 제외 하 고 이러한 매크로를 클래식 COM과 함께 사용 하지 마세요.

## <a name="requirements"></a>요구 사항

**헤더:** module .h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Module 클래스](module-class.md)
