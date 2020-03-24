---
title: 리소스 컴파일러 오류 RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: c428fefa90cceed6a8bc9b7f6e4b95ec2db5e039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182411"
---
# <a name="resource-compiler-warning-rc4005"></a>리소스 컴파일러 오류 RC4005

' identifier ': 매크로 재정의

식별자는 두 번 정의 됩니다. 컴파일러가 두 번째 매크로 정의를 사용 했습니다.

이 경고는 명령줄에서 매크로를 정의 하 고 `#define` 지시문을 사용 하 여 코드에 발생 하는 경우에 발생할 수 있습니다. 포함 파일에서 가져온 매크로로 인해 발생할 수도 있습니다.

이 경고를 제거 하려면 정의 중 하나를 제거 하거나 두 번째 정의 앞에 `#undef` 지시어를 사용 합니다.
