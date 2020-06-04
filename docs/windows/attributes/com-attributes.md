---
title: COM 특성
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: 15225d23abb66b8aadd5f82b8429334356bdaa8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168319"
---
# <a name="com-attributes"></a>COM 특성

COM 특성(attribute)은 COM 개발 및 .NET Framework 공용 언어 런타임 개발의 다양한 영역을 지원하는 코드를 삽입합니다. 이러한 영역 범위는 사용자 지정 인터페이스 구현 및 기존 인터페이스 지원, 스톡 속성, 메서드 및 이벤트 지원에 이르기까지 다양합니다. 또한 복합 및 ActiveX 컨트롤 구현에 대한 지원 사항도 찾을 수 있습니다.

|특성|설명|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|다른 컨트롤에서 컨트롤을 집계할 수 있음을 나타냅니다.|
|[aggregates](aggregates.md)|컨트롤이 대상 클래스를 집계 함을 나타냅니다.|
|[coclass](coclass.md)|Com 인터페이스를 구현할 수 있는 COM 개체를 만듭니다.|
|[com_interface_entry](com-interface-entry-cpp.md)|인터페이스 항목을 COM 맵에 추가 합니다.|
|[implements_category](implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정 합니다.|
|[progid](progid.md)|컨트롤의 ProgID를 정의 합니다.|
|[rdx](rdx.md)|레지스트리 키를 만들거나 수정 합니다.|
|[registration_script](registration-script.md)|지정 된 등록 스크립트를 실행 합니다.|
|[requires_category](requires-category.md)|클래스에 대 한 필수 구성 요소 범주를 지정 합니다.|
|[support_error_info](support-error-info.md)|대상 개체에 대 한 오류 보고를 지원 합니다.|
|[synchronize](synchronize.md)|메서드에 대 한 액세스를 동기화 합니다.|
|[threading](threading-cpp.md)|COM 개체의 스레딩 모델을 지정 합니다.|
|[vi_progid](vi-progid.md)|컨트롤에 대 한 버전 독립 ProgID를 정의 합니다.|

## <a name="see-also"></a>참고 항목

[그룹별 특성](attributes-by-group.md)
