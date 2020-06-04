---
title: marshal_context 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 110fe4abf7eb90b05e7feef563efa4882bed0fc6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332006"
---
# <a name="marshal_context-class"></a>marshal_context 클래스

이 클래스는 네이티브 환경과 관리되는 환경 간에 데이터를 변환합니다.

## <a name="syntax"></a>구문

```cpp
class marshal_context
```

## <a name="remarks"></a>설명

컨텍스트가 `marshal_context` 필요한 데이터 변환에 클래스를 사용합니다. 컨텍스트가 필요한 변환과 포함해야 하는 마샬링 파일에 대한 자세한 내용은 [C++ 마샬링 의 마샬링 개요를](../dotnet/overview-of-marshaling-in-cpp.md)참조하십시오. 컨텍스트를 사용할 때 마샬링의 결과는 `marshal_context` 개체가 소멸될 때까지만 유효합니다. 결과를 보존하려면 데이터를 복사해야 합니다.

수많은 `marshal_context` 데이터 변환에 대해동일한 것을 사용할 수 있습니다. 이러한 방식으로 컨텍스트를 다시 사용하면 이전 마샬링 호출의 결과에 영향을 주지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|관리되는 `marshal_context` 데이터 형식과 네이티브 데이터 형식 간의 데이터 변환에 사용할 개체를 생성합니다.|
|[marshal_context:~marshal_context](#tilde-marshal-context)|`marshal_context` 개체를 제거합니다.|

### <a name="public-methods"></a>public 메서드

|속성|Description|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|특정 데이터 개체에 대한 마샬링을 수행하여 관리되는 데이터 형식과 네이티브 데이터 형식 간에 변환합니다.|

## <a name="requirements"></a>요구 사항

**헤더 파일:** \<msclr\marshal.h \<>, msclr\marshal_windows.h>, \<msclr\marshal_cppstd.h>, 또는 \<msclr\marshal_atl.h>

**네임 스페이스 :** msclr :::interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context:marshal_context

관리되는 `marshal_context` 데이터 형식과 네이티브 데이터 형식 간의 데이터 변환에 사용할 개체를 생성합니다.

```cpp
marshal_context();
```

### <a name="remarks"></a>설명

일부 데이터 변환에는 마샬링 컨텍스트가 필요합니다. 컨텍스트가 필요한 번역및 응용 프로그램에 포함해야 하는 마샬링 파일에 대한 자세한 내용은 [C++에서 마샬링 개요를](../dotnet/overview-of-marshaling-in-cpp.md)참조하십시오.

### <a name="example"></a>예제

[marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md)에 대한 예제를 참조하십시오.

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context:~marshal_context

`marshal_context` 개체를 제거합니다.

```cpp
~marshal_context();
```

### <a name="remarks"></a>설명

일부 데이터 변환에는 마샬링 컨텍스트가 필요합니다. 컨텍스트가 필요한 번역과 응용 프로그램에 포함해야 하는 마샬링 파일에 대한 자세한 내용은 [C++에서 마샬링 개요를](../dotnet/overview-of-marshaling-in-cpp.md) 참조하십시오.

개체를 `marshal_context` 삭제하면 해당 컨텍스트에서 변환된 데이터가 무효화됩니다. `marshal_context` 개체가 소멸된 후 데이터를 보존하려면 데이터를 유지될 변수에 수동으로 복사해야 합니다.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context:marshal_as

특정 데이터 개체에 대한 마샬링을 수행하여 관리되는 데이터 형식과 네이티브 데이터 형식 간에 변환합니다.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>매개 변수

*input*<br/>
【인】 변수에 마샬링할 값입니다. `To_Type`

### <a name="return-value"></a>반환 값

변환된 값인 형식의 `To_Type` `input`변수입니다.

### <a name="remarks"></a>설명

이 함수는 특정 데이터 개체에 대한 마샬링을 수행합니다. [C++ 마샬링 개요에서](../dotnet/overview-of-marshaling-in-cpp.md)표에 표시된 변환에만 이 함수를 사용합니다.

지원되지 `marshal_as` 않는 데이터 형식 쌍을 마샬링하려고 하면 컴파일 시 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 오류가 발생합니다. 자세한 내용은 이 오류와 함께 제공된 메시지를 읽어보십시오. 더 `C4996` 이상 사용되지 이상인 함수 이상에 대해 오류를 생성할 수 있습니다. 이 오류를 생성하는 두 가지 조건은 지원되지 않는 데이터 형식 쌍을 `marshal_as` 마샬링하고 컨텍스트가 필요한 변환에 사용하려고 합니다.

마샬링 라이브러리는 여러 헤더 파일로 구성됩니다. 모든 변환에는 하나의 파일만 필요하지만 다른 변환을 위해 필요한 경우 추가 파일을 포함할 수 있습니다. 테이블은 `Marshaling Overview in C++` 각 변환에 포함해야 하는 마샬링 파일을 나타냅니다.

### <a name="example"></a>예제

이 예제는 a에서 `System::String` 변수 형식으로 `const char *` 마샬링하기 위한 컨텍스트를 만듭니다. 변환된 데이터는 컨텍스트를 삭제하는 줄 이후에 유효하지 않습니다.

```cpp
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```
