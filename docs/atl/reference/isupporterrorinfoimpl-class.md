---
title: ISupportErrorInfoImpl 클래스
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 4c60b58ba697f00b146077a2cdecd727fe2cac02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326374"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl 클래스

이 클래스는 [ISupportErrorInfo 인터페이스의](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) 기본 구현을 제공하며 단일 인터페이스만 개체에 오류를 생성할 때 사용할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>매개 변수

*piid*<br/>
[IErrorInfo를](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)지원하는 인터페이스의 IID에 대한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[ISupportErrorInfoImpl::인터페이스지원오류정보](#interfacesupportserrorinfo)|로 식별된 `riid` 인터페이스가 [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스를 지원하는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

[ISupportErrorInfo 인터페이스는](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) 오류 정보를 클라이언트에 반환할 수 있도록 합니다. 를 사용하는 `IErrorInfo` 개체는 을 구현해야 `ISupportErrorInfo`합니다.

클래스는 `ISupportErrorInfoImpl` `ISupportErrorInfo` 기본 구현을 제공하며 단일 인터페이스만 개체에 오류를 생성할 때 사용할 수 있습니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::인터페이스지원오류정보

로 식별된 `riid` 인터페이스가 [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) 인터페이스를 지원하는지 여부를 나타냅니다.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>설명

[ISupportErrorInfo::인터페이스지원윈도우](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) SDK에서 오류정보.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
