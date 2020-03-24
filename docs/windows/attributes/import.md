---
title: import (C++ COM 특성)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: f2a0aa9a68c081e83a7a5278aa37a7fddac85416
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166838"
---
# <a name="import"></a>수입

주 IDL에서 참조 하려는 정의가 포함 된 다른 .idl, odl 또는 헤더 파일을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>매개 변수

*idl_file*<br/>
현재 프로젝트의 형식 라이브러리로 가져올 .idl 파일의 이름입니다.

## <a name="remarks"></a>설명

**Import** C++ 특성을 통해 `#import` 문이 생성 된 .idl 파일의 `import "docobj.idl"` 문 아래에 배치 됩니다. **가져오기** 특성은 [가져오기](/windows/win32/Midl/import) MIDL 특성과 동일한 기능을 포함 합니다.

**가져오기** 특성은 지정 된 파일을 프로젝트에 의해 생성 되는 .idl 파일에만 배치 합니다. **가져오기** 특성을 사용 하면 프로젝트의 소스 코드에서 지정 된 파일의 구문을 호출할 수 없습니다.  프로젝트의 소스 코드에서 지정 된 파일의 구문을 호출 하려면 [#import](../../preprocessor/hash-import-directive-cpp.md) 및 `embedded_idl` 특성을 사용 하거나 .h 파일이 있는 경우 *idl_file*의 .h 파일을 포함 하면 됩니다.

## <a name="example"></a>예제

코드는 다음과 같습니다.

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

는 생성 된 .idl 파일에서 다음 코드를 생성 합니다.

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
