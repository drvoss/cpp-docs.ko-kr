---
title: ATL Typedef
ms.date: 11/04/2016
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
ms.openlocfilehash: f3db32e85ea9cba1e946db6259c00c621650e969
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423605"
---
# <a name="atl-typedefs"></a>ATL Typedef

액티브 템플릿 라이브러리에는 다음 형식 정의를 포함 합니다.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)기반으로 하는 typedef로 정의 됩니다.|
|[_ATL_COM_MODULE](#_atl_com_module)|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)기반으로 하는 typedef로 정의 됩니다.|
|[_ATL_MODULE](#_atl_module)|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)기반으로 하는 typedef로 정의 됩니다.|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 기반으로 하는 typedef로 정의 됨|
|[ATL_URL_PORT](#atl_url_port)|포트 번호를 지정 하기 위해 [말아](../../atl/reference/curl-class.md) 에서 사용 하는 형식입니다.|
|[CComDispatchDriver](#ccomdispatchdriver)|이 클래스는 COM 인터페이스 포인터를 관리 합니다.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|사용 되는 스레딩 모델에 관계 없이 적절 한 스레드 모델 메서드를 호출 합니다.|
|[CComObjectThreadModel](#ccomobjectthreadmodel)|사용 되는 스레딩 모델에 관계 없이 적절 한 스레드 모델 메서드를 호출 합니다.|
|[CContainedWindow](#ccontainedwindow)|이 클래스는 `CContainedWindowT`의 특수화입니다.|
|[CPath](#cpath)|`CString`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.|
|[CPathA](#cpatha)|`CStringA`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.|
|[CPathW](#cpathw)|`CStringW`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.|
|[CSimpleValArray](#csimplevalarray)|단순 형식을 저장 하기 위한 배열을 나타냅니다.|
|[DefaultThreadTraits](#defaultthreadtraits)|기본 스레드 특성 클래스입니다.|
|[LPCURL](#lpcurl)|상수 [말아](../../atl/reference/curl-class.md) 개체에 대 한 포인터입니다.|
|[LPURL](#lpurl)|[말아](../../atl/reference/curl-class.md) 개체에 대 한 포인터입니다.|

##  <a name="_atl_base_module"></a>_ATL_BASE_MODULE

_ATL_BASE_MODULE70 기반으로 하는 typedef로 정의 됩니다.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>설명

모든 ATL 프로젝트에서 사용 됩니다. [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)기반.

ATL 7.0 모듈 클래스의 일부인 클래스는 _ATL_BASE_MODULE 구조체에서 파생 됩니다.  ATL 모듈 클래스에 대 한 자세한 내용은 [COM 모듈 클래스](../../atl/com-modules-classes.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="_atl_com_module"></a>_ATL_COM_MODULE

_ATL_COM_MODULE70 기반으로 하는 typedef로 정의 됩니다.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>설명

COM 기능을 사용 하는 ATL 프로젝트에서 사용 됩니다. [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)기반.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="_atl_module"></a>_ATL_MODULE

_ATL_MODULE70 기반으로 하는 typedef로 정의 됩니다.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>요구 사항

**헤더:**

### <a name="remarks"></a>설명

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)기반.

##  <a name="_atl_win_module"></a>_ATL_WIN_MODULE

_ATL_WIN_MODULE70 기반으로 하는 typedef로 정의 됩니다.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>설명

창 및 기능을 사용 하는 ATL 프로젝트에서 사용 됩니다. [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)기반.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="atl_url_port"></a>ATL_URL_PORT

포트 번호를 지정 하기 위해 [말아](curl-class.md) 에서 사용 하는 형식입니다.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="ccomdispatchdriver"></a>CComDispatchDriver

이 클래스는 COM 인터페이스 포인터를 관리 합니다.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel

사용 되는 스레딩 모델에 관계 없이 적절 한 스레드 모델 메서드를 호출 합니다.

```
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComGlobalsThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>설명

응용 프로그램에서 사용 하는 스레딩 모델에 따라 **typedef** 이름 `CComGlobalsThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 참조 합니다. 이러한 클래스는 임계 영역 클래스를 참조 하는 추가 `typedef` 이름을 제공 합니다.

> [!NOTE]
> `CComGlobalsThreadModel` [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)클래스를 참조 하지 않습니다.

`CComGlobalsThreadModel`를 사용 하면 특정 스레딩 모델 클래스를 지정할 수 있습니다. 사용 되는 스레딩 모델에 관계 없이 적절 한 메서드가 호출 됩니다.

`CComGlobalsThreadModel`이외에도 ATL은 **typedef** 이름 [CComObjectThreadModel](#ccomobjectthreadmodel)을 제공 합니다. 각 `typedef`에서 참조 하는 클래스는 다음 표에 나와 있는 것 처럼 사용 된 스레딩 모델에 따라 달라 집니다.

|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

단일 개체 클래스 내에서 `CComObjectThreadModel`를 사용 합니다. 프로그램에서 전역적으로 사용할 수 있는 개체의 `CComGlobalsThreadModel` 또는 여러 스레드에서 모듈 리소스를 보호 하려는 경우에 사용 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="ccomobjectthreadmodel"></a>CComObjectThreadModel

사용 되는 스레딩 모델에 관계 없이 적절 한 스레드 모델 메서드를 호출 합니다.

```
#if defined(_ATL_SINGLE_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_APARTMENT_THREADED)
typedef CComSingleThreadModel CComObjectThreadModel;
#elif defined(_ATL_FREE_THREADED)
typedef CComMultiThreadModel CComObjectThreadModel;
#else
#pragma message ("No global threading model defined")
#endif
```

### <a name="remarks"></a>설명

응용 프로그램에서 사용 하는 스레딩 모델에 따라 `typedef` 이름은 `CComObjectThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 참조 합니다. 이러한 클래스는 임계 영역 클래스를 참조 하는 추가 `typedef` 이름을 제공 합니다.

> [!NOTE]
> `CComObjectThreadModel` [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)클래스를 참조 하지 않습니다.

`CComObjectThreadModel`를 사용 하면 특정 스레딩 모델 클래스를 지정할 수 있습니다. 사용 되는 스레딩 모델에 관계 없이 적절 한 메서드가 호출 됩니다.

`CComObjectThreadModel`이외에도 ATL은 **typedef** 이름 [CComGlobalsThreadModel](#ccomglobalsthreadmodel)을 제공 합니다. 각 **typedef** 에서 참조 하는 클래스는 다음 표에 나와 있는 것 처럼 사용 된 스레딩 모델에 따라 달라 집니다.

|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

단일 개체 클래스 내에서 `CComObjectThreadModel`를 사용 합니다. 프로그램에서 전역적으로 사용할 수 있는 개체 또는 여러 스레드에서 모듈 리소스를 보호 하려는 경우에 `CComGlobalsThreadModel`를 사용 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="ccontainedwindow"></a>CContainedWindow

이 클래스는 `CContainedWindowT`의 특수화입니다.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>요구 사항

**헤더:.**

### <a name="remarks"></a>설명

`CContainedWindow`는 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)의 특수화입니다. 기본 클래스 또는 특성을 변경 하려면 `CContainedWindowT`를 직접 사용 합니다.

##  <a name="cpath"></a>CPath

`CString`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>요구 사항

**헤더:** 이 경로 .h

##  <a name="cpatha"></a>CPathA

`CStringA`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>요구 사항

**헤더:** 이 경로 .h

##  <a name="cpathw"></a>CPathW

`CStringW`사용 하는 [Cpatht](../../atl/reference/cpatht-class.md) 의 특수화입니다.

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>요구 사항

**헤더:** 이 경로 .h

##  <a name="csimplevalarray"></a>CSimpleValArray

단순 형식을 저장 하기 위한 배열을 나타냅니다.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>설명

단순 데이터 형식이 포함 된 배열을 만들고 관리 하기 위한 `CSimpleValArray` 제공 됩니다. [CSimpleArray](../../atl/reference/csimplearray-class.md)의 간단한 #define입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll

##  <a name="lpcurl"></a>LPCURL

상수 [말아](../../atl/reference/curl-class.md) 개체에 대 한 포인터입니다.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="defaultthreadtraits"></a>DefaultThreadTraits

기본 스레드 특성 클래스입니다.

### <a name="syntax"></a>구문

```
#if defined(_MT)
   typedef CRTThreadTraits DefaultThreadTraits;
#else
   typedef Win32ThreadTraits DefaultThreadTraits;
#endif
```

## <a name="remarks"></a>설명

현재 프로젝트에서 다중 스레드 CRT를 사용 하는 경우 DefaultThreadTraits은 CRTThreadTraits로 정의 됩니다. 그렇지 않으면 Win32ThreadTraits가 사용 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="lpurl"></a>LPURL

[말아](../../atl/reference/curl-class.md) 개체에 대 한 포인터입니다.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>요구 사항

**헤더:**

## <a name="see-also"></a>참고 항목

[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)<br/>
[함수](../../atl/reference/atl-functions.md)<br/>
[전역 변수](../../atl/reference/atl-global-variables.md)<br/>
[클래스 및 구조체](../../atl/reference/atl-classes.md)<br/>
[매크로](../../atl/reference/atl-macros.md)
