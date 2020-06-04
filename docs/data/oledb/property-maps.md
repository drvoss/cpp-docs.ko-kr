---
title: 속성 맵
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 79a65290c24ab016d9f81b54b9b7720d5c4ff352
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544557"
---
# <a name="property-maps"></a>속성 맵

각 공급자는 세션, 행 집합 및 선택적 명령 개체 외에 하나 이상의 속성을 지원합니다. 이러한 속성은 **OLE DB 공급자 마법사**에서 만든 헤더 파일에 저장 된 속성 맵에 정의 됩니다. 각 헤더 파일에는 그 파일에서 정의된 개체나 개체들에 대해 정의한 OLE DB 속성 그룹의 속성에 대한 맵이 있습니다. 데이터 원본 개체를 포함 하는 헤더 파일에도 [DataSource 속성](/previous-versions/windows/desktop/ms724188(v=vs.85))에 대 한 속성 맵이 포함 됩니다. [세션 속성](/previous-versions/windows/desktop/ms714221(v=vs.85))에 대 한 속성 맵을 포함 하 `Session.h`입니다. 행 집합 및 명령 개체는 *projectname*RS. h 라는 단일 헤더 파일에 있습니다. 이러한 속성은 [행 집합 속성](/previous-versions/windows/desktop/ms711252(v=vs.85)) 그룹의 멤버입니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
