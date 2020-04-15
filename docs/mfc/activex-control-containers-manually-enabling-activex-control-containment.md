---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 94ad6e8356b5dab54ae97dbdd90812039d1425c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322071"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정

응용 프로그램을 생성하기 위해 MFC 응용 프로그램 마법사를 사용할 때 ActiveX 제어 지원을 사용하도록 설정하지 않은 경우 이 지원을 수동으로 추가해야 합니다. 이 문서에서는 기존 OLE 컨테이너 응용 프로그램에 ActiveX 제어 포함을 수동으로 추가하는 프로세스에 대해 설명합니다. OLE 컨테이너에서 ActiveX 컨트롤 지원을 원하는 경우 [MFC ActiveX 컨트롤 컨테이너 만들기](../mfc/reference/creating-an-mfc-activex-control-container.md)문서를 참조하십시오.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

> [!NOTE]
> 이 문서에서는 컨테이너라는 대화 상자 기반 ActiveX 제어 컨테이너 프로젝트와 Circ라는 임베디드 컨트롤을 프로시저 및 코드의 예로 사용합니다.

ActiveX 컨트롤을 지원하려면 프로젝트 파일 중 두 개에 한 줄의 코드를 추가해야 합니다.

- 기본 대화 상자의 `InitInstance` 기능을 수정합니다(컨테이너에 있습니다.) CPP) 다음 예제와 같이 [AfxEnableControlContainer를](reference/ole-initialization.md#afxenablecontrolcontainer)호출하는 MFC 응용 프로그램 마법사에서:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- 프로젝트의 STDAFX에 다음을 추가합니다. H 헤더 파일:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

이 단계를 완료한 후 **빌드** 메뉴에서 **빌드를** 클릭하여 프로젝트를 다시 빌드합니다.

## <a name="see-also"></a>참고 항목

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
