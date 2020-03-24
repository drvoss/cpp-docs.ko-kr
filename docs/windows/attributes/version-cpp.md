---
title: version (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: e5fcf80ef753a869b8798d6ab9c8e9f8ecff16fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165992"
---
# <a name="version-c"></a>version(C++)

클래스의 여러 버전에서 특정 버전을 식별 합니다.

## <a name="syntax"></a>구문

```cpp
[ version("version") ]
```

### <a name="parameters"></a>매개 변수

*version*<br/>
`coclass`의 버전 번호입니다. 지정 하지 않으면 1.0가 .idl 파일에 배치 됩니다.

## <a name="remarks"></a>설명

**Version** C++ 특성은 [버전](/windows/win32/Midl/version) MIDL 특성과 동일한 기능을 포함 하며 생성 된 .idl 파일로 전달 됩니다.

## <a name="example"></a>예제

**버전**의 샘플 사용에 대 한 [바인딩](bindable.md) 가능한 예제를 참조 하십시오.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**|
|**반복 가능**|예|
|**필수 특성**|**coclass**|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)<br/>
[클래스 특성](class-attributes.md)
