---
title: out (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: b99e520a11c2e8110d2e63fa85ddb1dd444e56e6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837101"
---
# <a name="out-c"></a>out(C++)

호출된 프로시저에서 호출하는 프로시저로 반환된(서버에서 클라이언트로 반환된) 포인터 매개 변수를 식별합니다.

## <a name="syntax"></a>구문

```cpp
[out]
```

## <a name="remarks"></a>설명

**out** C++ 특성에는 [out](/windows/win32/Midl/out-idl) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

[out](bindable.md) 의 샘플 사용에 대해서는 **bindable**에 대한 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

| 특성 컨텍스트 | 값 |
|-|-|
|**적용 대상**|인터페이스 매개 변수|
|**불가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)
