---
title: 개체 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 66a418019ba506a5832c8e3ad86a3764c1186df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326209"
---
# <a name="object-map-macros"></a>개체 맵 매크로

이러한 매크로는 개체 맵과 항목을 정의합니다.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|개체 맵에 입력할 클래스 개체의 텍스트 설명을 지정할 수 있습니다.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|ATL 개체를 개체 맵에 입력하고 레지스트리를 업데이트하고 개체의 인스턴스를 만듭니다.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="declare_object_description"></a><a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

클래스 개체에 대한 텍스트 설명을 지정할 수 있습니다.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 클래스 개체의 설명입니다.

### <a name="remarks"></a>설명

ATL은 [OBJECT_ENTRY_AUTO](#object_entry_auto) 매크로를 통해 개체 맵에 이 설명을 입력합니다.

DECLARE_OBJECT_DESCRIPTION `GetObjectDescription` [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) 메서드를 재정의하는 데 사용할 수 있는 함수를 구현합니다.

함수를 `GetObjectDescription` 호출합니다. `IComponentRegistrar::GetComponents` `IComponentRegistrar`는 DLL에서 개별 구성 요소를 등록하고 등록 취소할 수 있는 자동화 인터페이스입니다. ATL 프로젝트 마법사를 사용하여 구성 요소 레지스트라 개체를 만들면 `IComponentRegistrar` 마법사가 자동으로 인터페이스를 구현합니다. `IComponentRegistrar`일반적으로 Microsoft 트랜잭션 서버에서 사용됩니다.

ATL 프로젝트 마법사에 대한 자세한 내용은 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

ATL 개체를 개체 맵에 입력하고 레지스트리를 업데이트하고 개체의 인스턴스를 만듭니다.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 C++ *클래스에*의해 구현된 COM 클래스의 CLSID입니다.

*class*<br/>
【인】 *clsid로*표시되는 COM 클래스를 구현하는 C++ 클래스의 이름입니다.

### <a name="remarks"></a>설명

개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.

OBJECT_ENTRY_AUTO 자동 생성된 ATL 개체 맵에 이 개체에 대한 작성자 클래스 및 클래스 팩터리 작성자 클래스 함수의 함수 포인터를 `CreateInstance` 입력합니다. [CAtlComModule::RegisterServer가](catlcommodule-class.md#registerserver) 호출되면 개체 맵의 각 개체에 대한 시스템 레지스트리가 업데이트됩니다.

아래 표는 이 매크로에 대한 두 번째 매개 변수로 지정된 클래스에서 개체 맵에 추가된 정보를 가져오는 방법을 설명합니다.

|에 대한 정보|에서 얻은|
|---------------------|-------------------|
|COM 등록|[레지스트리 매크로](../../atl/reference/registry-macros.md)|
|클래스 공장 생성|[클래스 공장 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|
|인스턴스 생성|[집계 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|
|구성 요소 범주 등록|[범주 매크로](../../atl/reference/category-macros.md)|
|클래스 수준의 초기화 및 정리|[개체 메인](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 C++ *클래스에*의해 구현된 COM 클래스의 CLSID입니다.

*class*<br/>
【인】 *clsid로*표시되는 COM 클래스를 구현하는 C++ 클래스의 이름입니다.

### <a name="remarks"></a>설명

개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO 객체를 등록하고 초기화하도록 지정할 수 있지만(자세한 내용은 [OBJECT_ENTRY_AUTO](#object_entry_auto) 참조) 을 `CoCreateInstance`통해 삐걱거리면 안 됩니다.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
