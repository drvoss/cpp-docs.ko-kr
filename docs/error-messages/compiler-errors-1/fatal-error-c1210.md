---
title: 심각한 오류 C1210
ms.date: 11/04/2016
f1_keywords:
- C1210
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
ms.openlocfilehash: 50bafa522c931c909b5ce163a78305ffc028765a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203387"
---
# <a name="fatal-error-c1210"></a>심각한 오류 C1210

> 설치된 런타임 버전에서는 /clr:pure 및 /clr:safe가 지원되지 않습니다.

**/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

현재 릴리스에 대한 컴파일러가 있지만 이전 릴리스의 공용 언어 런타임을 사용하는 경우 C1210이 발생합니다.

컴파일러의 일부 기능은 이전 버전의 런타임에서 작동하지 않을 수 있습니다.

C1210을 해결하려면 컴파일러와 함께 사용하도록 디자인된 공용 언어 런타임 버전을 설치합니다.
