---
title: idl_quote (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: 4b05da6d237d71e0cc645ad0f626f75ecd85c827
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168031"
---
# <a name="idl_quote"></a>idl_quote

현재 버전의 Visual C++ 에서 지원 되지 않는 idl 구문을 사용 하 여 생성 된 .idl 파일로 전달 하도록 할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>매개 변수

*text*<br/>
Microsoft C++ 컴파일러에서 컴파일러 오류를 반환 하지 않고 생성 된 .idl 파일로 전달 하려는 특성 이름입니다.

## <a name="remarks"></a>주의

**Idl_quote** C++ 특성을 닫는 대괄호 뒤에 세미콜론을 사용 하 여 독립 실행형 특성으로 사용 하는 경우에는 *텍스트가* 병합 된 .idl 파일에 있는 그대로 배치 됩니다. 기호에 **idl_quote** 를 사용 하는 경우 *텍스트* 는 해당 기호에 대 한 특성 블록 내에 배치 됩니다.

## <a name="example"></a>예제

다음 코드에서는 지원 되는 **에서**를 사용 하 여 지원 되지 않는 특성을 지정 하 고 정의 되지 않은 .idl 구문을 정의 하 고 사용 하는 방법을 보여 줍니다.

```cpp
// cpp_attr_ref_idl_quote.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];

[export]
struct MYFLOT {
   int i;
};

[export]
struct MYDUB {
   int i;
};

[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];

typedef struct _S1_TYPE {
   long l1;

union {
   MYFLOT f1; MYDUB d2; } U1_TYPE;
} S1_TYPE;

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]
__interface IStatic{
   HRESULT Func1([idl_quote("in")] int i);
   HRESULT func( S1_TYPE* myStruct );
};
```

이 코드는 `MYFLOT` 및 `MYDUB`를 발생 시키고 *텍스트* 항목을 생성 된 .idl 파일에 배치 합니다. *Name* 매개 변수는 생성 된 .idl 파일에서 *이름을* 참조 하는 항목 앞에 *텍스트가* 배치 되도록 합니다. *종속성* 매개 변수는 종속성 목록 정의가 생성 된 .idl 파일의 *텍스트* 앞에 배치 되도록 합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)
