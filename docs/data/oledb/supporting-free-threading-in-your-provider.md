---
title: 공급자에서 자유 스레딩 지원
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 50e05b70a782dd343031443540790697e980c994
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209551"
---
# <a name="supporting-free-threading-in-your-provider"></a>공급자에서 자유 스레딩 지원

모든 OLE DB 공급자 클래스는 스레드로부터 안전하고, 레지스트리 항목도 이에 따라 설정됩니다. 자유 스레드를 지원하여 다중 사용자 환경에서 성능을 향상시키는 것이 좋습니다. 공급자를 스레드로부터 안전하게 유지하려면 코드에 액세스하지 못하도록 적절히 차단해야 합니다. 데이터를 쓰거나 저장할 때마다 임계 섹션을 사용하여 액세스를 차단해야 합니다.

각 OLE DB 공급자 템플릿 개체에는 자체의 임계 섹션이 있습니다. 차단을 쉽게 하려면 사용자가 새로 만든 각 클래스가 부모 클래스 이름을 인수로 취하는 템플릿 클래스여야 합니다.

다음 예제에서는 코드를 차단 하는 방법을 보여 줍니다.

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

`Lock` 및 `Unlock`를 사용 하 여 중요 한 섹션을 보호 하는 방법에 대 한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)을 참조 하세요.

재정의 하는 메서드 (예: `Execute`)가 스레드로부터 안전 하 게 보호 되는지 확인 합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)
