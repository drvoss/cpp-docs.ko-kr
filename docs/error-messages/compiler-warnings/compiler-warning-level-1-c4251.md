---
title: 컴파일러 경고(수준 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 8a723b7ce7fc79fb6be9c9dd2b500631098622b0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163221"
---
# <a name="compiler-warning-level-1-c4251"></a>컴파일러 경고(수준 1) C4251

' identifier ': ' type ' 클래스는 ' type2 ' 클래스의 클라이언트에서 사용할 dll 인터페이스를 포함 해야 합니다.

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)를 사용 하 여 클래스를 내보낼 때 데이터가 손상 될 가능성을 최소화 하려면 다음을 확인 합니다.

- 모든 정적 데이터는 DLL에서 내보낸 함수를 통해 액세스할 수 있습니다.

- 클래스의 인라인 메서드는 정적 데이터를 수정할 수 없습니다.

- CRT 함수 또는 다른 라이브러리 함수를 사용 하는 클래스의 인라인 메서드는 정적 데이터를 사용 하지 않습니다. 자세한 내용은 [DLL 경계를 넘어 Crt 개체를 전달 하는 잠재적 오류](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) 를 참조 하세요.

- 인라인에 관계 없이 클래스의 메서드는 EXE 및 DLL의 인스턴스화에 정적 데이터 차이가 있는 형식을 사용할 수 있습니다.

가상 함수를 사용 하 여 클래스를 정의 하는 DLL을 정의 하 고 해당 형식의 개체를 인스턴스화하고 삭제 하기 위해 호출할 수 있는 함수를 정의 하 여 클래스를 내보내지 않을 수 있습니다.  그런 다음 해당 형식에 대 한 가상 함수를 호출 하면 됩니다.

C++ 표준 라이브러리의 형식에서 파생 하 고, 디버그 릴리스 ( **/MTd**)를 컴파일하고, 컴파일러 오류 메시지가 _Container_base를 참조 하는 경우에는 C4251을 무시할 수 있습니다.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```
