---
title: ARM64 내장 함수
description: 비주얼 스튜디오에서 Microsoft C++ 컴파일러에서 지원하는 ARM64 내장 함수의 참조 목록입니다.
f1_keywords:
- __break
- __addx18byte
- __addx18word
- __addx18dword
- __addx18qword
- __cas8
- __cas16
- __cas32
- __cas64
- __casa8
- __casa16
- __casa32
- __casa64
- __casl8
- __casl16
- __casl32
- __casl64
- __casal8
- __casal16
- __casal32
- __casal64
- __crc32b
- __crc32h
- __crc32w
- __crc32d
- __crc32cb
- __crc32ch
- __crc32cw
- __crc32cd
- __getReg
- __getRegFp
- __getCallerReg
- __getCallerRegFp
- __hlt
- __incx18byte
- __incx18word
- __incx18dword
- __incx18qword
- __ldar8
- __ldar16
- __ldar32
- __ldar64
- __ldapr8
- __ldapr16
- __ldapr32
- __ldapr64
- __prefetch2
- __readx18byte
- __readx18word
- __readx18dword
- __readx18qword
- __setReg
- __setRegFp
- __setCallerReg
- __setCallerRegFp
- __stlr8
- __stlr16
- __stlr32
- __stlr64
- __swp8
- __swp16
- __swp32
- __swp64
- __swpa8
- __swpa16
- __swpa32
- __swpa64
- __swpl8
- __swpl16
- __swpl32
- __swpl64
- __swpal8
- __swpal16
- __swpal32
- __swpal64
- __sys
- __svc
- __writex18byte
- __writex18word
- __writex18dword
- __writex18qword
helpviewer_keywords:
- __break ARM64 intrinsic
- __addx18byte ARM64 intrinsic
- __addx18word ARM64 intrinsic
- __addx18dword ARM64 intrinsic
- __addx18qword ARM64 intrinsic
- __cas8 ARM64 intrinsic
- __cas16 ARM64 intrinsic
- __cas32 ARM64 intrinsic
- __cas64 ARM64 intrinsic
- __casa8 ARM64 intrinsic
- __casa16 ARM64 intrinsic
- __casa32 ARM64 intrinsic
- __casa64 ARM64 intrinsic
- __casl8 ARM64 intrinsic
- __casl16 ARM64 intrinsic
- __casl32 ARM64 intrinsic
- __casl64 ARM64 intrinsic
- __casal8 ARM64 intrinsic
- __casal16 ARM64 intrinsic
- __casal32 ARM64 intrinsic
- __casal64 ARM64 intrinsic
- __crc32b ARM64 intrinsic
- __crc32h ARM64 intrinsic
- __crc32w ARM64 intrinsic
- __crc32d ARM64 intrinsic
- __crc32cb ARM64 intrinsic
- __crc32ch ARM64 intrinsic
- __crc32cw ARM64 intrinsic
- __crc32cd ARM64 intrinsic
- __getReg ARM64 intrinsic
- __getRegFp ARM64 intrinsic
- __getCallerReg ARM64 intrinsic
- __getCallerRegFp ARM64 intrinsic
- __hlt ARM64 intrinsic
- __incx18byte ARM64 intrinsic
- __incx18word ARM64 intrinsic
- __incx18dword ARM64 intrinsic
- __incx18qword ARM64 intrinsic
- __ldar8 ARM64 intrinsic
- __ldar16 ARM64 intrinsic
- __ldar32 ARM64 intrinsic
- __ldar64 ARM64 intrinsic
- __ldapr8 ARM64 intrinsic
- __ldapr16 ARM64 intrinsic
- __ldapr32 ARM64 intrinsic
- __ldapr64 ARM64 intrinsic
- __prefetch2 ARM64 intrinsic
- __readx18byte ARM64 intrinsic
- __readx18word ARM64 intrinsic
- __readx18dword ARM64 intrinsic
- __readx18qword ARM64 intrinsic
- __setReg ARM64 intrinsic
- __setRegFp ARM64 intrinsic
- __setCallerReg ARM64 intrinsic
- __setCallerRegFp ARM64 intrinsic
- __stlr8 ARM64 intrinsic
- __stlr16 ARM64 intrinsic
- __stlr32 ARM64 intrinsic
- __stlr64 ARM64 intrinsic
- __swp8 ARM64 intrinsic
- __swp16 ARM64 intrinsic
- __swp32 ARM64 intrinsic
- __swp64 ARM64 intrinsic
- __swpa8 ARM64 intrinsic
- __swpa16 ARM64 intrinsic
- __swpa32 ARM64 intrinsic
- __swpa64 ARM64 intrinsic
- __swpl8 ARM64 intrinsic
- __swpl16 ARM64 intrinsic
- __swpl32 ARM64 intrinsic
- __swpl64 ARM64 intrinsic
- __swpal8 ARM64 intrinsic
- __swpal16 ARM64 intrinsic
- __swpal32 ARM64 intrinsic
- __swpal64 ARM64 intrinsic
- __sys ARM64 intrinsic
- __svc ARM64 intrinsic
- __writex18byte ARM64 intrinsic
- __writex18word ARM64 intrinsic
- __writex18dword ARM64 intrinsic
- __writex18qword ARM64 intrinsic
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 27325df55d128337a45e76bbf5387508a523f57c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754528"
---
# <a name="arm64-intrinsics"></a>ARM64 내장 함수

