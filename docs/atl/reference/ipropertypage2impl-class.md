---
title: IPropertyPage2Impl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: d112a2411a9debbf2eb77e6b851f4500e8d32ab8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329588"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl 클래스

이 클래스는 `IUnknown` [IPropertyPageImpl의](../../atl/reference/ipropertypageimpl-class.md)기본 구현을 구현하고 상속합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IPropertyPage2Impl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IPropertyPage2Impl::편집속성](#editproperty)|속성 페이지가 활성화될 때 포커스를 받을 속성 컨트롤을 지정합니다. ATL 구현은 E_NOTIMPL 반환합니다.|

## <a name="remarks"></a>설명

[IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) 인터페이스는 `EditProperty` 메서드를 추가하여 [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage)를 확장합니다. 이 메서드를 사용 하 고 클라이언트속성 페이지 개체에서 특정 속성을 선택할 수 있습니다.

클래스는 `IPropertyPage2Impl` 단순히 `IPropertyPage2::EditProperty`에 대한 E_NOTIMPL 반환합니다. 그러나 [IPropertyPageImpl의](../../atl/reference/ipropertypageimpl-class.md) 기본 구현을 상속 하 `IUnknown` 고 디버그 빌드에서 덤프 장치에 정보를 전송 하 여 구현 합니다.

속성 페이지를 만들 때 클래스는 일반적으로 에서 `IPropertyPageImpl`파생됩니다. `IPropertyPage2`의 추가 지원을 제공하려면 클래스 정의를 수정하고 `EditProperty` 메서드를 재정의합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a>IPropertyPage2Impl::편집속성

속성 페이지가 활성화될 때 포커스를 받을 속성 컨트롤을 지정합니다.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

[IPropertyPage2::편집Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) SDK에서 속성 입니다.

## <a name="see-also"></a>참고 항목

[아이퍼프로퍼티브라우징임플 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[I지정속성페이지임플 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
