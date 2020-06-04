---
title: 'MFC ActiveX 컨트롤: 스톡 속성 페이지 사용'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
ms.openlocfilehash: 13a0edb72657c9ffad00dcb909019bdfe4b87e11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358209"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX 컨트롤: 스톡 속성 페이지 사용

이 문서에서는 ActiveX 컨트롤에 사용할 수 있는 스톡 속성 페이지와 해당 페이지를 사용하는 방법에 대해 설명합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

ActiveX 컨트롤에서 속성 페이지 사용에 대한 자세한 내용은 다음 문서를 참조하십시오.

- [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC는 ActiveX 컨트롤에 `CLSID_CColorPropPage` `CLSID_CFontPropPage` `CLSID_CPicturePropPage`사용할 세 가지 스톡 속성 페이지를 제공합니다. 이 페이지에는 스톡 색상, 글꼴 및 그림 속성에 대한 사용자 인터페이스가 각각 표시됩니다.

이러한 속성 페이지를 컨트롤에 통합하려면 컨트롤의 속성 페이지 아이디 배열을 초기화하는 코드에 해당 의 해당 코드를 추가합니다. 다음 예제에서 이 코드는 제어 구현 파일에 있습니다( CPP) 세 가지 stock 속성 페이지와 기본 속성 페이지(이 `CMyPropPage` 예제에서 명명됨)를 모두 포함하도록 배열을 초기화합니다.

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

BEGIN_PROPPAGEIDS 매크로의 속성 페이지 수는 4입니다. 이는 ActiveX 컨트롤에서 지원하는 속성 페이지 수를 나타냅니다.

이러한 수정이 이루어진 후 프로젝트를 다시 빌드합니다. 이제 컨트롤에 글꼴, 그림 및 색상 속성에 대한 속성 페이지가 있습니다.

> [!NOTE]
> 제어 스톡 속성 페이지에 액세스할 수 없는 경우 MFC DLL(MFCxx.DLL)이 현재 운영 체제에 제대로 등록되지 않았기 때문일 수 있습니다. 일반적으로 현재 실행 중인 운영 체제와 다른 운영 체제 아래에 Visual C++를 설치하면 됩니다.

> [!TIP]
> 스톡 속성 페이지가 표시되지 않는 경우(이전 참고 참조) 명령줄에서 DLL에 대한 전체 경로 이름으로 RegSvr32.exe를 실행하여 DLL을 등록합니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)