MICROSOFT C++ 컴파일러(MSVC)는 ARM64 아키텍처에서 다음과 같은 기본 정보를 사용할 수 있습니다. ARM에 대한 자세한 내용은 [ARM 개발자 설명서](https://developer.arm.com/docs) 웹 사이트의 아키텍처 및 소프트웨어 개발 도구 섹션을 참조하십시오.

## <a name="neon"></a><a name="top"></a>네온

ARM64에 대한 네온 벡터 명령 세트 확장은 단일 명령 다중 데이터(SIMD) 기능을 제공합니다. x86 및 x64 아키텍처 프로세서에 공통적인 MMX 및 SSE 벡터 명령어 집합의 명령어와 유사합니다.

헤더 파일 *arm64_neon.h에*제공된 대로 NEON 내장 함수가 지원됩니다. 네온 내장 에 대한 MSVC 지원은 ARM 정보 센터 웹 사이트의 [ARM 네온 본질 참조에](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf) 문서화 된 ARM64 컴파일러의 것과 유사합니다.

## <a name="arm64-specific-intrinsics-listing"></a><a name="A"></a>ARM64 관련 내장 목록

|함수 이름|명령|함수 프로토타입|
|-------------------|-----------------|------------------------|
|__break|BRK (주)(영국)|보이드 __break(int)|
|__addx18byte||void __addx18byte(서명되지 않은 긴, 서명되지 않은 문자)|
|__addx18word||void __addx18word(서명되지 않은 긴, 서명되지 않은 짧은)|
|__addx18dword||void __addx18dword(서명되지 않은 긴, 서명되지 않은 긴)|
|__addx18qword||void __addx18qword(서명되지 않은 긴 __int64)|
|__cas8|CASB|서명되지 않은 __int8 __cas8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Comp, 서명되지 않은 __int8 _Value)|
|__cas16|현금|서명되지 않은 __int16 __cas16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Comp, 서명되지 않은 __int16 _Value)|
|__cas32|CAS|서명되지 않은 __int32 __cas32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Comp, 서명되지 않은 __int32 _Value)|
|__cas64|CAS|서명되지 않은 __int64 __cas64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Comp, 서명되지 않은 __int64 _Value)|
|__casa8|카사브 (동안)|서명되지 않은 __int8 __casa8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Comp, 서명되지 않은 __int8 _Value)|
|__casa16|카사 (것)이 많은|서명되지 않은 __int16 __casa16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Comp, 서명되지 않은 __int16 _Value)|
|__casa32|카사|서명되지 않은 __int32 __casa32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Comp, 서명되지 않은 __int32 _Value)|
|__casa64|카사|서명되지 않은 __int64 __casa64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Comp, 서명되지 않은 __int64 _Value)|
|__casl8|CASLB|서명되지 않은 __int8 __casl8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Comp, 서명되지 않은 __int8 _Value)|
|__casl16|카일 (것)|서명되지 않은 __int16 __casl16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Comp, 서명되지 않은 __int16 _Value)|
|__casl32|CASL|서명되지 않은 __int32 __casl32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Comp, 서명되지 않은 __int32 _Value)|
|__casl64|CASL|서명되지 않은 __int64 __casl64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Comp, 서명되지 않은 __int64 _Value)|
|__casal8|카살레이|서명되지 않은 __int8 __casal8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Comp, 서명되지 않은 __int8 _Value)|
|__casal16|카살 (것)에|서명되지 않은 __int16 __casal16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Comp, 서명되지 않은 __int16 _Value)|
|__casal32|Casal|서명되지 않은 __int32 __casal32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Comp, 서명되지 않은 __int32 _Value)|
|__casal64|Casal|서명되지 않은 __int64 __casal64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Comp, 서명되지 않은 __int64 _Value)|
|__crc32b|CRC32B|서명되지 않은 __int32 __crc32b(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32h|CRC32H|서명되지 않은 __int32 __crc32h(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32w|CRC32W|서명되지 않은 __int32 __crc32w(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32d|CRC32X|서명되지 않은 __int32 __crc32d(서명되지 않은 __int32, 서명되지 않은 __int64)|
|__crc32cb|CRC32CB|서명되지 않은 __int32 __crc32cb(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32ch|CRC32CH|서명되지 않은 __int32 __crc32ch(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32cw|CRC32CW|서명되지 않은 __int32 __crc32cw(서명되지 않은 __int32, 서명되지 않은 __int32)|
|__crc32cd|CRC32CX|서명되지 않은 __int32 __crc32cd(서명되지 않은 __int32, 서명되지 않은 __int64)|
|__dmb|DMB|void __dmb(unsigned int `_Type`)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한 의 종류에 대한 자세한 내용은 [메모리 장벽 제한을](#BarrierRestrictions)참조하십시오.|
|__dsb|DSB|void __dsb(unsigned int _Type)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한 의 종류에 대한 자세한 내용은 [메모리 장벽 제한을](#BarrierRestrictions)참조하십시오.|
|__isb|ISB|void __isb(unsigned int _Type)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한 의 종류에 대한 자세한 내용은 [메모리 장벽 제한을](#BarrierRestrictions)참조하십시오.|
|__getReg||서명되지 않은 __int64 __getReg(int)|
|__getRegFp||더블 __getRegFp(int)|
|__getCallerReg||서명되지 않은 __int64 __getCallerReg(int)|
|__getCallerRegFp||더블 __getCallerRegFp(int)|
|__hvc|HVC|unsigned int __hvc(unsigned int, ...)|
|__hlt|찾 았 어|int __hlt (서명되지 않은 int, ...)|
|__incx18byte||빈 __incx18byte(서명되지 않은 긴)|
|__incx18word||빈 __incx18word(서명되지 않은 긴)|
|__incx18dword||void __incx18dword(서명되지 않은 긴)|
|__incx18qword||보이드 __incx18qword(서명되지 않은 긴)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16(휘발성 \__int16) \*<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_load32||__int32 \__iso_volatile_load32(휘발성 \__int32) \*<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_load64||__int64 \__iso_volatile_load64(휘발성 \__int64) \*<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_load8||__int8 \__iso_volatile_load8(휘발성 \__int8) \*<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_store16||무효 \___iso_volatile_store16(휘발성 \* \__int16, _int16)<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_store32||보이드 \___iso_volatile_store32(휘발성 \* \__int32, _int32)<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_store64||무효 \___iso_volatile_store64(휘발성 \* \__int64, _int64)<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__iso_volatile_store8||무효 \___iso_volatile_store8(휘발성 \* \__int8, _int8)<br /><br /> 자세한 내용은 [__iso_volatile_load/매장 내장 을](#IsoVolatileLoadStore)참조하십시오.|
|__ldar8|LDARB|서명되지 않은 __int8 __ldar8(서명되지 않은 __int8 휘발성* _Target)|
|__ldar16|LDARH|서명되지 않은 __int16 __ldar16(서명되지 않은 __int16 휘발성* _Target)|
|__ldar32|LDAR|서명되지 않은 __int32 __ldar32(서명되지 않은 __int32 휘발성* _Target)|
|__ldar64|LDAR|서명되지 않은 __int64 __ldar64(서명되지 않은 __int64 휘발성* _Target)|
|__ldapr8|LDAPRB|서명되지 않은 __int8 __ldapr8(서명되지 않은 __int8 휘발성* _Target)|
|__ldapr16|LDAPRH|서명되지 않은 __int16 __ldapr16(서명되지 않은 __int16 휘발성* _Target)|
|__ldapr32|LDAPR|서명되지 않은 __int32 __ldapr32(서명되지 않은 __int32 휘발성* _Target)|
|__ldapr64|LDAPR|서명되지 않은 __int64 __ldapr64(서명되지 않은 __int64 휘발성* _Target)|
|__mulh||\__int64 __mulh\_(_int64, \__int64)|
|__prefetch|PRFM|무효 \___cdecl _prefetch(const void) \*<br /><br /> `PRFM` 지정된 주소 또는 그 근처의 `PLDL1KEEP` 메모리에 곧 액세스할 수 있는 시스템에 프리페치 작업과 함께 메모리 힌트를 제공합니다. 일부 시스템은 런타임 성능을 향상시키기 위해 해당 메모리 액세스 패턴을 최적화하도록 선택할 수 있습니다. 그러나 C++ 언어의 관점에서 함수는 눈에 띄는 효과가 없고 아무 작업도 하지 않을 수 있습니다.|
|__prefetch2|PRFM|보이드 \___cdecl _prefetch(const void, \*uint8_t prfop)<br /><br /> `PRFM` 지정된 주소 또는 그 근처의 메모리에 곧 액세스할 수 있는 시스템에 제공된 프리페치 작업과 함께 메모리 힌트를 제공합니다. 일부 시스템은 런타임 성능을 향상시키기 위해 해당 메모리 액세스 패턴을 최적화하도록 선택할 수 있습니다. 그러나 C++ 언어의 관점에서 함수는 눈에 띄는 효과가 없고 아무 작업도 하지 않을 수 있습니다.|
|__readx18byte||서명되지 않은 char __readx18byte(서명되지 않은 긴)|
|__readx18word||서명되지 않은 짧은 __readx18word(서명되지 않은 긴)|
|__readx18dword||서명되지 않은 긴 __readx18dword(서명되지 않은 긴)|
|__readx18qword||서명되지 않은 __int64 __readx18qword(서명되지 않은 긴)|
|__setReg||무효 __setReg(int, 서명되지 않은 __int64)|
|__setRegFp||보이드 __setRegFp(int, 더블)|
|__setCallerReg||무효 __setCallerReg(int, 서명되지 않은 __int64)|
|__setCallerRegFp||보이드 __setCallerRegFp(int, 더블)|
|__sev|SEV|void __sev(void)|
|__static_assert||빈 공간 __static_assert(int, \*const char)|
|__stlr8|STLRB|무효 __stlr8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Value)|
|__stlr16|STLRH|무효 __stlr16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Value)|
|__stlr32|STLR|void __stlr32(__int32 비서명* _Target, __int32 _Value)|
|__stlr64|STLR|무효 __stlr64(__int64 __int64 휘발성* _Target, __int64 _Value)|
|__swp8|SWPB|서명되지 않은 __int8 __swp8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Value)|
|__swp16|SWPH|서명되지 않은 __int16 __swp16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Value)|
|__swp32|Swp|서명되지 않은 __int32 __swp32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Value)|
|__swp64|Swp|서명되지 않은 __int64 __swp64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Value)|
|__swpa8|SWPAB|서명되지 않은 __int8 __swpa8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Value)|
|__swpa16|스WPAH|서명되지 않은 __int16 __swpa16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Value)|
|__swpa32|스WPA|서명되지 않은 __int32 __swpa32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Value)|
|__swpa64|스WPA|서명되지 않은 __int64 __swpa64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Value)|
|__swpl8|SWPLB|서명되지 않은 __int8 __swpl8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Value)|
|__swpl16|SWPLH|서명되지 않은 __int16 __swpl16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Value)|
|__swpl32|SWPL|서명되지 않은 __int32 __swpl32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Value)|
|__swpl64|SWPL|서명되지 않은 __int64 __swpl64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Value)|
|__swpal8|SWPALB|서명되지 않은 __int8 __swpal8(서명되지 않은 __int8 휘발성* _Target, 서명되지 않은 __int8 _Value)|
|__swpal16|SWPALH|서명되지 않은 __int16 __swpal16(서명되지 않은 __int16 휘발성* _Target, 서명되지 않은 __int16 _Value)|
|__swpal32|SWPAL|서명되지 않은 __int32 __swpal32(서명되지 않은 __int32 휘발성* _Target, 서명되지 않은 __int32 _Value)|
|__swpal64|SWPAL|서명되지 않은 __int64 __swpal64(서명되지 않은 __int64 휘발성* _Target, 서명되지 않은 __int64 _Value)|
|__sys|Sys|서명되지 않은 int __sys(int, __int64)|
|__svc|SVC|서명되지 않은 int __svc(서명되지 않은 int, ...)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|__writex18byte||void __writex18byte(서명되지 않은 긴, 서명되지 않은 문자)|
|__writex18word||void __writex18word(서명되지 않은 긴, 서명되지 않은 짧은)|
|__writex18dword||void __writex18dword(서명되지 않은 긴, 서명되지 않은 긴)|
|__writex18qword||void __writex18qword(서명되지 않은 긴, 서명되지 않은 __int64)|
|__umulh||서명되지 \_않은 _int64 \___umulh(서명되지 \_않은 _int64, 서명되지 않은 _int64)|
|_CopyDoubleFromInt64||더블 _CopyDoubleFromInt64\_(_int64)|
|_CopyFloatFromInt32||플로트\__CopyFloatFromInt32 (_int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(unsigned long)|
|_CountLeadingOnes64||서명되지 않은 int \__CountLeadingOnes64(서명되지 않은 _int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||서명되지 않은 int _CountLeadingSigns64(_int64)\_|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(unsigned long)|
|_CountLeadingZeros64||서명되지 않은 int \__CountLeadingZeros64(서명되지 않은 _int64)|
|_ReadStatusReg|MRS|\__int64 _ReadStatusReg(int)|
|_WriteStatusReg|MSR|무효 _WriteStatusReg(int, \__int64)|

[[맨 위로 돌아가기]](#top)

### <a name="memory-barrier-restrictions"></a><a name="BarrierRestrictions"></a>메모리 장벽 제한

내장 `__dmb` 함수(데이터 메모리 장벽), `__dsb` (데이터 동기화 장벽) 및 `__isb` (명령 동기화 장벽)은 미리 정의된 다음 값을 사용하여 공유 도메인 및 작업의 영향을 받는 액세스 의 종류 측면에서 메모리 장벽 제한을 지정합니다.

|제한 값|Description|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|전체 시스템, 읽기 및 쓰기|
|_ARM64_BARRIER_ST|전체 시스템, 쓰기 전용|
|_ARM64_BARRIER_LD|전체 시스템, 읽기 만.|
|_ARM64_BARRIER_ISH|내부 공유 가능, 읽기 및 쓰기|
|_ARM64_BARRIER_ISHST|내부 공유 가능, 쓰기 전용|
|_ARM64_BARRIER_ISHLD|내부 는 자할 수 있으며 읽기만 가능합니다.|
|_ARM64_BARRIER_NSH|공유 불가, 읽기 및 쓰기|
|_ARM64_BARRIER_NSHST|공유 불가, 쓰기 전용|
|_ARM64_BARRIER_NSHLD|비(non)는 읽을 수 있습니다.|
|_ARM64_BARRIER_OSH|외부 공유 가능, 읽기 및 쓰기|
|_ARM64_BARRIER_OSHST|외부 공유 가능, 쓰기 전용|
|_ARM64_BARRIER_OSHLD|외부 는 거리, 읽기 만.|

본질적인 `__isb` 경우 현재 유효한 유일한 제한은 _ARM64_BARRIER_SY. 다른 모든 값은 아키텍처에 의해 예약됩니다.

### <a name="__iso_volatile_loadstore-intrinsics"></a><a name="IsoVolatileLoadStore"></a>__iso_volatile_load/매장 내장

이러한 내장 함수는 컴파일러 최적화의 대상이 되지 않는 로드 및 저장소를 명시적으로 수행합니다.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>매개 변수

*위치*\
읽거나 쓸 메모리 위치의 주소입니다.

*값*\
지정된 메모리 위치에 쓸 값입니다(내장만 저장).

#### <a name="return-value-load-intrinsics-only"></a>반환 값(로드 내장만)

*위치*에 의해 지정된 메모리 위치의 값입니다.

#### <a name="remarks"></a>설명

및 `__iso_volatile_store8/16/32/64` 내장 `__iso_volatile_load8/16/32/64` 함수를 사용하여 컴파일러 최적화의 대상이 되지 않는 메모리 액세스를 명시적으로 수행할 수 있습니다. 컴파일러는 이러한 작업의 상대적 순서를 제거, 합성 또는 변경할 수 없습니다. 그러나 암시적 하드웨어 메모리 장벽을 생성 하지 않습니다. 따라서 하드웨어는 여러 스레드 간의 식별할 수 있는 메모리 액세스를 여전히 다시 정렬할 수 있습니다. 더 정확하게 말하면, 이러한 내장 함수는 **/volatile:iso**에서 컴파일된 다음 식과 동일합니다.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

내장 함수가 휘발성 포인터를 취하여 휘발성 변수를 수용합니다. 그러나 휘발성 포인터를 인수로 사용할 필요 또는 권장 사항은 없습니다. 이러한 작업의 의미 체계는 일반 비휘발성 형식을 사용하는 경우 정확히 동일합니다.

**/volatile:iso** 명령줄 인수에 대한 자세한 내용은 [/volatile(휘발성 키워드 해석)을](../build/reference/volatile-volatile-keyword-interpretation.md)참조하십시오.

## <a name="arm64-support-for-intrinsics-from-other-architectures"></a><a name="I"></a>다른 아키텍처의 내장 함수에 대한 ARM64 지원

다음 표에는 ARM64 플랫폼에서 지원되는 다른 아키텍처의 기본 함수가 나열되어 있습니다. ARM64의 내장 동작이 다른 하드웨어 아키텍처의 동작과 다른 경우 추가 세부 사항에 유의해야 합니다.

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|빈 __code_seg (const char) \*|
|__debugbreak|무효 \___cdecl _debugbreak(무효)|
|__fastfail|__declspec(무수익) \_void _fastfail(서명되지 않은 int)|
|__nop|void __nop(void)|
|__yield|void __yield(void) **주:** ARM64 플랫폼에서 이 함수는 YIELD 명령을 생성합니다. 이 명령은 스레드가 프로그램에 부정적인 영향을 주지 않고 실행(예: 스핀잠금)에서 일시적으로 중단될 수 있는 작업을 수행하고 있음을 나타냅니다. 이를 통해 CPU는 실행 주기 중에 낭비되는 다른 작업을 실행할 수 있습니다.|
|_AddressOfReturnAddress|무효 \* _AddressOfReturnAddress(무효)|
|_BitScanForward|서명되지 않은 char _BitScanForward(서명되지 않은 긴 \* _Index, 서명되지 않은 긴 _Mask)|
|_BitScanForward64|서명되지 않은 char _BitScanForward64(서명되지 않은 긴 \* _Index, 서명되지 않은 __int64 _Mask)|
|_BitScanReverse|서명되지 않은 char _BitScanReverse(서명되지 않은 긴 \* _Index, 서명되지 않은 긴 _Mask)|
|_BitScanReverse64|서명되지 않은 char _BitScanReverse64(서명되지 않은 긴 \* _Index, 서명되지 않은 __int64 _Mask)|
|_bittest|서명되지 않은 char _bittest \*(긴 const, 긴)|
|_bittest64|서명되지 않은 char _bittest64 \*(__int64 const , __int64)|
|_bittestandcomplement|서명되지 않은 char \*_bittestandcomplement(긴 길이)|
|_bittestandcomplement64|서명되지 않은 char \*_bittestandcomplement64 (__int64 , __int64)|
|_bittestandreset|서명되지 않은 char \*_bittestandreset(긴 길이)|
|_bittestandreset64|서명되지 않은 문자 \*_bittestandreset64 (__int64 , __int64)|
|_bittestandset|서명되지 않은 char \*_bittestandset(긴 길이)|
|_bittestandset64|서명되지 않은 char \*_bittestandset64 (__int64 , __int64)|
|_byteswap_uint64|서명되지 \_않은 __int64 _cdecl \__byteswap_uint64(서명되지 않은 _int64)|
|_byteswap_ulong|unsigned long __cdecl _byteswap_ulong(unsigned long)|
|_byteswap_ushort|unsigned short __cdecl _byteswap_ushort(unsigned short)|
|_disable|void __cdecl _disable (void) **참고 :** ARM64 플랫폼에서이 `MSR DAIFCLR,#2`함수는 명령을 생성합니다. 본질적으로 사용할 수 있습니다.|
|_enable|void __cdecl _enable (void) **참고 :** ARM64 플랫폼에서이 `MSR DAIFSET,#2`함수는 명령을 생성합니다. 본질적으로 사용할 수 있습니다.|
|_lrotl|unsigned long __cdecl _lrotl(unsigned long, int)|
|_lrotr|unsigned long __cdecl _lrotr(unsigned long, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|무효 \* _ReturnAddress(무효)|
|_rotl|unsigned int __cdecl _rotl(unsigned int _Value, int _Shift)|
|_rotl16|unsigned short _rotl16(unsigned short _Value, unsigned char _Shift)|
|_rotl64|서명되지 \_않은 __int64 _cdecl \__rotl64(서명되지 않은 _int64 _Value, int _Shift)|
|_rotl8|unsigned char _rotl8(unsigned char _Value, unsigned char _Shift)|
|_rotr|unsigned int __cdecl _rotr(unsigned int _Value, int _Shift)|
|_rotr16|unsigned short _rotr16(unsigned short _Value, unsigned char _Shift)|
|_rotr64|서명되지 \_않은 __int64 _cdecl \__rotr64(서명되지 않은 _int64 _Value, int _Shift)|
|_rotr8|unsigned char _rotr8(unsigned char _Value, unsigned char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[맨 위로 돌아가기]](#top)

## <a name="interlocked-intrinsics"></a>연동된 내장

Interlocked 내장 함수는 원자성 읽기-수정-쓰기 작업을 수행하는데 사용되는 내장 함수 집합입니다. 일부 내장 함수는 모든 플랫폼에 공통적입니다. 그들은 그들 중 많은 수가 있기 때문에 여기에 별도로 나열됩니다. 정의는 대부분 중복되므로 일반적인 용어로 생각하기가 더 쉽습니다. 내장 함수의 이름을 사용해 정확한 동작을 파악할 수 있습니다.

다음 표에서는 비비트테스트 연동 내장 함수의 ARM64 지원을 요약합니다. 테이블의 각 셀은 `_Interlocked`에 행의 가장 왼쪽 셀에 작업 이름 및 열의 맨 위 셀에 형식 이름을 추가하여 파생된 이름을 뜻합니다. 예를 들어 `Xor` 행과 열의 교차점에 `8` 있는 셀은 `_InterlockedXor8` 해당하며 완전히 지원됩니다. 대부분의 지원되는 함수에는 옵션 접미사 `_acq`, `_rel`, 및 `_nf`가 제공됩니다. `_acq` 접미사는 "acquire" 의미를 나타내며 `_rel` 접미사는 "release" 의미를 나타냅니다. `_nf` 또는 "울타리 없음" 접미사는 ARM 및 ARM64에 고유하며 다음 섹션에서 설명합니다.

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|추가|None|None|전체|전체|None|None|
|그리고|전체|전체|전체|전체|None|None|
|CompareExchange|전체|전체|전체|전체|전체|전체|
|감소|None|전체|전체|전체|None|None|
|Exchange|전체|전체|전체|전체|None|전체|
|ExchangeAdd|전체|전체|전체|전체|None|None|
|ID 증가값|None|전체|전체|전체|None|None|
|Or|전체|전체|전체|전체|None|None|
|Xor|전체|전체|전체|전체|None|None|

키:

- **전체**: `_acq`일반, `_rel`, `_nf` 및 양식을 지원합니다.

- **없음**: 지원되지 않음

### <a name="_nf-no-fence-suffix"></a><a name="nf_suffix"></a>_nf(울타리 없음) 접미사

또는 `_nf` "울타리 없음" 접미사는 작업이 다른 세 가지 형태(일반 및 `_acq`일반 및 기타)와 `_rel`달리 모든 종류의 메모리 장벽으로 동작하지 않는다는 것을 나타냅니다. 양식의 `_nf` 한 가지 가능한 용도는 여러 스레드에서 동시에 업데이트되지만 여러 스레드가 실행되는 동안 값이 달리 사용되지 않는 통계 카운터를 유지하는 것입니다.

### <a name="list-of-interlocked-intrinsics"></a>연동된 내장 함수 목록

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|_InterlockedAdd|긴 _InterlockedAdd (긴 _volatile \*, 긴)|
|_InterlockedAdd64|__int64\__InterlockedAdd64(_int64 \* \_휘발성, _int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq\_(_int64 \_휘발성, \*_int64)|
|_InterlockedAdd64_nf|__int64\__InterlockedAdd64_nf(_int64 \* \_휘발성, _int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel\_(_int64 \_휘발성, \*_int64)|
|_InterlockedAdd_acq|긴 _InterlockedAdd_acq (긴 휘발성 \*, 긴)|
|_InterlockedAdd_nf|긴 _InterlockedAdd_nf (긴 휘발성 \*, 긴)|
|_InterlockedAdd_rel|긴 _InterlockedAdd_rel (긴 휘발성 \*, 긴)|
|_InterlockedAnd|긴 _InterlockedAnd (긴 휘발성 \*, 긴)|
|_InterlockedAnd16|짧은 _InterlockedAnd16 (짧은 휘발성, \*짧은)|
|_InterlockedAnd16_acq|짧은 _InterlockedAnd16_acq(짧은 \*휘발성, 짧은)|
|_InterlockedAnd16_nf|짧은 _InterlockedAnd16_nf (짧은 휘발성, \*짧은)|
|_InterlockedAnd16_rel|짧은 _InterlockedAnd16_rel (짧은 휘발성, \*짧은)|
|_InterlockedAnd64|__int64\__InterlockedAnd64(_int64 \* \_휘발성, _int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq\_(_int64 \_휘발성, \*_int64)|
|_InterlockedAnd64_nf|__int64\__InterlockedAnd64_nf(휘발성 \* \__int64, _int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel\_(_int64 \_휘발성, \*_int64)|
|_InterlockedAnd8|char _InterlockedAnd8 (char 휘발성 \*, char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq (char 휘발성 \*, char)|
|_InterlockedAnd8_nf|char _InterlockedAnd8_nf (char 휘발성 \*, char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel (char 휘발성 \*, char)|
|_InterlockedAnd_acq|긴 _InterlockedAnd_acq (긴 휘발성 \*, 긴)|
|_InterlockedAnd_nf|긴 _InterlockedAnd_nf (긴 휘발성 \*, 긴)|
|_InterlockedAnd_rel|긴 _InterlockedAnd_rel (긴 휘발성 \*, 긴)|
|_InterlockedCompareExchange|긴 __cdecl _InterlockedCompareExchange \*(긴 휘발성, 긴, 긴)|
|_InterlockedCompareExchange_acq|긴 _InterlockedCompareExchange_acq (긴 휘발성, \*긴, 긴)|
|_InterlockedCompareExchange_nf|긴 _InterlockedCompareExchange_nf (긴 휘발성 \*, 긴, 긴)|
|_InterlockedCompareExchange_rel|긴 _InterlockedCompareExchange_rel (긴 휘발성, \*긴, 긴)|
|_InterlockedCompareExchange16|짧은 _InterlockedCompareExchange16 (짧은 휘발성, \*짧은, 짧은)|
|_InterlockedCompareExchange16_acq|짧은 _InterlockedCompareExchange16_acq (짧은 휘발성, \*짧은, 짧은)|
|_InterlockedCompareExchange16_nf|짧은 _InterlockedCompareExchange16_nf (짧은 휘발성, \*짧은, 짧은)|
|_InterlockedCompareExchange16_rel|짧은 _InterlockedCompareExchange16_rel (짧은 휘발성, \*짧은, 짧은)|
|_InterlockedCompareExchange64|\___int64 _InterlockedCompareExchange64(_int64 \* \_휘발성, \__int64, _int64)|
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq\_ \*(_int64 \_휘발성, _int64, \__int64)|
|_InterlockedCompareExchange64_nf|\___int64 _InterlockedCompareExchange64_nf(_int64 \* \_휘발성, \__int64, _int64)|
|_InterlockedCompareExchange64_rel|\___int64 _InterlockedCompareExchange64_rel(_int64 \* \_휘발성, \__int64, _int64)|
|_InterlockedCompareExchange8|char _InterlockedCompareExchange8 (char 휘발성, \*char, char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq (char 휘발성, \*차, 문자)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf (char 휘발성, \*char, char)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel (char 휘발성, \*차, 문자)|
|_InterlockedCompareExchangePointer|빈 \* \* _InterlockedCompareExchangePointer(무효 \*휘발성, \* \*무효, 무효)|
|_InterlockedCompareExchangePointer_acq|무효 \* \* _InterlockedCompareExchangePointer_acq(무효 \*휘발성, 무효, \*무효) \*|
|_InterlockedCompareExchangePointer_nf|무효 \* \* _InterlockedCompareExchangePointer_nf(무효 \*휘발성, 무효, \*무효) \*|
|_InterlockedCompareExchangePointer_rel|무효 \* \* _InterlockedCompareExchangePointer_rel(무효 \*휘발성, 무효, \*무효) \*|
|_InterlockedCompareExchange128|서명되지 않은\_차 \* _InterlockedCompareExchange128 \_(휘발성 \__Destination, \__int64 \* _ExchangeHigh, _int64 _ExchangeLow, _int64 _ComparandResult _int64)|
|_InterlockedCompareExchange128_acq|서명되지 않은\_char \* _InterlockedCompareExchange128_acq \_(휘발성 \__Destination, \__int64 \* _ExchangeHigh, _int64 _ExchangeLow, _int64 _ComparandResult _int64)|
|_InterlockedCompareExchange128_nf|서명되지 않은\_char \* _InterlockedCompareExchange128_nf \_(휘발성 \__Destination, \__int64 \* _ExchangeHigh, _int64 _ExchangeLow, _int64 _ComparandResult _int64)|
|_InterlockedCompareExchange128_rel|서명되지 않은\_차 \* _InterlockedCompareExchange128_rel \_(휘발성 \__Destination, \__int64 \* _ExchangeHigh, _int64 _ExchangeLow, _int64 _ComparandResult _int64)|
|_InterlockedDecrement|긴 __cdecl _InterlockedDecrement \*(긴 휘발성)|
|_InterlockedDecrement16|짧은 _InterlockedDecrement16(짧은 \*휘발성)|
|_InterlockedDecrement16_acq|짧은 _InterlockedDecrement16_acq(짧은 \*휘발성)|
|_InterlockedDecrement16_nf|짧은 _InterlockedDecrement16_nf(짧은 \*휘발성)|
|_InterlockedDecrement16_rel|짧은 _InterlockedDecrement16_rel(짧은 \*휘발성)|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64\_(_int64 휘발성) \*|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq\_(_int64 휘발성) \*|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf\_(_int64 휘발성) \*|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel\_(휘발성 \*_int64)|
|_InterlockedDecrement_acq|긴 _InterlockedDecrement_acq (긴 휘발성) \*|
|_InterlockedDecrement_nf|긴 _InterlockedDecrement_nf (긴 휘발성) \*|
|_InterlockedDecrement_rel|긴 _InterlockedDecrement_rel (긴 휘발성) \*|
|_InterlockedExchange|긴 __cdecl _InterlockedExchange \* (긴 휘발성 _Target, 긴)|
|_InterlockedExchange_acq|긴 _InterlockedExchange_acq (긴 휘발성 \* _Target, 긴)|
|_InterlockedExchange_nf|긴 _InterlockedExchange_nf(긴 \* 휘발성 _Target, 긴)|
|_InterlockedExchange_rel|긴 _InterlockedExchange_rel(긴 \* 휘발성 _Target, 긴)|
|_InterlockedExchange16|짧은 _InterlockedExchange16(짧은 \* 휘발성 _Target, 짧은)|
|_InterlockedExchange16_acq|짧은 _InterlockedExchange16_acq (짧은 휘발성 \* _Target, 짧은)|
|_InterlockedExchange16_nf|짧은 _InterlockedExchange16_nf (짧은 휘발성 \* _Target, 짧은)|
|_InterlockedExchange16_rel|짧은 _InterlockedExchange16_rel (짧은 휘발성 \* _Target, 짧은)|
|_InterlockedExchange64|__int64\__InterlockedExchange64(휘발성 \* _Target \__int64, _int64)|
|_InterlockedExchange64_acq|__int64\__InterlockedExchange64_acq(휘발성 \* _Target \__int64, _int64)|
|_InterlockedExchange64_nf|__int64\__InterlockedExchange64_nf(휘발성 \* _Target \__int64, _int64)|
|_InterlockedExchange64_rel|__int64\__InterlockedExchange64_rel(_int64 \* 휘발성 \__Target, _int64)|
|_InterlockedExchange8|차 _InterlockedExchange8 (차 휘발성 \* _Target, 차)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq (char 휘발성 \* _Target, char)|
|_InterlockedExchange8_nf|문자 _InterlockedExchange8_nf (차 휘발성 \* _Target, 차)|
|_InterlockedExchange8_rel|차 _InterlockedExchange8_rel (차 휘발성 \* _Target, 차)|
|_InterlockedExchangeAdd|긴 __cdecl _InterlockedExchangeAdd \*(긴 휘발성 , 긴)|
|_InterlockedExchangeAdd16|짧은 _InterlockedExchangeAdd16(짧은 \*휘발성, 짧은)|
|_InterlockedExchangeAdd16_acq|짧은 _InterlockedExchangeAdd16_acq(짧은 \*휘발성, 짧은)|
|_InterlockedExchangeAdd16_nf|짧은 _InterlockedExchangeAdd16_nf (짧은 휘발성, \*짧은)|
|_InterlockedExchangeAdd16_rel|짧은 _InterlockedExchangeAdd16_rel (짧은 휘발성, \*짧은)|
|_InterlockedExchangeAdd64|__int64\__InterlockedExchangeAdd64(_int64 \* \_휘발성, _int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq\_(_int64 \_휘발성, \*_int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf\_(_int64 휘발성 \*, \__int64)|
|_InterlockedExchangeAdd64_rel|__int64\__InterlockedExchangeAdd64_rel(_int64 \* \_휘발성, _int64)|
|_InterlockedExchangeAdd8|char _InterlockedExchangeAdd8 (char 휘발성 \*, char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq (char 휘발성 \*, 문자)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf (char 휘발성 \*, char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel (char 휘발성 \*, char)|
|_InterlockedExchangeAdd_acq|긴 _InterlockedExchangeAdd_acq (긴 휘발성 \*, 긴)|
|_InterlockedExchangeAdd_nf|긴 _InterlockedExchangeAdd_nf (긴 휘발성 \*, 긴)|
|_InterlockedExchangeAdd_rel|긴 _InterlockedExchangeAdd_rel (긴 휘발성 \*, 긴)|
|_InterlockedExchangePointer|보이드 \* \* _InterlockedExchangePointer(무효 \* 휘발성 \*_Target, 무효)|
|_InterlockedExchangePointer_acq|무효 \* \* _InterlockedExchangePointer_acq(무효 \* 휘발성 \*_Target, 무효)|
|_InterlockedExchangePointer_nf|무효 \* \* _InterlockedExchangePointer_nf(무효 \* 휘발성 \*_Target, 무효)|
|_InterlockedExchangePointer_rel|무효 \* \* _InterlockedExchangePointer_rel(무효 \* 휘발성 \*_Target, 무효)|
|_InterlockedIncrement|긴 __cdecl _InterlockedIncrement \*(긴 휘발성)|
|_InterlockedIncrement16|짧은 _InterlockedIncrement16 (짧은 휘발성) \*|
|_InterlockedIncrement16_acq|짧은 _InterlockedIncrement16_acq(짧은 \*휘발성)|
|_InterlockedIncrement16_nf|짧은 _InterlockedIncrement16_nf(짧은 \*휘발성)|
|_InterlockedIncrement16_rel|짧은 _InterlockedIncrement16_rel(짧은 \*휘발성)|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64\_(_int64 휘발성) \*|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq\_(_int64 휘발성) \*|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf\_(_int64 휘발성) \*|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel\_(_int64 휘발성) \*|
|_InterlockedIncrement_acq|긴 _InterlockedIncrement_acq (긴 휘발성) \*|
|_InterlockedIncrement_nf|긴 _InterlockedIncrement_nf (긴 휘발성) \*|
|_InterlockedIncrement_rel|긴 _InterlockedIncrement_rel (긴 휘발성) \*|
|_InterlockedOr|긴 _InterlockedOr (긴 휘발성 \*, 긴)|
|_InterlockedOr16|짧은 _InterlockedOr16 (짧은 휘발성, \*짧은)|
|_InterlockedOr16_acq|짧은 _InterlockedOr16_acq (짧은 휘발성, \*짧은)|
|_InterlockedOr16_nf|짧은 _InterlockedOr16_nf (짧은 휘발성, \*짧은)|
|_InterlockedOr16_rel|짧은 _InterlockedOr16_rel (짧은 휘발성, \*짧은)|
|_InterlockedOr64|__int64\__InterlockedOr64(_int64 \* \_휘발성, _int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq\_(_int64 \_휘발성, \*_int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf\_(_int64 \_휘발성, \*_int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel\_(_int64 \_휘발성, \*_int64)|
|_InterlockedOr8|char _InterlockedOr8 (char 휘발성 \*, char)|
|_InterlockedOr8_acq|char _InterlockedOr8_acq (char 휘발성 \*, char)|
|_InterlockedOr8_nf|char _InterlockedOr8_nf (char 휘발성 \*, char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel (char 휘발성 \*, char)|
|_InterlockedOr_acq|긴 _InterlockedOr_acq (긴 휘발성 \*, 긴)|
|_InterlockedOr_nf|긴 _InterlockedOr_nf (긴 휘발성 \*, 긴)|
|_InterlockedOr_rel|긴 _InterlockedOr_rel (긴 휘발성 \*, 긴)|
|_InterlockedXor|긴 _InterlockedXor (긴 휘발성 \*, 긴)|
|_InterlockedXor16|짧은 _InterlockedXor16 (짧은 휘발성, \*짧은)|
|_InterlockedXor16_acq|짧은 _InterlockedXor16_acq (짧은 휘발성, \*짧은)|
|_InterlockedXor16_nf|짧은 _InterlockedXor16_nf(짧은 \*휘발성, 짧은)|
|_InterlockedXor16_rel|짧은 _InterlockedXor16_rel (짧은 휘발성, \*짧은)|
|_InterlockedXor64|__int64 _InterlockedXor64\_(_int64 \_휘발성, \*_int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq\_(_int64 \_휘발성, \*_int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf\_ \*(휘발성 \__int64, _int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel\_(_int64 \_휘발성, \*_int64)|
|_InterlockedXor8|char _InterlockedXor8 (char 휘발성 \*, char)|
|_InterlockedXor8_acq|문자 _InterlockedXor8_acq (char 휘발성 \*, 문자)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf (char 휘발성 \*, char)|
|_InterlockedXor8_rel|문자 _InterlockedXor8_rel (char 휘발성 \*, 문자)|
|_InterlockedXor_acq|긴 _InterlockedXor_acq (긴 휘발성 \*, 긴)|
|_InterlockedXor_nf|긴 _InterlockedXor_nf (긴 휘발성 \*, 긴)|
|_InterlockedXor_rel|긴 _InterlockedXor_rel (긴 휘발성 \*, 긴)|

[[맨 위로 돌아가기]](#top)

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest 내장

일반 연동 비트 테스트 내장은 모든 플랫폼에 공통적입니다. ARM64는 `_acq` `_rel`이 `_nf` 문서의 앞에서 [_nf(울타리 없음) 접미사에](#nf_suffix) 설명된 대로 작업의 장벽 의미체계를 수정하는 및 변형을 추가합니다.

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|_interlockedbittestandreset|서명되지 않은 char \*_interlockedbittestandreset (긴 휘발성 , 긴)|
|_interlockedbittestandreset_acq|서명되지 않은 char \*_interlockedbittestandreset_acq (긴 휘발성 , 긴)|
|_interlockedbittestandreset_nf|서명되지 않은 char \*_interlockedbittestandreset_nf (긴 휘발성 , 긴)|
|_interlockedbittestandreset_rel|서명되지 않은 char \*_interlockedbittestandreset_rel (긴 휘발성 , 긴)|
|_interlockedbittestandreset64|서명되지 않은 char \*_interlockedbittestandreset64 (__int64 휘발성 , __int64)|
|_interlockedbittestandreset64_acq|서명되지 않은 차 \*_interlockedbittestandreset64_acq (__int64 휘발성, __int64)|
|_interlockedbittestandreset64_nf|서명되지 않은 char \*_interlockedbittestandreset64_nf (__int64 휘발성, __int64)|
|_interlockedbittestandreset64_rel|서명되지 않은 char \*_interlockedbittestandreset64_rel (__int64 휘발성 , __int64)|
|_interlockedbittestandset|서명되지 않은 char \*_interlockedbittestandset (긴 휘발성 , 긴)|
|_interlockedbittestandset_acq|서명되지 않은 char \*_interlockedbittestandset_acq (긴 휘발성 , 긴)|
|_interlockedbittestandset_nf|서명되지 않은 char \*_interlockedbittestandset_nf (긴 휘발성 , 긴)|
|_interlockedbittestandset_rel|서명되지 않은 char \*_interlockedbittestandset_rel (긴 휘발성 , 긴)|
|_interlockedbittestandset64|서명되지 않은 char \*_interlockedbittestandset64 (__int64 휘발성, __int64)|
|_interlockedbittestandset64_acq|서명되지 않은 char \*_interlockedbittestandset64_acq (__int64 휘발성 , __int64)|
|_interlockedbittestandset64_nf|서명되지 않은 char \*_interlockedbittestandset64_nf (__int64 휘발성, __int64)|
|_interlockedbittestandset64_rel|서명되지 않은 char \*_interlockedbittestandset64_rel (__int64 휘발성 , __int64)|

[[맨 위로 돌아가기]](#top)

## <a name="see-also"></a>참조

[컴파일러 내장](../intrinsics/compiler-intrinsics.md)\
[ARM 내장](arm-intrinsics.md)\
[ARM 어셈블러 레퍼런스](../assembler/arm/arm-assembler-reference.md)\
[C++ 언어 참조](../cpp/cpp-language-reference.md)
