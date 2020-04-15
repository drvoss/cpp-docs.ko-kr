---
title: 런타임 개체 모델 서비스
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f1cefdad368ebcd006dcb4ecf653247147f36d03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372946"
---
# <a name="run-time-object-model-services"></a>런타임 개체 모델 서비스

클래스 [CObject](../../mfc/reference/cobject-class.md) 및 [CRuntimeClass런타임](../../mfc/reference/cruntimeclass-structure.md) 클래스 정보에 대 한 액세스를 포함 하 여 여러 개체 서비스를 캡슐화, 직렬화 및 동적 개체 만들기. 이 기능을 상속하는 모든 클래스입니다. `CObject`

런타임 클래스 정보에 액세스하면 런타임에 개체의 클래스에 대한 정보를 확인할 수 있습니다. 런타임에 개체의 클래스를 결정하는 기능은 함수 인수의 추가 형식 검사가 필요하고 개체의 클래스에 따라 특수 목적 코드를 작성해야 하는 경우에 유용합니다. 런타임 클래스 정보는 C++ 언어에서 직접 지원되지 않습니다.

직렬화는 개체의 내용을 파일로 또는 파일에서 쓰거나 읽는 프로세스입니다. 직렬화를 사용하여 응용 프로그램이 종료된 후에도 개체의 내용을 저장할 수 있습니다. 그런 다음 응용 프로그램을 다시 시작할 때 파일에서 개체를 읽을 수 있습니다. 이러한 데이터 개체는 "영구"라고 합니다.

동적 개체 생성을 사용하면 런타임에 지정된 클래스의 개체를 만들 수 있습니다. 예를 들어, 문서, 뷰 및 프레임 개체는 프레임워크가 동적으로 만들어야 하기 때문에 동적 생성을 지원해야 합니다.

다음 표에는 런타임 클래스 정보, 직렬화 및 동적 만들기를 지원하는 MFC 매크로가 나열되어 있습니다.

이러한 런타임 개체 서비스 및 직렬화에 대한 자세한 내용은 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)문서를 참조하십시오.

