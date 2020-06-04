---
title: 레지스트리 매크로
ms.date: 08/19/2019
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: fd012b4300f4cd72cdc9ab363b770ac1dbefa06e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326040"
---
# <a name="registry-macros"></a>레지스트리 매크로

이러한 매크로는 유용한 형식 라이브러리 및 레지스트리 시설을 정의합니다.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL에 대한 종속성을 피하기 위해 개체의 등록 코드를 개체에 포함하도록 지정함을 나타냅니다. Dll.|
|[DECLARE_LIBID](#declare_libid)|ATL이 형식 라이브러리의 *libid를* 얻을 수 있는 방법을 제공합니다.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|기본 ATL 등록을 방지합니다.|
|[DECLARE_REGISTRY](#declare_registry)|시스템 레지스트리에서 주 개체의 항목을 입력하거나 제거합니다.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|*appid를*자동으로 등록하는 데 필요한 정보를 지정합니다.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|명명된 리소스를 찾아 레지스트리 스크립트를 실행합니다.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 번호로 식별된 리소스를 찾아 레지스트리 스크립트를 실행합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY

ATL에 대한 종속성을 피하기 위해 개체의 등록 코드를 개체에 포함하려는 기호입니다. Dll.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>설명

ATL_STATIC_REGISTRY 정의할 때는 다음 코드를 사용해야 합니다.

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a>DECLARE_LIBID

ATL이 형식 라이브러리의 *libid를* 얻을 수 있는 방법을 제공합니다.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>매개 변수

*Libid*<br/>
형식 라이브러리의 GUID입니다.

### <a name="remarks"></a>설명

`CAtlModuleT`-derived 클래스에서 DECLARE_LIBID 사용합니다.

### <a name="example"></a>예제

어트리뷰션되지 않은 마법사 생성 ATL 프로젝트에는 이 매크로를 사용하는 샘플이 있습니다.

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY

이 매크로가 나타나는 클래스에 대한 기본 ATL 등록을 피하려면 DECLARE_NO_REGISTRY 사용하십시오.

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a>DECLARE_REGISTRY

표준 클래스 등록을 시스템 레지스트리에 입력하거나 시스템 레지스트리에서 제거합니다.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>매개 변수

*class*<br/>
【인】 이전 버전과의 호환성을 위해 포함되어 있습니다.

*pid*<br/>
【인】 버전별 프로그램 식별자인 LPCTSTR입니다.

*vpid*<br/>
【인】 버전 독립적인 프로그램 식별자인 LPCTSTR입니다.

*Nid*<br/>
【인】 레지스트리의 리소스 문자열 인덱스인 UINT는 프로그램의 설명으로 사용할 수 있습니다.

*플래그*<br/>
【인】 레지스트리에 프로그램의 스레딩 모델을 포함하는 DWORD입니다. THREADFLAGS_APARTMENT, THREADFLAGS_BOTH 또는 AUTPRXFLAG의 다음 값 중 하나여야 합니다.

### <a name="remarks"></a>설명

표준 등록은 CLSID, 프로그램 ID, 버전 독립적 프로그램 ID, 설명 문자열 및 스레드 모델로 구성됩니다.

ATL 클래스 추가 마법사를 사용하여 개체 또는 컨트롤을 만들면 마법사가 스크립트 기반 레지스트리 지원을 자동으로 구현하고 [파일에 DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) 매크로를 추가합니다. 스크립트 기반 레지스트리 지원을 원하지 않는 경우 이 매크로를 DECLARE_REGISTRY 바꿔야 합니다. DECLARE_REGISTRY 위에서 설명한 다섯 가지 기본 키만 레지스트리에 삽입합니다. 레지스트리에 다른 키를 삽입하려면 코드를 수동으로 작성해야 합니다.

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID

*appid를*자동으로 등록하는 데 필요한 정보를 지정합니다.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>매개 변수

*리시드 (것)*<br/>
*appid에*대한 정보가 포함된 .rgs 파일의 리소스 ID입니다.

*Appid*<br/>
GUID

### <a name="remarks"></a>설명

`CAtlModuleT`-파생 클래스에서 DECLARE_REGISTRY_APPID_RESOURCEID 사용합니다.

### <a name="example"></a>예제

클래스 추가 코드 마법사를 사용하여 ATL 프로젝트에 추가된 클래스에는 이 매크로를 사용하는 샘플이 있습니다.

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE

레지스트리 파일을 포함하는 명명된 리소스를 가져옵니다 및 시스템 레지스트리에 개체를 입력 하거나 시스템 레지스트리에서 그들을 제거 하는 스크립트를 실행 합니다.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 리소스의 문자열 식별자입니다.

### <a name="remarks"></a>설명

ATL 프로젝트 마법사를 사용하여 개체 또는 컨트롤을 만들면 마법사는 스크립트 기반 레지스트리 지원을 자동으로 구현하고 DECLARE_REGISTRY_RESOURCE 유사한 [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) 매크로를 파일에 추가합니다.

최적화된 레지스트리 액세스를 위해 ATL 레지스트리 구성 요소(등록기관)와 정적으로 연결할 수 있습니다. 등록 기관 코드에 정적으로 연결하려면 *pch.h* 파일에 다음 줄을 추가합니다(Visual Studio 2017 및 이전 의*stdafx.h).*

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL이 런타임에 대체 값을 대체하려면 DECLARE_REGISTRY_RESOURCE 지정하거나 DECLARE_REGISTRY_RESOURCEID 매크로를 지정하지 마십시오. 대신 각 항목에 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자를 대체할 값과 쌍을 이루는 변수 자리 표시자가 포함된 구조의 배열을 만듭니다. 그런 다음 [CAtlModule::업데이트레지스트리FromResourceD](catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS를](catlmodule-class.md#updateregistryfromresources)호출하여 배열을 전달합니다. 이렇게 하면 `_ATL_REGMAP_ENTRIES` 구조의 모든 대체 값이 등록기관의 대체 맵에 추가됩니다.

대체 가능한 매개 변수 및 스크립팅에 대한 자세한 내용은 [ATL 레지스트리 구성 요소(등록기관)](../../atl/atl-registry-component-registrar.md)문서를 참조하십시오.

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID

[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) 마찬가지로 마법사에서 생성된 UINT를 사용하여 문자열 이름이 아닌 리소스를 식별합니다.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 리소스의 마법사 생성 식별자입니다.

### <a name="remarks"></a>설명

ATL 프로젝트 마법사를 사용하여 개체 또는 컨트롤을 만들면 마법사가 스크립트 기반 레지스트리 지원을 자동으로 구현하고 파일에 DECLARE_REGISTRY_RESOURCEID 매크로를 추가합니다.

최적화된 레지스트리 액세스를 위해 ATL 레지스트리 구성 요소(등록기관)와 정적으로 연결할 수 있습니다. 등록 기관 코드에 정적으로 연결하려면 *stdafx.h* 파일에 다음 줄을 추가합니다(Visual Studio 2019*이상pch.h).*

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL이 런타임에 대체 값을 대체하려면 DECLARE_REGISTRY_RESOURCE 지정하거나 DECLARE_REGISTRY_RESOURCEID 매크로를 지정하지 마십시오. 대신 각 항목에 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자를 대체할 값과 쌍을 이루는 변수 자리 표시자가 포함된 구조의 배열을 만듭니다. 그런 다음 [CAtlModule::업데이트레지스트리FromResourceD](catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS를](catlmodule-class.md#updateregistryfromresources)호출하여 배열을 전달합니다. 이렇게 하면 `_ATL_REGMAP_ENTRIES` 구조의 모든 대체 값이 등록기관의 대체 맵에 추가됩니다.

대체 가능한 매개 변수 및 스크립팅에 대한 자세한 내용은 [ATL 레지스트리 구성 요소(등록기관)](../../atl/atl-registry-component-registrar.md)문서를 참조하십시오.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
