---
title: 크런타임클래스 구조
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: a58b9c97d5683423a0f81f6b5424f19f987943bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318561"
---
# <a name="cruntimeclass-structure"></a>크런타임클래스 구조

파생된 `CObject` 각 클래스는 런타임에 `CRuntimeClass` 개체 또는 해당 기본 클래스에 대한 정보를 가져오는 데 사용할 수 있는 구조와 연결됩니다.

## <a name="syntax"></a>구문

```
struct CRuntimeClass
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRuntime클래스::오브젝트 만들기](#createobject)|런타임 중에 개체를 만듭니다.|
|[크런 타임 클래스::FromName](#fromname)|익숙한 클래스 이름을 사용하여 런타임 중에 개체를 만듭니다.|
|[크런타임 클래스::파생](#isderivedfrom)|클래스가 지정된 클래스에서 파생되는지 여부를 결정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[크런타임 클래스:m_lpszClassName](#m_lpszclassname)|클래스의 이름입니다.|
|[크런타임 클래스:m_nObjectSize](#m_nobjectsize)|개체의 크기(바이트)입니다.|
|[크런타임 클래스:m_pBaseClass](#m_pbaseclass)|기본 클래스의 `CRuntimeClass` 구조에 대한 포인터입니다.|
|[크런타임클래스::m_pfnCreateObject](#m_pfncreateobject)|개체를 동적으로 만드는 함수에 대한 포인터입니다.|
|[크런타임 클래스::m_pfnGetBaseClass](#m_pfngetbaseclass)|구조를 `CRuntimeClass` 반환합니다(동적으로 연결된 경우에만 사용 가능).|
|[크런타임 클래스:m_wSchema](#m_wschema)|클래스의 스키마 수입니다.|

## <a name="remarks"></a>설명

`CRuntimeClass`는 구조이므로 기본 클래스가 없습니다.

런타임에 개체의 클래스를 결정하는 기능은 함수 인수의 추가 형식 검사가 필요하거나 개체의 클래스를 기반으로 특수 목적 코드를 작성해야 하는 경우에 유용합니다. 런타임 클래스 정보는 C++ 언어에서 직접 지원되지 않습니다.

`CRuntimeClass`은 기본 클래스의 포인터 및 관련 `CRuntimeClass` 클래스의 ASCII 클래스 이름과 같은 관련 C++ 개체에 대한 정보를 제공합니다. 또한 이 구조는 개체를 동적으로 만드는 데 사용할 수 있는 다양한 함수를 구현하고, 친숙한 이름을 사용하여 개체 유형을 지정하고, 관련 클래스가 특정 클래스에서 파생되었는지 여부를 결정합니다.

사용에 `CRuntimeClass`대한 자세한 내용은 [런타임 클래스 정보에 액세스하는](../../mfc/accessing-run-time-class-information.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRuntimeClass`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a>CRuntime클래스::오브젝트 만들기

런타임 중에 지정된 클래스를 동적으로 만들려면 이 함수를 호출합니다.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
만들 클래스의 친숙한 이름입니다.

### <a name="return-value"></a>Return Value

새로 만든 개체에 대한 포인터 또는 클래스 이름을 찾을 수 없거나 개체를 만들 수 있는 메모리가 부족한 경우 NULL입니다.

### <a name="remarks"></a>설명

파생된 `CObject` 클래스는 런타임에 지정된 클래스의 개체를 만드는 기능인 동적 생성을 지원할 수 있습니다. 예를 들어 문서, 보기 및 프레임 클래스는 동적 생성을 지원해야 합니다. 동적 생성 및 `CreateObject` 멤버에 대한 자세한 내용은 [CObject 클래스](../../mfc/using-cobject.md) 및 [CObject 클래스: 기능 수준 지정을](../../mfc/specifying-levels-of-functionality.md)참조하십시오.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="cruntimeclassfromname"></a><a name="fromname"></a>크런 타임 클래스::FromName

이 함수를 호출하여 익숙한 이름과 연결된 `CRuntimeClass` 구조를 검색합니다.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
에서 파생된 클래스의 친숙한 `CObject`이름입니다.

### <a name="return-value"></a>Return Value

`CRuntimeClass` *lpszClassName에서*전달된 이름에 해당하는 개체에 대한 포인터입니다. 일치하는 클래스 이름을 찾지 못하면 함수가 NULL을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a>크런타임 클래스::파생

이 함수를 호출하여 호출 클래스가 *pBaseClass* 매개 변수에 지정된 클래스에서 파생되는지 확인합니다.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>매개 변수

*pBaseClass*<br/>
에서 파생된 클래스의 친숙한 `CObject`이름입니다.

### <a name="return-value"></a>Return Value

TRUE 클래스 호출이 `IsDerivedFrom` `CRuntimeClass` 구조가 매개 변수로 지정된 기본 클래스에서 파생되는 경우 입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

관계는 멤버의 클래스에서 파생 클래스의 체인을 맨 위로 "걷기"로 결정합니다. 이 함수는 기본 클래스에 대한 일치를 찾을 수 없는 경우에만 FALSE를 반환합니다.

> [!NOTE]
> `CRuntimeClass` 구조를 사용하려면 런타임 개체 정보를 검색하려는 클래스의 구현에 IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE 또는 IMPLEMENT_SERIAL 매크로를 포함해야 합니다.

사용에 `CRuntimeClass`대한 자세한 내용은 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a>크런타임 클래스:m_lpszClassName

ASCII 클래스 이름을 포함하는 null 종료 된 문자열입니다.

### <a name="remarks"></a>설명

이 이름은 멤버 함수를 사용하여 클래스의 `FromName` 인스턴스를 만드는 데 사용할 수 있습니다.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a>크런타임 클래스:m_nObjectSize

바이트로 개체의 크기입니다.

### <a name="remarks"></a>설명

개체에 할당된 메모리를 가리키는 데이터 멤버가 있는 경우 해당 메모리의 크기는 포함되지 않습니다.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a>크런타임 클래스:m_pBaseClass

응용 프로그램이 정적으로 MFC에 연결하는 경우 이 데이터 `CRuntimeClass` 멤버에는 기본 클래스의 구조에 대한 포인터가 포함되어 있습니다.

### <a name="remarks"></a>설명

응용 프로그램이 MFC 라이브러리에 동적으로 링크되는 경우 [m_pfnGetBaseClass](#m_pfngetbaseclass)를 참조하십시오.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a>크런타임클래스::m_pfnCreateObject

클래스의 개체를 만드는 기본 생성자에 대한 함수 포인터입니다.

### <a name="remarks"></a>설명

이 포인터는 클래스가 동적 생성을 지원하는 경우에만 유효합니다. 그렇지 않으면 함수가 NULL을 반환합니다.

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a>크런타임 클래스::m_pfnGetBaseClass

응용 프로그램에서 MFC 라이브러리를 공유 DLL로 사용하는 경우 이 데이터 `CRuntimeClass` 멤버는 기본 클래스의 구조를 반환하는 함수를 가리킵니다.

### <a name="remarks"></a>설명

응용 프로그램이 MFC 라이브러리에 정적으로 링크되는 경우 [m_pBaseClass](#m_pbaseclass)을 참조하십시오.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a>크런타임 클래스:m_wSchema

스키마 번호(직렬화할 수 없는 클래스의 경우 -1)입니다.

### <a name="remarks"></a>설명

스키마 번호에 대한 자세한 내용은 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 참조하십시오.

### <a name="example"></a>예제

  파생 된에 대 한 [예제를](#isderivedfrom)참조 합니다 .

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject::GetRuntime클래스](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[C오브젝트::이킨드오브](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
