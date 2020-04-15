---
title: ATL 형식 정의
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
ms.openlocfilehash: 5548bee36ac52dbd6add31241714b0404289be45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319191"
---
# <a name="atl-typedefs"></a>ATL 형식 정의

활성 템플릿 라이브러리에는 다음 형식defs가 포함됩니다.

|||
|-|-|
|[_ATL_BASE_MODULE](#_atl_base_module)|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)을 기반으로 하는 형식def로 정의됩니다.|
|[_ATL_COM_MODULE](#_atl_com_module)|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)을 기반으로 하는 형식def로 정의됩니다.|
|[_ATL_MODULE](#_atl_module)|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)을 기반으로 하는 형식def로 정의됩니다.|
|[_ATL_WIN_MODULE](#_atl_win_module)|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 기반으로 하는 형식def로 정의|
|[ATL_URL_PORT](#atl_url_port)|포트 번호를 지정하기 위해 [CUrl에서](../../atl/reference/curl-class.md) 사용하는 형식입니다.|
|[CComDispatch 드라이버](#ccomdispatchdriver)|이 클래스는 COM 인터페이스 포인터를 관리합니다.|
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|사용 중인 스레딩 모델에 관계없이 적절한 스레드 모델 메서드를 호출합니다.|
|[CComObject스레드모델](#ccomobjectthreadmodel)|사용 중인 스레딩 모델에 관계없이 적절한 스레드 모델 메서드를 호출합니다.|
|[CContained윈도우](#ccontainedwindow)|이 클래스는 의 `CContainedWindowT`전문 분야입니다.|
|[C패스 (주)](#cpath)|를 사용하는 `CString` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.|
|[CPathA](#cpatha)|를 사용하는 `CStringA` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.|
|[C패스W](#cpathw)|를 사용하는 `CStringW` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.|
|[심플발어레이](#csimplevalarray)|간단한 형식을 저장하기 위한 배열을 나타냅니다.|
|[기본 스레드 특성](#defaultthreadtraits)|기본 스레드 특성 클래스입니다.|
|[LPCURL](#lpcurl)|상수 [CUrl](../../atl/reference/curl-class.md) 개체에 대한 포인터입니다.|
|[LPURL](#lpurl)|[CUrl](../../atl/reference/curl-class.md) 개체에 대한 포인터입니다.|

## <a name="_atl_base_module"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE

_ATL_BASE_MODULE70 기반으로 하는 형식def로 정의됩니다.

```
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;
```

### <a name="remarks"></a>설명

모든 ATL 프로젝트에 사용됩니다. [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).

ATL 7.0 모듈 클래스의 일부인 클래스는 _ATL_BASE_MODULE 구조에서 파생됩니다.  ATL 모듈 클래스에 대한 자세한 내용은 [COM 모듈 클래스를](../../atl/com-modules-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="_atl_com_module"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE

_ATL_COM_MODULE70 기반으로 하는 형식def로 정의됩니다.

```
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;
```

### <a name="remarks"></a>설명

COM 기능을 사용하는 ATL 프로젝트에서 사용합니다. [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="_atl_module"></a><a name="_atl_module"></a>_ATL_MODULE

_ATL_MODULE70 기반으로 하는 형식def로 정의됩니다.

```
typedef ATL::_ATL_MODULE70 _ATL_MODULE;
```

## <a name="requirements"></a>요구 사항

**헤더:**

### <a name="remarks"></a>설명

[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).

## <a name="_atl_win_module"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE

_ATL_WIN_MODULE70 기반으로 하는 형식def로 정의됩니다.

```
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE;
```

### <a name="remarks"></a>설명

창 기능을 사용하는 모든 ATL 프로젝트에서 사용됩니다. [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atl_url_port"></a><a name="atl_url_port"></a>ATL_URL_PORT

포트 번호를 지정하기 위해 [CUrl에서](curl-class.md) 사용하는 형식입니다.

```
typedef WORD ATL_URL_PORT;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatch 드라이버

이 클래스는 COM 인터페이스 포인터를 관리합니다.

```
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobals스레드모델

사용 중인 스레딩 모델에 관계없이 적절한 스레드 모델 메서드를 호출합니다.

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

응용 프로그램에서 사용하는 스레딩 모델에 따라 **typedef** 이름은 `CComGlobalsThreadModel` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)을 참조합니다. 이러한 클래스는 `typedef` 중요 섹션 클래스를 참조하는 추가 이름을 제공합니다.

> [!NOTE]
> `CComGlobalsThreadModel`클래스 [CComMultiThreadModelNoCS를](../../atl/reference/ccommultithreadmodelnocs-class.md)참조하지 않습니다.

사용 `CComGlobalsThreadModel` 하면 특정 스레딩 모델 클래스를 지정 할 수 없습니다. 사용 중인 스레딩 모델에 관계없이 적절한 메서드가 호출됩니다.

ATL은 **형식 def** 이름 [CComObjectThreadModel을](#ccomobjectthreadmodel)제공합니다. `CComGlobalsThreadModel` 각 `typedef` 클래스에서 참조하는 클래스는 다음 표와 같이 사용되는 스레딩 모델에 따라 다릅니다.

|형식 정의|단일 스레딩|아파트 스레딩|무료 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S `CComSingleThreadModel`= ; M =`CComMultiThreadModel`

단일 `CComObjectThreadModel` 개체 클래스 내에서 사용합니다. 프로그램에서 `CComGlobalsThreadModel` 전역적으로 사용할 수 있는 개체또는 여러 스레드에서 모듈 리소스를 보호하려는 경우에 사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObject스레드모델

사용 중인 스레딩 모델에 관계없이 적절한 스레드 모델 메서드를 호출합니다.

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

응용 프로그램에서 사용하는 스레딩 모델에 `typedef` 따라 `CComObjectThreadModel` 이름은 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)을 참조합니다. 이러한 클래스는 `typedef` 중요 섹션 클래스를 참조하는 추가 이름을 제공합니다.

> [!NOTE]
> `CComObjectThreadModel`클래스 [CComMultiThreadModelNoCS를](../../atl/reference/ccommultithreadmodelnocs-class.md)참조하지 않습니다.

사용 `CComObjectThreadModel` 하면 특정 스레딩 모델 클래스를 지정 할 수 없습니다. 사용 중인 스레딩 모델에 관계없이 적절한 메서드가 호출됩니다.

ATL은 `CComObjectThreadModel` **형식 def** 이름 [CComGlobalsThread Model을](#ccomglobalsthreadmodel)제공합니다. 각 **typedef에서** 참조하는 클래스는 다음 표와 같이 사용되는 스레딩 모델에 따라 다릅니다.

|형식 정의|단일 스레딩|아파트 스레딩|무료 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S `CComSingleThreadModel`= ; M =`CComMultiThreadModel`

단일 `CComObjectThreadModel` 개체 클래스 내에서 사용합니다. 프로그램에서 `CComGlobalsThreadModel` 전역적으로 사용할 수 있는 개체또는 여러 스레드에서 모듈 리소스를 보호하려는 경우에 사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccontainedwindow"></a><a name="ccontainedwindow"></a>CContained윈도우

이 클래스는 의 `CContainedWindowT`전문 분야입니다.

```
typedef CContainedWindowT<CWindow> CContainedWindow;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

### <a name="remarks"></a>설명

`CContainedWindow`[는 CContained윈도우T의](../../atl/reference/ccontainedwindowt-class.md)전문화입니다. 기본 클래스 나 특성을 변경하려면 `CContainedWindowT` 직접 사용하십시오.

## <a name="cpath"></a><a name="cpath"></a>C패스 (주)

를 사용하는 `CString` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.

```
typedef CPathT<CString> CPath;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h

## <a name="cpatha"></a><a name="cpatha"></a>CPathA

를 사용하는 `CStringA` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.

```
typedef CPathT<CStringA> CPathA;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h

## <a name="cpathw"></a><a name="cpathw"></a>C패스W

를 사용하는 `CStringW` [CPathT의](../../atl/reference/cpatht-class.md) 전문화.

```
typedef ATL::CPathT<CStringW> CPathW;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlpath.h

## <a name="csimplevalarray"></a><a name="csimplevalarray"></a>심플발어레이

간단한 형식을 저장하기 위한 배열을 나타냅니다.

```
#define CSimpleValArray CSimpleArray
```

### <a name="remarks"></a>설명

`CSimpleValArray`은 간단한 데이터 형식을 포함하는 배열을 만들고 관리하기 위해 제공됩니다. 그것은 [CSimpleArray의](../../atl/reference/csimplearray-class.md)간단한 #define.

## <a name="requirements"></a>요구 사항

**헤더:** 아시프콜.h

## <a name="lpcurl"></a><a name="lpcurl"></a>LPCURL

상수 [CUrl](../../atl/reference/curl-class.md) 개체에 대한 포인터입니다.

```
typedef const CUrl* LPCURL;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="defaultthreadtraits"></a><a name="defaultthreadtraits"></a>기본 스레드 특성

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

현재 프로젝트에서 다중 스레드 CRT를 사용하는 경우 DefaultThreadTraits는 CRTThreadTraits로 정의됩니다. 그렇지 않으면 Win32ThreadTraits가 사용됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="lpurl"></a><a name="lpurl"></a>LPURL

[CUrl](../../atl/reference/curl-class.md) 개체에 대한 포인터입니다.

```
typedef CUrl* LPURL;
```

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="see-also"></a>참고 항목

[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)<br/>
[Functions](../../atl/reference/atl-functions.md)<br/>
[전역 변수](../../atl/reference/atl-global-variables.md)<br/>
[클래스 및 구조체](../../atl/reference/atl-classes.md)<br/>
[매크로](../../atl/reference/atl-macros.md)
