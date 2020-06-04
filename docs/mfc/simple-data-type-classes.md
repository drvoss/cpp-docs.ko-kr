---
title: 단순 데이터 형식 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: d4038334e35b734370a437d35519498b96c00770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365407"
---
# <a name="simple-data-type-classes"></a>단순 데이터 형식 클래스

다음 클래스는 그리기 좌표, 문자열, 시간 및 날짜 정보를 캡슐화하여 C++ 구문을 편리하게 사용할 수 있게 해줍니다. 이러한 개체는 클래스 라이브러리에서 Windows 클래스의 멤버 함수에 대한 매개 변수로 광범위하게 사용됩니다. `CSize`에 대해 `CRect` **POINT**, **SIZE**및 **RECT** 구조체에 각각 일치하므로 `CPoint`Windows SDK에서 이러한 C 언어 구조를 사용할 수 있는 모든 곳에서 이러한 C++ 클래스의 개체를 사용할 수 있습니다. 클래스는 해당 멤버 함수를 통해 유용한 인터페이스를 제공합니다. `CStringT`는 매우 유연한 동적 문자열을 제공합니다. `CTime`및 시간 `COleTimeSpan` 및 날짜 값을 나타냅니다. `COleDateTime` `CTimeSpan` 이러한 클래스에 대한 자세한 내용은 [날짜 및 시간](../atl-mfc-shared/date-and-time.md)문서를 참조하십시오.

"로`COle`시작하는 클래스는 OLE에서 제공하는 데이터 형식의 캡슐화입니다. 이러한 데이터 형식은 다른 OLE 기능이 사용되는지 여부에 관계없이 Windows 프로그램에서 사용할 수 있습니다.

[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)<br/>
문자열을 저장합니다.

[Ctime](../atl-mfc-shared/reference/ctime-class.md)<br/>
절대 시간 및 날짜 값을 저장합니다.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE 자동화 유형 **DATE에**대한 래퍼입니다. 날짜 및 시간 값을 나타냅니다.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
상대 날짜 및 시간 값을 저장합니다.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
두 `COleDateTime` 값 사이의 차이점과 같은 상대적 `COleDateTime` 값을 저장합니다.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
좌표(x, y) 쌍을 저장합니다.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
거리, 상대 위치 또는 쌍으로 이뤄진 값을 저장합니다.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
사각형 영역의 좌표를 저장합니다.

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Windows 이미지 목록의 기능을 제공합니다. 이미지 목록은 목록 컨트롤 및 트리 컨트롤과 함께 사용됩니다. 이러한 컨트롤은 또한 동일한 크기의 비트맵 집합을 저장하고 아카이브하는 데 사용할 수 있습니다.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE 자동화 유형 **VARIANT용**래퍼입니다. **VARIANTs의**데이터는 다양한 형식으로 저장할 수 있습니다.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE 자동화 유형 **통화에**대한 래퍼는 소수점 앞에 15자리, 후 4자리숫자로 고정소수점 산술 유형입니다.

> [!NOTE]
> `CRect`을 `CSize`사용하며 `CPoint` ATL 또는 MFC 응용 프로그램에서 사용할 수 있습니다. 또한 MFC `CStringT` 독립적인 `CString`클래스를 제공합니다. 공유 유틸리티 클래스에 대한 자세한 내용은 [공유 클래스](../atl-mfc-shared/atl-mfc-shared-classes.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
