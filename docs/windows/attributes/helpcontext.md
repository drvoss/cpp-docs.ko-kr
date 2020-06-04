---
title: helpcontext (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 292db21e8092284a92b09ef3f889bb0475d0d886
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167006"
---
# <a name="helpcontext"></a>helpcontext

사용자가 **도움말** 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>매개 변수

*id*<br/>
도움말 항목의 컨텍스트 ID입니다. 컨텍스트 Id에 대 한 자세한 내용은 [HTML 도움말: 프로그램에 대 한 상황](../../mfc/html-help-context-sensitive-help-for-your-programs.md) 에 맞는 도움말을 참조 하세요.

## <a name="remarks"></a>설명

**Helpcontext** C++ 특성은 [helpcontext](/windows/win32/Midl/helpcontext) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Helpcontext**를 사용 하는 방법에 대 한 예제는 [defaultvalue](defaultvalue.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**, **typedef**, **클래스**, 메서드, 속성|
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
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
