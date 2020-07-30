---
title: 컴파일러 경고 C4577
description: 컴파일러 경고 C4577 설명 및 솔루션입니다.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: fb9d412196e7764326a397a4bf6e76c8723ac2ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196255"
---
# <a name="compiler-warning-level-1-c4577"></a>컴파일러 경고 (수준 1) C4577

> 예외 처리 모드를 지정 하지 않고 ' noexcept '을 사용 했습니다. 예외에서 종료는 보장 되지 않습니다. /EHsc 지정

컴파일러가 **`noexcept`** 사양을 검색 했지만 표준 c + + 예외 처리가 지정 되지 않았습니다. [/Ehsc](../../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 지정 하지 않으면 컴파일러가 c + + 표준에 따라 예외 처리를 완전히 지원 하지 않습니다. 이 문제를 해결 하려면 **/ehsc** 컴파일러 옵션을 설정 합니다.

이 경고는 Visual Studio 2015의 새로운 기능은 기본적으로 해제 되어 있습니다. 자세한 내용은 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조 하세요.
