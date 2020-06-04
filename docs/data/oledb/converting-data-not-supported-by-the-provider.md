---
title: 공급자가 지원하지 않는 데이터 변환
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e87aebc4d6f23343af9a2f966d2c522e95b304ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211499"
---
# <a name="converting-data-not-supported-by-the-provider"></a>공급자가 지원하지 않는 데이터 변환

소비자가 공급자가 지원 하지 않는 데이터 형식을 요청 하면 `IRowsetImpl::GetData`에 대 한 OLE DB 공급자 템플릿 코드가 Msdadc를 호출 하 여 데이터 형식을 변환 합니다.

데이터 변환이 필요한 `IRowsetChange`와 같은 인터페이스를 구현 하는 경우 Msdaenum를 호출 하 여 변환을 수행할 수 있습니다. Atldb.h에 정의 된 `GetData`를 예로 사용 합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)
