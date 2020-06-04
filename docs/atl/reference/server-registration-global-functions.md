---
title: 서버 등록 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: fb6353b52f487d0511c54223fe9e31dab88704b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325923"
---
# <a name="server-registration-global-functions"></a>서버 등록 전역 함수

이러한 함수는 개체 맵에서 서버 개체를 등록하고 등록 취소하는 기능을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|이 함수는 개체 맵의 모든 개체를 등록하기 위해 호출됩니다.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|이 함수는 개체 맵의 모든 개체를 등록 취소하기 위해 호출됩니다.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|이 함수는 클래스 개체를 등록하기 위해 호출됩니다.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|이 함수는 COM 모듈에서 클래스 개체를 해지하기 위해 호출됩니다.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|이 함수는 클래스 개체를 얻기 위해 호출됩니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>아틀컴모듈레지스터서버

이 함수는 개체 맵의 모든 개체를 등록하기 위해 호출됩니다.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>매개 변수

*pComModule*<br/>
COM 모듈에 대한 포인터입니다.

*bRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록할 경우

*pCLSID*<br/>
등록할 개체의 CLSID를 가리킵니다. NULL이면 개체 맵의 모든 오브젝트가 등록됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`AtlComModuleRegisterServer`ATL 자동 생성된 개체 맵을 안내하고 맵의 각 개체를 등록합니다. *pCLSID가* NULL이 아닌 경우 *pCLSID에서* 참조하는 개체만 등록됩니다. 그렇지 않으면 모든 개체가 등록됩니다.

이 함수는 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>AtlComModule UnregisterServer

이 함수는 개체 맵의 모든 개체를 등록 취소하기 위해 호출됩니다.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>매개 변수

*pComModule*<br/>
COM 모듈에 대한 포인터입니다.

*bUnRegTypeLib*<br/>
TRUE 형식 라이브러리를 등록할 경우

*pCLSID*<br/>
등록취소할 개체의 CLSID를 가리킵니다. NULL이 면 개체 맵의 모든 객체가 등록 취소됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`AtlComModuleUnregisterServer`ATL 오브젝트 맵을 안내하고 맵의 각 오브젝트를 등록 취소합니다. *pCLSID가* NULL이 아닌 경우 *pCLSID에서* 참조하는 개체만 등록되지 않습니다. 그렇지 않으면 모든 개체가 등록되지 않습니다.

이 함수는 [CAtlComModule::registerServer](catlcommodule-class.md#unregisterserver).

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>AtlCom모듈레지스터클래스개체

이 함수는 클래스 개체를 등록하기 위해 호출됩니다.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*pComModule*<br/>
COM 모듈에 대한 포인터입니다.

*dwClsContext*<br/>
클래스 개체를 실행할 컨텍스트를 지정합니다. 가능한 값은 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER 또는 CLSCTX_LOCAL_SERVER. 자세한 내용은 [CLSCTX를](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) 참조하십시오.

*dwFlags*<br/>
클래스 개체에 대한 연결 유형을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE 또는 REGCLS_MULTI_SEPARATE. 자세한 내용은 [REGCLS를](/windows/win32/api/combaseapi/ne-combaseapi-regcls) 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수는 [CComModule::RegisterClassObjects(ATL](ccommodule-class.md#registerclassobjects) 7.0에서 사용되지 않음) 및 [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)에서 사용됩니다.

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>아틀콤모듈레서보어클래스오브젝트

이 함수는 실행 개체 테이블에서 클래스 팩터리를 제거하기 위해 호출됩니다.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>매개 변수

*pComModule*<br/>
COM 모듈에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수는 [CComModule::해지클래스](ccommodule-class.md#revokeclassobjects) 개체(ATL 7.0에서 사용되지 않음) 및 [CAtlExeModuleT::취소클래스 개체에](catlexemodulet-class.md#revokeclassobjects)의해 사용됩니다.

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>아틀콤모듈겟클래스오브젝트

이 함수는 클래스 팩터리를 반환하기 위해 호출됩니다.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>매개 변수

*pComModule*<br/>
COM 모듈에 대한 포인터입니다.

*rclsid*<br/>
만들 개체의 CLSID입니다.

*riid*<br/>
요청된 인터페이스의 IID입니다.

*ppv*<br/>
*riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppv가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수는 [CComModule::GetClassObject(ATL](ccommodule-class.md#getclassobject) 7.0에서 사용되지 않음) 및 [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)에서 사용됩니다.

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
