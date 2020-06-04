---
title: in (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: f25f15148621d7092858577825dbdd6caa1ae0be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166798"
---
# <a name="in-c"></a>in(C++)

호출 하는 프로시저에서 호출 되는 프로시저로 매개 변수가 전달 됨을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[in]
```

## <a name="remarks"></a>설명

**In** C++ 특성에는 [in](/windows/win32/Midl/in) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**에서**를 사용 하는 방법에 대 한 예제는 [바인딩](bindable.md) 가능을 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|**retval**|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)<br/>
[out](out-cpp.md)
