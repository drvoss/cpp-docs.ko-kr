---
title: ATL Typedefs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d721cefd20ae5eb208c74d973069fb9365273d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-typedefs"></a>ATL Typedefs
액티브 템플릿 라이브러리는 다음 형식 정의 포함합니다.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|형식 정의 기반으로 정의 된 [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)합니다.|  
|[_ATL_COM_MODULE](#_atl_com_module)|형식 정의 기반으로 정의 된 [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)합니다.|  
|[_ATL_MODULE](#_atl_module)|형식 정의 기반으로 정의 된 [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)합니다.|  
|[_ATL_WIN_MODULE](#_atl_win_module)|형식 정의 기반으로 정의 된 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|사용 되는 형식을 [CUrl](../../atl/reference/curl-class.md) 포트 번호를 지정 하는 데 있습니다.|  
|[CComDispatchDriver](#ccomdispatchdriver)|이 클래스는 COM 인터페이스 포인터를 관리합니다.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|적절 한 스레드 사용 되는 스레딩 모델에 관계 없이 모델 메서드를 호출 합니다.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|적절 한 스레드 사용 되는 스레딩 모델에 관계 없이 모델 메서드를 호출 합니다.|  
|[CContainedWindow](#ccontainedwindow)|이 클래스의 특수화는 **CContainedWindowT 합니다.**|  
|[CPath](#cpath)|특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CString`합니다.|  
|[CPathA](#cpatha)|특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringA`합니다.|  
|[CPathW](#cpathw)|특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringW`합니다.|  
|[CSimpleValArray](#csimplevalarray)|단순 형식 저장 하기 위한 배열을 나타냅니다.|  
|[DefaultThreadTraits](#defaultthreadtraits)|기본 스레드 특성 클래스입니다.|  
|[LPCURL](#lpcurl)|상수에 대 한 포인터 [CUrl](../../atl/reference/curl-class.md) 개체입니다.|  
|[LPURL](#lpurl)|에 대 한 포인터는 [CUrl](../../atl/reference/curl-class.md) 개체입니다.|  
  
##  <a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 _ATL_BASE_MODULE70에 따라 형식 정의로 정의 됩니다.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>설명  
 모든 ATL 프로젝트에서 사용 합니다. 에 따라 [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)합니다.  
  
 ATL 7.0 모듈 클래스의 일부인 클래스 _ATL_BASE_MODULE 구조에서 파생 됩니다.  ATL 모듈 클래스에 대 한 자세한 내용은 참조 [COM 모듈 클래스](../../atl/com-modules-classes.md)합니다.  

## <a name="requirements"></a>요구 사항
**헤더:** atlcore.h

##  <a name="_atl_com_module"></a>_ATL_COM_MODULE  
 _ATL_COM_MODULE70에 따라 형식 정의로 정의 됩니다.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>설명  
 COM 기능을 사용 하는 ATL 프로젝트에서 사용 합니다. 에 따라 [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)합니다.  

## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h
  
##  <a name="_atl_module"></a>_ATL_MODULE  
 _ATL_MODULE70에 따라 형식 정의로 정의 됩니다.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
## <a name="requirements"></a>요구 사항
**헤더:** 
  
### <a name="remarks"></a>설명  
 에 따라 [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)합니다.  
  
##  <a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 _ATL_WIN_MODULE70에 따라 형식 정의로 정의 됩니다.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>설명  
 창 작업 기능을 사용 하는 ATL 프로젝트에서 사용 합니다. 에 따라 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)합니다.  

## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h 
  
##  <a name="atl_url_port"></a>ATL_URL_PORT 
  사용 되는 형식을 [CUrl](curl-class.md) 포트 번호를 지정 하는 데 있습니다.
```  
typedef WORD ATL_URL_PORT;
```  

## <a name="requirements"></a>요구 사항
**헤더:** atlutil.h

##  <a name="ccomdispatchdriver"></a>CComDispatchDriver  
 이 클래스는 COM 인터페이스 포인터를 관리합니다.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h
  
##  <a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 적절 한 스레드 사용 되는 스레딩 모델에 관계 없이 모델 메서드를 호출 합니다.  
  
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
 응용 프로그램에서 사용 되는 스레딩 모델에 따라는 `typedef` 이름 `CComGlobalsThreadModel` 참조 하거나 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)합니다. 이 클래스는 제공 추가 `typedef` 임계 영역 클래스를 참조 하는 이름입니다.  
  
> [!NOTE]
> `CComGlobalsThreadModel`클래스를 참조 하지 않는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)합니다.  
  
 사용 하 여 `CComGlobalsThreadModel` 특정 스레딩 모델 클래스를 지정 하에서 실행을 해제 합니다. 사용 되는 스레딩 모델에 관계 없이 적절 한 메서드 호출 됩니다.  
  
 외에 `CComGlobalsThreadModel`, ATL은 제공 된 `typedef` 이름 [CComObjectThreadModel](#ccomobjectthreadmodel)합니다. 각에서 참조 하는 클래스 `typedef` 다음 표에 나와 있는 것 처럼을 사용 하는 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 사용 하 여 `CComObjectThreadModel` 단일 개체 클래스 내에서. 사용 하 여 `CComGlobalsThreadModel` 프로그램에 전체적으로 사용할 수 없거나 여러 스레드에서 모듈 리소스를 보호 하려는 경우 개체에 있습니다.  

## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h
  
##  <a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 적절 한 스레드 사용 되는 스레딩 모델에 관계 없이 모델 메서드를 호출 합니다.  
  
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
 응용 프로그램에서 사용 되는 스레딩 모델에 따라는 `typedef` 이름 `CComObjectThreadModel` 참조 하거나 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)합니다. 이 클래스는 제공 추가 `typedef` 임계 영역 클래스를 참조 하는 이름입니다.  
  
> [!NOTE]
> `CComObjectThreadModel`클래스를 참조 하지 않는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)합니다.  
  
 사용 하 여 `CComObjectThreadModel` 특정 스레딩 모델 클래스를 지정 하에서 실행을 해제 합니다. 사용 되는 스레딩 모델에 관계 없이 적절 한 메서드 호출 됩니다.  
  
 외에 `CComObjectThreadModel`, ATL은 제공 된 `typedef` 이름 [CComGlobalsThreadModel](#ccomglobalsthreadmodel)합니다. 각에서 참조 하는 클래스 `typedef` 다음 표에 나와 있는 것 처럼을 사용 하는 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 사용 하 여 `CComObjectThreadModel` 단일 개체 클래스 내에서. 사용 하 여 `CComGlobalsThreadModel` 있거나 하는 개체에 여러 스레드에서 모듈 리소스를 보호 하려는 경우 또는 프로그램에 전체적으로 사용할 수 있습니다.  

## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h
  
##  <a name="ccontainedwindow"></a>CContainedWindow  
 이 클래스의 특수화는 **CContainedWindowT 합니다.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  

## <a name="requirements"></a>요구 사항
**헤더:** atlwin.h
  
### <a name="remarks"></a>설명  
 `CContainedWindow`특수화 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)합니다. 기본 클래스 또는 특성을 변경 하려는 경우 사용 하 여 `CContainedWindowT` 직접 합니다.  
  
##  <a name="cpath"></a>CPath  
 특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CString`합니다.  
  
```   
typedef CPathT<CString> CPath;   
```  

## <a name="requirements"></a>요구 사항
**헤더:** atlpath.h
  
##  <a name="cpatha"></a>CPathA  
 특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringA`합니다.  
  
```   
typedef CPathT<CStringA> CPathA;   
```

## <a name="requirements"></a>요구 사항
**헤더:** atlpath.h  
  
##  <a name="cpathw"></a>CPathW  
 특수화 [CPathT](../../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringW`합니다.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
## <a name="requirements"></a>요구 사항
**헤더:** atlpath.h
  
##  <a name="csimplevalarray"></a>CSimpleValArray  
 단순 형식 저장 하기 위한 배열을 나타냅니다.  
  
```   
#define CSimpleValArray CSimpleArray   
```  

  
### <a name="remarks"></a>설명  
 `CSimpleValArray`만들기 및 관리 단순한 데이터 형식이 포함 된 배열에 대 한 제공 됩니다. 단순 #define의 [CSimpleArray](../../atl/reference/csimplearray-class.md)합니다.  


## <a name="requirements"></a>요구 사항
**헤더:** atlsimpcoll.h
  
##  <a name="lpcurl"></a>LPCURL  
 상수에 대 한 포인터 [CUrl](../../atl/reference/curl-class.md) 개체입니다.  
  
```   
typedef const CUrl* LPCURL;   
```  

## <a name="requirements"></a>요구 사항
**헤더:** atlutil.h

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
현재 프로젝트는 다중 스레드 CRT를 사용 하는 경우 DefaultThreadTraits CRTThreadTraits로 정의 됩니다. 그렇지 않으면 Win32ThreadTraits 사용 됩니다.


## <a name="requirements"></a>요구 사항
**헤더:** atlbase.h
  
##  <a name="lpurl"></a>LPURL  
 에 대 한 포인터는 [CUrl](../../atl/reference/curl-class.md) 개체입니다.  
  
```   
typedef CUrl* LPURL;   
```  

## <a name="requirements"></a>요구 사항
**헤더:** atlutil.h


## <a name="see-also"></a>참고 항목  
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)   
 [함수](../../atl/reference/atl-functions.md)   
 [전역 변수](../../atl/reference/atl-global-variables.md)   
 [구조체](../../atl/reference/atl-structures.md)   
 [매크로](../../atl/reference/atl-macros.md)   
 [클래스](../../atl/reference/atl-classes.md)