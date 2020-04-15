---
title: IDataObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 618f8248a03297120ae2504bcb30ba8f080b184d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329836"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl 클래스

이 클래스는 균일한 데이터 전송을 지원하고 연결을 관리하는 방법을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IDataObjectImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IDataObjectImpl::D조언](#dadvise)|데이터 개체와 조언 싱크 사이의 연결을 설정합니다. 이렇게 하면 조언 싱크 개체의 변경 내용 알림을 받을 수 있습니다.|
|[IDataObjectImpl::Dunadvise](#dunadvise)|을 통해 `DAdvise`이전에 설정된 연결을 종료합니다.|
|[IDataObjectImpl::에이넘어](#enumdadvise)|현재 권고 연결을 반복할 열거형기를 만듭니다.|
|[IDataObjectImpl::에이넘 포맷등](#enumformatetc)|데이터 개체에서 지원하는 `FORMATETC` 구조를 반복할 열거체를 만듭니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IDataObjectImpl::FireDatachange](#firedatachange)|각 조언 싱크에 변경 알림을 다시 보냅니다.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|논리적으로 동등한 `FORMATETC` 구조를 더 복잡한 구조로 검색합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IDataObjectImpl::GetData](#getdata)|데이터 개체에서 클라이언트로 데이터를 전송합니다. 데이터는 구조에 `FORMATETC` 설명되며 `STGMEDIUM` 구조를 통해 전송됩니다.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|`GetData`클라이언트를 제외한 것과 유사하게 `STGMEDIUM` 구조를 할당해야 합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IDataObjectImpl::쿼리GetData](#querygetdata)|데이터 개체가 데이터 전송을 `FORMATETC` 위한 특정 구조를 지원하는지 여부를 결정합니다. ATL 구현은 E_NOTIMPL 반환합니다.|
|[IData개체임플::세트데이터](#setdata)|클라이언트에서 데이터 개체로 데이터를 전송합니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) 인터페이스는 균일한 데이터 전송을 지원하는 메서드를 제공합니다. `IDataObject`표준 형식 구조 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 및 [STGMEDIUM를](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 사용하여 데이터를 검색하고 저장합니다.

`IDataObject`또한 데이터 변경 알림을 처리하기 위해 싱크를 조언하는 연결을 관리합니다. 클라이언트가 데이터 개체에서 데이터 변경 알림을 받으려면 클라이언트는 조언 싱크라는 개체에 [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) 인터페이스를 구현해야 합니다. 그런 다음 클라이언트가 호출하면 `IDataObject::DAdvise`데이터 개체와 조언 싱크 사이에 연결이 설정됩니다.

클래스는 `IDataObjectImpl` 디버그 `IDataObject` 빌드에서 `IUnknown` 덤프 장치에 정보를 전송하여 구현 및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::D조언

데이터 개체와 조언 싱크 사이의 연결을 설정합니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

이렇게 하면 조언 싱크 개체의 변경 내용 알림을 받을 수 있습니다.

연결을 종료하려면 [DUnadvise](#dunadvise)로 전화하십시오.

[IDataObject::DWindows](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) SDK에서 조언참조.

## <a name="idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::Dunadvise

[DAdvise](#dadvise)를 통해 이전에 설정된 연결을 종료합니다.

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>설명

Windows SDK에서 [iDataObject::DUnadvise를](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) 참조하십시오.

## <a name="idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl::에이넘어

현재 권고 연결을 반복할 열거형기를 만듭니다.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

[IDataObject::열거윈도우](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) SDK에서 조언.

## <a name="idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IDataObjectImpl::에이넘 포맷등

데이터 개체에서 지원하는 `FORMATETC` 구조를 반복할 열거체를 만듭니다.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>설명

윈도우 SDK에서 [IDataObject::에이그넘포맷등](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) 참조.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

## <a name="idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl::FireDatachange

현재 관리 중인 각 조언 싱크에 변경 알림을 다시 보냅니다.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc

논리적으로 동등한 `FORMATETC` 구조를 더 복잡한 구조로 검색합니다.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

참조 [IDataObject::GetCanFormat기타](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) 윈도우 SDK에서.

## <a name="idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl::GetData

데이터 개체에서 클라이언트로 데이터를 전송합니다.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>설명

*pformatetcIn* 매개 변수는 TYMED_MFPICT 저장소 매체 유형을 지정해야 합니다.

[IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 윈도우 SDK를 참조하십시오.

## <a name="idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl::GetDataHere

`GetData`클라이언트를 제외한 것과 유사하게 `STGMEDIUM` 구조를 할당해야 합니다.

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IDataObject::GetData여기](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) 윈도우 SDK에서 참조하십시오.

## <a name="idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl::쿼리GetData

데이터 개체가 데이터 전송을 `FORMATETC` 위한 특정 구조를 지원하는지 여부를 결정합니다.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

Windows SDK에서 [IDataObject::QueryGetData를](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) 참조하십시오.

## <a name="idataobjectimplsetdata"></a><a name="setdata"></a>IData개체임플::세트데이터

클라이언트에서 데이터 개체로 데이터를 전송합니다.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

Windows SDK에서 [IDataObject::SetData를](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
