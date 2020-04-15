---
title: CComCoClass 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: 11e724a982f3a2f404473dbdd34d848842cc8e14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320834"
---
# <a name="ccomcoclass-class"></a>CComCoClass 클래스

이 클래스는 클래스의 인스턴스를 만들고 해당 속성을 가져오는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `CComCoClass`

*pclsid*<br/>
개체의 CLSID에 대한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComCoClass::만들기 인스턴스](#createinstance)|(정적) 인터페이스에 대한 클래스 및 쿼리의 인스턴스를 만듭니다.|
|[CComCoClass::오류](#error)|(정적) 풍부한 오류 정보를 클라이언트에 반환합니다.|
|[CComCoClass::겟오브젝트클시드](#getobjectclsid)|(정적) 개체의 클래스 식별자를 반환합니다.|
|[CComCoClass::GetObject 설명](#getobjectdescription)|(정적) 개체의 설명을 반환하려면 재정의합니다.|

## <a name="remarks"></a>설명

`CComCoClass`는 개체의 CLSID를 검색하고, 오류 정보를 설정하고, 클래스의 인스턴스를 만드는 메서드를 제공합니다. 개체 맵에 등록된 모든 클래스는 `CComCoClass`에서 파생되어야 합니다.

`CComCoClass`또한 개체에 대한 기본 클래스 팩터리 및 집계 모델을 정의합니다. `CComCoClass`다음 두 매크로를 사용합니다.

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) 클래스 팩터리를 [CComClassFactory로](../../atl/reference/ccomclassfactory-class.md)선언합니다.

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) 개체를 집계할 수 있음을 선언합니다.

클래스 정의에서 다른 매크로를 지정하여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 들어 `CComClassFactory`, 대신 [CComClassFactory2를](../../atl/reference/ccomclassfactory2-class.md) 사용하려면 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로를 지정합니다.

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomcoclasscreateinstance"></a><a name="createinstance"></a>CComCoClass::만들기 인스턴스

이러한 `CreateInstance` 함수를 사용하여 COM 개체의 인스턴스를 만들고 COM API를 사용하지 않고 인터페이스 포인터를 검색합니다.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>매개 변수

*Q*<br/>
*PP를*통해 반환해야 하는 COM 인터페이스 .

*펑크 아우터*<br/>
【인】 외부 알 수 없거나 골재의 알 수 없는 제어.

*Pp*<br/>
【아웃】 생성이 성공하면 요청된 인터페이스 포인터를 수신하는 포인터 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다. 가능한 반환 값에 대한 설명은 Windows SDK의 [CoCreateInstance를](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) 참조하십시오.

### <a name="remarks"></a>설명

일반적인 개체 만들기에 이 함수의 첫 번째 오버로드를 사용합니다. 생성중인 개체를 집계해야 할 때 두 번째 오버로드를 사용합니다.

필요한 COM 개체(즉, [CComCoClass의](../../atl/reference/ccomcoclass-class.md)첫 번째 템플릿 매개 변수로 사용되는 클래스)를 구현하는 ATL 클래스는 호출 코드와 동일한 프로젝트에 있어야 합니다. COM 개체의 생성은 이 ATL 클래스에 등록된 클래스 팩터리에서 수행됩니다.

이러한 함수는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) 매크로를 사용하여 외부에서 삐걱거리는 것을 방지한 개체를 만드는 데 유용합니다. 또한 효율성 때문에 COM API를 피하려는 상황에서도 유용합니다.

인터페이스 *Q에는* [__uuidof](../../cpp/uuidof-operator.md) 연산자를 사용하여 검색할 수 있는 IID가 연결되어 있어야 합니다.

### <a name="example"></a>예제

다음 예제에서는 `CDocument` 인터페이스를 구현하는 마법사에서 `CComCoClass` 파생된 ATL 클래스입니다. `IDocument` 클래스는 OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO 매크로와 개체 맵에 등록되므로 클라이언트는 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)를 사용하여 문서의 인스턴스를 만들 수 없습니다. `CApplication`는 문서 클래스의 인스턴스를 만드는 자체 COM 인터페이스 중 하나에 메서드를 제공하는 CoClass입니다. 아래 코드는 기본 클래스에서 상속된 `CreateInstance` 멤버를 사용하여 문서 클래스의 인스턴스를 `CComCoClass` 만드는 것이 얼마나 쉬운지 보여 주며 있습니다.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

