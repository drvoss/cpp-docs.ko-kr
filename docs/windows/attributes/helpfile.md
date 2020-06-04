---
title: helpfile (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 1f928fa281c99630ad52ce1fde184c44e9387263
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166980"
---
# <a name="helpfile"></a>helpfile

형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.

## <a name="syntax"></a>구문

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
도움말 항목을 포함 하는 파일의 이름입니다.

## <a name="remarks"></a>설명

**Helpfile** C++ 특성은 [helpfile](/windows/win32/Midl/helpfile) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Helpfile**를 사용 하는 방법에 대 한 예제는 [module](module-cpp.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**, **typedef**, **클래스**, 메서드, **속성**|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)
