---
title: 공급자 서비스 사용 및 사용 안 함
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: a74f8a8b099a30cf25007547e8059c77728435f9
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2019
ms.locfileid: "79544461"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>공급자 서비스 사용 및 사용 안 함

기본적으로 단일 공급자에 액세스하는 모든 응용 프로그램에 대해 개별 OLE DB 서비스를 사용하거나 사용하지 않을 수 있습니다. 공급자의 CLSID에 다음 표에서와 같이 서비스 사용 또는 사용하지 않음을 지정하는 DWORD 값을 지정하여 OLEDB_SERVICES 레지스트리 항목을 추가하면 됩니다.

|기본 서비스 사용|DWORD 값|
|------------------------------|-------------------|
|클라이언트 커서 및 풀링을 제외한 모든 서비스|0xfffffffa|
|클라이언트 커서를 제외한 모든 서비스|0xfffffffb|
|풀링 및 자동 인 리스트 먼 트를 제외한 모든 서비스|0xfffffffc|
|풀링을 제외한 모든 서비스|0xfffffffe|
|모든 서비스 (기본값)|0xffffffff|
|서비스 사용 안 함|0x00000000|
|집계가 없습니다. 모든 서비스를 사용할 수 없습니다.|OLEDB_Services 레지스트리 항목이 없습니다.|

## <a name="see-also"></a>참고 항목

[OLE DB 서비스 사용 및 사용 안 함](../../data/oledb/enabling-and-disabling-ole-db-services.md)
