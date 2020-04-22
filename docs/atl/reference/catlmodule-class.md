---
title: 카틀 모듈 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: cfc11a95a8d5d9354279f4c71698a6bc35c7aca7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748626"
---
# <a name="catlmodule-class"></a>카틀 모듈 클래스

이 클래스는 여러 ATL 모듈 클래스에서 사용되는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtl 모듈 ::CAtl모듈](#catlmodule)|생성자입니다.|
|[CAtl모듈:~카틀모듈](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlModule::커먼러GS 교체](#addcommonrgsreplacements)|이 메서드를 재정의하여 ATL 레지스트리 구성 요소(등록기관) 대체 맵에 매개 변수를 추가합니다.|
|[카틀 모듈 ::AddTermFunc](#addtermfunc)|모듈이 종료될 때 호출할 새 함수를 추가합니다.|
|[카틀 모듈 ::GetGITPtr](#getgitptr)|전역 인터페이스 포인터를 반환합니다.|
|[카틀 모듈 ::GetLockCount](#getlockcount)|잠금 수를 반환합니다.|
|[CAtl모듈::잠금](#lock)|잠금 수를 증가시입니다.|
|[CAtl모듈::기간](#term)|모든 데이터 멤버를 해제합니다.|
|[카틀 모듈 ::잠금 해제](#unlock)|잠금 횟수를 줄입니다.|
|[CAtl모듈::업데이트레지스트리로부터자원](#updateregistryfromresourced)|지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다.|
|[CAtlModule::업데이트레지스트리FromResourceDhelper](#updateregistryfromresourcedhelper)|이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 하기 위해 호출 됩니다.|
|[CAtlModule::업데이트레지스트리From리소스](#updateregistryfromresources)|지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다. 이 메서드는 ATL 레지스트리 구성 요소에 정적으로 연결 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAtl모듈:m_libid](#m_libid)|현재 모듈의 GUID를 포함합니다.|
|[CAtl모듈:m_pGIT](#m_pgit)|전역 인터페이스 테이블에 대한 포인터입니다.|

## <a name="remarks"></a>설명

이 클래스는 각각 DLL 응용 프로그램, EXE 응용 프로그램 및 Windows 서비스에 대한 지원을 제공하기 위해 [CAtlDllModuleT 클래스,](../../atl/reference/catldllmodulet-class.md) [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)및 [CAtlServiceModuleT 클래스에서](../../atl/reference/catlservicemodulet-class.md) 사용됩니다.

ATL 모듈에 대한 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md)참조하십시오.

이 클래스는 이전 버전의 ATL에서 사용된 사용되지 않는 [CComModule 클래스를](../../atl/reference/ccommodule-class.md) 대체합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::커먼러GS 교체

이 메서드를 재정의하여 ATL 레지스트리 구성 요소(등록기관) 대체 맵에 매개 변수를 추가합니다.

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>매개 변수

*p등록기관*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

대체 가능한 매개 변수를 사용하면 레지스트라의 클라이언트가 런타임 데이터를 지정할 수 있습니다. 이를 위해 등록기관은 스크립트에서 대체 가능한 매개 변수와 관련된 값을 입력하는 대체 맵을 유지 관리합니다. 레지스트라는 런타임에 이러한 항목을 만듭니다.

자세한 내용은 [대체 가능한 매개 변수 사용 항목(레지스트라의 사전 처리기)을](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 참조하십시오.

## <a name="catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>카틀 모듈 ::AddTermFunc

모듈이 종료될 때 호출할 새 함수를 추가합니다.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>매개 변수

*pFunc*<br/>
추가할 함수에 대한 포인터입니다.

*dw*<br/>
함수에 전달되는 사용자 정의 데이터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtl 모듈 ::CAtl모듈

생성자입니다.

```
CAtlModule() throw();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화하고 모듈 스레드에 대한 중요한 섹션을 시작합니다.

## <a name="catlmodulecatlmodule"></a><a name="dtor"></a>CAtl모듈:~카틀모듈

소멸자입니다.

```
~CAtlModule() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다.

## <a name="catlmodulegetgitptr"></a><a name="getgitptr"></a>카틀 모듈 ::GetGITPtr

전역 인터페이스 테이블에 대한 포인터를 검색합니다.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>매개 변수

*ppGIT*<br/>
전역 인터페이스 테이블에 대한 포인터를 수신할 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 코드가 실패할 경우 반환합니다. *ppGIT가* NULL과 같으면 E_POINTER 반환됩니다.

### <a name="remarks"></a>설명

전역 인터페이스 테이블 개체가 없으면 해당 개체가 만들어지고 해당 주소가 멤버 변수 [CAtlModule:m_pGIT](#m_pgit)에 저장됩니다.

디버그 빌드에서 *ppGIT가* NULL과 같거나 전역 인터페이스 테이블 포인터를 가져올 수 없는 경우 어설션 오류가 발생합니다.

글로벌 인터페이스 테이블에 대한 자세한 내용은 [IGlobalInterfaceTable을](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable) 참조하십시오.

## <a name="catlmodulegetlockcount"></a><a name="getlockcount"></a>카틀 모듈 ::GetLockCount

잠금 수를 반환합니다.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Return Value

잠금 수를 반환합니다. 이 값은 진단 및 디버깅에 유용할 수 있습니다.

## <a name="catlmodulelock"></a><a name="lock"></a>CAtl모듈::잠금

잠금 수를 증가시입니다.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Return Value

잠금 수를 증가시키고 업데이트된 값을 반환합니다. 이 값은 진단 및 디버깅에 유용할 수 있습니다.

## <a name="catlmodulem_libid"></a><a name="m_libid"></a>CAtl모듈:m_libid

현재 모듈의 GUID를 포함합니다.

```
static GUID m_libid;
```

## <a name="catlmodulem_pgit"></a><a name="m_pgit"></a>CAtl모듈:m_pGIT

전역 인터페이스 테이블에 대한 포인터입니다.

```
IGlobalInterfaceTable* m_pGIT;
```

## <a name="catlmoduleterm"></a><a name="term"></a>CAtl모듈::기간

모든 데이터 멤버를 해제합니다.

```cpp
void Term() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다. 이 메서드는 소멸자에서 호출합니다.

## <a name="catlmoduleunlock"></a><a name="unlock"></a>카틀 모듈 ::잠금 해제

잠금 횟수를 줄입니다.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Return Value

잠금 수를 감소시키고 업데이트된 값을 반환합니다. 이 값은 진단 및 디버깅에 유용할 수 있습니다.

## <a name="catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtl모듈::업데이트레지스트리로부터자원

지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다.

```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
리소스 이름입니다.

*nResID*<br/>
리소스 ID입니다.

*bRegister*<br/>
TRUE 개체를 등록해야 하는 경우; 그렇지 않으면 거짓.

*pMapEntries*<br/>
스크립트의 대체 가능한 매개 변수와 연결된 값을 저장하는 대체 맵에 대한 포인터입니다. ATL은 자동으로 %모듈%를 사용합니다. 추가 대체 가능한 매개 변수를 사용하려면 [CAtlModule::AddCommonRGSReplacement를](#addcommonrgsreplacements)참조하십시오. 그렇지 않으면 NULL 기본값을 사용합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

*lpszRes 또는 nResID에*의해 지정 된 리소스에 포함 된 스크립트를 실행 합니다. *bRegister가* TRUE이면 이 메서드는 시스템 레지스트리에 개체를 등록합니다. 그렇지 않으면 레지스트리에서 개체를 제거합니다.

ATL 레지스트리 구성 요소(레지스트라)에 정적으로 연결하려면 [CAtlModule:::UpdateRegistryFromResourceS](#updateregistryfromresources)를 참조하십시오.

이 메서드는 [CAtlModule::업데이트레지스트리FromResourceD도움말](#updateregistryfromresourcedhelper) 및 [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).

## <a name="catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::업데이트레지스트리FromResourceDhelper

이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 하기 위해 호출 됩니다.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
리소스 이름입니다.

*bRegister*<br/>
개체를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
스크립트의 대체 가능한 매개 변수와 연결된 값을 저장하는 대체 맵에 대한 포인터입니다. ATL은 자동으로 %모듈%를 사용합니다. 추가 대체 가능한 매개 변수를 사용하려면 [CAtlModule::AddCommonRGSReplacement를](#addcommonrgsreplacements)참조하십시오. 그렇지 않으면 NULL 기본값을 사용합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).

## <a name="catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule::업데이트레지스트리From리소스

지정된 리소스에 포함된 스크립트를 실행하여 개체를 등록하거나 등록 취소합니다. 이 메서드는 ATL 레지스트리 구성 요소에 정적으로 연결 됩니다.

```
HRESULT WINAPI UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*nResID*<br/>
리소스 ID입니다.

*lpszRes*<br/>
리소스 이름입니다.

*bRegister*<br/>
리소스 스크립트를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
스크립트의 대체 가능한 매개 변수와 연결된 값을 저장하는 대체 맵에 대한 포인터입니다. ATL은 자동으로 %모듈%를 사용합니다. 추가 대체 가능한 매개 변수를 사용하려면 [CAtlModule::AddCommonRGSReplacement를](#addcommonrgsreplacements)참조하십시오. 그렇지 않으면 NULL 기본값을 사용합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlModule::업데이트레지스트리FromResourceD](#updateregistryfromresourced) ATL `CAtlModule::UpdateRegistryFromResourceS` 레지스트리 구성 요소에 정적 링크를 만듭니다 (레지스트라).

## <a name="see-also"></a>참조

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)<br/>
[레지스트리 구성 요소(등록자)](../../atl/atl-registry-component-registrar.md)
