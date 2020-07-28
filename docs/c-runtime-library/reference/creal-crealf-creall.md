---
title: creal, crealf, creall
ms.date: 03/30/2018
api_name:
- creal
- crealf
- creall
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
ms.openlocfilehash: 14d7bc25e514a217a6ab1160d41895ce2473b409
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87189352"
---
# <a name="creal-crealf-creall"></a>creal, crealf, creall

복소수의 실수부를 검색합니다.

## <a name="syntax"></a>구문

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
```

```cpp
float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>매개 변수

*-*<br/>
복소수입니다.

## <a name="return-value"></a>Return Value

*Z*의 실제 부분입니다.

## <a name="remarks"></a>설명

C + +에서는 오버 로드를 허용 하므로 **_Fcomplex** 또는 **_Lcomplex** 값을 사용 하 고 또는 값을 반환 하는 **creal** 의 오버 로드를 호출할 수 있습니다 **`float`** **`long double`** . C 프로그램에서 **creal** 은 항상 **_Dcomplex** 값을 사용 하 고 값을 반환 **`double`** 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**creal**, **crealf**, **creal**|\<complex.h>|\<ccomplex>|

**_Fcomplex**, **_Dcomplex**및 **_Lcomplex** 형식은 각각 Microsoft에서 구현 되지 않은 네이티브 C99 유형 **float _Complex**, **double _Complex**및 **long double _Complex**에 해당 합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
