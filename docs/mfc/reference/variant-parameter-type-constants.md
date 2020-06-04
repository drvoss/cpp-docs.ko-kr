---
title: 가변 매개 변수 형식 상수
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: f73c72830216679f8a91d0037d48c1e1b8e400c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372862"
---
# <a name="variant-parameter-type-constants"></a>가변 매개 변수 형식 상수

이 항목에서는 Microsoft Foundation 클래스 라이브러리의 OLE 컨트롤 클래스와 함께 사용하도록 설계된 변형 매개 변수 형식을 나타내는 새 상수를 나열합니다.

다음은 클래스 상수 목록입니다.

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>변형 데이터 상수

- VTS_COLOR RGB 색상 값을 나타내는 데 사용되는 32비트 정수입니다.

- VTS_FONT OLE 글꼴 개체의 인터페이스에 대한 `IFontDisp` 포인터입니다.

- VTS_HANDLE Windows 핸들 값입니다.

- VTS_PICTURE OLE 그림 `IPictureDisp` 개체의 인터페이스에 대한 포인터입니다.

- VTS_OPTEXCLUSIVE 라디오 단추와 같은 컨트롤 그룹에 사용되는 컨트롤에 사용되는 16비트 값입니다. 이 형식은 컨테이너에 그룹의 한 컨트롤에 TRUE 값이 있는 경우 다른 모든 컨트롤은 FALSE여야 함을 알려줍니다.

- VTS_TRISTATE 세 가지 가능한 값 중 하나(선택됨, 선택취소됨, 사용할 수 없음) 확인란을 가질 수 있는 속성에 사용되는 16비트 서명 정수입니다.

- VTS_XPOS_HIMETRIC HIMETRIC 단위의 x축을 따라 위치를 나타내는 데 사용되는 32비트 서명되지 않은 정수입니다.

- VTS_YPOS_HIMETRIC HIMETRIC 단위의 y축을 따라 위치를 나타내는 데 사용되는 32비트 서명되지 않은 정수입니다.

- VTS_XPOS_PIXELS 픽셀에서 x축을 따라 위치를 나타내는 데 사용되는 32비트 서명되지 않은 정수입니다.

- VTS_YPOS_PIXELS 32비트 서명되지 않은 정수는 y축을 따라 픽셀 단위로 위치를 나타내는 데 사용됩니다.

- VTS_XSIZE_PIXELS 32비트 서명되지 않은 정수는 화면 개체의 너비를 픽셀 단위로 나타내는 데 사용됩니다.

- VTS_YSIZE_PIXELS 32비트 서명되지 않은 정수는 화면 개체의 높이를 픽셀 단위로 나타내는 데 사용됩니다.

- VTS_XSIZE_HIMETRIC HIMETRIC 단위에서 화면 개체의 너비를 나타내는 데 사용되는 32비트 서명되지 않은 정수입니다.

- VTS_YSIZE_HIMETRIC HIMETRIC 단위에서 화면 개체의 높이를 나타내는 데 사용되는 32비트 서명되지 않은 정수입니다.

    > [!NOTE]
    >  변형 데이터 상수에 대한 포인터를 제공하는 VTS_FONT 및 VTS_PICTURE 제외한 모든 변형 형식에 대해 추가 변형 상수가 정의되었습니다. 이러한 상수는 VTS_P`constantname` 규칙을 사용하여 명명됩니다. 예를 들어 VTS_PCOLOR VTS_COLOR 상수에 대한 포인터입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
