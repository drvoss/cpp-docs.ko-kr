---
title: 심각한 오류 C1047
ms.date: 11/04/2016
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
ms.openlocfilehash: 5ab98c46d60d15cdcb6de22aa922d62453d41880
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204494"
---
# <a name="fatal-error-c1047"></a>심각한 오류 C1047

개체 또는 라이브러리 파일 'file'은 다른 개체에 사용한 컴파일러보다 이전 컴파일러로 만들어졌습니다. 해당 개체 및 라이브러리를 다시 빌드하세요.

**/LTCG** 로 빌드되는 개체 파일 또는 라이브러리가 함께 연결되었지만 해당 개체 파일 또는 라이브러리가 다른 버전의 Visual C++ 도구 집합으로 빌드되는 경우 C1047이 발생합니다.

새 버전의 컴파일러를 사용하여 시작되지만 기존 개체 파일 또는 라이브러리를 완전히 다시 빌드하지 않는 경우 발생할 수 있습니다.

C1047을 해결하려면 모든 개체 파일 또는 라이브러리를 다시 빌드합니다.
