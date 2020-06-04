---
title: 콜레오브젝트팩토리 클래스
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 165ba7c1918c3ccc5d5d7e0bc067fba86678a3e7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753811"
---
# <a name="coleobjectfactory-class"></a>콜레오브젝트팩토리 클래스

서버, 자동화 개체, 문서와 같은 OLE 개체를 만드는 OLE 클래스 팩터리를 구현합니다.

## <a name="syntax"></a>구문

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레오브젝트팩토리::콜레오브젝트팩토리](#coleobjectfactory)|`COleObjectFactory` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레오브젝트팩토리::겟클래스ID](#getclassid)|이 팩터리에서 만드는 개체의 OLE 클래스 ID를 반환합니다.|
|[콜레오브젝트팩토리::유효하다](#islicensevalid)|컨트롤의 라이센스가 유효한지 확인합니다.|
|[콜레오브젝트팩토리::등록](#isregistered)|개체 팩터리가 OLE 시스템 DLL에 등록되어 있는지 여부를 나타냅니다.|
|[콜레오브젝트팩토리::레지스터](#register)|이 개체 팩터리를 OLE 시스템 DLL로 등록합니다.|
|[콜레오브젝트팩토리::레지스터모두](#registerall)|응용 프로그램의 모든 개체 팩터리를 OLE 시스템 DLL로 등록합니다.|
|[콜레오브젝트팩토리::취소](#revoke)|OLE 시스템 DLL을 사용 하 고이 개체 팩터리의 등록을 취소 합니다.|
|[콜레오브젝트팩토리::모두 취소](#revokeall)|OLE 시스템 DLL을 사용 하 고 응용 프로그램의 개체 팩터리의 등록을 취소 합니다.|
|[콜레오브젝트팩토리::모두 등록 취소](#unregisterall)|응용 프로그램의 모든 개체 팩터리를 등록 취소합니다.|
|[콜레오브젝트팩토리::업데이트레지스트리](#updateregistry)|이 개체 팩터리는 OLE 시스템 레지스트리에 등록합니다.|
|[콜레오브젝트팩토리::업데이트레지스트리모두](#updateregistryall)|응용 프로그램의 모든 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[콜레오브젝트팩토리::GetLicenseKey키](#getlicensekey)|컨트롤의 DLL에서 고유한 키를 요청합니다.|
|[콜레오브젝트팩토리::온크리에오브젝트](#oncreateobject)|이 팩터리 형식의 새 개체를 만들기 위해 프레임워크에서 호출합니다.|
|[콜레오브젝트팩토리::라이센스 키 확인](#verifylicensekey)|컨트롤에 포함된 키가 컨테이너에 포함된 키와 일치하는지 확인합니다.|
|[콜레오브젝트팩토리::검증유저 라이센스](#verifyuserlicense)|컨트롤이 디자인 타임 사용을 위해 라이선스가 부여되어 있는지 확인합니다.|

## <a name="remarks"></a>설명

`COleObjectFactory` 클래스에는 다음 기능을 수행하기 위한 멤버 함수가 있습니다.

- 개체 등록 관리.

- OLE 시스템 레지스터 업데이트및 개체가 실행 중이며 메시지를 받을 준비가 되었다는 것을 OLE에 알리는 런타임 등록을 업데이트합니다.

- 디자인 타임에 라이선스개발자로, 런타임에 라이선스가 부여된 응용 프로그램으로 컨트롤 사용을 제한하여 라이선스를 적용합니다.

- 제어 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.

개체 생성에 대한 자세한 내용은 [OLE(데이터 개체 및 데이터 원본)](../../mfc/data-objects-and-data-sources-ole.md) 및 [데이터 개체 및 데이터 원본: 생성 및 소멸](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)문서를 참조하십시오. 등록에 대한 자세한 내용은 문서 [등록을](../../mfc/registration.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="coleobjectfactorycoleobjectfactory"></a><a name="coleobjectfactory"></a>콜레오브젝트팩토리::콜레오브젝트팩토리

개체를 `COleObjectFactory` 구성하고 등록되지 않은 개체 팩터리로 초기화한 다음 팩터리 목록에 추가합니다.

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
이 개체 팩터리는 OLE 클래스 ID에 대한 참조입니다.

*pRuntime클래스*<br/>
이 팩터리에서 만들 수 있는 C++ 개체의 런타임 클래스에 대한 포인터입니다.

*bMulti인스턴스*<br/>
응용 프로그램의 단일 인스턴스가 여러 인스턴스를 지원할 수 있는지 여부를 나타냅니다. TRUE인 경우 개체를 만들기 위해 각 요청에 대해 응용 프로그램의 여러 인스턴스가 시작됩니다.

*nFlags*<br/>
다음 플래그 중 하나 이상을 포함합니다.

- `afxRegDefault`스레딩 모델을 스레딩모델=아파트로 설정합니다.

- `afxRegInsertable`OLE 개체에 대한 **개체 삽입** 대화 상자에 컨트롤이 표시되도록 허용합니다.

- `afxRegApartmentThreading`레지스트리의 스레딩 모델을 스레딩모델=아파트로 설정합니다.

- `afxRegFreeThreading`레지스트리의 스레딩 모델을 스레딩모델=무료로 설정합니다.

   두 플래그를 `afxRegApartmentThreading` 결합하고 `afxRegFreeThreading` 스레딩 모델=둘 다로 설정할 수 있습니다. 스레딩 모델 등록에 대한 자세한 내용은 Windows SDK의 [InprocServer32를](/windows/win32/com/inprocserver32) 참조하십시오.

*lpszProgID*<br/>
"Microsoft Excel"과 같은 구두 프로그램 식별자가 포함된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

그러나 개체를 사용하려면 객체를 등록해야 합니다.

자세한 내용은 Windows SDK의 [CLSID 키를](/windows/win32/com/clsid-key-hklm) 참조하십시오.

## <a name="coleobjectfactorygetclassid"></a><a name="getclassid"></a>콜레오브젝트팩토리::겟클래스ID

이 팩터리는 이 팩터리에서 나타내는 OLE 클래스 ID에 대한 참조를 반환합니다.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Return Value

이 팩터리는 이 팩터리에서 나타내는 OLE 클래스 ID에 대한 참조입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [CLSID 키를](/windows/win32/com/clsid-key-hklm) 참조하십시오.

## <a name="coleobjectfactorygetlicensekey"></a><a name="getlicensekey"></a>콜레오브젝트팩토리::GetLicenseKey키

컨트롤의 DLL에서 고유한 라이센스 키를 요청 하 고 *pbstrKey에*의해 가리키는 BSTR에 저장 합니다.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
다음에 사용하도록 예약됩니다.

*pbstrKey*<br/>
라이센스 키를 저장할 BSTR에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

라이센스 키 문자열이 NULL이 아닌 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 0을 반환하고 BSTR에 아무 것도 저장하지 않습니다. MFC ActiveX ControlWizard를 사용하여 프로젝트를 만드는 경우 ControlWizard는 컨트롤의 라이센스 키를 검색하는 재정의를 제공합니다.

## <a name="coleobjectfactoryislicensevalid"></a><a name="islicensevalid"></a>콜레오브젝트팩토리::유효하다

컨트롤의 라이센스가 유효한지 확인합니다.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Return Value

true 경우 성공; 그렇지 않으면 거짓.

## <a name="coleobjectfactoryisregistered"></a><a name="isregistered"></a>콜레오브젝트팩토리::등록

팩터리가 OLE 시스템 DLL에 등록된 경우 비영값을 반환합니다.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Return Value

출고된 경우 그렇지 않으면 0.

## <a name="coleobjectfactoryoncreateobject"></a><a name="oncreateobject"></a>콜레오브젝트팩토리::온크리에오브젝트

새 개체를 만들기 위해 프레임워크에서 호출합니다.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Return Value

생성된 개체에 대한 포인터입니다. 실패하면 메모리 예외를 throw할 수 있습니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 생성자에게 전달된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이외의 개체에서 개체를 만듭니다.

## <a name="coleobjectfactoryregister"></a><a name="register"></a>콜레오브젝트팩토리::레지스터

이 개체 팩터리를 OLE 시스템 DLL로 등록합니다.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Return Value

출고가가 성공적으로 등록된 경우 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 일반적으로 응용 프로그램이 시작될 때 [CWinApp::InitInstance에서](../../mfc/reference/cwinapp-class.md#initinstance) 호출합니다.

## <a name="coleobjectfactoryregisterall"></a><a name="registerall"></a>콜레오브젝트팩토리::레지스터모두

응용 프로그램의 모든 개체 팩터리를 OLE 시스템 DLL로 등록합니다.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Return Value

공장이 성공적으로 등록된 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 일반적으로 응용 프로그램이 시작될 때 [CWinApp::InitInstance에서](../../mfc/reference/cwinapp-class.md#initinstance) 호출합니다.

## <a name="coleobjectfactoryrevoke"></a><a name="revoke"></a>콜레오브젝트팩토리::취소

OLE 시스템 DLL을 사용 하 고이 개체 팩터리의 등록을 취소 합니다.

```cpp
void Revoke();
```

### <a name="remarks"></a>설명

프레임워크는 응용 프로그램이 종료되기 전에 이 함수를 자동으로 호출합니다. 필요한 경우 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)의 재정의에서 호출합니다.

## <a name="coleobjectfactoryrevokeall"></a><a name="revokeall"></a>콜레오브젝트팩토리::모두 취소

OLE 시스템 DLL을 사용 하 고 응용 프로그램의 개체 팩터리의 모든 등록을 취소 합니다.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>설명

프레임워크는 응용 프로그램이 종료되기 전에 이 함수를 자동으로 호출합니다. 필요한 경우 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)의 재정의에서 호출합니다.

## <a name="coleobjectfactoryunregisterall"></a><a name="unregisterall"></a>콜레오브젝트팩토리::모두 등록 취소

응용 프로그램의 모든 개체 팩터리를 등록 취소합니다.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

## <a name="coleobjectfactoryupdateregistry"></a><a name="updateregistry"></a>콜레오브젝트팩토리::업데이트레지스트리

응용 프로그램의 모든 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.

```cpp
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>매개 변수

*lpszProgID*<br/>
"Excel.Document.5"와 같이 사람이 읽을 수 있는 프로그램 식별자를 포함하는 문자열에 대한 포인터입니다.

*bRegister*<br/>
컨트롤 클래스의 개체 팩터리등록 여부를 결정합니다.

### <a name="remarks"></a>설명

이 함수에 대한 두 가지 양식에 대한 간략한 설명은 다음과 같습니다.

- **레지스트리 업데이트()** `lpszProgID` **)** 이 개체 팩터리는 OLE 시스템 레지스트리에 등록합니다. 이 함수는 일반적으로 응용 프로그램이 시작될 때 [CWinApp::InitInstance에서](../../mfc/reference/cwinapp-class.md#initinstance) 호출합니다.

- **레지스트리 업데이트()** `bRegister` **)** 이 형태의 함수는 재정의할 수 있습니다. *bRegister가* TRUE이면 이 함수는 제어 클래스를 시스템 레지스트리에 등록합니다. 그렇지 않으면 클래스를 등록 취소합니다.

   MFC ActiveX ControlWizard를 사용하여 프로젝트를 만드는 경우 ControlWizard는 이 순수 가상 함수에 재정의를 제공합니다.

## <a name="coleobjectfactoryupdateregistryall"></a><a name="updateregistryall"></a>콜레오브젝트팩토리::업데이트레지스트리모두

응용 프로그램의 모든 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>매개 변수

*bRegister*<br/>
컨트롤 클래스의 개체 팩터리등록 여부를 결정합니다.

### <a name="return-value"></a>Return Value

공장이 성공적으로 업데이트되는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 일반적으로 응용 프로그램이 시작될 때 [CWinApp::InitInstance에서](../../mfc/reference/cwinapp-class.md#initinstance) 호출합니다.

## <a name="coleobjectfactoryverifylicensekey"></a><a name="verifylicensekey"></a>콜레오브젝트팩토리::라이센스 키 확인

컨테이너가 OLE 컨트롤을 사용하도록 라이선스가 있는지 확인합니다.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>매개 변수

*블스트키*<br/>
컨테이너의 라이센스 문자열 버전을 저장하는 BSTR입니다.

### <a name="return-value"></a>Return Value

런타임 라이센스가 유효한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 버전은 [GetLicenseKey를](#getlicensekey) 호출하여 컨트롤의 라이센스 문자열의 복사본을 얻고 *bstrKey*의 문자열과 비교합니다. 두 문자열이 일치하면 함수는 zero가 아닌 값을 반환합니다. 그렇지 않으면 0을 반환합니다.

이 기능을 재정의하여 라이선스에 대한 사용자 지정 확인을 제공할 수 있습니다.

[VerifyUserLicense](#verifyuserlicense) 기능은 디자인 타임 라이센스를 확인합니다.

## <a name="coleobjectfactoryverifyuserlicense"></a><a name="verifyuserlicense"></a>콜레오브젝트팩토리::검증유저 라이센스

OLE 컨트롤에 대한 디자인 타임 라이센스를 확인합니다.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Return Value

디자인 타임 라이센스가 유효한 경우 비영; 그렇지 않으면 0.

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COle템플릿서버 클래스](../../mfc/reference/coletemplateserver-class.md)
