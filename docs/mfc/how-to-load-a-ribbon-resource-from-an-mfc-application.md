---
title: '방법: MFC 애플리케이션에서 리본 리소스 로드'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 47a3b94bbcb14c6c2923524db1f6a83b687e50e8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626409"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>방법: MFC 애플리케이션에서 리본 리소스 로드

애플리케이션에서 리본 리소스를 사용하려면 애플리케이션을 수정하여 리본 리소스를 로드합니다.

### <a name="to-load-a-ribbon-resource"></a>리본 리소스를 로드하려면

1. `Ribbon Control` 클래스에서 `CMainFrame` 개체를 선언합니다.

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. `CMainFrame::OnCreate`에서 리본 컨트롤을 만들고 초기화합니다.

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>참고 항목

[리본 디자이너(MFC)](ribbon-designer-mfc.md)
