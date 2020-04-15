---
title: 교체 가능한 매개 변수 사용(ATL 레지스트라)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 2474db2de384baa9113ed39aef4d3d9c9048903d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329224"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>교체 가능한 매개 변수 사용(레지스트라&#39;전처리기)

대체 가능한 매개 변수를 사용하면 레지스트라의 클라이언트가 런타임 데이터를 지정할 수 있습니다. 이를 위해 등록기관은 스크립트에서 대체 가능한 매개 변수와 관련된 값을 입력하는 대체 맵을 유지 관리합니다. 레지스트라는 런타임에 이러한 항목을 만듭니다.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>%모듈% 사용

[ATL 제어 마법사는](../atl/reference/atl-control-wizard.md) 을 사용하는 `%MODULE%`스크립트를 자동으로 생성합니다. ATL은 서버의 DLL 또는 EXE의 실제 위치에 대해 이 대체 가능한 매개 변수를 사용합니다.

## <a name="concatenating-run-time-data-with-script-data"></a>스크립트 데이터와 런타임 데이터 연결

전처리기의 또 다른 용도는 런타임 데이터를 스크립트 데이터와 연결하는 것입니다. 예를 들어 끝에 ""`, 1`문자열이 추가된 모듈에 대한 전체 경로가 포함된 항목이 필요하다고 가정합니다. 먼저 다음 확장을 정의합니다.

```
'MySampleKey' = s '%MODULE%, 1'
```

그런 다음 스크립트 호출에 나열된 스크립트 처리 방법 중 하나를 호출하기 전에 맵에 대체 메서드를 [추가합니다.](../atl/invoking-scripts.md)

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

스크립트를 구문 분석하는 동안 등록기관은 `'%MODULE%, 1'` 로 `c:\mycode\mydll.dll, 1`확장됩니다.

> [!NOTE]
> 레지스트라 스크립트에서 4K는 최대 토큰 크기입니다. 토큰은 구문에서 인식할 수 있는 요소입니다. 여기에는 전처리업체가 만들거나 확장한 토큰이 포함됩니다.

> [!NOTE]
> 런타임에 대체 값을 대체하려면 스크립트에서 호출을 [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) 또는 [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) 매크로로 제거합니다. 대신 `UpdateRegistry` [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS를](../atl/reference/catlmodule-class.md#updateregistryfromresources)호출하는 사용자 고유의 메서드로 바꾸고 _ATL_REGMAP_ENTRY 구조의 배열을 전달합니다. _ATL_REGMAP_ENTRY 배열에는 {NULL,NULL}로 설정된 항목이 하나 이상 있어야 하며 이 항목은 항상 마지막 항목이어야 합니다. 그렇지 않으면 호출될 때 `UpdateRegistryFromResource` 액세스 위반 오류가 생성됩니다.

> [!NOTE]
> 실행 자를 출력하는 프로젝트를 빌드할 때 ATL은 런타임에 생성된 경로 이름 주위에 **%MODULE%** 레지스트라 스크립트 매개 변수를 사용하여 자동으로 견적 부호를 추가합니다. 경로 이름에 따옴표를 포함하지 않으려면 대신 새 **%MODULE_RAW%** 매개 변수를 사용합니다.
>
> DLL을 출력하는 프로젝트를 빌드할 때 **ATL은 %MODULE%** 또는 **%MODULE_RAW%를** 사용하는 경우 경로 이름에 견적 부호를 추가하지 않습니다.

## <a name="see-also"></a>참고 항목

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
