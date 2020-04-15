---
title: safebuffer
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: bc4736ce233ce026ecab9ef38ac8379466b5a0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365579"
---
# <a name="safebuffers"></a>safebuffer

**마이크로소프트 특정**

함수에 대한 버퍼 오버런 보안 검사를 삽입하지 않도록 컴파일러에 지시합니다.

## <a name="syntax"></a>구문

```
__declspec( safebuffers )
```

## <a name="remarks"></a>설명

**/GS** 컴파일러 옵션을 사용하면 컴파일러가 스택에 보안 검사를 삽입하여 버퍼 오버런을 테스트합니다. 보안 검사를 받을 수 있는 데이터 구조의 형식은 [/GS(버퍼 보안 검사)에](../build/reference/gs-buffer-security-check.md)설명되어 있습니다. 버퍼 오버런 검색에 대한 자세한 내용은 [MSVC의 보안 기능을](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)참조하십시오.

전문가 수동 코드 검토 또는 외부 분석이 함수가 버퍼 오버런으로부터 안전한지 확인할 수 있습니다. 이 경우 함수 선언에 **__declspec(safebuffers) 키워드를** 적용하여 함수에 대한 보안 검사를 억제할 수 있습니다.

> [!CAUTION]
> 그러나 버퍼 보안 검사는 중요한 보안 보호를 제공하고 성능에 별다른 영향을 미치지 않으므로, 함수의 성능이 매우 중요하고 해당 함수의 안전성이 파악되는 드문 경우를 제외하고, 버퍼 보안 검사를 억제하지 않도록 권장합니다.

## <a name="inline-functions"></a>인라인 함수

*기본 함수는* [인라이닝](inline-functions-cpp.md) 키워드를 사용하여 보조 *함수의*복사본을 삽입할 수 있습니다. **__declspec(safebuffers)** 키워드가 함수에 적용되면 해당 함수에 대해 버퍼 오버런 검색이 억제됩니다. 그러나 인라인은 다음과 같은 방법으로 **__declspec(safebuffers)** 키워드에 영향을 줍니다.

**/GS** 컴파일러 옵션이 두 함수 모두에 대해 지정되었지만 기본 함수에서 **__declspec(safebuffers) 키워드를 지정한다고 가정합니다.** 보조 함수의 데이터 구조는 보안 검사를 가능하게 하기 때문에 이 함수는 보안 검사를 억제하지 않습니다. 이 경우 다음과 같습니다.

- 컴파일러 최적화에 관계없이 컴파일러가 해당 함수를 인라인하도록 두도록 보조 함수에서 [__forceinline](inline-functions-cpp.md) 키워드를 지정합니다.

- 보조 함수는 보안 검사를 받을 수 있으므로 **__declspec(safebuffers)** 키워드를 지정하더라도 보안 검사도 기본 함수에 적용됩니다.

## <a name="example"></a>예제

다음 코드에서는 **__declspec(safebuffers) 키워드를** 사용하는 방법을 보여 주십니다.

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
