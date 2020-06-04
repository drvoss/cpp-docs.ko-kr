---
title: OLE 컨트롤의 지속성
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 88707da503b1d1cdc809827dc4d1bac0ccad9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373007"
---
# <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성

OLE 컨트롤의 한 가지 기능은 속성 지속성(또는 직렬화)으로, OLE 컨트롤이 파일 또는 스트림에서 속성 값을 읽거나 쓸 수 있도록 합니다. 컨테이너 응용 프로그램은 직렬화를 사용하여 응용 프로그램이 컨트롤을 삭제한 후에도 컨트롤의 속성 값을 저장할 수 있습니다. 그런 다음 나중에 컨트롤의 새 인스턴스를 만들 때 OLE 컨트롤의 속성 값을 파일 또는 스트림에서 읽을 수 있습니다.

### <a name="persistence-of-ole-controls"></a>OLE 컨트롤의 지속성

|||
|-|-|
|[PX_Blob](#px_blob)|이진 큰 개체 (BLOB) 데이터를 저장 하는 컨트롤 속성을 교환 합니다.|
|[PX_Bool](#px_bool)|**BOOL**형식의 제어 속성을 교환합니다.|
|[PX_Color](#px_color)|컨트롤의 색상 속성을 교환합니다.|
|[PX_Currency](#px_currency)|**유형 CY의**제어 속성을 교환합니다.|
|[PX_DataPath](#px_datapath)|형식의 `CDataPathProperty`컨트롤 속성을 교환합니다.|
|[PX_Double](#px_double)|**double**형식의 제어 속성을 교환합니다.|
|[PX_Font](#px_font)|컨트롤의 글꼴 속성을 교환합니다.|
|[PX_Float](#px_float)|형식 **float의**컨트롤 속성을 교환합니다.|
|[PX_IUnknown](#px_iunknown)|정의되지 않은 형식의 제어 속성을 교환합니다.|
|[PX_Long](#px_long)|형식 **긴의**제어 속성을 교환합니다.|
|[PX_Picture](#px_picture)|컨트롤의 그림 속성을 교환합니다.|
|[PX_Short](#px_short)|**짧은**형식의 제어 속성을 교환합니다.|
|[PX_ULong](#px_ulong)|**ULONG**형식의 제어 속성을 교환합니다.|
|[PX_UShort](#px_ushort)|**USHORT**형식의 제어 속성을 교환합니다.|
|[PX스트링](#px_string)|문자열 컨트롤 속성을 교환합니다.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX 컨트롤의 글꼴 관련 속성을 OLE 컨트롤 글꼴 속성으로 교환합니다.|

또한 TYPEDESC와 지정된 GUID 간의 일치를 테스트하기 위해 `AfxOleTypeMatchGuid` 전역 함수가 제공됩니다.

## <a name="px_blob"></a><a name="px_blob"></a>PX_Blob

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 이진 큰 개체(BLOB) 데이터를 저장하는 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*hBlob*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*hBlobDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *hBlob에서*참조하는 변수에서 읽거나 적절하게 기록됩니다. 이 변수는 처음 호출하기 `PX_Blob` 전에 NULL로 초기화되어야 합니다(일반적으로 컨트롤의 생성자에서 수행할 수 있음). *hBlobDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 초기화 또는 직렬화 프로세스가 실패하는 경우에 사용됩니다.

*핸들 hBlob* 및 *hBlobDefault는* 다음을 포함하는 메모리 블록을 참조합니다.

- 다음에 오는 이진 데이터의 길이(바이트)를 포함하는 DWORD다음에

- 실제 이진 데이터를 포함하는 메모리 블록입니다.

`PX_Blob`에서는 BLOB 형식 속성을 로드할 때 Windows [globalalloc](/windows/win32/api/winbase/nf-winbase-globalalloc) API를 사용하여 메모리를 할당합니다. 이 메모리를 해제할 책임은 귀하에게 있습니다. 따라서 컨트롤의 소멸자는 컨트롤에 할당된 메모리를 해제하기 위해 모든 BLOB 형식 속성 핸들에서 [GlobalFree를](/windows/win32/api/winbase/nf-winbase-globalfree) 호출해야 합니다.

## <a name="px_bool"></a><a name="px_bool"></a>PX_Bool

BOOL 형식의 속성을 `DoPropExchange` 직렬화하거나 초기화하려면 컨트롤의 멤버 함수 내에서 이 함수를 호출합니다.

```cpp
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*b값*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*bDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *bValue에서*참조하는 변수에서 읽거나 적절하게 기록됩니다. *bDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_color"></a><a name="px_color"></a>PX_Color

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 OLE_COLOR 형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*clrValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*clrDefault*<br/>
컨트롤 개발자가 정의한 대로 속성에 대한 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값에서 읽거나 *clrValue에*의해 참조 되는 변수에 기록 됩니다. *clrDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_currency"></a><a name="px_currency"></a>PX_Currency

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 형식 **통화의**속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*cyValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*cyDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값에서 읽거나 *cyValue에서*참조 하는 변수에 기록 됩니다. *cyDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_datapath"></a><a name="px_datapath"></a>PX_DataPath

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) 형식의 데이터 경로 속성을 serialize 하거나 초기화하려면 컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출합니다.

```cpp
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*dataPathProperty*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

데이터 경로 속성은 비동기 제어 속성을 구현합니다. 속성의 값에서 읽거나 *dataPathProperty에서*참조 하는 변수에 기록 됩니다.

## <a name="px_double"></a><a name="px_double"></a>PX_Double

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **double**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*doubleValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*doubleDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *doubleValue에서*참조하는 변수에서 읽거나 적절하게 기록됩니다. *doubleDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_font"></a><a name="px_font"></a>PX_Font

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 문자 글꼴의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*글꼴*<br/>
글꼴 속성을 `CFontHolder` 포함하는 개체에 대한 참조입니다.

*pFontDesc*<br/>
`FONTDESC` *pFontDispAmbient가* NULL인 경우 글꼴 속성의 기본 상태를 초기화하는 데 사용할 값을 포함하는 구조에 대한 포인터입니다.

*pFontDispAmbient*<br/>
글꼴 속성의 기본 상태를 초기화하는 데 사용할 글꼴 `IFontDisp` 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 적절한 경우 참조를 `CFontHolder` 읽거나 참조로 `font`작성됩니다. *pFontDesc* 및 *pFontDispAmbient가* 지정되면 필요할 때 속성의 기본값을 초기화하는 데 사용됩니다. 이러한 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다. 일반적으로 *pFontDesc및* `COleControl::AmbientFont` *pFontDispAmbient에*대해 반환되는 주변 값에 대해 NULL을 전달합니다. 반환되는 `COleControl::AmbientFont` 글꼴 개체는 `IFontDisp::Release` 멤버 함수에 대한 호출에 의해 해제되어야 합니다.

## <a name="px_float"></a><a name="px_float"></a>PX_Float

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **float**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*플로트밸류*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*floatDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *floatValue에서*참조하는 변수에서 읽거나 적절하게 기록됩니다. *floatDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_iunknown"></a><a name="px_iunknown"></a>PX_IUnknown

`IUnknown`컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 -derived 인터페이스를 갖는 개체로 표시되는 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*pUnk*<br/>
속성 값을 나타내는 개체의 인터페이스를 포함하는 변수를 참조합니다.

*Iid*<br/>
컨트롤에서 사용되는 속성 개체의 인터페이스를 나타내는 인터페이스 ID입니다.

*pUnkDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *pUnk에서*참조하는 변수를 적절히 읽거나 작성합니다. *pUnkDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_long"></a><a name="px_long"></a>PX_Long

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **long**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*lValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*lDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *lValue에서*참조하는 변수를 적절히 읽거나 기록합니다. *lDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_picture"></a><a name="px_picture"></a>PX_Picture

컨트롤의 멤버 함수 내에서 `DoPropExchange` 이 함수를 호출하여 컨트롤의 그림 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*pict*<br/>
속성이 저장되는 [CPictureHolder](../../mfc/reference/cpictureholder-class.md) 개체(일반적으로 클래스의 멤버 변수)를 참조합니다.

*pictDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *적절하게 pict에서*참조하는 변수에서 읽거나 기록됩니다. *pictDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_short"></a><a name="px_short"></a>PX_Short

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **짧은**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*sValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*sDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *sValue에서*참조하는 변수를 적절히 읽거나 기록합니다. *sDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_ulong"></a><a name="px_ulong"></a>PX_ULong

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **ULONG**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소 이름입니다.

*ulValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*ulDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *ulValue에서*참조하는 변수에서 읽거나 적절하게 기록됩니다. *ulDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_ushort"></a><a name="px_ushort"></a>PX_UShort

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 **서명되지 않은 short**형식의 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소 이름입니다.

*usValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*usDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *usValue에서*참조하는 변수를 적절히 읽거나 기록합니다. *usDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="pxstring"></a><a name="px_string"></a>PX스트링

컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출하여 character string 속성을 직렬화하거나 초기화합니다.

```cpp
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*strValue*<br/>
속성이 저장되는 변수(일반적으로 클래스의 멤버 변수)를 참조합니다.

*strDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *strValue에서*참조하는 변수를 적절히 읽거나 작성합니다. *strDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화 프로세스가 실패하는 경우에 사용됩니다.

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert

VBX 컨트롤의 글꼴 관련 속성을 변환하여 글꼴 속성을 초기화하려면 컨트롤의 `DoPropExchange` 멤버 함수 내에서 이 함수를 호출합니다.

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>매개 변수

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md) 개체에 대한 포인터(일반적으로 매개 `DoPropExchange`변수로 전달).

*글꼴*<br/>
변환된 VBX 글꼴 관련 속성을 포함하는 OLE 컨트롤의 글꼴 속성입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

이 함수는 VBX 컨트롤을 직접 대체하도록 설계된 OLE 컨트롤에서만 사용해야 합니다. Visual Basic 개발 환경이 VBX 컨트롤을 포함하는 폼을 변환하여 해당 대체 OLE 컨트롤을 `IDataObject::SetData` 사용하도록 변환하면 VBX 컨트롤의 속성 데이터가 포함된 속성 집합을 전달하는 컨트롤의 함수를 호출합니다. 이 작업을 수행하면 컨트롤의 `DoPropExchange` 함수가 호출됩니다. `DoPropExchange`VBX 컨트롤의 글꼴 관련 속성(예: "FontName", "FontSize" 등)을 OLE 컨트롤의 글꼴 속성의 해당 구성 요소로 변환하기 위해 호출할 `PX_VBXFontConvert` 수 있습니다.

`PX_VBXFontConvert`컨트롤이 실제로 VBX 양식 응용 프로그램에서 변환될 때만 호출되어야 합니다. 예를 들어:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>참조

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
