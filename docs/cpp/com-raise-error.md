---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: f5efbe98a489a380c4e9be5a0e40603be2a409c0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745088"
---
# <a name="_com_raise_error"></a>_com_raise_error

**마이크로소프트 특정**

오류에 대한 응답으로 [_com_error](../cpp/com-error-class.md) throw합니다.

## <a name="syntax"></a>구문

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>매개 변수

*Hr*<br/>
HRESULT 정보.

*페르인포*<br/>
`IErrorInfo` 개체입니다.

## <a name="remarks"></a>설명

_com_raise_error> 정의된 동일한 이름과 프로토타입의 사용자 작성 버전으로 대체할 수 있습니다. **_com_raise_error** \< 이는 `#import`를 사용하고 C++ 예외 처리는 사용하지 않으려는 경우 실행할 수 있습니다. 이 경우 사용자 버전의 **_com_raise_error** 메시지 상자를 `longjmp` 수행하거나 표시하고 중지하도록 결정할 수 있습니다. 컴파일러 COM 지원 코드가 반환을 예상하고 있지 않기 때문에 사용자 버전은 반환할 수 없습니다.

[_set_com_error_handler](../cpp/set-com-error-handler.md) 사용하여 기본 오류 처리 함수를 바꿀 수도 있습니다.

기본적으로 **_com_raise_error** 다음과 같이 정의됩니다.

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comdef.h>

**Lib:** wchar_t **네이티브 형식** 컴파일러 옵션이 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용합니다. **wchar_t 네이티브 형식이** 꺼져 있는 경우 comsupp.lib를 사용합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조하세요.

## <a name="see-also"></a>참조

[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
