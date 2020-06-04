---
title: 컴파일러 경고(수준 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 9f261d3deb7f1cac8cd5c60b920e0be49bc8b7a6
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032332"
---
# <a name="compiler-warning-level-1-c4251"></a>컴파일러 경고(수준 1) C4251

> '*유형*' : 클래스 '*type1*' 클래스의 클라이언트에 의해 사용 될 dll 인터페이스가 필요 '*type2*'

## <a name="remarks"></a>설명

[__declspec(dllexport)로](../../cpp/dllexport-dllimport.md)선언된 클래스를 내보낼 때 데이터 손상 가능성을 최소화하려면 다음을 수행하십시오.

- 모든 정적 데이터는 DLL에서 내보낸 함수를 통해 액세스됩니다.

- 클래스의 인라인된 메서드는 정적 데이터를 수정할 수 없습니다.

- 클래스의 인라인 된 메서드는 정적 데이터를 사용하는 CRT 함수 또는 기타 라이브러리 함수를 사용하지 않습니다. 자세한 내용은 [DLL 경계를 가로질러 CRT 개체를 전달하는 잠재적 오류를](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)참조하십시오.

- 클래스의 메서드는 INLINED 여부에 관계없이 EXE 및 DLL의 인스턴스화에 정적 데이터 차이가 있는 형식을 사용할 수 없습니다.

DLL에서 클래스를 내보낼 때 문제를 방지할 수 있습니다. 그런 다음 형식에서 가상 함수를 호출할 수 있습니다.

클래스가 C++ 표준 라이브러리의 형식에서 파생되고 디버그 릴리스(/MTd)를 컴파일하고 컴파일러 **/MTd**오류 메시지가 참조하는 경우 C4251을 `_Container_base`무시할 수 있습니다.

## <a name="example"></a>예제

이 샘플은 에서 `VecWrapper` 파생된 `std::vector`특수 클래스를 내보올합니다.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
