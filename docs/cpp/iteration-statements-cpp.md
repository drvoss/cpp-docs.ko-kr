---
title: 반복 문 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: e8f064fd19e69de2819673f48a7f14e26d60b87e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178261"
---
# <a name="iteration-statements-c"></a>반복 문 (C++)

반복 문을 사용하면 루프 종료 조건에 따라 문(또는 복합 문)이 0회 이상 실행됩니다. 이러한 문이 복합 문인 경우 [break](../cpp/break-statement-cpp.md) 문이나 [continue](../cpp/continue-statement-cpp.md) 문이 발견 되는 경우를 제외 하 고 순서 대로 실행 됩니다.

C++[는 while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)및 [범위 기반에 대 한](../cpp/range-based-for-statement-cpp.md)4 개의 반복 문을 제공 합니다. 이러한 각는 종료 식이 0 (false)으로 계산 되거나 **break** 문으로 루프 종료가 강제 적용 될 때까지 반복 됩니다. 다음 표에는 이러한 문과 해당 작업이 요약되어 있습니다. 각 문에 대해서는 뒤에 나오는 단원에서 자세히 설명합니다.

### <a name="iteration-statements"></a>반복 문

|명세서|평가 위치|초기화|Increment|
|---------------|------------------|--------------------|---------------|
|**while**|루프의 맨 위|아니요|아니요|
|**do**|루프의 맨 아래|아니요|아니요|
|**for**|루프의 맨 위|예|예|
|**범위 기반**|루프의 맨 위|예|예|

반복 문의 문 부분은 선언일 수 없지만, 선언을 포함하는 복합 문일 수 있습니다.

## <a name="see-also"></a>참고 항목

[C++ 문 개요](../cpp/overview-of-cpp-statements.md)
