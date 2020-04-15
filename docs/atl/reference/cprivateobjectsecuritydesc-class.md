---
title: C프라이빗오브젝트보안데스클래스
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: 2fcfdfecab649b571047613ec0889b02d2c7a7a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331414"
---
# <a name="cprivateobjectsecuritydesc-class"></a>C프라이빗오브젝트보안데스클래스

이 클래스는 개인 개체 보안 설명자 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C프라이빗오브젝트보안데스크::C프라이빗오브젝트보안데스](#cprivateobjectsecuritydesc)|생성자입니다.|
|[C프라이빗오브젝트보안데스크::~CPrivateObject보안데스](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPrivate개체보안데스크::변환토오토승계](#converttoautoinherit)|이 메서드를 호출하여 보안 설명자와 해당 액세스 제어 목록(ACL)을 상속 가능한 액세스 제어 항목(AE)의 자동 전파를 지원하는 형식으로 변환합니다.|
|[C프라이빗 오브젝트보안데스크::만들기](#create)|호출 리소스 관리자가 만든 개인 개체에 대한 자체 상대 보안 설명기를 할당하고 초기화하려면 이 메서드를 호출합니다.|
|[C프라이빗 오브젝트 보안데스크::Get](#get)|개인 개체의 보안 설명자에서 정보를 검색하려면 이 메서드를 호출합니다.|
|[C프라이빗 오브젝트보안데스크:::세트](#set)|개인 개체의 보안 설명기를 수정하려면 이 메서드를 호출합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[CSecurityDesc에서](../../atl/reference/csecuritydesc-class.md)파생된 이 클래스는 개인 개체의 보안 설명자 만들기 및 관리 방법을 제공합니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>CPrivate개체보안데스크::변환토오토승계

이 메서드를 호출하여 보안 설명자와 해당 액세스 제어 목록(ACL)을 상속 가능한 액세스 제어 항목(AE)의 자동 전파를 지원하는 형식으로 변환합니다.

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
개체의 상위 컨테이너를 참조하는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체에 대한 포인터입니다. 상위 컨테이너가 없는 경우 이 매개 변수는 NULL입니다.

*개체 유형*<br/>
현재 개체와 연결된 개체의 형식을 식별하는 `GUID` 구조체에 대한 포인터입니다. 개체에 GUID가 없는 경우 *ObjectType을* NULL로 설정합니다.

*비스디렉터리오브젝트*<br/>
새 개체에 다른 개체를 포함할 수 있는지 여부를 지정합니다. true 값은 새 개체가 컨테이너임을 나타냅니다. false 값은 새 개체가 컨테이너가 아님을 나타냅니다.

*제네릭 매핑*<br/>
개체에 대한 특정 권한에 대한 각 일반 권한의 매핑을 지정하는 [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 현재 보안 설명자의 임의 액세스 제어 목록(DACL) 및 시스템 액세스 제어 목록(SACL)의 AC가 상위 보안 설명자로부터 상속되었는지 여부를 확인하려고 시도합니다. [변환토오토상속프라이빗오브젝트보안](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) 함수를 호출합니다.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>C프라이빗오브젝트보안데스크::C프라이빗오브젝트보안데스

생성자입니다.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>설명

`CPrivateObjectSecurityDesc` 개체를 초기화합니다.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>C프라이빗오브젝트보안데스크::~CPrivateObject보안데스

소멸자입니다.

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당된 모든 리소스를 해제하고 개인 개체의 보안 설명자입니다.

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a>C프라이빗 오브젝트보안데스크::만들기

호출 리소스 관리자가 만든 개인 개체에 대한 자체 상대 보안 설명기를 할당하고 초기화하려면 이 메서드를 호출합니다.

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
새 개체가 생성되는 상위 디렉터리를 참조하는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체에 대한 포인터입니다. 상위 디렉터리가 없는 경우 NULL로 설정합니다.

*p 크리에이터*<br/>
개체 작성자가 제공하는 보안 설명자에 대한 포인터입니다. 개체 작성자가 새 개체에 대한 보안 정보를 명시적으로 전달하지 않는 경우 이 매개 변수를 NULL로 설정합니다.

*비스디렉터리오브젝트*<br/>
새 개체에 다른 개체를 포함할 수 있는지 여부를 지정합니다. true 값은 새 개체가 컨테이너임을 나타냅니다. false 값은 새 개체가 컨테이너가 아님을 나타냅니다.

*토큰*<br/>
개체를 대신하여 생성되는 클라이언트 프로세스에 대한 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체에 대한 참조입니다.

*제네릭 매핑*<br/>
개체에 대한 특정 권한에 대한 각 일반 권한의 매핑을 지정하는 [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) 구조에 대한 포인터입니다.

*개체 유형*<br/>
현재 개체와 연결된 개체의 형식을 식별하는 `GUID` 구조체에 대한 포인터입니다. 개체에 GUID가 없는 경우 *ObjectType을* NULL로 설정합니다.

*비스컨테이너 오브젝트*<br/>
새 개체에 다른 개체를 포함할 수 있는지 여부를 지정합니다. true 값은 새 개체가 컨테이너임을 나타냅니다. false 값은 새 개체가 컨테이너가 아님을 나타냅니다.

*자동 상속 플래그*<br/>
액세스 제어 항목(AEs)이 *pParent에서*상속되는 방법을 제어하는 비트 플래그 집합입니다. 자세한 내용은 [CreatePrivateObject보안Ex를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) 참조하십시오.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [CreatePrivateObjectSercurity](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) 또는 [CreatePrivateObjectSecurityEx를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)호출합니다.

두 번째 메서드는 새 개체의 개체 형식 GUID를 지정하거나 AC를 상속하는 방법을 제어할 수 있도록 합니다.

> [!NOTE]
> 자기 상대적 보안 설명자는 모든 보안 정보를 연속된 메모리 블록에 저장하는 보안 설명자입니다.

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a>C프라이빗 오브젝트 보안데스크::Get

개인 개체의 보안 설명자에서 정보를 검색하려면 이 메서드를 호출합니다.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>매개 변수

*Si*<br/>
검색할 보안 설명자의 일부를 나타내는 비트 플래그 집합입니다. 이 값은 [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) 비트 플래그의 조합일 수 있습니다.

*p결과*<br/>
지정된 보안 설명자에서 요청된 정보의 복사본을 받는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

보안 설명자는 보안 개체에 대한 보안 정보를 포함하는 구조 및 관련 데이터입니다.

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>CPrivate개체보안데스::연산자 =

대입 연산자입니다.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
현재 개체에 할당할 `CPrivateObjectSecurityDesc` 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CPrivateObjectSecurityDesc` 개체를 반환합니다.

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a>C프라이빗 오브젝트보안데스크:::세트

개인 개체의 보안 설명기를 수정하려면 이 메서드를 호출합니다.

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>매개 변수

*Si*<br/>
설정할 보안 설명자의 일부를 나타내는 비트 플래그 집합입니다. 이 값은 [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) 비트 플래그의 조합일 수 있습니다.

*수정*<br/>
[CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체에 대한 포인터입니다. *si* 매개 변수로 표시된 이 보안 설명자의 부분은 개체의 보안 설명자에 적용됩니다.

*제네릭 매핑*<br/>
개체에 대한 특정 권한에 대한 각 일반 권한의 매핑을 지정하는 [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) 구조에 대한 포인터입니다.

*토큰*<br/>
개체를 대신하여 생성되는 클라이언트 프로세스에 대한 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체에 대한 참조입니다.

*자동 상속 플래그*<br/>
액세스 제어 항목(AEs)이 *pParent에서*상속되는 방법을 제어하는 비트 플래그 집합입니다. 자세한 내용은 [CreatePrivateObject보안Ex를](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) 참조하십시오.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

두 번째 메서드는 개체의 개체 형식 GUID를 지정하거나 AC를 상속하는 방법을 제어할 수 있도록 합니다.

## <a name="see-also"></a>참고 항목

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc 클래스](../../atl/reference/csecuritydesc-class.md)
