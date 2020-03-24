---
title: 리소스 컴파일러 경고 RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: ca0fb271a5ab43994ec37cc8d59c33877903f6e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182346"
---
# <a name="resource-compiler-warning-rw4004"></a>리소스 컴파일러 경고 RW4004

ASCII 문자가 가상 키 코드와 일치하지 않습니다.

VIRTKEY 형식 액셀러레이터의 가상 키 코드에 문자열 리터럴을 사용했습니다.

이 경고가 표시되어도 계속 진행할 수 있지만 생성된 액셀러레이터 키가 지정한 문자열과 일치하지 않을 수 있습니다. (VIRTKEY가 ASCII 액셀러레이터와 다른 키 코드를 사용합니다.)

문자열 리터럴은 구문상 유효 하지만, WINDOWS의 **VK_\* #define** 값을 사용 하 여 원하는 액셀러레이터 키만 얻을 수 있습니다.
