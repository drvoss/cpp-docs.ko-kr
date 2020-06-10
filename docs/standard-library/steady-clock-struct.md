---
title: steady_clock 구조체
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 19e9f5c4dcfc7306b989605894e9a0787e0920ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412399"
---
# <a name="steady_clock-struct"></a>steady_clock 구조체

*안정적인* 시간을 표현합니다.

## <a name="syntax"></a>구문

```cpp
struct steady_clock;
```

## <a name="remarks"></a>설명

Windows에서 `steady_clock`은 `QueryPerformanceCounter`의 래퍼 함수입니다.

`now`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *monotonic*입니다. 클록이 *monotonic*이고 클록 틱간 시간이 지속적이면 해당 클록은 *steady*입니다.

`high_resolution_clock`은 `steady_clock`의 typedef 입니다.

### <a name="public-typedefs"></a>공용 typedefs

|이름|설명|
|----------|-----------------|
|`steady_clock::duration`|\<chrono>에 정의된 `nanoseconds`의 동의어|
|`steady_clock::period`|\<ratio>에 정의된 `nano`의 동의어|
|`steady_clock::rep`|`duration`의 인스턴스화에서 클록 틱 수를 나타내는 데 사용되는 **long** **long** 형식|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>`의 동의어|

## <a name="public-functions"></a>공용 함수

|함수|설명|
|--------------|-----------------|
|`now`|현재 시간을 `time_point` 값으로 반환합니다.|

## <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|`steady_clock::is_steady`|**true**를 유지합니다. `steady_clock`은 *steady*입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<chrono>

**네임스페이스:** std::chrono

## <a name="see-also"></a>참고자료

- [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 구조체](../standard-library/system-clock-structure.md)
