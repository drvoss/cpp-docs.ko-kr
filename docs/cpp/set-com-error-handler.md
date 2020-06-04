---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: debad733f351c710ada342e29fa95a4d1ff03b7d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749801"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

COM 오류 처리에 사용되는 기본 함수를 대체합니다. **_set_com_error_handler** Microsoft에 만전을 기하고 있습니다.

## <a name="syntax"></a>구문

```cpp
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>매개 변수

*pHandler*<br/>
대체 함수에 대한 포인터입니다.

*Hr*<br/>
HRESULT 정보.

*페르인포*<br/>
`IErrorInfo` 개체입니다.

## <a name="remarks"></a>설명

기본적으로 [_com_raise_error](../cpp/com-raise-error.md) 모든 COM 오류를 처리합니다. **_set_com_error_handler** 사용하여 사용자 고유의 오류 처리 함수를 호출하여 이 동작을 변경할 수 있습니다.

대체 함수에는 `_com_raise_error`의 시그니처에 해당하는 시그니처가 있어야 합니다.

## <a name="example"></a>예제

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>요구 사항

**헤더:** \<comdef.h>

**Lib:** **/Zc:wchar_t** 컴파일러 옵션이 지정되면(기본값) comsuppw.lib 또는 comsuppwd.lib를 사용합니다. **/Zc:wchar_t 컴파일러** 옵션을 지정하면 comsupp.lib를 사용합니다. IDE에서 이 옵션을 설정하는 방법을 포함하여 자세한 내용은 [/Zc:wchar_t(wchar_t 네이티브 유형)을](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)참조하십시오.

## <a name="see-also"></a>참조

[컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)