### <a name="run-time-object-model-services-macros"></a>런타임 개체 모델 서비스 매크로

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|런타임 클래스 정보에 대한 액세스를 활성화합니다(클래스 선언에 사용해야 합니다).|
|[DECLARE_DYNCREATE](#declare_dyncreate)|동적 생성 및 런타임 클래스 정보에 대한 액세스를 활성화합니다(클래스 선언에 사용해야 합니다).|
|[DECLARE_SERIAL](#declare_serial)|직렬화 및 런타임 클래스 정보에 대한 액세스를 활성화합니다(클래스 선언에 사용해야 합니다).|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|런타임 클래스 정보에 대한 액세스를 활성화합니다(클래스 구현에서 사용해야 합니다).|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|동적 생성 및 런타임 정보에 대한 액세스를 활성화합니다(클래스 구현에서 사용해야 합니다).|
|[IMPLEMENT_SERIAL](#implement_serial)|직렬화 및 런타임 클래스 정보에 대한 액세스를 허용합니다(클래스 구현에 사용해야 합니다).|
|[RUNTIME_CLASS](#runtime_class)|명명된 `CRuntimeClass` 클래스에 해당하는 구조를 반환합니다.|

OLE는 런타임에 개체를 동적으로 생성해야 하는 경우가 많습니다. 예를 들어 OLE 서버 응용 프로그램은 클라이언트의 요청에 응답하여 OLE 항목을 동적으로 만들 수 있어야 합니다. 마찬가지로 자동화 서버는 자동화 클라이언트의 요청에 대한 응답으로 항목을 만들 수 있어야 합니다.

Microsoft 재단 클래스 라이브러리는 OLE와 관련된 두 개의 매크로를 제공합니다.

### <a name="dynamic-creation-of-ole-objects"></a>OLE 개체의 동적 생성

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|공통 제어 라이브러리가 지정된 API를 구현하는지 여부를 결정합니다.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|공통 제어 라이브러리가 지정된 API를 구현하는지 여부를 결정합니다.|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE 자동화를 통해 개체를 만들 수 있습니다.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|컨트롤 `GetUserTypeNameID` 클래스의 `GetMiscStatus` 및 멤버 함수를 선언합니다.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE 컨트롤은 해당 속성을 표시하는 속성 페이지 목록을 제공한다고 선언합니다.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE 시스템에서 개체를 만들 수 있습니다.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|컨트롤 `GetUserTypeNameID` 클래스의 `GetMiscStatus` 및 멤버 함수를 구현합니다.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|이 매크로 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) 를 사용하는 `DECLARE_OLECREATE`모든 클래스의 구현 파일에 나타나야 합니다. |

## <a name="afx_comctl32_if_exists"></a><a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

공통 제어 라이브러리가 지정된 API를 구현하는지 여부를 결정합니다.

### <a name="syntax"></a>구문

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>매개 변수

*proc*<br/>
함수 이름을 포함하는 null-terminated 문자열에 대한 포인터 또는 함수의 서수 값을 지정합니다. 이 매개 변수가 서수 값인 경우 하위 순서 단어여야 합니다. 높은 순서의 단어는 0이어야 합니다. 이 매개 변수는 유니코드에 있어야 합니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 일반 컨트롤이 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)를 호출하는 대신 *proc에서* 지정한 함수를 라이브러리하는지 여부를 확인합니다.

### <a name="requirements"></a>요구 사항

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a><a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

공통 제어 라이브러리가 지정된 API를 구현하는지 여부를 결정합니다(AFX_COMCTL32_IF_EXISTS 유니코드 [버전).](#afx_comctl32_if_exists)

### <a name="syntax"></a>구문

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>매개 변수

*proc*<br/>
함수 이름을 포함하는 null-terminated 문자열에 대한 포인터 또는 함수의 서수 값을 지정합니다. 이 매개 변수가 서수 값인 경우 하위 순서 단어여야 합니다. 높은 순서의 단어는 0이어야 합니다. 이 매개 변수는 유니코드에 있어야 합니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 일반 컨트롤이 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)를 호출하는 대신 *proc에서* 지정한 함수를 라이브러리하는지 여부를 확인합니다. 이 매크로는 유니코드 버전의 AFX_COMCTL32_IF_EXISTS.

### <a name="requirements"></a>요구 사항

afxcomctl32.h, afxcomctl32.inl

## <a name="declare_dynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC

`CObject`에서 클래스를 파생할 때 개체의 클래스에 대한 런타임 정보에 액세스하는 기능이 추가됩니다.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

DECLARE_DYNAMIC 매크로를 클래스의 헤더(h) 모듈에 추가한 다음 이 클래스의 개체에 액세스해야 하는 모든 .cpp 모듈에 해당 모듈을 포함합니다.

설명된 대로 DECLARE_ DYNAMIC 및 IMPLEMENT_DYNAMIC 매크로를 사용하는 경우 RUNTIME_CLASS `CObject::IsKindOf` 매크로 및 함수를 사용하여 런타임에 개체의 클래스를 결정할 수 있습니다.

DECLARE_DYNAMIC 클래스 선언에 포함된 경우 IMPLEMENT_DYNAMIC 클래스 구현에 포함되어야 합니다.

DECLARE_DYNAMIC 매크로에 대한 자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

### <a name="example"></a>예제

[IMPLEMENT_DYNAMIC](#implement_dynamic)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="declare_dyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE

-derived `CObject`클래스의 개체를 런타임에 동적으로 만들 수 있습니다.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

프레임워크는 이 기능을 사용하여 새 개체를 동적으로 만듭니다. 예를 들어 새 문서를 열 때 작성된 새 뷰입니다. 문서, 보기 및 프레임 클래스는 프레임워크가 동적으로 만들어야 하기 때문에 동적 생성을 지원해야 합니다.

클래스의 .h 모듈에 DECLARE_DYNCREATE 매크로를 추가한 다음 이 클래스의 개체에 액세스해야 하는 모든 .cpp 모듈에 해당 모듈을 포함합니다.

DECLARE_DYNCREATE 클래스 선언에 포함 된 경우 IMPLEMENT_DYNCREATE 클래스 구현에 포함 되어야 합니다.

DECLARE_DYNCREATE 매크로에 대한 자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

> [!NOTE]
> DECLARE_DYNCREATE 매크로에는 DECLARE_DYNAMIC 모든 기능이 포함되어 있습니다.

### <a name="example"></a>예제

[IMPLEMENT_DYNCREATE](#implement_dyncreate)에 대한 예제를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="declare_olectltype"></a><a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

컨트롤 `GetUserTypeNameID` 클래스의 `GetMiscStatus` 및 멤버 함수를 선언합니다.

### <a name="syntax"></a>구문

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

`GetUserTypeNameID`에 `GetMiscStatus` 선언된 순수 가상 `COleControl`함수입니다. 이러한 함수는 순수 가상이므로 컨트롤 클래스에서 재정의해야 합니다. DECLARE_OLECTLTYPE 외에도 컨트롤 클래스 선언에 IMPLEMENT_OLECTLTYPE 매크로를 추가해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="declare_proppageids"></a><a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

OLE 컨트롤은 해당 속성을 표시하는 속성 페이지 목록을 제공한다고 선언합니다.

### <a name="syntax"></a>구문

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
속성 페이지를 소유 하는 컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

클래스 `DECLARE_PROPPAGEIDS` 선언의 끝에 있는 매크로를 사용합니다. 그런 다음 클래스의 멤버 함수를 정의하는 .cpp 파일에서 `BEGIN_PROPPAGEIDS` 매크로, 컨트롤의 각 속성 페이지에 대한 매크로 `END_PROPPAGEIDS` 항목 및 매크로를 사용하여 속성 페이지 목록의 끝을 선언합니다.

속성 페이지에 대한 자세한 내용은 [ActiveX 컨트롤: 속성 페이지를](../mfc-activex-controls-property-pages.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="declare_serial"></a><a name="declare_serial"></a>DECLARE_SERIAL

직렬화할 수 있는 `CObject`-derived 클래스에 필요한 C++ 헤더 코드를 생성합니다.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

직렬화는 파일에서 개체의 내용을 작성하거나 읽는 프로세스입니다.

.h 모듈에서 DECLARE_SERIAL 매크로를 사용한 다음 이 클래스의 개체에 액세스해야 하는 모든 .cpp 모듈에 해당 모듈을 포함합니다.

DECLARE_SERIAL 클래스 선언에 포함되는 경우 IMPLEMENT_SERIAL 클래스 구현에 포함되어야 합니다.

DECLARE_SERIAL 매크로에는 DECLARE_DYNAMIC 및 DECLARE_DYNCREATE 모든 기능이 포함됩니다.

AFX_API 매크로를 사용하여 DECLARE_SERIAL 및 `CArchive` IMPLEMENT_SERIAL 매크로를 사용하는 클래스에 대해 추출 연산자내보내기를 자동으로 내보낼 수 있습니다. 클래스 선언(.h 파일에 있음)을 다음 코드와 함께 괄호로 묶습니다.

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL 매크로에 대한 자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="implement_dynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC

계층 내의 클래스 이름 및 `CObject`위치에 대한 런타임 액세스가 있는 동적 파생 클래스에 필요한 C++ 코드를 생성합니다.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 이름입니다.

### <a name="remarks"></a>설명

.cpp 모듈에서 IMPLEMENT_DYNAMIC 매크로를 사용한 다음 결과 개체 코드를 한 번만 연결합니다.

자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="implement_dyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE

DECLARE_DYNCREATE 매크로와 함께 사용할 때 런타임에 -derived 클래스의 `CObject`개체를 동적으로 만들 수 있습니다.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

프레임워크는 이 기능을 사용하여 직렬화 중에 디스크에서 개체를 읽을 때와 같은 새 개체를 동적으로 만듭니다. 클래스 구현 파일에 IMPLEMENT_DYNCREATE 매크로를 추가합니다. 자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

DECLARE_DYNCREATE 및 IMPLEMENT_DYNCREATE 매크로를 사용하는 경우 RUNTIME_CLASS 매크로 및 `CObject::IsKindOf` 멤버 함수를 사용하여 런타임에 개체의 클래스를 결정할 수 있습니다.

DECLARE_DYNCREATE 클래스 선언에 포함 된 경우 IMPLEMENT_DYNCREATE 클래스 구현에 포함 되어야 합니다.

이 매크로 정의는 클래스의 기본 생성자 호출을 호출합니다. 간단한 생성자가 클래스에서 명시적으로 구현되는 경우 기본 생성자도 명시적으로 구현해야 합니다. 기본 생성자는 클래스의 **개인** 또는 **보호된** 멤버 섹션에 추가하여 클래스 구현 외부에서 호출되지 않도록 할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="implement_olecreate_flags"></a><a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

이 매크로 또는 [IMPLEMENT_OLECREATE](#implement_olecreate) DECLARE_OLECREATE 사용하는 모든 클래스의 구현 파일에 나타나야 합니다.

### <a name="syntax"></a>구문

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*external_name*<br/>
다른 응용 프로그램에 노출된 개체 이름(따옴표로 동봉됨).

*nFlags*<br/>
다음 플래그 중 하나 이상을 포함합니다.

- `afxRegInsertable`OLE 개체에 대한 개체 삽입 대화 상자에 컨트롤이 표시되도록 허용합니다.
- `afxRegApartmentThreading`레지스트리의 스레딩 모델을 스레딩모델=아파트로 설정합니다.
- `afxRegFreeThreading`레지스트리의 스레딩 모델을 스레딩모델=무료로 설정합니다.

두 플래그를 `afxRegApartmentThreading` 결합하고 `afxRegFreeThreading` 스레딩 모델=둘 다로 설정할 수 있습니다. 스레딩 모델 등록에 대한 자세한 내용은 Windows SDK의 [InprocServer32를](/windows/win32/com/inprocserver32) 참조하십시오.

*l*, *w1*, *w2*, *b1,* *b2,* *b3,* *b4,* *b5,* *b6,* *b7,* *b8* 클래스의 CLSID 구성 요소.

### <a name="remarks"></a>설명

> [!NOTE]
> IMPLEMENT_OLECREATE_FLAGS 사용하는 경우 *nFlags* 매개 변수를 사용하여 개체가 지원하는 스레딩 모델을 지정할 수 있습니다. 단일 트레드 모델만 지원하려면 IMPLEMENT_OLECREATE 사용합니다.

외부 이름은 다른 응용 프로그램에 노출된 식별자입니다. 클라이언트 응용 프로그램은 외부 이름을 사용하여 자동화 서버에서 이 클래스의 개체를 요청합니다.

OLE 클래스 ID는 개체에 대한 고유한 128비트 식별자입니다. 구문 설명에서 *l,* *w1*, *w2*및 *b1에서 b8까지의* **긴**단어 *b8* s 와 8 **BYTE**s로 구성됩니다. **WORD** 응용 프로그램 마법사 및 코드 마법사는 필요에 따라 고유한 OLE 클래스 암호를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="implement_olectltype"></a><a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

컨트롤 `GetUserTypeNameID` 클래스의 `GetMiscStatus` 및 멤버 함수를 구현합니다.

### <a name="syntax"></a>구문

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
컨트롤 클래스의 이름입니다.

*idsUserTypeName*<br/>
컨트롤의 외부 이름을 포함하는 문자열의 리소스 ID입니다.

*dwOleMisc*<br/>
하나 이상의 플래그를 포함하는 열거형입니다. 이 열거형에 대한 자세한 내용은 Windows SDK의 [OLEMISC를](/windows/win32/api/oleidl/ne-oleidl-olemisc) 참조하십시오.

### <a name="remarks"></a>설명

IMPLEMENT_OLECTLTYPE 외에도 컨트롤 클래스 선언에 DECLARE_OLECTLTYPE 매크로를 추가해야 합니다.

멤버 `GetUserTypeNameID` 함수는 컨트롤 클래스를 식별하는 리소스 문자열을 반환합니다. `GetMiscStatus`을 사용 하 고 컨트롤에 대 한 OLEMISC 비트를 반환 합니다. 이 열거형은 컨트롤의 기타 특성을 설명하는 설정 컬렉션을 지정합니다. OLEMISC 설정에 대한 전체 설명은 Windows SDK의 [OLEMISC를](/windows/win32/api/oleidl/ne-oleidl-olemisc) 참조하십시오.

> [!NOTE]
> ActiveX ControlWizard에서 사용하는 기본 설정은 OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE 및 OLEMISC_RECOMPOSEONRESIZE입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="implement_serial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL

계층 내의 클래스 이름 및 `CObject`위치에 대한 런타임 액세스가 있는 동적 파생 클래스에 필요한 C++ 코드를 생성합니다.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*base_class_name*<br/>
기본 클래스의 이름입니다.

*wSchema*<br/>
이전 프로그램 버전에서 생성된 데이터를 식별하고 처리할 수 있는 직렬화 프로그램을 사용할 수 있도록 아카이브에 인코딩되는 UINT "버전 번호"입니다. 클래스 스키마 번호는 -1이어야 합니다.

### <a name="remarks"></a>설명

.cpp 모듈에서 IMPLEMENT_SERIAL 매크로를 사용합니다. 그런 다음 결과 개체 코드를 한 번만 연결합니다.

AFX_API 매크로를 사용하여 DECLARE_SERIAL 및 `CArchive` IMPLEMENT_SERIAL 매크로를 사용하는 클래스에 대해 추출 연산자내보내기를 자동으로 내보낼 수 있습니다. 클래스 선언(.h 파일에 있음)을 다음 코드와 함께 괄호로 묶습니다.

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="runtime_class"></a><a name="runtime_class"></a>RUNTIME_CLASS

C++ 클래스의 이름에서 런타임 클래스 구조를 가져옵니다.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름(따옴표로 묶이지 않음)입니다.

### <a name="remarks"></a>설명

RUNTIME_CLASS *class_name*지정한 클래스에 대한 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터를 반환합니다. DECLARE_DYNAMIC, DECLARE_DYNCREATE 또는 DECLARE_SERIAL 선언된 -derived 클래스만 `CObject` `CRuntimeClass` 구조에 포인터를 반환합니다.

자세한 내용은 [CObject 클래스 항목을](../../mfc/using-cobject.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="declare_olecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE

OLE 자동화를 통해 -파생 클래스의 `CCmdTarget`개체를 만들 수 있습니다.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하면 다른 OLE 지원 응용 프로그램에서 이 유형의 개체를 만들 수 있습니다.

클래스의 .h 모듈에 DECLARE_OLECREATE 매크로를 추가한 다음 이 클래스의 개체에 액세스해야 하는 모든 .cpp 모듈에 해당 모듈을 포함합니다.

DECLARE_OLECREATE 클래스 선언에 포함되는 경우 IMPLEMENT_OLECREATE 클래스 구현에 포함되어야 합니다. DECLARE_OLECREATE 사용하는 클래스 선언도 DECLARE_DYNCREATE 사용하거나 DECLARE_SERIAL.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="implement_olecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

이 매크로 또는 [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) 를 사용하는 `DECLARE_OLECREATE`모든 클래스의 구현 파일에 나타나야 합니다.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
클래스의 실제 이름입니다.

*external_name*<br/>
다른 응용 프로그램에 노출된 개체 이름(따옴표로 동봉됨).

*l*, *w1*, *w2*, *b1,* *b2,* *b3,* *b4,* *b5,* *b6,* *b7,* *b8* 클래스의 CLSID 구성 요소.

### <a name="remarks"></a>설명

> [!NOTE]
> IMPLEMENT_OLECREATE 사용하는 경우 기본적으로 단일 스레딩 모델만 지원합니다. IMPLEMENT_OLECREATE_FLAGS 사용하는 경우 *nFlags* 매개 변수를 사용하여 개체가 지원하는 스레딩 모델을 지정할 수 있습니다.

외부 이름은 다른 응용 프로그램에 노출된 식별자입니다. 클라이언트 응용 프로그램은 외부 이름을 사용하여 자동화 서버에서 이 클래스의 개체를 요청합니다.

OLE 클래스 ID는 개체에 대한 고유한 128비트 식별자입니다. 구문 설명에서 *l,* *w1*, *w2*및 *b1에서 b8까지의* **긴**단어 *b8* s 와 8 **BYTE**s로 구성됩니다. **WORD** 응용 프로그램 마법사 및 코드 마법사는 필요에 따라 고유한 OLE 클래스 암호를 만듭니다.

### <a name="requirements"></a>요구 사항

**헤더**: afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[MFC 공용 컨트롤 라이브러리 격리](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID 키](/windows/win32/com/clsid-key-hklm)
