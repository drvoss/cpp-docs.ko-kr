---
title: 명령줄 경고 D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 7c685a1ca3195ad4ab52bab8b5d32b1a51534b24
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196577"
---
# <a name="command-line-warning-d9041"></a>명령줄 경고 D9041

'/option '의 ' value ' 값이 잘못 되었습니다. ' value '로 가정 합니다. 이 경고를 지정 하는 경우 명령줄 옵션에 '/analyze '를 추가 합니다.

**/Wd**, **/we**, **/wo**또는 **/wl** 명령줄 옵션에도 **/analyze** 명령줄 옵션을 지정 하지 않고 코드 분석 경고 번호가 추가 되었습니다. 이 오류를 해결 하려면 **/analyze** 명령줄 옵션을 추가 하거나 적절 한 **/w** 명령줄 옵션에서 잘못 된 경고 번호를 제거 합니다.

## <a name="example"></a>예제

다음 명령줄 예제에서는 D9041 경고를 생성 합니다.

```
cl /EHsc /LD /wd6001 filename.cpp
```

이 경고를 해결 하려면 **/analyze** 명령줄 옵션을 추가 합니다. 버전의 컴파일러에서 **/analyze** 가 지원 되지 않는 경우 **/wd** 옵션에서 잘못 된 경고 번호를 제거 합니다.

## <a name="see-also"></a>참고 항목

[명령줄 오류(D8000 ~ D9999)](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 컴파일러 옵션](../../build/reference/compiler-options.md)