## <a name="ccomcoclasserror"></a><a name="error"></a>CComCoClass::오류

이 정적 함수는 `IErrorInfo` 클라이언트에 오류 정보를 제공하기 위해 인터페이스를 설정합니다.

```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>매개 변수

*lpszDesc*<br/>
【인】 오류를 설명하는 문자열입니다. 유니코드 버전의 `Error` *lpszDesc이* LPCOLESTR 형식임을 지정합니다. ANSI 버전은 LPCSTR 의 유형을 지정합니다.

*Iid*<br/>
【인】 운영 체제에 의해 오류가 정의된 경우 오류 또는 GUID_NULL(기본값)을 정의하는 인터페이스의 IID입니다.

*hRes*<br/>
【인】 호출자에게 반환하려는 HRESULT입니다. 기본값은 0입니다. *reres에*대한 자세한 내용은 비고를 참조하십시오.

*nID*<br/>
【인】 오류 설명 문자열이 저장되는 리소스 식별자입니다. 이 값은 포함적으로 0x0200과 0xFFFF 사이에 있어야 합니다. 디버그 빌드에서 *nID가* 유효한 문자열을 인덱싱하지 않으면 **ASSERT가** 발생합니다. 릴리스 빌드에서 오류 설명 문자열이 "알 수 없는 오류"로 설정됩니다.

*dwHelpID*<br/>
【인】 오류에 대한 도움말 컨텍스트 식별자입니다.

*lpszHelpFile*<br/>
【인】 오류를 설명하는 도움말 파일의 경로 및 이름입니다.

*힌스트 (약)*<br/>
【인】 리소스에 대한 핸들입니다. 기본적으로 이 매개 `_AtlModule::GetResourceInstance`변수는 `_AtlModule` [CAtlModule](../../atl/reference/catlmodule-class.md)의 전역 인스턴스입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

호출하려면 `Error`개체가 인터페이스를 `ISupportErrorInfo Interface` 구현해야 합니다.

*hRes* 매개 변수가 0이 `Error` 아닌 경우 *reRes 값을 반환합니다.* *reRes가* 0이면 처음 네 가지 `Error` 버전의 반환이 DISP_E_EXCEPTION. 마지막 두 버전은 매크로 **MAKE_HRESULT(1, FACILITY_ITF,** *nID)의* **)** 결과를 반환합니다.

## <a name="ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>CComCoClass::겟오브젝트클시드

개체의 CLSID를 검색하는 일관된 방법을 제공합니다.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Return Value

개체의 클래스 식별자입니다.

## <a name="ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>CComCoClass::GetObject 설명

이 정적 함수는 클래스 개체에 대한 텍스트 설명을 검색합니다.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Return Value

클래스 개체의 설명입니다.

### <a name="remarks"></a>설명

기본 구현은 NULL을 반환합니다. [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) 매크로로 이 메서드를 재정의할 수 있습니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription``IComponentRegistrar::GetComponents`에서 호출됩니다. `IComponentRegistrar`는 DLL에서 개별 구성 요소를 등록하고 등록 취소할 수 있는 자동화 인터페이스입니다. ATL 프로젝트 마법사를 사용하여 구성 요소 레지스트라 개체를 만들면 `IComponentRegistrar` 마법사가 자동으로 인터페이스를 구현합니다. `IComponentRegistrar`일반적으로 Microsoft 트랜잭션 서버에서 사용됩니다.

ATL 프로젝트 마법사에 대한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)문서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
