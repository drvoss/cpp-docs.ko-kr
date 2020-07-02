---
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: d19d47fe7120301740e1431765fc6edbeaa48c60
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448200"
---
# <a name="_scl_secure_no_warnings"></a>_SCL_SECURE_NO_WARNINGS

C++ 표준 라이브러리에서 잠재적으로 안전하지 않은 메서드를 호출하면 [컴파일러 경고(수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)이 발생합니다. 이 경고를 사용하지 않도록 설정하려면 코드에서 _SCL_SECURE_NO_WARNINGS 매크로를 정의합니다.

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

미리 컴파일된 헤더를 사용하는 경우 C 런타임 라이브러리 또는 표준 라이브러리 헤더를 포함하기 전에 미리 컴파일된 헤더 파일에 이 지시문을 추가합니다. 미리 컴파일된 헤더 파일을 포함하기 전에 개별 소스 코드 파일에 배치하는 경우 컴파일러에서 무시됩니다.

## <a name="remarks"></a>설명

C4996 경고를 비활성화하는 다른 방법은 다음과 같습니다.

- [/D (전처리기 정의)](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용합니다.

   > cl /D_SCL_SECURE_NO_WARNINGS [기타 컴파일러 옵션] myfile .cpp

- [/w](../build/reference/compiler-option-warning-level.md) 컴파일러 옵션을 사용합니다.

   > cl /wd4996 [other compiler options] myfile.cpp

- [#pragma warning](../preprocessor/warning.md) 경고를 사용합니다.

   ```cpp
   #pragma warning(disable:4996)
   ```

**/w\<l>\<n>** 컴파일러 옵션을 사용하여 경고 C4996의 수준을 수동으로 변경할 수도 있습니다. 예를들어 C4996 경고를 수준 4로 설정하려면 다음 코드를 사용합니다.

> cl /w44996 [other compiler options] myfile.cpp

자세한 내용은 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)](../build/reference/compiler-option-warning-level.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)
