---
title: call_in_appdomain 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: da0f2bc1a503226e41198871e6dc48ace7a86854
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545374"
---
# <a name="call_in_appdomain-function"></a>call_in_appdomain 함수

지정 된 응용 프로그램 도메인에서 함수를 실행 합니다.

## <a name="syntax"></a>구문

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>매개 변수

*appdomainId*<br/>
함수를 호출할 appdomain입니다.

*voidFunc*<br/>
N 개의 매개 변수를 사용 하는 `void` 함수에 대 한 포인터입니다 (0 < = N < = 15).

*nonvoidFunc*<br/>
N 개의 매개 변수를 사용 하는 비`void` 함수에 대 한 포인터입니다 (0 < = N < = 15).

*arg1 ... argN*<br/>
다른 appdomain의 `voidFunc` 또는 `nonvoidFunc`에 전달 되는 매개 변수는 0 ~ 15입니다.

## <a name="return-value"></a>반환 값

지정 된 응용 프로그램 도메인에서 `voidFunc` 또는 `nonvoidFunc`를 실행 한 결과입니다.

## <a name="remarks"></a>주의

`call_in_appdomain`에 전달 된 함수의 인수는 CLR 형식이 아니어야 합니다.

## <a name="example"></a>예제

```cpp
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>출력

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\appdomain.h >

Msclr **네임 스페이스**
