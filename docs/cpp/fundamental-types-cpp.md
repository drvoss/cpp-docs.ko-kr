---
title: 기본 제공 형식 (C++)
ms.date: 12/11/2019
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- char8_t_cpp
- char16_t_cpp
- char32_t_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: 14d96453785a55f625b5467458f9cf79e6739acf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188616"
---
# <a name="built-in-types-c"></a>기본 제공 형식 (C++)

기본 제공 형식 ( *기본 형식*이 라고도 함)은 C++ 언어 표준에 의해 지정 되며 컴파일러에 기본 제공 됩니다. 기본 제공 형식은 헤더 파일에 정의 되어 있지 않습니다. 기본 제공 형식은 정수 계열, 부동 소수점 및 void의 세 가지 범주로 구분 됩니다. 정수 계열 형식은 정수를 처리할 수 있습니다. 부동 소수점 형식은 소수 부분이 있을 수 있는 값을 지정할 수 있습니다.

[void](void-cpp.md) 형식은 빈 값 집합을 설명합니다. **Void** 형식의 변수를 지정할 수 없습니다 .이 변수는 주로 값을 반환 하지 않는 함수를 선언 하거나 형식화 되지 않은 형식이 나 임의로 형식화 된 데이터에 대 한 제네릭 포인터를 선언 하는 데 사용 됩니다. 모든 식은 명시적으로 변환 되거나 **void**형식으로 캐스팅 될 수 있습니다. 그러나 이러한 식은 사용이 다음으로 제한됩니다.

- 식 문. (자세한 내용은 [식](expressions-cpp.md)을 참조 하세요.)

- 쉼표 연산자의 왼쪽 피연산자. (자세한 내용은 [쉼표 연산자](comma-operator.md)를 참조 하세요.)

- 조건 연산자의 두 번째 또는 세 번째 피연산자(`? :`)입니다. (자세한 내용은 [조건 연산자를 사용 하는 식](conditional-operator-q.md)을 참조 하세요.)

다음 표에서는 서로 관련 된 형식 크기에 대 한 제한 사항을 설명 합니다. 이러한 제한은 표준에 C++ 의해 적용 되며 Microsoft 구현과는 독립적입니다. 특정 기본 제공 형식의 절대 크기가 표준에 지정 되어 있지 않습니다.

### <a name="built-in-type-size-restrictions"></a>기본 제공 형식 크기 제한

|범주|형식|목차|
|--------------|----------|--------------|
|정수 계열|**char**|**Char** 형식은 일반적으로 기본 실행 문자 집합의 멤버를 포함 하는 정수 계열 형식입니다. 기본적으로 MICROSOFT C++에서는 ASCII입니다.<br /><br /> 컴파일러 C++ 는 **char**, **signed char**및 **unsigned char** 형식의 변수를 서로 다른 형식으로 처리 합니다. /J 컴파일 옵션을 사용 하지 않는 한 **char** 형식의 변수는 기본적으로 **signed char** 형식으로 지정 된 **int** 로 승격 됩니다. 이 경우 **부호 없는 char** 형식으로 처리 되 고 부호 확장 없이 **int** 로 승격 됩니다.|
||**bool**|**Bool** 형식은 **true** 또는 **false**의 두 값 중 하나를 가질 수 있는 정수 계열 형식입니다. 크기는 지정되지 않습니다.|
||**short**|**Short int** (또는 간단히 **short**) 형식은 **char**형식의 크기 보다 크거나 같고 **int**형식의 크기 보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> **Short** 형식의 개체는 **signed short** 또는 **unsigned short**로 선언할 수 있습니다. **Signed short** 는 **short**의 동의어입니다.|
||**int**|**Int** 형식은 **short int**형식의 크기 보다 크거나 같고 **long**형식의 크기 보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> **Int** 형식의 개체는 **signed int** 또는 **unsigned int**로 선언할 수 있습니다. **부호 있는 int** 는 **int**의 동의어입니다.|
||**__int8**, **__int16**, **__int32**, **__int64**|크기가 지정된 정수 `__int n`입니다. 여기서 `n` 은 정수 변수의 크기(비트)입니다. **__int8**, **__int16**, **__int32** 및 **__int64** 은 Microsoft 전용 키워드입니다. 모든 아키텍처에서 모든 형식을 사용할 수 있는 것은 아닙니다. **__int128** 지원 되지 않습니다.|
||**long**|**Long** 형식 (또는 **long int**)은 **int**형식의 크기 보다 크거나 같은 정수 계열 형식입니다. Windows의 **long** 은 **int**와 동일한 크기입니다.<br /><br /> **Long** 형식의 개체는 **signed long** 또는 **unsigned long**으로 선언할 수 있습니다. **Signed long** 은 **long**의 동의어입니다.|
||**long long**|부호 없는 **long**보다 큽니다.<br /><br /> **Long long** 형식의 개체는 **signed long long** 또는 **unsigned long**long으로 선언할 수 있습니다. **부호 있는 long** long은 **long long**과 동의어입니다.|
||**wchar_t**, **__wchar_t**|**Wchar_t** 형식의 변수는 와이드 문자 또는 멀티 바이트 문자 형식을 지정 합니다. 기본적으로 **wchar_t** 는 네이티브 형식 이지만 [/zc: wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 를 사용 하 여 **서명 되지 않은 short**에 대 한 typedef **wchar_t** 만들 수 있습니다. **__Wchar_t** 형식은 네이티브 **wchar_t** 형식의 Microsoft 전용 동의어입니다.<br /><br /> 문자 또는 문자열 리터럴 앞에 L 접두사를 사용하여 와이드 문자 형식을 지정합니다.|
|부동 소수점|**float**|**Float** 형식은 가장 작은 부동 소수점 형식입니다.|
||**double**|**Double** 형식은 **float**형식 보다 크거나 같지만 **long double**형식의 크기 보다 짧거나 같은 부동 소수점 형식입니다.<br /><br /> Microsoft 전용: **long double** 및 **double** 의 표현은 동일 합니다. 그러나 **long double** 과 **double** 은 별개 형식입니다.|
||**long double**|**Long double** 형식은 **double**형식 보다 크거나 같은 부동 소수점 형식입니다.|

**Microsoft 전용**

다음 표에서는 Microsoft C++의 기본 제공 형식에 필요한 저장소 크기를 나열 합니다. 특히 64 비트 운영 체제 에서도 **long** 은 4 바이트입니다.

### <a name="sizes-of-built-in-types"></a>기본 제공 형식의 크기

|형식|크기|
|----------|----------|
|**bool**, **char**, **unsigned char**, **signed char**, **__int8**|1바이트|
|**__int16**, **short**, **unsigned short**, **wchar_t**, **__wchar_t**|2bytes|
|**float**, **__int32**, **int**, **unsigned int**, **long**, **unsigned long**|4바이트|
|**double**, **__int64**, **long double**, **long long**|8바이트|

**Microsoft 전용 종료**

각 형식의 값 범위에 대한 요약은 [데이터 형식 범위](data-type-ranges.md) 를 참조하세요.

형식 변환에 대한 자세한 내용은 [표준 변환](standard-conversions.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[데이터 형식 범위](data-type-ranges.md)
