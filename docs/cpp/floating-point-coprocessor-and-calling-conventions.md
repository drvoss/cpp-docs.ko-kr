---
title: 부동 소수점 보조 프로세서 및 호출 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: c70dd3b049ca353acc8a504df52b2c61feaf1974
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188625"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>부동 소수점 보조 프로세서 및 호출 규칙

부동 소수점 보조 프로세서에 대 한 어셈블리 루틴을 작성 하는 경우 부동 소수점 제어 단어를 유지 하 고 **float** 또는 **double** 값 (함수에서 ST (0)으로 반환 해야 함)을 반환 하지 않는 한 보조 프로세서 스택을 정리 해야 합니다.

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)
