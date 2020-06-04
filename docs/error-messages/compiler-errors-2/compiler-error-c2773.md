---
title: 컴파일러 오류 C2773
ms.date: 11/04/2016
f1_keywords:
- C2773
helpviewer_keywords:
- C2773
ms.assetid: 8d564b26-1623-4d92-aabc-dff33f7b1145
ms.openlocfilehash: 661c607183697b0ace12291d9d1305b262a80c6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176990"
---
# <a name="compiler-error-c2773"></a>컴파일러 오류 C2773

\#가져오기 및 #using는 C++ 컴파일러 에서만 사용할 수 있습니다.

C 컴파일러는 `#import` 전처리기 지시문을 인식 하지 못합니다. 소스를로 C++컴파일합니다. 필요한 경우 [/tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 를 사용 합니다.
