---
title: '방법: weak_ptr 인스턴스 만들기 및 사용'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 32e8d64fdb6449f1d40aec4161bfda54987ca66a
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245597"
---
# <a name="how-to-create-and-use-weak_ptr-instances"></a>방법: weak_ptr 인스턴스 만들기 및 사용

경우에 따라 개체가 참조 횟수를 증가 시 키 지 않고 [shared_ptr](../standard-library/shared-ptr-class.md) 의 기본 개체에 액세스 하는 방법을 저장 해야 합니다. 일반적으로 이러한 상황은 `shared_ptr` 인스턴스 사이에 순환 참조가 있는 경우에 발생 합니다.

가능 하면 언제 든 지 포인터의 공유 소유권을 방지 하는 것이 가장 좋습니다. 그러나 `shared_ptr` 인스턴스에 대 한 공유 소유권이 있어야 하는 경우에는 두 항목 간의 순환 참조를 사용 하지 마십시오. 순환 참조가 피할 수 없는 경우 또는 어떤 이유로 든 더 선호 하는 경우에는 [weak_ptr](../standard-library/weak-ptr-class.md) 를 사용 하 여 하나 이상의 소유자에 게 다른 `shared_ptr`에 대 한 약한 참조를 제공 합니다. `weak_ptr`를 사용 하 여 기존 관련 인스턴스 집합에 조인 하는 `shared_ptr`을 만들 수 있습니다. 단, 기본 메모리 리소스가 여전히 유효 합니다. `weak_ptr` 자체는 참조 횟수에 참여 하지 않으므로 참조 횟수가 0으로 이동 하는 것을 방지할 수 없습니다. 그러나 `weak_ptr`를 사용 하 여 초기화 된 `shared_ptr`의 새 복사본을 가져오려고 시도할 수 있습니다. 메모리가 이미 삭제 된 경우 `weak_ptr`의 bool 연산자는 `false`를 반환 합니다. 메모리가 여전히 유효한 경우 새 공유 포인터는 참조 횟수를 증가 시키고 `shared_ptr` 변수가 범위 내에 있는 한 메모리를 유효 하 게 유지 하도록 보장 합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 `weak_ptr`를 사용 하 여 순환 종속성이 있는 개체를 적절 하 게 삭제 하는 경우를 보여 줍니다. 예제를 검토할 때 대체 솔루션이 고려 된 후에만 생성 된 것으로 가정 합니다. `Controller` 개체는 컴퓨터 프로세스의 일부 측면을 나타내며 독립적으로 작동 합니다. 각 컨트롤러는 언제 든 지 다른 컨트롤러의 상태를 쿼리할 수 있어야 하며 각 컨트롤러에는 이러한 목적을 위한 개인 `vector<weak_ptr<Controller>>` 포함 되어 있습니다. 각 벡터는 순환 참조를 포함 하므로 `shared_ptr`대신 `weak_ptr` 인스턴스가 사용 됩니다.

[!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]

```Output
Creating Controller0
Creating Controller1
Creating Controller2
Creating Controller3
Creating Controller4
push_back to v[0]: 1
push_back to v[0]: 2
push_back to v[0]: 3
push_back to v[0]: 4
push_back to v[1]: 0
push_back to v[1]: 2
push_back to v[1]: 3
push_back to v[1]: 4
push_back to v[2]: 0
push_back to v[2]: 1
push_back to v[2]: 3
push_back to v[2]: 4
push_back to v[3]: 0
push_back to v[3]: 1
push_back to v[3]: 2
push_back to v[3]: 4
push_back to v[4]: 0
push_back to v[4]: 1
push_back to v[4]: 2
push_back to v[4]: 3
use_count = 1
Status of 1 = On
Status of 2 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 2 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 1 = On
Status of 3 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 1 = On
Status of 2 = On
Status of 4 = On
use_count = 1
Status of 0 = On
Status of 1 = On
Status of 2 = On
Status of 3 = On
Destroying Controller0
Destroying Controller1
Destroying Controller2
Destroying Controller3
Destroying Controller4
Press any key
```

실험으로 벡터 `others`를 `vector<shared_ptr<Controller>>`으로 수정한 다음 출력에서 `TestRun` 반환 될 때 소멸자가 호출 되지 않는지 확인 합니다.

## <a name="see-also"></a>참고 항목

[스마트 포인터(모던 C++)](../cpp/smart-pointers-modern-cpp.md)
