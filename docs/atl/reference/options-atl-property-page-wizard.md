---
title: 옵션, ATL 속성 페이지 마법사
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: a46a55cca221293e83a72bf0c2670e2343c744b0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076203"
---
# <a name="options-atl-property-page-wizard"></a>옵션, ATL 속성 페이지 마법사

::: moniker range="vs-2019"

Visual Studio 2019 이상에서는 ATL 속성 페이지 마법사를 사용할 수 없습니다.

::: moniker-end

::: moniker range="<=vs-2017"

이 마법사 페이지를 사용하여 만드는 속성 페이지의 스레딩 모델 및 집계 수준을 정의할 수 있습니다.

- **스레딩 모델**

   속성 페이지에서 사용되는 스레딩 모델을 지정합니다.

   자세한 내용은 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md)을 참조하세요.

   |옵션|설명|
   |------------|-----------------|
   |**단일**|속성 페이지가 주 COM 스레드에서만 실행됩니다.|
   |**아파트**|모든 단일 스레드 아파트에서 속성 페이지를 만들 수 있습니다. 기본값입니다.|

- **집계**

   만드는 속성 페이지에 대한 집계 지원을 추가합니다. 자세한 내용은 [집계](../../atl/aggregation.md)를 참조하세요.

   |옵션|설명|
   |------------|-----------------|
   |**예**|집계할 수 있는 속성 페이지를 만듭니다.|
   |**아니요**|집계할 수 없는 속성 페이지를 만듭니다.|
   |**해당 항목만**|집계를 통해서만 인스턴스화할 수 있는 속성 페이지를 만듭니다.|

::: moniker-end

## <a name="see-also"></a>참고 항목

[ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)<br/>
[문자열, ATL 속성 페이지 마법사](../../atl/reference/strings-atl-property-page-wizard.md)
