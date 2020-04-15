---
title: 보안 글로벌 기능
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
ms.openlocfilehash: 682d44aa80f5d6de521223dfd67db2813cb6738c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326030"
---
# <a name="security-global-functions"></a>보안 글로벌 기능

이러한 함수는 SID 및 ACL 개체를 수정하는 데 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlGetDacl](#atlgetdacl)|지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.|
|[AtlSetDacl](#atlsetdacl)|지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.|
|[AtlGetGroupSid](#atlgetgroupsid)|개체의 그룹 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.|
|[AtlSetGroupSid](#atlsetgroupsid)|개체의 그룹 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.|
|[AtlGetOwnerSid](#atlgetownersid)|개체의 소유자 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.|
|[AtlSetOwnerSid](#atlsetownersid)|개체의 소유자 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.|
|[AtlGetSacl](#atlgetsacl)|지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.|
|[AtlSetSacl](#atlsetsacl)|지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|지정된 개체의 보안 설명자를 검색하려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a>아틀겟다클

지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 검색할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*pDacl*<br/>
검색된 보안 정보를 포함하는 DACL 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *hObject* 또는 *pDacl이* 유효하지 않은 경우 어설션 오류가 발생합니다.

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a>아틀셋다클

지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 설정할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*rDacl*<br/>
새 보안 정보가 포함된 DACL입니다.

*dw상속흐름제어*<br/>
상속 흐름 제어입니다. 이 값은 0(기본값), PROTECTED_DACL_SECURITY_INFORMATION 또는 UNPROTECTED_DACL_SECURITY_INFORMATION 수 있습니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *hObject가* 유효하지 않거나 *dwInheritanceFlowControl이* 허용된 세 값 중 하나가 아닌 경우 어설션 오류가 발생합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a>아틀겟그룹시드

개체의 그룹 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 검색할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*p시드 (것)와 함께*<br/>
새 보안 `CSid` 정보를 포함하는 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a>아틀셋그룹시드

개체의 그룹 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 설정할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*rSid*<br/>
새 `CSid` 보안 정보가 포함된 개체입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a>아틀겟오너시드

개체의 소유자 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 검색할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*p시드 (것)와 함께*<br/>
새 보안 `CSid` 정보를 포함하는 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a>아틀셋 오너시드

개체의 소유자 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 설정할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*rSid*<br/>
새 `CSid` 보안 정보가 포함된 개체입니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a>아틀겟사클

지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 검색할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*pSacl*<br/>
검색된 보안 정보를 포함하는 SACL 개체에 대한 포인터입니다.

*b요청필요프리빌리지*<br/>
true이면 함수는 SE_SECURITY_NAME 권한을 활성화하고 완료 시 복원하려고 시도합니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

여러 `AtlGetSacl` 개체에서 여러 번 호출되는 경우 *함수를* 호출하기 전에 한 번 SE_SECURITY_NAME 권한을 활성화하는 것이 더 효율적입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a>아틀셋사클

지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
보안 정보를 설정할 개체를 처리합니다.

*개체 유형*<br/>
SE_OBJECT_TYPE 열거형에서 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) *hObject* 매개 변수로 식별된 개체의 형식을 나타내는 값을 지정합니다.

*rSacl*<br/>
새 보안 정보가 포함된 SACL입니다.

*dw상속흐름제어*<br/>
상속 흐름 제어입니다. 이 값은 0(기본값), PROTECTED_SACL_SECURITY_INFORMATION 또는 UNPROTECTED_SACL_SECURITY_INFORMATION 수 있습니다.

*b요청필요프리빌리지*<br/>
true이면 함수는 SE_SECURITY_NAME 권한을 활성화하고 완료 시 복원하려고 시도합니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 *hObject가* 유효하지 않거나 *dwInheritanceFlowControl이* 허용된 세 값 중 하나가 아닌 경우 어설션 오류가 발생합니다.

여러 `AtlSetSacl` 개체에서 여러 번 호출되는 경우 *함수를* 호출하기 전에 한 번 SE_SECURITY_NAME 권한을 활성화하는 것이 더 효율적입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>아틀겟시큐리티 설명자

지정된 개체의 보안 설명자를 검색하려면 이 함수를 호출합니다.

> [!IMPORTANT]
> 이 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszObjectName*<br/>
보안 정보를 검색할 개체의 이름을 지정하는 null-종단 문자열에 대한 포인터입니다.

*개체 유형*<br/>
*pszObjectName* 매개 변수로 식별 된 개체의 형식을 나타내는 [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) 열거형에서 값을 지정 합니다.

*보안 설명자*<br/>
요청된 보안 설명자(보안 설명자)를 받는 개체입니다.

*요청된정보*<br/>
검색할 보안 정보의 유형을 나타내는 [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) 비트 플래그 집합입니다. 이 매개 변수는 다음 값의 조합일 수 있습니다.

*b요청필요프리빌리지*<br/>
true이면 함수는 SE_SECURITY_NAME 권한을 활성화하고 완료 시 복원하려고 시도합니다.

### <a name="return-value"></a>Return Value

실패에 대한 거짓, 성공에 대한 true를 반환합니다.

### <a name="remarks"></a>설명

여러 `AtlGetSecurityDescriptor` 개체에서 여러 번 호출되는 경우 *함수를* 호출하기 전에 한 번 SE_SECURITY_NAME 권한을 활성화하는 것이 더 효율적입니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
