---
title: 마샬링
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 83cf29fb45347b7bfcfc1644546684f074061d25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319344"
---
# <a name="marshaling"></a>마샬링

마샬링의 COM 기술을 사용하면 한 프로세스의 개체에 의해 노출된 인터페이스를 다른 프로세스에서 사용할 수 있습니다. 마샬링에서 COM은 메서드매개 변수를 프로세스 간에 이동할 수 있는 형식으로 압축하고 다른 컴퓨터에서 실행되는 프로세스로 이동할 수 있는 형식으로 메서드 매개 변수를 압축하고 다른 쪽 끝에서 해당 매개 변수의 압축을 풀기 위해 코드(또는 인터페이스 구현자가 제공하는 코드를 사용)를 제공합니다. 마찬가지로 COM은 호출에서 반환할 때 동일한 단계를 수행해야 합니다.

> [!NOTE]
> 일반적으로 개체와 동일한 프로세스에서 개체에서 제공하는 인터페이스를 사용할 때 마샬링이 필요하지 않습니다. 그러나 스레드 간에 마샬링이 필요할 수 있습니다.


## <a name="see-also"></a>참고 항목

[COM 소개](../atl/introduction-to-com.md)<br/>
[세부 정보 마샬링](/windows/win32/com/marshaling-details)
