---
title: C메타파일DC 클래스
ms.date: 11/04/2016
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
ms.openlocfilehash: 0919dacfd758df39064c5381690e9e23a029fcd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369956"
---
# <a name="cmetafiledc-class"></a>C메타파일DC 클래스

원하는 이미지 또는 텍스트를 만들기 위해 재생할 수 있는 GDI(그래픽 디바이스 인터페이스) 명령 시퀀스가 포함된 Windows 메타파일을 구현합니다.

## <a name="syntax"></a>구문

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C메타파일DC::C메타파일DC](#cmetafiledc)|`CMetaFileDC` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C메타파일DC:닫기](#close)|장치 컨텍스트를 닫고 메타파일 핸들을 만듭니다.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|향상된 메타파일 장치 컨텍스트를 닫고 향상된 메타파일 핸들을 만듭니다.|
|[CMetaFileDC::Create](#create)|Windows 메타파일 장치 컨텍스트를 만들고 개체에 `CMetaFileDC` 연결합니다.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|향상된 형식의 메타파일에 대한 메타파일 장치 컨텍스트를 만듭니다.|

## <a name="remarks"></a>설명

Windows 메타파일을 구현하려면 먼저 개체를 `CMetaFileDC` 만듭니다. `CMetaFileDC` 생성자를 호출한 다음, Windows 메타 파일 장치 컨텍스트를 만들고 `CMetaFileDC` 개체에 연결하는 [Create](#create) member 함수를 호출합니다.

그런 다음 `CMetaFileDC` 재생하려는 CDC GDI 명령의 시퀀스를 개체에 보냅니다. `MoveTo` 및 와 `LineTo`같은 출력을 만드는 GDI 명령만 사용할 수 있습니다.

원하는 명령을 메타파일로 보낸 후 `Close` 메타파일 장치 컨텍스트를 닫고 메타파일 핸들을 반환하는 멤버 함수를 호출합니다. 그런 다음 `CMetaFileDC` 개체를 삭제합니다.

[CDC::PlayMetaFile은](../../mfc/reference/cdc-class.md#playmetafile) 메타파일 핸들을 사용하여 메타파일을 반복적으로 재생할 수 있습니다. 메타파일은 메타파일을 디스크에 복사하는 [CopyMetaFile과](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)같은 Windows 함수에서 조작할 수도 있습니다.

메타파일이 더 이상 필요하지 않은 경우 [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) Windows 함수를 사용 하 고 메모리에서 삭제 합니다.

또한 출력 호출과 와 같은 특성 GDI 호출을 모두 처리할 수 있도록 `CMetaFileDC` 개체를 구현할 수도 있습니다. `GetTextExtent` 이러한 메타파일은 더 유연하며 종종 출력 및 특성 호출의 혼합으로 구성된 일반 GDI 코드를 보다 쉽게 재사용할 수 있습니다. 클래스는 `CMetaFileDC` `m_hDC` CDC에서 두 개의 `m_hAttribDC`장치 컨텍스트 및 을 상속합니다. 장치 `m_hDC` 컨텍스트는 모든 [CDC](../../mfc/reference/cdc-class.md) GDI 출력 `m_hAttribDC` 호출을 처리하고 장치 컨텍스트는 모든 CDC GDI 특성 호출을 처리합니다. 일반적으로 이러한 두 장치 컨텍스트는 동일한 장치를 참조합니다. 의 경우 `CMetaFileDC`속성 DC는 기본적으로 NULL로 설정됩니다.

메타파일 이외 화면, 프린터 또는 장치를 가리키는 두 번째 장치 컨텍스트를 `SetAttribDC` 만든 다음 멤버 함수를 `m_hAttribDC`호출하여 새 장치 컨텍스트를 에 연결합니다. GDI는 이제 새로운 `m_hAttribDC`정보 로 이동합니다. 출력 GDI 호출은 `m_hDC`메타파일을 나타내는 로 이동합니다.

자세한 `CMetaFileDC`내용은 장치 [컨텍스트 를 참조하십시오.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cmetafiledcclose"></a><a name="close"></a>C메타파일DC:닫기

메타파일 장치 컨텍스트를 닫고 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) 멤버 함수를 사용하여 메타파일을 재생하는 데 사용할 수 있는 Windows 메타파일 핸들을 만듭니다.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Return Value

함수가 성공하면 유효한 HMETAFILE; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

Windows 메타파일 핸들을 사용하여 [CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)와 같은 Windows 함수를 사용하여 메타파일을 조작할 수도 있습니다.

Windows [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) 함수를 호출하여 사용 후 메타 파일을 삭제합니다.

## <a name="cmetafiledccloseenhanced"></a><a name="closeenhanced"></a>CMetaFileDC::닫기 강화

향상된 메타파일 장치 컨텍스트를 닫고 향상된 형식의 메타파일을 식별하는 핸들을 반환합니다.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Return Value

성공한 경우 향상된 메타파일의 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

응용 프로그램은 이 함수에서 반환된 향상된 메타파일 핸들을 사용하여 다음 작업을 수행할 수 있습니다.

- 향상된 메타파일에 저장된 그림 표시

- 향상된 메타파일 의 복사본 만들기

- 향상된 메타파일에서 개별 레코드를 확장, 편집 또는 복사

- 향상된 메타파일 헤더에서 메타파일 내용에 대한 선택적 설명을 검색합니다.

- 향상된 메타파일 헤더의 복사본을 검색합니다.

- 향상된 메타파일의 이진 복사본 을 검색합니다.

- 옵션 팔레트의 색상 을 [로 이):

- 향상된 형식의 메타파일을 Windows 형식 메타파일로 변환

응용 프로그램에 향상된 메타파일 핸들이 더 이상 필요하지 않은 경우 Win32 `DeleteEnhMetaFile` 함수를 호출하여 핸들을 해제해야 합니다.

## <a name="cmetafiledccmetafiledc"></a><a name="cmetafiledc"></a>C메타파일DC::C메타파일DC

두 `CMetaFileDC` 단계로 개체를 생성합니다.

```
CMetaFileDC();
```

### <a name="remarks"></a>설명

먼저 호출 `CMetaFileDC`합니다 `Create`. `CMetaFileDC`

## <a name="cmetafiledccreate"></a><a name="create"></a>CMetaFileDC::만들기

두 `CMetaFileDC` 단계로 개체를 생성합니다.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFilename*<br/>
null 종료된 문자 문자열을 가리킵니다. 만들 메타파일의 파일 이름을 지정합니다. *lpszFilename이* NULL이면 새 메모리 내 메타파일이 만들어집니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

먼저 생성자 `CMetaFileDC`호출 을 `Create`호출 한 다음 호출 `CMetaFileDC` 합니다 .

## <a name="cmetafiledccreateenhanced"></a><a name="createenhanced"></a>CMetaFileDC::강화된 만들기

향상된 형식의 메타파일에 대한 장치 컨텍스트를 만듭니다.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>매개 변수

*pDCRef*<br/>
향상된 메타파일의 참조 장치를 식별합니다.

*lpsz파일이름*<br/>
null 종료된 문자 문자열을 가리킵니다. 작성할 향상된 메타파일의 파일 이름을 지정합니다. 이 매개 변수가 NULL인 경우 향상된 메타파일은 메모리 기반이며 개체가 소멸되거나 Win32 `DeleteEnhMetaFile` 함수가 호출될 때 해당 내용이 손실됩니다.

*lpBounds*<br/>
향상된 메타파일에 저장할 그림의 HIMETRIC 단위(.01밀리미터 증분)의 치수를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 데이터 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체를 가리킵니다.

*lpszDescription*<br/>
그림을 만든 응용 프로그램의 이름과 그림 제목을 지정하는 0-종료된 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

성공한 경우 향상된 메타파일에 대한 장치 컨텍스트 의 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 DC는 장치 독립적인 그림을 저장하는 데 사용할 수 있습니다.

Windows는 *pDCRef* 매개 변수로 식별된 참조 장치를 사용하여 그림이 원래 나타난 장치의 해상도와 단위를 기록합니다. *pDCRef* 매개 변수가 NULL이면 현재 표시 장치를 참조로 사용합니다.

`RECT` *lpBounds* 매개 변수가 가리키는 데이터 구조의 왼쪽 및 위쪽 멤버는 각각 오른쪽 및 아래쪽 멤버보다 작아야 합니다. 사각형의 가장자리를 따라 있는 점이 그림에 포함됩니다. *lpBounds가* NULL인 경우 그래픽 장치 인터페이스(GDI)는 응용 프로그램에서 그린 그림을 둘러싸는 가장 작은 사각형의 크기를 계산합니다. 가능한 경우 *lpBounds* 매개 변수를 제공해야 합니다.

*lpszDescription* 매개 변수가 가리키는 문자열은 응용 프로그램 이름과 그림 이름 사이에 null 문자를 포함해야 하며 두 개의 null 문자(예: "XYZ Graphics Editor\0Bald Eagle\0\0")로 종료해야 합니다. *lpszDescription이* NULL이면 향상된 메타파일 헤더에 해당 항목이 없습니다.

응용 프로그램은 이 함수에서 만든 DC를 사용하여 향상된 메타파일에 그래픽 그림을 저장합니다. 이 DC를 식별하는 핸들은 모든 GDI 함수에 전달될 수 있습니다.

응용 프로그램이 향상된 메타파일에 그림을 저장한 후 함수를 호출하여 모든 출력 `CDC::PlayMetaFile` 장치에 그림을 표시할 수 있습니다. 그림을 표시할 때 Windows는 *lpBounds* 매개 변수가 가리키는 사각형과 참조 장치의 해상도 데이터를 사용하여 그림의 위치를 지정하고 배율을 조정합니다. 이 함수에서 반환되는 장치 컨텍스트에는 새 DC와 연결된 동일한 기본 특성이 포함됩니다.

응용 프로그램은 Win32 `GetWinMetaFileBits` 함수를 사용하여 향상된 메타파일을 이전 Windows 메타파일 형식으로 변환해야 합니다.

향상된 메타파일의 파일 이름은 을 사용해야 합니다. EMF 확장.

## <a name="see-also"></a>참고 항목

[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
