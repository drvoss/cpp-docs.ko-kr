---
title: 컴파일러 오류 C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 8aec3ae1ff629ef7fa000182cde29e306a471315
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165877"
---
# <a name="compiler-error-c3728"></a>컴파일러 오류 C3728

' event ': 이벤트에 raise 메서드가 없습니다.

가 정의 된 클래스 외부에서 발생 하 C#는 이벤트를 허용 하지 않는 등의 언어로 만든 메타 데이터가 [#using](../../preprocessor/hash-using-directive-cpp.md) 지시문에 포함 되었으며 CLR 프로그래밍을 사용 하는 시각적 C++ 프로그램에서 이벤트를 발생 시 키 려 고 했습니다.

과 C#같은 언어로 개발 된 프로그램에서 이벤트를 발생 시키려면 이벤트를 포함 하는 클래스가 이벤트를 발생 시키는 공용 메서드를 정의 해야 합니다.
