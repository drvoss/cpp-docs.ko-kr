---
title: 디스패치 맵
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 59dd8c7a7b0b930ffdb68fd96410fd73aeb02e81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365749"
---
# <a name="dispatch-maps"></a>디스패치 맵

OLE 자동화는 메서드를 호출하고 응용 프로그램 전체에서 속성에 액세스하는 방법을 제공합니다. 이러한 요청을 디스패치하기 위해 Microsoft Foundation 클래스 라이브러리에서 제공하는 메커니즘은 개체 함수 및 속성의 내부 및 외부 이름과 속성 자체 및 함수 인수의 데이터 형식을 지정하는 "디스패치 맵"입니다.

|디스패치 맵 매크로|Description|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|디스패치 맵이 클래스의 메서드 및 속성을 노출하는 데 사용됩니다(클래스 선언에 사용해야 함).|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|디스패치 맵의 정의를 시작합니다.|
|[END_DISPATCH_MAP](#end_dispatch_map)|디스패치 맵의 정의를 종료합니다.|
|[DISP_FUNCTION](#disp_function)|디스패치 맵에서 OLE 자동화 함수를 정의하는 데 사용됩니다.|
|[DISP_PROPERTY](#disp_property)|OLE 자동화 속성을 정의합니다.|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE 자동화 속성을 정의하고 Get 및 Set 함수의 이름을 지정합니다.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|알림으로 OLE 자동화 속성을 정의합니다.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|매개 변수를 사용 하 고 Get 및 Set 함수의 이름을 지정 하는 OLE 자동화 속성을 정의 합니다.|
|[DISP_DEFVALUE](#disp_defvalue)|기존 속성을 개체의 기본값으로 만듭니다.|

## <a name="declare_dispatch_map"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP

프로그램에서 `CCmdTarget`파생된 클래스가 OLE 자동화를 지원하는 경우 해당 클래스는 메서드 및 속성을 노출하기 위해 디스패치 맵을 제공해야 합니다.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>설명

클래스 선언의 끝에 DECLARE_DISPATCH_MAP 매크로를 사용합니다. 그런 다음 에서 . 클래스에 대 한 멤버 함수를 정의 하는 CPP 파일, BEGIN_DISPATCH_MAP 매크로를 사용 합니다. 그런 다음 클래스의 노출된 각 메서드 및 속성(DISP_FUNCTION, DISP_PROPERTY 등)에 대한 매크로 항목을 포함합니다. 마지막으로 END_DISPATCH_MAP 매크로를 사용합니다.

> [!NOTE]
> DECLARE_DISPATCH_MAP 이후에 멤버를 선언하는 경우 새 액세스 **유형(공개,** **비공개**또는 **보호)을**지정해야 합니다.

응용 프로그램 마법사 및 코드 마법사는 자동화 클래스를 만들고 디스패치 맵을 유지하는 데 도움이 됩니다. 디스패치 맵에 대한 자세한 내용은 [자동화 서버를](../../mfc/automation-servers.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="begin_dispatch_map"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

디스패치 맵의 정의를 선언합니다.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 디스패치 맵을 소유하는 클래스의 이름을 지정합니다.

*베이스 클래스*<br/>
의 기본 클래스 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의하는 구현(.cpp) 파일에서 BEGIN_DISPATCH_MAP 매크로로 디스패치 맵을 시작하고, 각 디스패치 함수 및 속성에 대한 매크로 항목을 추가하고, END_DISPATCH_MAP 매크로로 디스패치 맵을 완료합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="end_dispatch_map"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP

디스패치 맵의 정의를 종료합니다.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>설명

BEGIN_DISPATCH_MAP 함께 사용해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_function"></a><a name="disp_function"></a>DISP_FUNCTION

디스패치 맵에서 OLE 자동화 기능을 정의합니다.

```cpp
DISP_FUNCTION(
    theClass,
    pszName,
    pfnMember,
    vtRetVal,
    vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
함수의 외부 이름입니다.

*pfn회원*<br/>
멤버 함수의 이름입니다.

*vtRetVal*<br/>
함수의 반환 형식을 지정 하는 값입니다.

*vtsParams*<br/>
함수의 매개 변수 목록을 지정하는 하나 이상의 상수의 공간으로 구분된 목록입니다.

### <a name="remarks"></a>설명

*vtRetVal* 인수는 VARTYPE 형식입니다. 이 인수에 대한 다음 가능한 `VARENUM` 값은 열거형에서 가져온 것입니다.

|기호|반환 형식|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**긴**|
|VT_R4|**플 로트**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LP디스패치|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LP알 수 없음|

*vtsParams* 인수는 `VTS_*` 상수에서 값의 공간 분리 된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 예를 들면 다음과 같습니다.

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

짧은 정수 뒤에 짧은 정수에 대한 포인터가 포함된 목록을 지정합니다.

`VTS_` 상수와 그 의미는 다음과 같습니다.

|기호|매개 변수 형식|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**긴**|
|VTS_R4|**플 로트**|
|VTS_R8|**double**|
|VTS_CY|`const CY` 또는 `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LP디스패치|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` 또는 `VARIANT&`|
|VTS_UNKNOWN|LP알 수 없음|
|VTS_PI2|__짧은\*__|
|VTS_PI4|__긴\*__|
|VTS_PR4|__플 로트\*__|
|VTS_PR8|__double\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|매개 변수 없음|

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property"></a><a name="disp_property"></a>DISP_PROPERTY

디스패치 맵에서 OLE 자동화 속성을 정의합니다.

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*Membername*<br/>
속성이 저장되는 멤버 변수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

*vtPropType* 인수는 **VARTYPE**형식입니다. 이 인수에 대한 가능한 값은 VARENUM 열거형에서 가져온 것입니다.

|기호|속성 형식|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**긴**|
|VT_R4|**플 로트**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LP디스패치|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LP알 수 없음|

외부 클라이언트가 속성을 변경하면 *memberName에서* 지정한 멤버 변수의 값이 변경됩니다. 변경에 대한 알림이 없습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_ex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX

OLE 자동화 속성을 정의하고 디스패치 맵에서 속성값을 얻고 설정하는 데 사용되는 함수의 이름을 지정합니다.

```cpp
DISP_PROPERTY_EX(
    theClass,
    pszName,
    memberGet,
    memberSet,
    vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
속성의 외부 이름입니다.

*멤버Get*<br/>
속성을 얻는 데 사용되는 멤버 함수의 이름입니다.

*Memberset*<br/>
속성을 설정하는 데 사용되는 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

*memberGet* 및 *멤버 집합* 함수에는 *vtPropType* 인수에 의해 결정된 서명이 있습니다. *memberGet* 함수는 인수를 취하지 않으며 *vtPropType*에 의해 지정된 형식의 값을 반환합니다. *memberSet* 함수는 *vtPropType에서* 지정한 형식의 인수를 취하고 아무 것도 반환하지 않습니다.

*vtPropType* 인수는 VARTYPE 형식입니다. 이 인수에 대한 가능한 값은 VARENUM 열거형에서 가져온 값입니다. 이러한 값 의 목록은 [DISP_FUNCTION](#disp_function) *vtRetVal* 매개 변수에 대한 비고를 참조하십시오. DISP_FUNCTION 설명에 나열된 VT_EMPTY 속성 데이터 유형으로 허용되지 않습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_notify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

디스패치 맵에서 알림이 있는 OLE 자동화 속성을 정의합니다.

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    szExternalName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*sz외부 이름*<br/>
속성의 외부 이름입니다.

*Membername*<br/>
속성이 저장되는 멤버 변수의 이름입니다.

*pfnAfterSet*<br/>
*szExternalName에*대 한 알림 함수의 이름 입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

### <a name="remarks"></a>설명

DISP_PROPERTY 정의된 속성과 달리 DISP_PROPERTY_NOTIFY 정의된 속성은 속성이 변경될 때 *pfnAfterSet에서* 지정한 함수를 자동으로 호출합니다.

*vtPropType* 인수는 VARTYPE 형식입니다. 이 인수에 대한 가능한 값은 VARENUM 열거형에서 가져온 것입니다.

|기호|속성 형식|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**긴**|
|VT_R4|**플 로트**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LP디스패치|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LP알 수 없음|

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_property_param"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM

별도의 `Get` 멤버 `Set` 함수로 액세스하는 속성을 정의합니다.

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszExternalName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*psz외부 이름*<br/>
속성의 외부 이름입니다.

*pfnGet*<br/>
속성을 얻는 데 사용되는 멤버 함수의 이름입니다.

*pfnSet*<br/>
속성을 설정하는 데 사용되는 멤버 함수의 이름입니다.

*vtPropType*<br/>
속성의 형식을 지정 하는 값입니다.

*vtsParams*<br/>
각 매개 변수에 `VTS_*` 대해 하나씩 공간 으로 구분된 변형 매개 변수 형식의 문자열입니다.

### <a name="remarks"></a>설명

DISP_PROPERTY_EX 매크로와 달리 이 매크로를 사용하면 속성에 대한 매개 변수 목록을 지정할 수 있습니다. 이 기능은 인덱싱되거나 매개 변수화된 속성을 구현하는 데 유용합니다.

### <a name="example"></a>예제

사용자가 속성에 액세스할 때 특정 행 과 열을 요청할 수 있도록 하는 get 및 set 멤버 함수의 다음 선언을 고려합니다.

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

컨트롤 디스패치 맵의 다음 DISP_PROPERTY_PARAM 매크로에 해당합니다.

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

또 다른 예로, 다음 get 및 set 멤버 함수를 고려하십시오.

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

컨트롤 디스패치 맵의 다음 DISP_PROPERTY_PARAM 매크로에 해당합니다.

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="disp_defvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE

기존 속성을 개체의 기본값으로 만듭니다.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
클래스의 이름입니다.

*pszName*<br/>
개체의 "값"을 나타내는 속성의 외부 이름입니다.

### <a name="remarks"></a>설명

기본값을 사용하면 Visual Basic 애플리케이션에 대한 자동화 개체 프로그래밍을 더 간소화할 수 있습니다.

개체의 "기본값"은 개체에 대한 참조가 속성 또는 멤버 함수를 지정하지 않을 때 검색 또는 설정되는 속성입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
