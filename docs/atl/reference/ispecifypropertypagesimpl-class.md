---
title: I지정속성페이지임플 클래스
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 06b6b60227a659bd35e042952c7464971fc40bdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326406"
---
# <a name="ispecifypropertypagesimpl-class"></a>I지정속성페이지임플 클래스

이 클래스는 `IUnknown` [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) 인터페이스의 기본 구현을 구현하 고 제공 합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `ISpecifyPropertyPagesImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I지정속성페이지임플::페이지 받기](#getpages)|계산된 UUID 값 배열을 채웁니다. 각 UUID는 개체의 속성 시트에 표시할 수 있는 속성 페이지 중 하나에 대한 CLSID에 해당합니다.|

## <a name="remarks"></a>설명

[ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) 인터페이스를 사용하면 클라이언트가 개체에서 지원하는 속성 페이지에 대한 CLSI 목록을 가져올 수 있습니다. 클래스는 `ISpecifyPropertyPagesImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

> [!NOTE]
> 개체가 `ISpecifyPropertyPages` 속성 페이지를 지원하지 않는 경우 인터페이스를 노출하지 마십시오.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a>I지정속성페이지임플::페이지 받기

개체의 속성 시트에 표시할 수 있는 속성 페이지에 대 한 CLSID를 포함 하 고 [CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) 구조의 배열을 채웁니다.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용하여 각 CLSID를 검색합니다.

Windows SDK의 [I지정속성 페이지::GetPages를](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) 참조하십시오.

## <a name="see-also"></a>참고 항목

[IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)<br/>
[아이퍼프로퍼티브라우징임플 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
