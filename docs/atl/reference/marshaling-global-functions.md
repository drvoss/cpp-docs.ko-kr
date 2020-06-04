---
title: 마샬링 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: b839e93b6251a09ce79df60a49b4054d1af76cc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326268"
---
# <a name="marshaling-global-functions"></a>마샬링 전역 함수

이러한 함수는 마샬링 데이터를 인터페이스 포인터로 마샬링하고 변환하는 데 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|마샬링 데이터와 포인터를 해제합니다. `IStream`|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|새 스트림 개체를 만들고 지정된 인터페이스 포인터를 마샬링합니다.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|스트림의 마샬링 데이터를 인터페이스 포인터로 변환합니다.|

## <a name="requirements"></a>요구 사항:

**헤더:** atlbase.h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a>아틀프리마샬스트림

스트림에서 마샬링 데이터를 해제한 다음 스트림 포인터를 해제합니다.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 마샬링에 `IStream` 사용되는 스트림의 인터페이스에 대한 포인터입니다.

### <a name="example"></a>예제

[AtlMarshalPtrInProc에](#atlmarshalptrinproc)대한 예제를 참조하십시오.

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a>아틀마샬프트르인프락

새 스트림 개체를 만들고, 프록시의 CLSID를 스트림에 쓰고, 프록시를 스트림으로 초기화하는 데 필요한 데이터를 작성하여 제공된 인터페이스 포인터를 마샬링합니다.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 마샬링할 인터페이스에 대한 포인터입니다.

*Iid*<br/>
【인】 마샬링되는 인터페이스의 GUID입니다.

*ppStream*<br/>
【아웃】 마샬링에 `IStream` 사용되는 새 스트림 개체의 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

포인터를 여러 스트림으로 마샬링할 수 있도록 MSHLFLAGS_TABLESTRONG 플래그가 설정됩니다. 포인터는 여러 번 마샬링해제할 수도 있습니다.

마샬링에 실패하면 스트림 포인터가 해제됩니다.

`AtlMarshalPtrInProc`프로세스 내 개체에 대한 포인터에서만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a>아틀룬마샬프트르

스트림의 마샬링 데이터를 클라이언트에서 사용할 수 있는 인터페이스 포인터로 변환합니다.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 마샬링되지 않은 스트림에 대한 포인터입니다.

*Iid*<br/>
【인】 마샬링되지 않은 인터페이스의 GUID입니다.

*ppunk*<br/>
【아웃】 마샬링되지 않은 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="example"></a>예제

[AtlMarshalPtrInProc에](#atlmarshalptrinproc)대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
