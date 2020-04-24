---
title: CObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
ms.openlocfilehash: 66d76e0062d13b2bd5a16d9b07f99db9e989805a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753985"
---
# <a name="cobject-class"></a>CObject 클래스

MFC 라이브러리의 주체 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[C오브젝트::C오브젝트](#cobject)|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CObject::어설션 유효](#assertvalid)|이 개체의 무결성을 확인합니다.|
|[CObject::Dump](#dump)|이 개체의 진단 덤프를 생성합니다.|
|[CObject::GetRuntime클래스](#getruntimeclass)|이 `CRuntimeClass` 개체의 클래스에 해당하는 구조를 반환합니다.|
|[C오브젝트::이킨드오브](#iskindof)|지정된 클래스에 대한 이 개체의 관계를 테스트합니다.|
|[CObject::직렬화 가능](#isserializable)|이 개체를 직렬화할 수 있는지 여부를 테스트합니다.|
|[CObject::직렬화](#serialize)|아카이브에서/아카이브에 개체를 로드하거나 저장합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CObject::연산자 삭제](#operator_delete)|특수 **삭제** 연산자.|
|[CObject::연산자 새](#operator_new)|특수 **새** 연산자.|

## <a name="remarks"></a>설명

`CFile` 이 루트는 와 `CObList`같은 라이브러리 클래스뿐만 아니라 작성하는 클래스의 루트 역할을 합니다. `CObject`다음과 같은 기본 서비스를 제공합니다.

- 직렬화 지원

- 런타임 클래스 정보

- 개체 진단 출력

- 컬렉션 클래스와의 호환성

다중 `CObject` 상속은 지원하지 않습니다. 파생 클래스에는 하나의 `CObject` 기본 클래스만 있을 `CObject` 수 있으며 계층 구조에서 가장 왼쪽에 있어야 합니다. 그러나 오른쪽 다중 상속 분기에 구조및 `CObject`파생되지 않은 클래스가 있는 것은 허용됩니다.

클래스 구현 및 `CObject` 선언에서 선택적 매크로 중 일부를 사용하면 파생의 주요 이점을 얻을 수 있습니다.

첫 번째 수준의 매크로, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) 및 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)계층 구조에서 클래스 이름과 해당 위치에 대한 런타임 액세스를 허용합니다. 이것은 차례로, 의미있는 진단 덤핑을 허용합니다.

두 번째 수준 [매크로인 DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)첫 번째 수준 매크로의 모든 기능을 포함하며 개체를 "아카이브"로 "직렬화"할 수 있습니다.

일반적으로 Microsoft Foundation 클래스 및 C++ 클래스를 파생하고 사용 하 여에 `CObject`대 한 자세한 내용은 [CObject](../../mfc/using-cobject.md) 및 [직렬화](../../mfc/serialization-in-mfc.md)사용 을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CObject`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>CObject::어설션 유효

이 개체의 무결성을 확인합니다.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>설명

`AssertValid`을 사용하여 내부 상태를 확인하여 이 개체에 대한 유효성 검사를 수행합니다. 라이브러리의 디버그 버전에서 `AssertValid` 어설션이 실패한 줄 번호와 파일 이름을 나열하는 메시지로 프로그램을 어설션하고 종료할 수 있습니다.

사용자 고유의 클래스를 `AssertValid` 작성할 때는 자신과 클래스의 다른 사용자에게 진단 서비스를 제공하는 기능을 재정의해야 합니다. 재정의된 경우 `AssertValid` 파생 `AssertValid` 클래스에 고유한 데이터 멤버를 검사하기 전에 일반적으로 기본 클래스의 함수를 호출합니다.

`AssertValid` **const** 함수이기 때문에 테스트 중에 개체 상태를 변경할 수 없습니다. 사용자 고유의 `AssertValid` 파생 클래스 함수는 예외를 throw하지 말고 잘못된 개체 데이터를 검색하는지 여부를 어설션해야 합니다.

"유효성"의 정의는 개체의 클래스에 따라 다릅니다. 일반적으로 함수는 "얕은 검사"를 수행해야 합니다. 즉, 개체에 다른 개체에 대한 포인터가 포함되어 있는 경우 포인터가 null이 아닌지 확인해야 하지만 포인터에서 참조하는 개체에 대한 유효성 테스트를 수행해서는 안 됩니다.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

또 다른 예는 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)를 참조하십시오.

## <a name="cobjectcobject"></a><a name="cobject"></a>C오브젝트::C오브젝트

이러한 함수는 표준 `CObject` 생성자입니다.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>매개 변수

*개체Src*<br/>
다른 참조`CObject`

### <a name="remarks"></a>설명

기본 버전은 파생 클래스의 생성자에서 자동으로 호출됩니다.

클래스가 직렬화 할 수있는 경우 (IMPLEMENT_SERIAL 매크로를 통합) 클래스 선언에 기본 생성자 (인수가없는 생성자)가 있어야합니다. 기본 생성자가 필요하지 않은 경우 개인 또는 보호된 "빈" 생성자라고 선언합니다. 자세한 내용은 [CObject 사용](../../mfc/using-cobject.md)을 참조하십시오.

표준 C++ 기본 클래스 복사 생성자는 멤버별 복사본을 수행합니다. 개인 `CObject` 복사 생성자가 있으면 클래스의 복사 생성자가 필요하지만 사용할 수 없는 경우 컴파일러 오류 메시지가 보장됩니다. 따라서 클래스에 이 기능이 필요한 경우 복사 생성자(copy 생성자)를 제공해야 합니다.

### <a name="example"></a>예제

예제에 사용된 `CAge` 클래스 목록은 `CObject` [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>CObject::D움프

개체의 내용을 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 개체에 덤프합니다.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
일반적으로 덤프에 대한 진단 `afxDump`덤프 컨텍스트입니다.

### <a name="remarks"></a>설명

사용자 고유의 클래스를 `Dump` 작성할 때는 자신과 클래스의 다른 사용자에게 진단 서비스를 제공하는 기능을 재정의해야 합니다. 재정의된 경우 `Dump` 파생 `Dump` 클래스에 고유한 데이터 멤버를 인쇄하기 전에 일반적으로 기본 클래스의 함수를 호출합니다. `CObject::Dump`은 클래스가 `IMPLEMENT_DYNAMIC` 매크로 또는 IMPLEMENT_SERIAL 사용하는 경우 클래스 이름을 인쇄합니다.

> [!NOTE]
> 함수는 `Dump` 출력 끝에 줄 바호 문자를 인쇄해서는 안 됩니다.

`Dump`호출은 Microsoft 재단 클래스 라이브러리의 디버그 버전에서만 의미가 있습니다. 조건부 컴파일을 위해 #ifdef **_DEBUG** /  `#endif` 문을 사용 하 여 호출, 함수 선언 및 함수 구현을 괄호로 묶아야 합니다.

`Dump` **const** 함수이므로 덤프 중에 개체 상태를 변경할 수 없습니다.

포인터가 삽입될 때 `CObject` [CDumpContext 삽입(<<) 연산자가](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) 호출합니다. `Dump`

`Dump`객체의 "비순환" 덤프만 허용합니다. 예를 들어 개체 목록을 덤프할 수 있지만 개체 중 하나가 목록 자체인 경우 결국 스택이 오버플로됩니다.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>CObject::GetRuntime클래스

이 `CRuntimeClass` 개체의 클래스에 해당하는 구조를 반환합니다.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Return Value

이 개체의 클래스에 해당하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다. 결코 **NULL**.

### <a name="remarks"></a>설명

각 `CObject`파생 `CRuntimeClass` 클래스에 대해 하나의 구조가 있습니다. 구조멤버는 다음과 같습니다.

- **LPCSTR m_lpszClassName** ASCII 클래스 이름을 포함하는 null 종료 된 문자열입니다.

- **인트 m_nObjectSize** 바이트로 개체의 크기입니다. 개체에 할당된 메모리를 가리키는 데이터 멤버가 있는 경우 해당 메모리의 크기는 포함되지 않습니다.

- **UINT m_wSchema** 스키마 번호 (- 직렬화할 수 없는 클래스의 경우 - 1). 스키마 번호에 대한 설명은 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 참조하십시오.

- **CObject\* \* (PASCAL m_pfnCreateObject))** 클래스의 개체를 만드는 기본 생성자 (클래스가 동적 생성을 지원하는 경우에만 유효합니다. 그렇지 않으면 **NULL을**반환)에 대한 함수 포인터입니다.

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass)()** 응용 프로그램이 AFXDLL 버전의 MFC에 동적으로 연결되어 있는 `CRuntimeClass` 경우 기본 클래스의 구조를 반환하는 함수에 대한 포인터입니다.

- **CRuntimeClass\* m_pBaseClass** 응용 프로그램이 기본 클래스의 `CRuntimeClass` 구조에 대한 포인터인 MFC에 정적으로 연결되어 있는 경우

이 함수는 클래스 구현에서 [IMPLEMENT_DYNAMIC,](run-time-object-model-services.md#implement_dynamic) [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)또는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 사용해야 합니다. 그렇지 않으면 잘못된 결과를 얻을 수 있습니다.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>C오브젝트::이킨드오브

지정된 클래스에 대한 이 개체의 관계를 테스트합니다.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>매개 변수

*pClass*<br/>
`CObject`-derived 클래스와 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

개체가 클래스에 해당하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 *pClass를* 테스트하여 (1) 지정된 클래스의 개체인지 또는 (2) 지정된 클래스에서 파생된 클래스의 개체인지 확인합니다. 이 함수는 [DECLARE_DYNAMIC,](run-time-object-model-services.md#declare_dynamic) [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)또는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로로 선언된 클래스에만 작동합니다.

C++ 다형성 기능을 무효화하므로 이 함수를 광범위하게 사용하지 마십시오. 대신 가상 함수를 사용합니다.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>CObject::직렬화 가능

이 개체가 직렬화할 수 있는지 여부를 테스트합니다.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Return Value

이 개체를 직렬화할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

클래스를 serializable 수 있도록 하려면 해당 선언에 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로를 포함 해야 합니다 및 구현 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로 포함 해야 합니다.

> [!NOTE]
> 이 함수를 재정의하지 마십시오.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>CObject::연산자 삭제

라이브러리의 릴리스 버전에 대 한 연산자 **삭제** 연산자 **새**에 의해 할당 된 메모리를 해제 합니다.

```cpp
void PASCAL operator delete(void* p);

void PASCAL operator delete(
    void* p,
    void* pPlace);

void PASCAL operator delete(
    void* p,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>설명

디버그 버전에서 운영자 **삭제는** 메모리 누수 를 감지하도록 설계된 할당 모니터링 체계에 참여합니다.

코드 줄을 사용하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

에서 구현하기 전에. CPP 파일은 세 번째 버전의 **삭제가** 사용되어 나중에 보고를 위해 할당된 블록에 파일 이름과 줄 번호를 저장합니다. 추가 매개 변수를 제공하는 것에 대해 걱정할 필요가 없습니다. 매크로가 당신을 위해 처리됩니다.

디버그 모드에서 DEBUG_NEW 사용하지 않더라도 위에서 설명한 소스 파일 라인 번호 보고가 없으면 누출 감지가 계속됩니다.

연산자 **새** 및 **삭제를**재정의하면 이 진단 기능이 상실됩니다.

### <a name="example"></a>예제

예제에 사용된 `CAge` 클래스 목록은 `CObject` [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>CObject::연산자 새

라이브러리의 릴리스 버전에 대해 연산자 **new는** `malloc`와 유사한 방식으로 최적의 메모리 할당을 수행합니다.

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>설명

디버그 버전에서 운영자 **새** 메모리 누수 를 감지 하도록 설계 된 할당 모니터링 체계에 참여 합니다.

코드 줄을 사용하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

에서 구현하기 전에. CPP 파일은 두 번째 버전의 **새** 파일이 사용되어 나중에 보고를 위해 할당된 블록에 파일 이름과 줄 번호를 저장합니다. 추가 매개 변수를 제공하는 것에 대해 걱정할 필요가 없습니다. 매크로가 당신을 위해 처리됩니다.

디버그 모드에서 DEBUG_NEW 사용하지 않더라도 위에서 설명한 소스 파일 라인 번호 보고가 없으면 누출 감지가 계속됩니다.

> [!NOTE]
> 이 연산자 재정의하는 경우 **delete도**재정의해야 합니다. 표준 라이브러리 `_new_handler` 기능을 사용하지 마십시오.

### <a name="example"></a>예제

예제에 사용된 `CAge` 클래스 목록은 `CObject` [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>CObject::직렬화

이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
직렬화할 `CArchive` 개체입니다.

### <a name="remarks"></a>설명

직렬화하려는 `Serialize` 각 클래스에 대해 재정의해야 합니다. 재정의된 먼저 `Serialize` 기본 클래스의 함수를 `Serialize` 호출해야 합니다.

또한 클래스 선언에서 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로를 사용해야 하며 구현에서 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 사용해야 합니다.

[CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) 또는 [CArchive::IsArchive를](../../mfc/reference/carchive-class.md#isstoring) 사용하여 보관이 로드 또는 저장중인지 여부를 확인합니다.

`Serialize`[CArchive::Read개체](../../mfc/reference/carchive-class.md#readobject) 및 [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject)에 의해 호출됩니다. 이러한 함수는 `CArchive` 삽입 연산자() ** < **및 추출 연산자()와 **>>** 연결됩니다.

직렬화 예제는 문서 [직렬화: 개체 직렬화를](../../mfc/serialization-serializing-an-object.md)참조하십시오.

### <a name="example"></a>예제

`CAge` 모든 `CObject` 예제에서 사용되는 클래스 목록은 [CObList::CObList를](../../mfc/reference/coblist-class.md#coblist) 참조하십시오.

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)
