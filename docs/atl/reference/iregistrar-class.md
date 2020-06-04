---
title: IRegistrar 인터페이스
ms.date: 02/01/2017
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 98943fe294322715723bd91207a6f3320ca1ffb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329459"
---
# <a name="iregistrar-interface"></a>IRegistrar 인터페이스

이 인터페이스는 atliface.h에 정의되어 있으며 [UpdateRegistryFromResourceD와](catlmodule-class.md#updateregistryfromresourced)같은 CAtlModule 멤버 함수에서 내부적으로 사용됩니다.

## <a name="syntax"></a>구문

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>설명

자세한 내용은 [대체 가능한 매개 변수 사용 항목(레지스트라의 사전 처리기)을](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 참조하십시오.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I레지스트라::리소스레지스터](#resourceregistersz)|리소스를 등록합니다. |
|[I레지스트라::리소스레지스터](#resourceunregistersz)| 리소스 등록을 취소합니다.|
|[I레지스트라::파일 레지스터](#fileregister)|파일을 등록합니다.|
|[I레지스트라::파일 등록 취소](#fileunregister)|파일 등록을 취소합니다.|
|[I레지스트라::문자열 레지스터](#stringregister)|문자열을 등록합니다.|
|[I레지스트라::스트링레지스터](#stringunregister)|문자열 등록 취소|
|[I등록자::리소스 레지스터](#resourceregister)|리소스를 등록합니다.|
|[I등록자::리소스 레지스터](#resourceunregister)|리소스 등록을 취소합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** 아를리파세.h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>I레지스트라::리소스레지스터

리소스를 등록합니다.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>I레지스트라::리소스레지스터

리소스 등록을 취소합니다.

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a>I레지스트라::파일 레지스터

파일을 등록합니다.

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a>I레지스트라::파일 등록 취소

파일 등록을 취소합니다.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a>I레지스트라::문자열 레지스터

지정된 문자열 데이터를 등록합니다.

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a>I레지스트라::스트링레지스터

지정된 문자열 데이터를 등록 취소합니다.

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a>I등록자::리소스 레지스터

리소스를 등록합니다.

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a>I등록자::리소스 레지스터

리소스 등록을 취소합니다.

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>참고 항목

[교체 가능한 매개 변수 사용(레지스트라의 사전 처리기)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)<br/>
[레지스트리 구성 요소(등록자)](../../atl/atl-registry-component-registrar.md)
