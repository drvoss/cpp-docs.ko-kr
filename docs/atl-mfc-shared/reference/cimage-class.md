---
title: C이미지 클래스
ms.date: 08/19/2019
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: a6d20e1bf12f5fe7d1e9b41d88b088ca9fad35ed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747173"
---
# <a name="cimage-class"></a>C이미지 클래스

`CImage`JPEG, GIF, BMP 및 PNG(휴대용 네트워크 그래픽) 형식으로 이미지를 로드하고 저장하는 기능을 포함하여 향상된 비트맵 지원을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CImage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C이미지::C이미지](#cimage)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C이미지::알파블렌드](#alphablend)|투명 또는 반투명 픽셀이 있는 비트맵을 표시합니다.|
|[CImage::Attach](#attach)|개체에 HBITMAP을 `CImage` 연결합니다. 비 DIB 섹션 비트맵 또는 DIB 섹션 비트맵과 함께 사용할 수 있습니다.|
|[CImage::BitBlt](#bitblt)|원본 장치 컨텍스트에서 이 현재 장치 컨텍스트로 비트맵을 복사합니다.|
|[CImage::Create](#create)|DIB 섹션 비트맵을 만들고 이전에 생성된 `CImage` 개체에 연결합니다.|
|[C이미지::만들기](#createex)|추가 매개 변수를 사용하여 DIB 섹션 비트맵을 만들고 이전에 `CImage` 생성된 개체에 연결합니다.|
|[CImage::Destroy](#destroy)|개체에서 비트맵을 `CImage` 분리하고 비트맵을 삭제합니다.|
|[C이미지::D](#detach)|개체에서 비트맵을 분리합니다. `CImage`|
|[C이미지::D로](#draw)|원본 사각형에서 비트맵을 대상 사각형으로 복사합니다. `Draw`필요한 경우 대상 사각형의 크기에 맞게 비트맵을 늘이거나 압축하고 알파 블렌딩 및 투명 색상을 처리합니다.|
|[CImage::GetBits](#getbits)|비트맵의 실제 픽셀 값에 대한 포인터를 검색합니다.|
|[CImage::GetBPP](#getbpp)|픽셀당 비트를 검색합니다.|
|[CImage::GetColorTable](#getcolortable)|색상 테이블의 다양한 항목에서 빨간색, 녹색, 파란색(RGB) 색상 값을 검색합니다.|
|[C이미지::GetDC](#getdc)|현재 비트맵이 선택된 장치 컨텍스트를 검색합니다.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|사용 가능한 이미지 형식과 해당 설명을 찾습니다.|
|[C이미지::GetHeight](#getheight)|현재 이미지의 높이를 픽셀 단위로 검색합니다.|
|[C이미지::GetImporter필터스트링](#getimporterfilterstring)|사용 가능한 이미지 형식과 해당 설명을 찾습니다.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|색상 테이블의 최대 항목 수를 검색합니다.|
|[C이미지::겟피치](#getpitch)|현재 이미지의 피치를 바이트로 검색합니다.|
|[C이미지::겟픽셀](#getpixel)|*x* 및 *y로*지정된 픽셀의 색상을 검색합니다.|
|[CImage::GetPixelAddress](#getpixeladdress)|지정된 픽셀의 주소를 검색합니다.|
|[CImage::GetTransparentColor](#gettransparentcolor)|색상 표에서 투명 색상의 위치를 검색합니다.|
|[CImage::GetWidth](#getwidth)|현재 이미지의 너비를 픽셀 단위로 검색합니다.|
|[CImage::IsDIBSection](#isdibsection)|연결된 비트맵이 DIB 섹션인지 여부를 결정합니다.|
|[CImage::IsIndexed](#isindexed)|비트맵의 색상이 인덱싱된 팔레트에 매핑되어 있음을 나타냅니다.|
|[CImage::IsNull](#isnull)|소스 비트맵이 현재 로드되었는지 를 나타냅니다.|
|[C이미지::투명성 지원](#istransparencysupported)|응용 프로그램이 투명 비트맵을 지원하는지 여부를 나타냅니다.|
|[CImage::Load](#load)|지정된 파일에서 이미지를 로드합니다.|
|[CImage::LoadFromResource](#loadfromresource)|지정된 리소스에서 이미지를 로드합니다.|
|[CImage::MaskBlt](#maskblt)|지정된 마스크 및 래스터 작업을 사용하여 소스 및 대상 비트맵의 색상 데이터를 결합합니다.|
|[CImage::PlgBlt](#plgblt)|소스 장치 컨텍스트의 사각형에서 대상 장치 컨텍스트의 평행 사변형으로 비트 블록 전송을 수행합니다.|
|[CImage::ReleaseDC](#releasedc)|[CImage::GetDC로](#getdc)검색된 장치 컨텍스트를 해제합니다.|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI+에서 사용하는 리소스를 릴리스합니다. 전역 `CImage` 개체에서 만든 리소스를 해제하려면 호출해야 합니다.|
|[CImage::Save](#save)|이미지를 지정된 유형으로 저장합니다. `Save`이미지 옵션을 지정할 수 없습니다.|
|[CImage::SetColorTable](#setcolortable)|DIB 섹션의 색상 표에 있는 항목 범위에서 빨간색, 녹색, 파란색 RGB) 색상 값을 설정합니다.|
|[CImage::SetPixel](#setpixel)|지정된 좌표에서 픽셀을 지정된 색상으로 설정합니다.|
|[CImage::SetPixelIndexed](#setpixelindexed)|지정된 좌표의 픽셀을 팔레트의 지정된 인덱스의 색상으로 설정합니다.|
|[C이미지::세트픽셀RGB](#setpixelrgb)|지정된 좌표에서 픽셀을 지정된 빨간색, 녹색, 파란색(RGB) 값으로 설정합니다.|
|[CImage::SetTransparentColor](#settransparentcolor)|투명으로 처리할 색상의 인덱스를 설정합니다. 팔레트의 색상은 하나의 색상만 투명할 수 있습니다.|
|[C이미지::스트레치블블](#stretchblt)|필요한 경우 소스 사각형에서 비트맵을 대상 사각형으로 복사하여 비트맵을 늘이거나 압축하여 대상 사각형의 크기에 맞게 늘립니다.|
|[CImage::TransparentBlt](#transparentblt)|소스 장치 컨텍스트에서 이 현재 장치 컨텍스트에 투명한 색상으로 비트맵을 복사합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C이미지::연산자 HBITMAP](#operator_hbitmap)|개체에 연결된 Windows `CImage` 핸들을 반환합니다.|

## <a name="remarks"></a>설명

`CImage`장치 독립적 인 비트 맵 (DIB) 섹션 또는하지 않는 비트 맵을 합니다. 그러나 DIB 섹션만 사용하여 [만들기](#create) 또는 [CImage::Load를](#load) 사용할 수 있습니다. [연결](#attach)을 사용 하 여 `CImage` `CImage` 개체에 비 DIB 섹션 비트 맵을 연결할 수 있습니다 하지만 다음 메서드를 사용할 수 없습니다., DIB 섹션 비트 맵만 지원 하는:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

연결된 비트맵이 DIB 섹션인지 확인하려면 [IsDibSection](#isdibsection)을 호출하십시오.

> [!NOTE]
> Visual Studio .NET 2003에서 이 클래스는 생성된 `CImage` 개체 수를 유지합니다. 개수가 0으로 바을 `GdiplusShutdown` 때마다 함수는 자동으로 호출되어 GDI+에서 사용하는 리소스를 해제합니다. 이렇게 하면 DLL에 의해 직접 또는 간접적으로 생성된 모든 `CImage` `GdiplusShutdown` 개체가 항상 `DllMain`제대로 소멸되고 에서 호출되지 않습니다.

> [!NOTE]
> DLL에서 전역 `CImage` 개체를 사용하는 것은 권장되지 않습니다. DLL에서 전역 `CImage` 개체를 사용해야 하는 경우 [CImage::ReleaseGDIPlus를](#releasegdiplus) 호출하여 GDI+에서 사용하는 리소스를 명시적으로 해제합니다.

`CImage`새 [CDC로](../../mfc/reference/cdc-class.md)선택할 수 없습니다. `CImage`이미지에 대한 자체 HDC를 만듭니다. HBITMAP은 한 번에 하나의 HDC로만 선택할 수 있으므로 HBITMAP과 연결된 HBITMAP은 다른 HDC로 선택할 `CImage` 수 없습니다. CDC가 필요한 경우 에서 HDC를 `CImage` 검색하여 [CDC::FromHandle에](../../mfc/reference/cdc-class.md#fromhandle)제공합니다.

## <a name="example"></a>예제

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

MFC `CImage` 프로젝트에서 사용할 때 프로젝트에서 어떤 멤버 함수가 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체에 대한 포인터를 예상할지 확인합니다. `CImage` [CMenu::AppendMenu와](../../mfc/reference/cmenu-class.md#appendmenu)같은 함수와 함께 사용하려면 [CBitmap::FromHandle을](../../mfc/reference/cbitmap-class.md#fromhandle)사용하여 `CImage` HBITMAP을 전달하고 반환된 `CBitmap*`을 사용합니다.

## <a name="example"></a>예제

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

을 `CImage`통해 DIB 섹션의 실제 비트에 액세스할 수 있습니다. 이전에 Win32 HBITMAP 또는 DIB 섹션을 사용했던 모든 곳에서 `CImage` 개체를 사용할 수 있습니다.

MFC `CImage` 또는 ATL에서 사용할 수 있습니다.

> [!NOTE]
> 을 사용하여 `CImage`프로젝트를 만들 때 `CString` *atlimage.h를*포함하기 전에 정의해야 합니다. 프로젝트에서 MFC 없이 ATL을 사용하는 경우 *atlimage.h를* 포함하기 전에 *atlstr.h를*포함하십시오. 프로젝트에서 MFC를 사용하는 경우(또는 MFC 지원이 있는 ATL 프로젝트인 경우) *atlimage.h를*포함하기 전에 *afxstr.h를* 포함합니다.<br/>
> <br/>
> 마찬가지로 *atlimpl.cpp를*포함하기 전에 *atlimage.h를* 포함해야 합니다. 이를 쉽게 수행하려면 *pch.h(Visual* Studio 2017 및 이전)에 *atlimage.h를* 포함하십시오.*stdafx.h*

## <a name="requirements"></a>요구 사항

**헤더:** atlimage.h

## <a name="cimagealphablend"></a><a name="alphablend"></a>C이미지::알파블렌드

투명 또는 반투명 픽셀이 있는 비트맵을 표시합니다.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트를 처리합니다.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 y 좌표입니다.

*bSrcAlpha*<br/>
전체 소스 비트맵에서 사용할 알파 투명도 값입니다. 기본 0xff(255)는 이미지가 불투명하고 픽셀당 알파 값만 사용한다고 가정합니다.

*bBlendOp*<br/>
소스 및 대상 비트맵에 대한 알파 혼합 함수, 전체 소스 비트맵에 적용할 전역 알파 값 및 소스 비트맵에 대한 형식 정보입니다. 소스 및 대상 블렌드 함수는 현재 AC_SRC_OVER 제한됩니다.

*pointDest*<br/>
논리적 단위로 대상 사각형의 왼쪽 위 모서리를 식별하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조에 대한 참조입니다.

*nDestWidth*<br/>
대상 사각형의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리적 단위로 높이입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 y 좌표입니다.

*nSrcWidth*<br/>
소스 사각형의 논리적 단위로 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리적 단위로 높이입니다.

*rectDest*<br/>
대상을 식별하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*rectSrc*<br/>
소스를 식별하는 `RECT` 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

알파 블렌드 비트맵은 픽셀단위로 색상 혼합을 지원합니다.

*bBlendOp가* AC_SRC_OVER 기본값으로 설정되면 소스 비트맵은 소스 픽셀의 알파 값을 기반으로 대상 비트맵 위에 배치됩니다.

## <a name="cimageattach"></a><a name="attach"></a>C이미지::첨부

*개체에 hBitmap을* 연결합니다. `CImage`

```cpp
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
HBITMAP에 대한 핸들입니다.

*eOrientation*<br/>
비트맵의 방향을 지정합니다. 다음 중 하나일 수 있습니다.

- DIBOR_DEFAULT 비트맵의 방향은 운영 체제에 의해 결정됩니다.

- DIBOR_BOTTOMUP 비트맵의 줄은 역순으로 표시됩니다. 이렇게 하면 [CImage::GetBits](#getbits) 비트 맵 버퍼의 끝 근처에 포인터를 반환 하 고 [CImage:GetPitch](#getpitch) 음수를 반환 합니다.

- DIBOR_TOPDOWN 비트맵의 줄은 맨 아래에서 아래로 정렬됩니다. 이렇게 하면 [CImage::GetBits](#getbits) 비트 맵 버퍼의 첫 번째 바이트에 대 한 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 양수를 반환 합니다.

### <a name="remarks"></a>설명

비트맵은 비DIB 섹션 비트맵 또는 DIB 섹션 비트맵일 수 있습니다. DIB 섹션 비트맵에서만 사용할 수 있는 메서드 목록은 [IsDIBSection을](#isdibsection) 참조하십시오.

## <a name="cimagebitblt"></a><a name="bitblt"></a>C이미지::비트블

원본 장치 컨텍스트에서 이 현재 장치 컨텍스트로 비트맵을 복사합니다.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 HDC.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 y 좌표입니다.

*dwROP*<br/>
수행될 래스터 조작. 래스터 작업 코드는 소스, 대상 및 패턴(현재 선택된 브러시에 의해 정의된 대로)의 비트를 결합하여 대상을 형성하는 방법을 정확하게 정의합니다. 다른 래스터 작업 코드 및 설명 목록은 Windows SDK의 [BitBlt를](/windows/win32/api/wingdi/nf-wingdi-bitblt) 참조하십시오.

*pointDest*<br/>
대상 사각형의 왼쪽 위 모서리를 나타내는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조입니다.

*nDestWidth*<br/>
대상 사각형의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리적 단위로 높이입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 y 좌표입니다.

*rectDest*<br/>
대상 사각형을 나타내는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조입니다.

*pointSrc*<br/>
소스 `POINT` 사각형의 왼쪽 위 모서리를 나타내는 구조입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [BitBlt를](/windows/win32/api/wingdi/nf-wingdi-bitblt) 참조하십시오.

## <a name="cimagecimage"></a><a name="cimage"></a>C이미지::C이미지

`CImage` 개체를 생성합니다.

```
CImage() throw();
```

### <a name="remarks"></a>설명

개체를 생성한 후에는 [만들기](#create), [로드](#load), [LoadFromResource](#loadfromresource)또는 [연결하여](#attach) 개체에 비트맵을 첨부합니다.

**참고 사항** Visual Studio에서 이 클래스는 생성된 `CImage` 개체 수를 유지합니다. 개수가 0으로 바을 `GdiplusShutdown` 때마다 함수는 자동으로 호출되어 GDI+에서 사용하는 리소스를 해제합니다. 이렇게 하면 DLL에 의해 직접 또는 간접적으로 생성된 모든 `CImage` `GdiplusShutdown` 개체가 항상 제대로 소멸되고 DllMain에서 호출되지 않습니다.

DLL에서 전역 `CImage` 개체를 사용하는 것은 권장되지 않습니다. DLL에서 전역 `CImage` 개체를 사용해야 하는 경우 [CImage::ReleaseGDIPlus를](#releasegdiplus) 호출하여 GDI+에서 사용하는 리소스를 명시적으로 해제합니다.

## <a name="cimagecreate"></a><a name="create"></a>C이미지::만들기

비트맵을 `CImage` 만들고 이전에 생성된 `CImage` 개체에 연결합니다.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
비트맵의 `CImage` 너비(픽셀)입니다.

*nHeight*<br/>
비트맵의 `CImage` 높이(픽셀)입니다. *nHeight가* 양수이면 비트맵은 상향식 DIB이고 원점은 왼쪽 아래 모서리입니다. *nHeight가* 음수이면 비트맵은 하향식 DIB이고 원점은 왼쪽 위 모서리입니다.

*nBPP*<br/>
비트맵의 픽셀당 비트 수입니다. 일반적으로 4, 8, 16, 24 또는 32. 흑백 비트맵 또는 마스크의 경우 1일 수 있습니다.

*dwFlags*<br/>
비트맵 개체에 알파 채널이 있는지 지정합니다. 다음 값 중 0 이상을 조합할 수 있습니다.

- *만들기알파채널* *nBPP가* 32이고 *eCompression가* BI_RGB 경우에만 사용할 수 있습니다. 지정된 경우 생성된 이미지에는 각 픽셀의 4바이트에 저장된 각 픽셀에 대한 알파(투명도) 값이 있습니다(비알파 32비트 이미지에는 사용되지 않음). 이 알파 채널은 [CImage::AlphaBlend](#alphablend)를 호출할 때 자동으로 사용됩니다.

> [!NOTE]
> [CImage::Draw를](#draw)호출할 때 알파 채널이 있는 이미지는 자동으로 대상에 알파혼합됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="cimagecreateex"></a><a name="createex"></a>C이미지::만들기

비트맵을 `CImage` 만들고 이전에 생성된 `CImage` 개체에 연결합니다.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
비트맵의 `CImage` 너비(픽셀)입니다.

*nHeight*<br/>
비트맵의 `CImage` 높이(픽셀)입니다. *nHeight가* 양수이면 비트맵은 상향식 DIB이고 원점은 왼쪽 아래 모서리입니다. *nHeight가* 음수이면 비트맵은 하향식 DIB이고 원점은 왼쪽 위 모서리입니다.

*nBPP*<br/>
비트맵의 픽셀당 비트 수입니다. 일반적으로 4, 8, 16, 24 또는 32. 흑백 비트맵 또는 마스크의 경우 1일 수 있습니다.

*eCompression*<br/>
압축된 상향식 비트맵에 대한 압축 유형을 지정합니다(하향식 DIF는 압축할 수 없음). 다음 값 중 하나를 사용할 수 있습니다.

- BI_RGB 형식이 압축되지 않았습니다. 호출할 `CImage::CreateEx` 때 이 값을 지정하는 것은 호출과 `CImage::Create`동일합니다.

- BI_BITFIELDS 형식은 압축되지 않고 색상 표는 각 픽셀의 빨간색, 녹색 및 파란색 구성 요소를 각각 지정하는 세 개의 DWORD 색상 마스크로 구성됩니다. 이 방법은 16bpp 및 32bpp 비트맵과 함께 사용할 때 유효합니다.

*pdwBitfields*<br/>
*eCompression가* BI_BITFIELDS 설정된 경우에만 사용되며, 그렇지 않으면 NULL이어야 합니다. 색상의 빨간색, 녹색 및 파란색 구성 요소에 각각 사용되는 각 픽셀의 비트를 지정하는 세 개의 DWORD 비트 마스크 배열에 대한 포인터입니다. 비트 필드에 대한 제한에 대한 자세한 내용은 Windows SDK의 [BITMAPINFOHEADER를](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) 참조하십시오.

*dwFlags*<br/>
비트맵 개체에 알파 채널이 있는지 지정합니다. 다음 값 중 0 이상을 조합할 수 있습니다.

- *만들기알파채널* *nBPP가* 32이고 *eCompression가* BI_RGB 경우에만 사용할 수 있습니다. 지정된 경우 생성된 이미지에는 각 픽셀의 4바이트에 저장된 각 픽셀에 대한 알파(투명도) 값이 있습니다(비알파 32비트 이미지에는 사용되지 않음). 이 알파 채널은 [CImage::AlphaBlend](#alphablend)를 호출할 때 자동으로 사용됩니다.

   > [!NOTE]
   > [CImage::Draw를](#draw)호출할 때 알파 채널이 있는 이미지는 자동으로 대상에 알파혼합됩니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE. 그렇지 않으면 거짓.

### <a name="example"></a>예제

다음 예제에서는 16비트를 사용하여 각 픽셀을 인코딩하는 100x100 픽셀 비트맵을 만듭니다. 지정된 16비트 픽셀에서 비트 0-3은 빨간색 구성 요소를 인코딩하고 비트 4-7은 녹색을 인코딩하고 비트 8-11은 파란색을 인코딩합니다. 나머지 4비트는 사용되지 않습니다.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a>C이미지::D에스트로이

개체에서 비트맵을 `CImage` 분리하고 비트맵을 삭제합니다.

```cpp
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a>C이미지::D

개체에서 비트맵을 분리합니다. `CImage`

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Return Value

비트맵에 대한 핸들이 분리되어 있거나 비트맵이 연결되어 있지 않은 경우 NULL입니다.

## <a name="cimagedraw"></a><a name="draw"></a>C이미지::D로

원본 장치 컨텍스트에서 현재 장치 컨텍스트로 비트맵을 복사합니다.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트에 대한 핸들입니다.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 y 좌표입니다.

*nDestWidth*<br/>
대상 사각형의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리적 단위로 높이입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*ySrc*<br/>
논리 단위로 소스 사각형의 왼쪽 위 모서리의 y 좌표입니다.

*nSrcWidth*<br/>
소스 사각형의 논리적 단위로 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리적 단위로 높이입니다.

*rectDest*<br/>
대상을 식별하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*rectSrc*<br/>
소스를 식별하는 `RECT` 구조에 대한 참조입니다.

*pointDest*<br/>
논리적 단위로 대상 사각형의 왼쪽 위 모서리를 식별하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Draw`이미지에 투명한 색상 또는 알파 채널이 포함되어 있지 않는 한 [StretchBlt와](#stretchblt)동일한 작업을 수행합니다. 이 경우 `Draw` 필요에 따라 [투명Blt](#transparentblt) 또는 [AlphaBlend와](#alphablend) 동일한 작업을 수행합니다.

소스 사각형을 `Draw` 지정하지 않는 버전의 경우 전체 소스 이미지가 기본값입니다. 대상 사각형의 `Draw` 크기를 지정하지 않는 버전의 경우 소스 이미지의 크기가 기본값이며 늘어나거나 축소되지 않습니다.

## <a name="cimagegetbits"></a><a name="getbits"></a>C이미지::겟비트

비트맵에서 지정된 픽셀의 실제 비트 값에 대한 포인터를 검색합니다.

```cpp
void* GetBits() throw();
```

### <a name="return-value"></a>Return Value

비트맵 버퍼에 대한 포인터입니다. 비트맵이 상향식 DIB인 경우 포인터는 버퍼의 끝 근처에 가리킵니다. 비트맵이 하향식 DIB인 경우 포인터는 버퍼의 첫 번째 바이트를 가리킵니다.

### <a name="remarks"></a>설명

이 포인터를 사용하여 [GetPitch에서](#getpitch)반환하는 값과 함께 이미지에서 개별 픽셀을 찾아 변경할 수 있습니다.

> [!NOTE]
> 이 메서드는 DIB 섹션 비트맵만 지원합니다. 따라서 DIB 섹션의 픽셀과 `CImage` 동일한 방식으로 개체의 픽셀에 액세스합니다. 반환된 포인터는 위치(0, 0)의 픽셀을 가리킵니다.

## <a name="cimagegetbpp"></a><a name="getbpp"></a>C이미지::GetBPP

픽셀당 비트 값을 검색합니다.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Return Value

픽셀당 비트 수입니다.

### <a name="remarks"></a>설명

이 값은 각 픽셀을 정의하는 비트 수와 비트맵의 최대 색상 수를 결정합니다.

픽셀당 비트는 일반적으로 1, 4, 8, 16, 24 또는 32입니다. 이 `biBitCount` 값에 대한 자세한 내용은 Windows SDK의 [BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) 멤버를 참조하십시오.

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a>C이미지::겟컬러테이블

DIB 섹션의 팔레트에 있는 항목 범위에서 빨간색, 녹색, 파란색(RGB) 색상 값을 검색합니다.

```cpp
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>매개 변수

*iFirstColor*<br/>
검색할 첫 번째 항목의 색상 표 인덱스입니다.

*nColors*<br/>
검색할 색상 테이블 항목의 수입니다.

*prgbColors*<br/>
색상 테이블 항목을 검색하는 [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) 구조의 배열에 대한 포인터입니다.

## <a name="cimagegetdc"></a><a name="getdc"></a>C이미지::GetDC

현재 이미지가 선택되어 있는 장치 컨텍스트를 검색합니다.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Return Value

디바이스 컨텍스트에 대한 핸들입니다.

### <a name="remarks"></a>설명

에 대한 `GetDC`각 호출에 대해 [ReleaseDC에](#releasedc)대한 후속 호출이 있어야 합니다.

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>C이미지::GetExporter필터스트링

이미지를 저장하는 데 사용할 수 있는 이미지 형식을 찾습니다.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>매개 변수

*strExporters*<br/>
`CSimpleString` 개체에 대한 참조입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.

*aguidFileTypes*<br/>
문자열의 파일 형식 중 하나에 해당하는 각 요소가 있는 GUID의 배열입니다. *아래 pszAllFilesDescription의* 예에서 *aguidFileType*[0]은 GUID_NULL 나머지 배열 값은 현재 운영 체제에서 지원하는 이미지 파일 형식입니다.

> [!NOTE]
> 상수의 전체 목록은 Windows SDK의 **이미지 파일 형식 상수를** 참조하십시오.

*pszAllFilesDescription*<br/>
이 매개 변수가 NULL이 아닌 경우 필터 문자열은 목록의 시작 부분에 하나의 추가 필터를 갖습니다. 이 필터는 설명에 대한 *pszAllFilesDescription의* 현재 값을 가지며 목록의 다른 내보내기에서 지원하는 모든 확장자의 파일을 허용합니다.

다음은 그 예입니다.

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
목록에서 제외할 파일 형식을 지정하는 비트 플래그 집합입니다. 허용 가능한 플래그는 다음과 같습니다.

- `excludeGIF`= 0x01 GIF 파일을 제외합니다.

- `excludeBMP`= 0x02 BMP(Windows 비트맵) 파일 제외.

- `excludeEMF`= 0x04 EMF(향상된 메타파일) 파일을 제외합니다.

- `excludeWMF`= 0x08 WMF (윈도우 메타 파일) 파일을 제외합니다.

- `excludeJPEG`= 0x10 JPEG 파일을 제외합니다.

- `excludePNG`= 0x20 PNG 파일 제외.

- `excludeTIFF`= 0x40 TIFF 파일을 제외합니다.

- `excludeIcon`= 0x80 ICO(Windows 아이콘) 파일 제외.

- `excludeOther`= 0x80000000 위에 나열되지 않은 다른 파일 형식은 제외됩니다.

- `excludeDefaultLoad`= 0 로드의 경우 모든 파일 형식이 기본적으로 포함됩니다.

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`저장을 위해 이러한 파일은 일반적으로 특별한 요구 사항이 있기 때문에 기본적으로 제외됩니다.

*chSeparator*<br/>
이미지 형식 간에 사용되는 구분 기호입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

결과 형식 문자열을 MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) 개체에 전달하여 파일 저장 대화 상자에서 사용 가능한 이미지 형식의 파일 확장을 노출할 수 있습니다.

매개 변수 *strExporter* 형식은 다음과 있습니다.

파일 설명0 \*&#124;.ext0&#124;\*파일 설명1&#124;.ext1&#124;... 파일 *n* 설명 \*n&#124;.ext *n*&#124;&#124;

여기서 '&#124;'은 에서 지정한 `chSeparator`구분 기호 문자입니다. 다음은 그 예입니다.

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

이 문자열을 MFC `CFileDialog` 개체에 전달하는 경우 기본 구분 기호 '&#124;'을 사용합니다. 이 문자열을 공통 파일 저장 대화 상자에 전달하는 경우 null 구분 기호 '\0'을 사용합니다.

## <a name="cimagegetheight"></a><a name="getheight"></a>C이미지::GetHeight

이미지의 높이를 픽셀 단위로 검색합니다.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Return Value

이미지의 높이(픽셀 단위)입니다.

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>C이미지::GetImporter필터스트링

이미지 로드에 사용할 수 있는 이미지 형식을 찾습니다.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>매개 변수

*strImporters*<br/>
`CSimpleString` 개체에 대한 참조입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.

*aguidFileTypes*<br/>
문자열의 파일 형식 중 하나에 해당하는 각 요소가 있는 GUID의 배열입니다. *아래 pszAllFilesDescription의* 예에서 *aguidFileType*[0]은 GUID_NULL 나머지 배열 값은 현재 운영 체제에서 지원하는 이미지 파일 형식입니다.

> [!NOTE]
> 상수의 전체 목록은 Windows SDK의 **이미지 파일 형식 상수를** 참조하십시오.

*pszAllFilesDescription*<br/>
이 매개 변수가 NULL이 아닌 경우 필터 문자열은 목록의 시작 부분에 하나의 추가 필터를 갖습니다. 이 필터는 설명에 대한 *pszAllFilesDescription의* 현재 값을 가지며 목록의 다른 내보내기에서 지원하는 모든 확장자의 파일을 허용합니다.

다음은 그 예입니다.

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
목록에서 제외할 파일 형식을 지정하는 비트 플래그 집합입니다. 허용 가능한 플래그는 다음과 같습니다.

- `excludeGIF`= 0x01 GIF 파일을 제외합니다.

- `excludeBMP`= 0x02 BMP(Windows 비트맵) 파일 제외.

- `excludeEMF`= 0x04 EMF(향상된 메타파일) 파일을 제외합니다.

- `excludeWMF`= 0x08 WMF (윈도우 메타 파일) 파일을 제외합니다.

- `excludeJPEG`= 0x10 JPEG 파일을 제외합니다.

- `excludePNG`= 0x20 PNG 파일 제외.

- `excludeTIFF`= 0x40 TIFF 파일을 제외합니다.

- `excludeIcon`= 0x80 ICO(Windows 아이콘) 파일 제외.

- `excludeOther`= 0x80000000 위에 나열되지 않은 다른 파일 형식은 제외됩니다.

- `excludeDefaultLoad`= 0 로드의 경우 모든 파일 형식이 기본적으로 포함됩니다.

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`저장을 위해 이러한 파일은 일반적으로 특별한 요구 사항이 있기 때문에 기본적으로 제외됩니다.

*chSeparator*<br/>
이미지 형식 간에 사용되는 구분 기호입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.

### <a name="remarks"></a>설명

결과 형식 문자열을 MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) 개체에 전달하여 **파일 열기** 대화 상자에서 사용 가능한 이미지 형식의 파일 확장을 노출할 수 있습니다.

매개 변수 *strImporter형식은* 다음과 같은 형식을 가지고 있습니다.

파일 설명0 \*&#124;.ext0&#124;\*파일 설명1&#124;.ext1&#124;... 파일 *n* 설명 \*n&#124;.ext *n*&#124;&#124;

여기서 '&#124;'은 *chsparator가*지정한 구분 기호 문자입니다. 다음은 그 예입니다.

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

이 문자열을 MFC `CFileDialog` 개체에 전달하는 경우 기본 구분 기호 '&#124;'을 사용합니다. 이 문자열을 공통 **파일 열기** 대화 상자에 전달하는 경우 null 구분 기호 '\0'을 사용합니다.

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>C이미지::겟맥스컬러테이블항목

색상 테이블의 최대 항목 수를 검색합니다.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Return Value

색상 테이블의 항목 수입니다.

### <a name="remarks"></a>설명

이 메서드는 DIB 섹션 비트맵만 지원합니다.

## <a name="cimagegetpitch"></a><a name="getpitch"></a>C이미지::겟피치

이미지의 피치를 검색합니다.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Return Value

이미지의 피치입니다. 반환 값이 음수이면 비트맵은 상향식 DIB이고 원점은 왼쪽 아래 모서리입니다. 반환 값이 양수이면 비트맵은 하향식 DIB이고 원점은 왼쪽 위 모서리입니다.

### <a name="remarks"></a>설명

피치는 한 비트맵 선의 시작과 다음 비트맵 선의 시작을 나타내는 두 메모리 주소 사이의 거리(바이트)입니다. 피치는 바이트 단위로 측정되므로 이미지의 피치를 사용하여 픽셀 형식을 결정하는 데 도움이 됩니다. 피치에는 비트맵에 예약된 추가 메모리도 포함될 수 있습니다.

[GetBits](#getbits)와 함께 `GetPitch`을 사용하여 이미지의 개별 픽셀을 찾습니다.

> [!NOTE]
> 이 메서드는 DIB 섹션 비트맵만 지원합니다.

## <a name="cimagegetpixel"></a><a name="getpixel"></a>C이미지::겟픽셀

*x* 및 *y로*지정된 위치에서 픽셀의 색상을 검색합니다.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
픽셀의 x 좌표입니다.

*Y*<br/>
픽셀의 y 좌표입니다.

### <a name="return-value"></a>Return Value

픽셀의 빨간색, 녹색, 파란색(RGB) 값입니다. 픽셀이 현재 클리핑 영역 외부에 있으면 반환 값이 CLR_INVALID.

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a>C이미지::겟픽셀주소

픽셀의 정확한 주소를 검색합니다.

```cpp
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
픽셀의 x 좌표입니다.

*Y*<br/>
픽셀의 y 좌표입니다.

### <a name="remarks"></a>설명

주소는 픽셀의 좌표, 비트맵의 피치 및 픽셀당 비트에 따라 결정됩니다.

픽셀당 8비트 미만의 형식의 경우 이 메서드는 픽셀을 포함하는 바이트의 주소를 반환합니다. 예를 들어 이미지 형식에 픽셀당 4비트가 있는 경우 바이트에서 첫 번째 픽셀의 주소를 `GetPixelAddress` 반환하고 바이트당 2픽셀씩 계산해야 합니다.

> [!NOTE]
> 이 메서드는 DIB 섹션 비트맵만 지원합니다.

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>C이미지::GetTransparentColor

색상 팔레트에서 투명 색상의 인덱싱된 위치를 검색합니다.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Return Value

투명 색상의 인덱스입니다.

## <a name="cimagegetwidth"></a><a name="getwidth"></a>C이미지::GetWidth

이미지의 너비를 픽셀 단위로 검색합니다.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Return Value

비트맵의 너비(픽셀)입니다.

## <a name="cimageisdibsection"></a><a name="isdibsection"></a>C이미지::IsDIBsection

연결된 비트맵이 DIB 섹션인지 여부를 결정합니다.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Return Value

연결된 비트맵이 DIB 섹션인 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

비트맵이 DIB 섹션이 아닌 경우 DIB `CImage` 섹션 비트맵만 지원하는 다음 방법을 사용할 수 없습니다.

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a>C이미지::인덱싱

비트맵의 픽셀이 색상 팔레트에 매핑되는지 여부를 결정합니다.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Return Value

TRUE 인덱싱된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 비트맵이 8비트(256색) 미만인 경우에만 TRUE를 반환합니다.

> [!NOTE]
> 이 메서드는 DIB 섹션 비트맵만 지원합니다.

## <a name="cimageisnull"></a><a name="isnull"></a>C이미지::이스널

비트맵이 현재 로드되었는지 여부를 결정합니다.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>설명

이 메서드는 비트맵이 현재 로드되지 않은 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a>C이미지::투명성 지원

응용 프로그램이 투명 비트맵을 지원하는지 여부를 나타냅니다.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Return Value

현재 플랫폼이 투명성을 지원하는 경우 비영. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

반환 값이 0이 아닌 경우 투명도가 지원되는 경우 [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt)또는 [Draw에](#draw) 대한 호출은 투명한 색상을 처리합니다.

## <a name="cimageload"></a><a name="load"></a>C이미지::로드

이미지를 로드합니다.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>매개 변수

*pszFileName*<br/>
로드할 이미지 파일의 이름이 포함된 문자열에 대한 포인터입니다.

*pStream*<br/>
로드할 이미지 파일의 이름이 포함된 스트림에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

*pszFileName* 또는 *pStream에*의해 지정된 이미지를 로드합니다.

유효한 이미지 유형은 BMP, GIF, JPEG, PNG 및 TIFF입니다.

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a>C이미지::로드From리소스

BITMAP 리소스에서 이미지를 로드합니다.

```cpp
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
로드할 이미지가 포함된 모듈의 인스턴스를 처리합니다.

*pszResourceName*<br/>
로드할 이미지를 포함하는 리소스의 이름을 포함하는 문자열에 대한 포인터입니다.

*nIDResource*<br/>
로드할 리소스의 ID입니다.

### <a name="remarks"></a>설명

리소스는 BITMAP 형식이어야 합니다.

## <a name="cimagemaskblt"></a><a name="maskblt"></a>C이미지::마스크블랫

지정된 마스크 및 래스터 작업을 사용하여 소스 및 대상 비트맵의 색상 데이터를 결합합니다.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
실행 할 수 있는 리소스가 포함된 모듈의 핸들입니다.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 y 좌표입니다.

*nDestWidth*<br/>
대상 사각형 및 소스 비트맵의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형 및 소스 비트맵의 논리적 단위로 높이입니다.

*xSrc*<br/>
소스 비트맵의 왼쪽 위 모서리의 논리적 x 좌표입니다.

*ySrc*<br/>
소스 비트맵의 왼쪽 위 모서리의 논리적 y 좌표입니다.

*hbmMask*<br/>
원본 장치 컨텍스트의 색상 비트맵과 결합된 흑백 마스크 비트맵을 처리합니다.

*xMask*<br/>
*hbmMask* 매개 변수에 의해 지정된 마스크 비트맵의 수평 픽셀 오프셋입니다.

*yMask*<br/>
*hbmMask* 매개 변수에 의해 지정된 마스크 비트맵의 수직 픽셀 오프셋입니다.

*dwROP*<br/>
메서드가 소스 및 대상 데이터의 조합을 제어하는 데 사용하는 전경 및 백그라운드 래스터 작업 코드를 모두 지정합니다. 배경 래스터 작업 코드는 이 값의 고차 단어의 고차 바이트로 저장됩니다. 전경 래스터 동작 코드는 이 값의 고차 단어의 저차 바이트로 저장됩니다. 이 값의 낮은 차수 단어는 무시되며 0이어야 합니다. 이 메서드의 컨텍스트에서 전경 및 배경에 대한 `MaskBlt` 설명은 Windows SDK를 참조하십시오. 일반적인 래스터 작업 코드 목록은 `BitBlt` Windows SDK를 참조하십시오.

*rectDest*<br/>
대상을 식별하는 `RECT` 구조에 대한 참조입니다.

*pointSrc*<br/>
소스 `POINT` 사각형의 왼쪽 위 모서리를 나타내는 구조입니다.

*pointMask*<br/>
마스크 `POINT` 비트맵의 왼쪽 위 모서리를 나타내는 구조입니다.

*pointDest*<br/>
논리적 단위로 `POINT` 대상 사각형의 왼쪽 위 모서리를 식별하는 구조체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows NT, 버전 4.0 이상에만 적용됩니다.

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>C이미지::연산자 HBITMAP

이 연산자를 사용하여 개체의 연결된 `CImage` Windows GDI 핸들을 가져옵니다. 이 연산자는 HBITMAP 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

## <a name="cimageplgblt"></a><a name="plgblt"></a>C이미지::PlgBlt

소스 장치 컨텍스트의 사각형에서 대상 장치 컨텍스트의 평행 사변형으로 비트 블록 전송을 수행합니다.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트에 대한 핸들입니다.

*pPoints*<br/>
대상 평행 사변형의 세 모서리를 식별하는 논리 공간에서 세 점의 배열에 대한 포인터입니다. 소스 사각형의 왼쪽 위 모서리는 이 배열의 첫 번째 점, 이 배열의 두 번째 지점으로 오른쪽 위 모서리, 왼쪽 아래 모서리를 세 번째 점으로 매핑합니다. 원본 사각형의 오른쪽 아래 모서리는 평행 사변형의 암시적 네 번째 점에 매핑됩니다.

*hbmMask*<br/>
소스 사각형의 색상을 마스킹하는 데 사용되는 선택적 흑백 비트맵에 대한 핸들입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*ySrc*<br/>
논리 단위로 소스 사각형의 왼쪽 위 모서리의 y 좌표입니다.

*nSrcWidth*<br/>
소스 사각형의 논리적 단위로 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리적 단위로 높이입니다.

*xMask*<br/>
흑백 비트맵의 왼쪽 위 모서리의 x 좌표입니다.

*yMask*<br/>
흑백 비트맵의 왼쪽 위 모서리의 y 좌표입니다.

*rectSrc*<br/>
소스 사각형의 좌표를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pointMask*<br/>
마스크 비트맵의 왼쪽 위 모서리를 나타내는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조입니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

*hbmMask가* 유효한 흑백 비트맵을 `PlgBit` 식별하는 경우 이 비트맵을 사용하여 소스 사각형에서 색상 데이터의 비트를 마스킹합니다.

이 메서드는 Windows NT, 버전 4.0 이상에만 적용됩니다. 자세한 내용은 Windows SDK의 [PlgBlt를](/windows/win32/api/wingdi/nf-wingdi-plgblt) 참조하십시오.

## <a name="cimagereleasedc"></a><a name="releasedc"></a>C이미지::릴리스DC

장치 컨텍스트를 해제합니다.

```cpp
void ReleaseDC() const throw();
```

### <a name="remarks"></a>설명

한 번에 하나의 비트맵만 장치 컨텍스트로 선택할 수 `ReleaseDC` 있으므로 [GetDC](#getdc)에 대한 각 호출을 호출해야 합니다.

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a>C이미지::릴리즈지디플러스

GDI+에서 사용하는 리소스를 릴리스합니다.

```cpp
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>설명

전역 `CImage` 개체에서 할당된 리소스를 확보하려면 이 메서드를 호출해야 합니다. [C이미지::C이미지](#cimage)를 참조하십시오.

## <a name="cimagesave"></a><a name="save"></a>C이미지::저장

디스크의 지정된 스트림 또는 파일에 이미지를 저장합니다.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
파일 이미지 데이터를 포함하는 COM IStream 개체에 대한 포인터입니다.

*pszFileName*<br/>
이미지의 파일 이름에 대한 포인터입니다.

*guidFileType*<br/>
이미지를 저장할 파일 형식입니다. 다음 중 하나일 수 있습니다.

- `ImageFormatBMP`압축되지 않은 비트맵 이미지입니다.

- `ImageFormatPNG`PNG(휴대용 네트워크 그래픽) 압축 이미지입니다.

- `ImageFormatJPEG`JPEG 압축 이미지입니다.

- `ImageFormatGIF`GIF 압축 이미지입니다.

> [!NOTE]
> 상수의 전체 목록은 Windows SDK의 **이미지 파일 형식 상수를** 참조하십시오.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

지정된 이름과 유형을 사용하여 이미지를 저장하려면 이 함수를 호출합니다. *guidFileType* 매개 변수가 포함되지 않은 경우 파일 이름의 파일 확장명을 사용하여 이미지 형식을 결정합니다. 확장이 제공되지 않으면 이미지가 BMP 형식으로 저장됩니다.

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a>C이미지::세트컬러테이블

DIB 섹션의 팔레트에 있는 항목 범위에 대해 빨간색, 녹색, 파란색(RGB) 색상 값을 설정합니다.

```cpp
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>매개 변수

*iFirstColor*<br/>
설정할 첫 번째 항목의 색상 표 인덱스입니다.

*nColors*<br/>
설정할 색상 테이블 항목의 수입니다.

*prgbColors*<br/>
색상 테이블 항목을 설정하는 [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) 구조의 배열에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 DIB 섹션 비트맵만 지원합니다.

## <a name="cimagesetpixel"></a><a name="setpixel"></a>C이미지::설정 픽셀

비트맵의 지정된 위치에서 픽셀의 색상을 설정합니다.

```cpp
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 수평 위치입니다.

*Y*<br/>
설정할 픽셀의 세로 위치입니다.

*색*<br/>
픽셀을 설정한 색상입니다.

### <a name="remarks"></a>설명

픽셀 좌표가 선택한 클리핑 영역 외부에 있는 경우 이 메서드가 실패합니다.

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a>C이미지:::세트픽셀인덱싱

픽셀 색상을 색상 팔레트의 *iIndex에* 있는 색상으로 설정합니다.

```cpp
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 수평 위치입니다.

*Y*<br/>
설정할 픽셀의 세로 위치입니다.

*iIndex*<br/>
색상 팔레트의 색상 인덱스입니다.

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a>C이미지::세트픽셀RGB

*x* 및 *y로* 지정된 위치에서 픽셀을 *빨간색,* 녹색, 파란색(RGB) 이미지에서 r, *g*및 *b로*표시된 색상으로 설정합니다.

```cpp
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
설정할 픽셀의 수평 위치입니다.

*Y*<br/>
설정할 픽셀의 세로 위치입니다.

*r*<br/>
빨간색의 강도입니다.

*G*<br/>
녹색의 강도입니다.

*B*<br/>
파란색의 강도입니다.

### <a name="remarks"></a>설명

빨간색, 녹색 및 파란색 매개변수는 각각 0에서 255 사이의 숫자로 표시됩니다. 세 매개변수를 모두 0으로 설정하면 결합된 결과 색상이 검은색입니다. 세 매개변수를 모두 255로 설정하면 결합된 결과 색상이 흰색입니다.

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a>C이미지::세트투명색상

지정된 인덱싱된 위치에서 색상을 투명으로 설정합니다.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>매개 변수

*iTransparentColor*<br/>
색 팔레트의 인덱스를 투명으로 설정할 수 있습니다. -1이면 색상이 투명하게 설정되지 않습니다.

### <a name="return-value"></a>Return Value

이전에 투명으로 설정된 색상의 인덱스입니다.

## <a name="cimagestretchblt"></a><a name="stretchblt"></a>C이미지::스트레치블블

원본 장치 컨텍스트에서 이 현재 장치 컨텍스트로 비트맵을 복사합니다.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트에 대한 핸들입니다.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 y 좌표입니다.

*nDestWidth*<br/>
대상 사각형의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리적 단위로 높이입니다.

*dwROP*<br/>
수행될 래스터 조작. 래스터 작업 코드는 소스, 대상 및 패턴(현재 선택된 브러시에 의해 정의된 대로)의 비트를 결합하여 대상을 형성하는 방법을 정확하게 정의합니다. 다른 래스터 작업 코드 및 설명 목록은 Windows SDK의 [BitBlt를](/windows/win32/api/wingdi/nf-wingdi-bitblt) 참조하십시오.

*rectDest*<br/>
대상을 식별하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*ySrc*<br/>
논리 단위로 소스 사각형의 왼쪽 위 모서리의 y 좌표입니다.

*nSrcWidth*<br/>
소스 사각형의 논리적 단위로 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리적 단위로 높이입니다.

*rectSrc*<br/>
소스를 식별하는 `RECT` 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [StretchBlt를](/windows/win32/api/wingdi/nf-wingdi-stretchblt) 참조하십시오.

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a>C이미지::투명블랫

원본 장치 컨텍스트에서 이 현재 장치 컨텍스트로 비트맵을 복사합니다.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>매개 변수

*hDestDC*<br/>
대상 장치 컨텍스트에 대한 핸들입니다.

*xDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*yDest*<br/>
대상 사각형의 왼쪽 위 모서리의 논리적 단위로 y 좌표입니다.

*nDestWidth*<br/>
대상 사각형의 논리적 단위로 너비입니다.

*nDestHeight*<br/>
대상 사각형의 논리적 단위로 높이입니다.

*crTransparent*<br/>
투명으로 처리할 소스 비트맵의 색상입니다. 기본적으로 CLR_INVALID 현재 이미지의 투명 색상으로 설정된 색상을 사용해야 합니다.

*rectDest*<br/>
대상을 식별하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*xSrc*<br/>
소스 사각형의 왼쪽 위 모서리의 논리적 단위로 x 좌표입니다.

*ySrc*<br/>
논리 단위로 소스 사각형의 왼쪽 위 모서리의 y 좌표입니다.

*nSrcWidth*<br/>
소스 사각형의 논리적 단위로 너비입니다.

*nSrcHeight*<br/>
소스 사각형의 논리적 단위로 높이입니다.

*rectSrc*<br/>
소스를 식별하는 `RECT` 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

TRUE 성공, 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

`TransparentBlt`픽셀당 4비트, 픽셀당 8비트의 소스 비트맵에 대해 지원됩니다. [CImage::AlphaBlend를](#alphablend) 사용하여 픽셀당 32비트 비트 비트맵을 투명도로 지정합니다.

### <a name="example"></a>예제

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>참조

[MMXSwarm 샘플](../../overview/visual-cpp-samples.md)<br/>
[심플이미지 샘플](../../overview/visual-cpp-samples.md)<br/>
[장치 독립적 비트맵](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)<br/>
[장치 독립적 비트맵](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
