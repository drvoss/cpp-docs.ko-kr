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
ms.openlocfilehash: 146a0f7a7cc1402f7c28e6bf09fead1914c7c6be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208529"
---
# <a name="marshal_context-class"></a>marshal_context 클래스

이 클래스는 네이티브 및 관리 되는 환경 간에 데이터를 변환 합니다.

## <a name="syntax"></a>구문

```cpp
class marshal_context
```

## <a name="remarks"></a>주의

컨텍스트가 필요한 데이터 변환에 `marshal_context` 클래스를 사용 합니다. 컨텍스트를 필요로 하는 변환과 마샬링 파일을 포함 해야 하는 변환에 대 한 자세한 내용은 [의 C++마샬링 개요 ](../dotnet/overview-of-marshaling-in-cpp.md)를 참조 하세요. 컨텍스트를 사용 하는 경우의 마샬링 결과는 `marshal_context` 개체가 제거 될 때 까지만 유효 합니다. 결과를 유지 하려면 데이터를 복사 해야 합니다.

다양 한 데이터 변환에 동일한 `marshal_context`를 사용할 수 있습니다. 이러한 방식으로 컨텍스트를 다시 사용 해도 이전 마샬링 호출의 결과에는 영향을 주지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|관리 되는 형식과 네이티브 데이터 형식 간의 데이터 변환에 사용할 `marshal_context` 개체를 생성 합니다.|
|[marshal_context::~marshal_context](#tilde-marshal-context)|`marshal_context` 개체를 제거합니다.|

### <a name="public-methods"></a>public 메서드

|이름|설명|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|특정 데이터 개체에 대 한 마샬링을 수행 하 여 관리 되는 형식과 네이티브 데이터 형식 간에 변환 합니다.|

## <a name="requirements"></a>요구 사항

**헤더 파일:** \<msclr\marshal.h >, \<msclr \ marshal_windows >, \<msclr \ marshal_cppstd > 또는 \<msclr \ marshal_atl. h >

**네임 스페이스:** msclr:: interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context:: marshal_context

관리 되는 형식과 네이티브 데이터 형식 간의 데이터 변환에 사용할 `marshal_context` 개체를 생성 합니다.

```cpp
marshal_context();
```

### <a name="remarks"></a>주의

일부 데이터 변환에는 marshal 컨텍스트가 필요 합니다. 컨텍스트를 필요로 하는 변환 및 응용 프로그램에 포함 해야 하는 마샬링 파일에 대 한 자세한 내용은 [의 C++마샬링 개요 ](../dotnet/overview-of-marshaling-in-cpp.md)를 참조 하세요.

### <a name="example"></a>예제

[Marshal_context:: marshal_as](../dotnet/marshal-context-marshal-as.md)의 예제를 참조 하세요.

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context:: ~ marshal_context

`marshal_context` 개체를 제거합니다.

```cpp
~marshal_context();
```

### <a name="remarks"></a>주의

일부 데이터 변환에는 marshal 컨텍스트가 필요 합니다. 컨텍스트를 필요로 하는 변환 및 응용 프로그램에 포함 해야 하는 마샬링 파일에 대 한 자세한 내용은 [ C++ 의 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md) 를 참조 하세요.

`marshal_context` 개체를 삭제 하면 해당 컨텍스트에 의해 변환 된 데이터가 무효화 됩니다. `marshal_context` 개체가 제거 된 후 데이터를 유지 하려면 데이터를 유지할 변수에 수동으로 복사 해야 합니다.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context:: marshal_as

특정 데이터 개체에 대 한 마샬링을 수행 하 여 관리 되는 형식과 네이티브 데이터 형식 간에 변환 합니다.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>매개 변수

*input*<br/>
진행 `To_Type` 변수로 마샬링할 값입니다.

### <a name="return-value"></a>반환 값

`input`의 변환 된 값인 `To_Type` 형식의 변수입니다.

### <a name="remarks"></a>주의

이 함수는 특정 데이터 개체에 대해 마샬링을 수행 합니다. [ C++에서의 마샬링 개요 ](../dotnet/overview-of-marshaling-in-cpp.md)에서 테이블이 나타내는 변환에만이 함수를 사용 합니다.

지원 되지 않는 데이터 형식 쌍을 마샬링하 려 `marshal_as` 고 하면 컴파일 시간에 C4996에서 오류 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 생성 됩니다. 자세한 내용은이 오류와 함께 제공 된 메시지를 참조 하세요. `C4996` 오류는 더 이상 사용 되지 않는 함수에 대해 생성할 수 있습니다. 이 오류를 생성 하는 두 가지 조건은 지원 되지 않는 데이터 형식 쌍을 마샬링하 려 고 컨텍스트가 필요한 변환에 `marshal_as`를 사용 하려고 시도 하는 것입니다.

마샬링 라이브러리는 여러 헤더 파일로 구성 되어 있습니다. 모든 변환에는 하나의 파일만 필요 하지만 다른 변환에 필요한 경우 추가 파일을 포함할 수 있습니다. `Marshaling Overview in C++` 표에는 각 변환에 포함 되어야 하는 마샬링 파일이 표시 됩니다.

### <a name="example"></a>예제

이 예제에서는 `System::String`에서 `const char *` 변수 형식으로 마샬링하는 컨텍스트를 만듭니다. 변환 된 데이터는 컨텍스트를 삭제 하는 줄 뒤에서 유효 하지 않습니다.

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
