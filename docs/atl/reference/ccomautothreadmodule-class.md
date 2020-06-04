---
title: CComAutoThreadModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 391354c5672cf15c0286491619a13c6005493cfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321062"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule 클래스

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>매개 변수

*스레드 알로카이터*<br/>
【인】 스레드 선택을 관리하는 클래스입니다. 기본값은 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)입니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Createinstance](#createinstance)|스레드를 선택한 다음 연결된 아파트에서 개체를 만듭니다.|
|[GetDefault스레드](#getdefaultthreads)|(정적) 프로세서 수에 따라 모듈의 스레드 수를 동적으로 계산합니다.|
|[Init](#init)|모듈의 스레드를 만듭니다.|
|[잠금](#lock)|모듈 및 현재 스레드의 잠금 수를 증가시입니다.|
|[잠금을 해제](#unlock)|모듈 및 현재 스레드의 잠금 수를 감소시입니다.|

### <a name="data-members"></a>데이터 멤버

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[dwThreadID](#dwthreadid)|현재 스레드의 식별자를 포함합니다.|
|[m_Allocator](#m_allocator)|스레드 선택을 관리합니다.|
|[m_nThreads](#m_nthreads)|모듈의 스레드 수를 포함합니다.|
|[m_pApartments](#m_papartments)|모듈의 아파트를 관리합니다.|

## <a name="remarks"></a>설명

> [!NOTE]
> 이 클래스는 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및 [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스로 대체되었기 때문에 더 이상 사용되지 않습니다. 다음 정보는 ATL의 이전 릴리스와 함께 사용할 수 있습니다.

`CComAutoThreadModule`을 사용하므로 [CComModule에서](../../atl/reference/ccommodule-class.md) 파생되어 EXE 및 Windows 서비스에 대한 스레드 풀리풀아파트 모델 COM 서버를 구현합니다. `CComAutoThreadModule`[CComApartment를](../../atl/reference/ccomapartment-class.md) 사용하여 모듈의 각 스레드에 대한 아파트를 관리합니다.

여러 아파트에서 `CComAutoThreadModule` 객체를 만들려는 경우모듈을 파생시. 또한 개체의 클래스 정의에 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 매크로를 포함해야 [CComClassFactoryAutoThread를](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 지정합니다.

기본적으로 ATL COM 앱 마법사(Visual Studio .NET의 ATL 프로젝트 마법사)는 에서 `CComModule`모듈을 파생합니다. 사용하려면 `CComAutoThreadModule`클래스 정의를 수정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CCom자동 스레드 모듈::만들기 인스턴스

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*pfnCreate인스턴스*<br/>
【인】 작성자 함수에 대한 포인터입니다.

*riid*<br/>
【인】 요청된 인터페이스의 IID입니다.

*ppvObj*<br/>
【아웃】 *riid로*식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *ppvObj가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

스레드를 선택한 다음 연결된 아파트에서 개체를 만듭니다.

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAuto스레드모듈::d스레드ID

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>설명

현재 스레드의 식별자를 포함합니다.

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CCom자동 스레드 모듈::getDefault스레드

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Return Value

EXE 모듈에서 생성할 스레드 수입니다.

### <a name="remarks"></a>설명

이 정적 함수는 프로세서 수에 따라 EXE 모듈의 최대 스레드 수를 동적으로 계산합니다. 기본적으로 이 반환 값은 [Init](#init) 메서드에 전달되어 스레드를 만듭니다.

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThread 모듈::init

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 개체 맵 항목의 배열에 대한 포인터입니다.

*H*<br/>
【인】 HINSTANCE또는에 `DLLMain` `WinMain`전달되었습니다.

*plibid*<br/>
【인】 프로젝트와 연결된 형식 라이브러리의 LIBID에 대한 포인터입니다.

*n스레드*<br/>
【인】 만들 스레드 수입니다. 기본적으로 *nThread는* [GetDefaultThread에서 반환하는 값입니다.](#getdefaultthreads)

### <a name="remarks"></a>설명

데이터 멤버를 초기화하고 *nThread에서*지정한 스레드 수를 만듭니다.

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a>CComAutoThread모듈::잠금

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
LONG Lock();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

모듈 및 현재 스레드의 잠금 수에 대해 원자성 증분을 수행합니다. `CComAutoThreadModule`은 모듈 잠금 수를 사용하여 클라이언트가 모듈에 액세스하고 있는지 여부를 확인합니다. 현재 스레드의 잠금 수는 통계 목적으로 사용됩니다.

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a>CComAuto스레드 모듈::m_Allocator

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>설명

스레드 선택을 관리하는 개체입니다. 기본적으로 `ThreadAllocator` 클래스 템플릿 매개 변수는 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)입니다.

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a>CComAuto스레드 모듈::m_nThreads

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
int m_nThreads;
```

### <a name="remarks"></a>설명

EXE 모듈의 스레드 수를 포함합니다. [Init가](#init) 호출되면 `m_nThreads` nThreads 매개 변수 값으로 *설정됩니다.* 각 스레드의 관련 아파트는 [CComApartment](../../atl/reference/ccomapartment-class.md) 개체에 의해 관리됩니다.

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a>CComAuto스레드 모듈::m_pApartments

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>설명

모듈에서 아파트를 관리하는 [각각의 CComApartment](../../atl/reference/ccomapartment-class.md) 개체 배열을 가리킵니다. 배열의 요소 수는 [m_nThreads](#m_nthreads) 멤버를 기반으로 합니다.

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a>CComAutoThread모듈::잠금 해제

ATL 7.0은 `CComAutoThreadModule` 더 이상 사용되지 않습니다: 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

```
LONG Unlock();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

모듈 및 현재 스레드의 잠금 수에 대한 원자감소를 수행합니다. `CComAutoThreadModule`은 모듈 잠금 수를 사용하여 클라이언트가 모듈에 액세스하고 있는지 여부를 확인합니다. 현재 스레드의 잠금 수는 통계 목적으로 사용됩니다.

모듈 잠금 수가 0에 도달하면 모듈을 언로드할 수 있습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
