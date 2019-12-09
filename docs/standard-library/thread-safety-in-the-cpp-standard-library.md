---
title: C++ 표준 라이브러리의 스레드 보안
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: 4ac029a119a77fa87c6cd004fece9c4e6b382026
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460060"
---
# <a name="thread-safety-in-the-c-standard-library"></a>C++ 표준 라이브러리의 스레드 보안

다음 스레드 보안 규칙은 C++ 표준 라이브러리의 모든 클래스에 적용됩니다. 아래에서 설명하는 것처럼 이 라이브러리에는 `shared_ptr`이 포함됩니다.  경우에 따라 좀 더 강력하게 적용되기도 합니다. 예를 들어 아래에서 설명하는 것처럼 표준 iostream 개체 및 [\<atomic>](../standard-library/atomic.md)의 형식과 같은 다중 스레딩에 사용되기 위한 형식이 그러한 경우입니다.

개체는 여러 스레드에서 읽기 위해 스레드로부터 안전하게 보호됩니다. 예를 들어 개체A가 있다고 가정하면 스레드1과 스레드2에서 개체A를 동시에 안전하게 읽을 수 있습니다.

스레드 하나에서 개체에 쓰는 경우 동일하거나 다른 스레드에서 해당 개체에 대한 모든 읽기 및 쓰기가 보호되어야 합니다. 예를 들어 개체A가 있다고 가정하면 스레드1이 A에 쓰는 경우 스레드2는 A에서 읽거나 A에 쓸 수 없어야 합니다.

다른 스레드가 동일한 형식의 다른 인스턴스를 읽거나 이러한 인스턴스에 쓰는 경우에 해당 형식의 인스턴스 하나에 대한 읽기 및 쓰기가 보호됩니다. 예를 들어 형식이 동일한 개체A와 B가 있다고 가정하면 스레드1에서 개체A에 쓰는 중이고 스레드2에서 개체B를 읽는 중인 경우 안전합니다.

## <a name="sharedptr"></a>shared_ptr

개체가 소유권을 공유하는 복사본이더라도 다중 스레드가 여러 [shared_ptr](../standard-library/shared-ptr-class.md) 개체를 동시에 읽고 쓸 수 있습니다.

## <a name="iostream"></a>iostream

표준 iostream 개체 `cin`, `cout`, `cerr`, `clog`, `wcin`, `wcout`, `wcerr` 및 `wclog`는 다중 스레드에서 개체에 쓰기가 보호된다는 점을 제외하면 다른 클래스와 동일한 규칙을 따릅니다. 예를 들어 스레드1은 스레드2와 동시에 [cout](../standard-library/iostream.md#cout)에 쓸 수 있습니다. 그러나 이로 인해 두 스레드에서 나온 출력이 섞일 수 있습니다.

> [!NOTE]
> 스트림 버퍼에서의 읽기는 읽기 작업으로 간주되지 않습니다. 대신에 클래스 상태가 변하기 때문에 쓰기 작업으로 간주됩니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)
