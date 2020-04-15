---
title: tchar.h의 제네릭 텍스트 매핑
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: bf872df2e6fb49e64a973e8799eef98dec1cb472
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361351"
---
# <a name="generic-text-mappings-in-tcharh"></a>tchar.h의 제네릭 텍스트 매핑

Microsoft 런타임 라이브러리는 국제적인 사용을 위해 코드 전송을 단순화하기 위해 많은 데이터 형식, 루틴 및 기타 개체에 대해 Microsoft 전용 일반 텍스트 매핑을 제공합니다. tchar.h에 정의된 이러한 매핑을 사용하여 `#define` 문을 사용하여 정의하는 매니페스트 상수에 따라 단일 바이트, 다수 바이트 또는 유니코드 문자 집합에 대해 컴파일할 수 있는 제네릭 코드를 작성할 수 있습니다. 제네릭 텍스트 매핑은 ANSI와 호환되지 않는 Microsoft 확장입니다.

tchar.h를 사용하면 동일한 소스에서 단일 바이트, 다중 바이트 문자 집합(MBCS) 및 유니코드 응용 프로그램을 빌드할 수 있습니다. tchar.h는 올바른 전처리기 정의를 `_tcs`사용하여 적절하 게 `str`에 `_mbs` `wcs` 매핑 하는 매크로(접두사가 있는)를 정의합니다. MBCS를 빌드하려면 기호를 `_MBCS`정의합니다. 유니코드를 빌드하려면 기호를 `_UNICODE`정의합니다. 단일 바이트 응용 프로그램을 빌드하려면 둘 중 하나(기본값)를 정의합니다. 기본적으로 `_UNICODE` MFC 응용 프로그램에 대해 정의됩니다.

데이터 `_TCHAR` 형식은 tchar.h에서 조건부로 정의됩니다. 빌드에 `_TCHAR` `_UNICODE` 대해 기호가 정의된 경우 **wchar_t.** 그렇지 않으면 단일 바이트 및 MBCS 빌드의 경우 **char로**정의됩니다. **(wchar_t,** 기본 유니코드 와이드 문자 데이터 형식은 8비트 서명된 **char에**대한 16비트 대응입니다.) 국제 응용 프로그램의 경우 `_tcs` 바이트가 아닌 `_TCHAR` 단위로 작동하는 함수 제품군을 사용합니다. `_tcsncpy` 예를 `n` `_TCHARs`들어, 복사는 `n` 바이트가 아닙니다.

일부 단일 바이트 문자 집합 (SBCS) 문자열 처리 함수는 (서명 된) `char*` 매개 변수를 `_MBCS` 사용 하기 때문에 형식 불일치 컴파일러 경고 정의 될 때 발생 합니다. 이 경고를 방지하는 방법에는 세 가지가 있습니다.

1. tchar.h에서 형식이 안전한 인라인 함수 썽크를 사용합니다. 기본 동작입니다.

1. 명령줄을 정의하여 `_MB_MAP_DIRECT` tchar.h에서 직접 매크로를 사용합니다. 이렇게 하는 경우 형식을 수동으로 일치시켜야 합니다. 이 방법은 가장 빠른 방법이지만 형식이 안전하지는 않습니다.

1. tchar.h에서 형식이 안전한 정적 연결 라이브러리 함수 썽크를 사용합니다. 이렇게 하려면 명령줄에서 `_NO_INLINING` 상수를 정의합니다. 이는 속도가 가장 느린 방법이지만 형식은 가장 안전합니다.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>일반 텍스트 매핑용 전처리기 지시문

|# 정의|컴파일 버전|예제|
|---------------|----------------------|-------------|
|`_UNICODE`|유니코드(와이드 문자)|`_tcsrev`는 `_wcsrev`에 매핑됩니다.|
|`_MBCS`|멀티바이트 문자|`_tcsrev`는 `_mbsrev`에 매핑됩니다.|
|없음(기본값에 `_UNICODE` 정의되지 않음) `_MBCS`|SBCS(ASCII)|`_tcsrev`는 `strrev`에 매핑됩니다.|

예를 들어 tchar.h에 정의된 제네릭 `_tcsrev`텍스트 함수는 `_mbsrev` 프로그램에서 `_MBCS` 정의된 경우 또는 `_wcsrev` 정의된 `_UNICODE`경우에 매핑됩니다. 그렇지 않으면 `_tcsrev`는 `strrev`로 매핑됩니다. 다른 데이터 형식 매핑은 프로그래밍 편의를 위해 tchar.h로 제공되지만 `_TCHAR` 가장 유용합니다.

### <a name="generic-text-data-type-mappings"></a>일반 텍스트 데이터 형식 매핑

|일반 텍스트<br /> 데이터 유형 이름|_UNICODE &<br /> _MBCS 정의되지 않음|_MBCS<br /> 정의됨|_UNICODE<br /> 정의됨|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**Int**|**부호 없는 정수**|`wint_t`|
|`_TSCHAR`|**signed char**|**signed char**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` 또는 `_TEXT`|효과 없음(전처리기에 의해 제거됨)|효과 없음(전처리기에 의해 제거됨)|`L`(다음 문자 또는 문자열을 유니코드 대응으로 변환)|

루틴, 변수 및 기타 개체의 일반 텍스트 매핑 목록은 런타임 라이브러리 참조의 [일반 텍스트 매핑을](../c-runtime-library/generic-text-mappings.md) 참조하십시오.

> [!NOTE]
> 포함된 null `str` 바이트를 포함할 가능성이 있는 유니코드 문자열과 함수 패밀리를 사용하지 마십시오. 마찬가지로 MBCS(또는 `wcs` SBCS) 문자열이 있는 함수 패밀리를 사용하지 마십시오.

다음 코드 조각은 MBCS, 유니코드 및 SBCS 모델에 매핑하는 데 `_TCHAR` 및 `_tcsrev`를 사용하는 방법을 보여 줍니다.

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

정의된 `_MBCS` 경우 전처리기는 이 조각을 이 코드에 매핑합니다.

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

정의된 `_UNICODE` 경우 전처리기는 이 조각을 이 코드에 매핑합니다.

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

정의되지 `_MBCS` `_UNICODE` 않은 경우 전처리기는 다음과 같이 조각을 단일 바이트 ASCII 코드에 매핑합니다.

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

따라서 세 가지 문자 집합 중 하나에 특정한 루틴으로 실행할 단일 소스 코드 파일을 작성, 유지 관리 및 컴파일할 수 있습니다.

## <a name="see-also"></a>참고 항목

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[_MBCS 코드와 TCHAR.H 데이터 형식 사용](../text/using-tchar-h-data-types-with-mbcs-code.md)
