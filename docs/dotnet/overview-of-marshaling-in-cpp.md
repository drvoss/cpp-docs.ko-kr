---
title: C++ 마샬링 개요
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 0c7bf18fa823c6301a79c3f989efa73c9e8f628a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372005"
---
# <a name="overview-of-marshaling-in-ccli"></a>C++/CLI에서 마샬링 개요

혼합 모드에서는 네이티브 형식과 관리되는 형식 간에 데이터를 마샬링해야 하는 경우가 있습니다. *마샬링 라이브러리를* 사용하면 간단한 방법으로 데이터를 마샬링하고 변환할 수 있습니다.  마샬링 라이브러리는 함수 집합과 공통 `marshal_context` 형식에 대한 마샬링을 수행하는 클래스로 구성됩니다. 라이브러리는 Visual Studio 에디션에 대한 **포함/msclr** 디렉터리에서 이러한 헤더에 정의되어 있습니다.

|헤더|Description|
|---------------|-----------------|
|마샬h|`marshal_context`클래스 및 컨텍스트 없는 마샬링 기능|
|marshal_atl.h| ATL 형식 마샬링 기능|
|marshal_cppstd.h|표준 C++ 형식 마샬링 기능|
|marshal_windows.h|Windows 유형 마샬링 기능|

**msclr** 폴더의 기본 경로는 어떤 버전과 빌드 번호에 따라 다음과 같습니다.

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

[marshal_context 클래스의](../dotnet/marshal-context-class.md)유무에 관계없이 마샬링 라이브러리를 사용할 수 있습니다. 일부 변환에는 컨텍스트가 필요합니다. 다른 변환은 [marshal_as](../dotnet/marshal-as.md) 함수를 사용하여 구현할 수 있습니다. 다음 표에는 지원되는 현재 변환, 컨텍스트가 필요한지 여부 및 포함해야 하는 마샬링 파일이 나열되어 있습니다.

|에서 유형|입력하려면|마샬링 메서드|파일 포함|
|---------------|-------------|--------------------|------------------|
|시스템 ::문자열^|const char\*|marshal_context|마샬h|
|const char\*|시스템 ::문자열^|marshal_as|마샬h|
|Char\*|시스템 ::문자열^|marshal_as|마샬h|
|시스템 ::문자열^|wchar_t\*|marshal_context|마샬h|
|wchar_t\*|시스템 ::문자열^|marshal_as|마샬h|
|Wchar_t\*|시스템 ::문자열^|marshal_as|마샬h|
|시스템::인트Ptr|HANDLE|marshal_as|marshal_windows.h|
|HANDLE|시스템::인트Ptr|marshal_as|marshal_windows.h|
|시스템 ::문자열^|BSTR|marshal_context|marshal_windows.h|
|BSTR|시스템 ::문자열^|marshal_as|마샬h|
|시스템 ::문자열^|bstr_t|marshal_as|marshal_windows.h|
|bstr_t|시스템 ::문자열^|marshal_as|marshal_windows.h|
|시스템 ::문자열^|std::문자열|marshal_as|marshal_cppstd.h|
|std::문자열|시스템 ::문자열^|marshal_as|marshal_cppstd.h|
|시스템 ::문자열^|std::wstring|marshal_as|marshal_cppstd.h|
|std::wstring|시스템 ::문자열^|marshal_as|marshal_cppstd.h|
|시스템 ::문자열^|CStringT\<문자>|marshal_as|marshal_atl.h|
|CStringT\<문자>|시스템 ::문자열^|marshal_as|marshal_atl.h|
|시스템 ::문자열^|><wchar_t<CStringT|marshal_as|marshal_atl.h|
|><wchar_t<CStringT|시스템 ::문자열^|marshal_as|marshal_atl.h|
|시스템 ::문자열^|CComBSTR|marshal_as|marshal_atl.h|
|CComBSTR|시스템 ::문자열^|marshal_as|marshal_atl.h|

마샬링에는 관리되는 데이터 형식에서 네이티브 데이터 형식으로 마샬링하는 경우에만 컨텍스트가 필요하며 변환하는 네이티브 형식에는 자동 정리를 위한 소멸자가 없습니다. 마샬링 컨텍스트는 소멸자에서 할당된 네이티브 데이터 형식을 파괴합니다. 따라서 컨텍스트가 필요한 변환은 컨텍스트가 삭제될 때까지만 유효합니다. 마샬링된 값을 저장하려면 값을 사용자 고유의 변수에 복사해야 합니다.

> [!NOTE]
> 문자열에 s를 포함한 `NULL`경우 문자열을 마샬링하는 결과가 보장되지 않습니다. 포함된 `NULL`s는 문자열이 잘리거나 보존될 수 있습니다.

이 예제에서는 포함 헤더 선언에 msclr 디렉터리를 포함 하는 방법을 보여 주어 있습니다.

`#include "msclr\marshal_cppstd.h"`

마샬링 라이브러리는 확장할 수 있으므로 고유한 마샬링 형식을 추가할 수 있습니다. 마샬링 라이브러리 확장에 대한 자세한 내용은 [마샬링 라이브러리 확장 방법을](../dotnet/how-to-extend-the-marshaling-library.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[C++ 지원 라이브러리](../dotnet/cpp-support-library.md)<br/>
[방법: 마샬링 라이브러리 확장](../dotnet/how-to-extend-the-marshaling-library.md)
