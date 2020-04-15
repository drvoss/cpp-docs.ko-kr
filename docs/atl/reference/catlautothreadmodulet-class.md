---
title: CAtlAutoThreadModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: e7b7a327d7c47c4472b43ed58fbe9ad0556a7620
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321551"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT 클래스

이 클래스는 스레드 풀로 풀려진 아파트 모델 COM 서버를 구현하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
COM 서버를 구현할 클래스입니다.

*스레드 알로카이터*<br/>
스레드 선택을 관리하는 클래스입니다. 기본값은 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)입니다.

*dwWait*<br/>
시간 시간 간격을 밀리초 단위로 지정합니다. 기본값은 INFINITE이며, 이는 메서드의 시간 시간 간격이 결코 경과되지 않는다는 것을 의미합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlAutoThread 모듈: :getdefaultThreads](#getdefaultthreads)|이 정적 함수는 프로세서 수에 따라 EXE 모듈의 최대 스레드 수를 동적으로 계산하고 반환합니다.|

## <a name="remarks"></a>설명

클래스 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 스레드 `CAtlAutoThreadModuleT` 풀린 아파트 모델 COM 서버를 구현 하기 위해에서 파생 됩니다. 사용되지 않는 클래스 [CComAutoThreadModule을](../../atl/reference/ccomautothreadmodule-class.md)대체합니다.

> [!NOTE]
> 이 클래스는 기본 *dwWait* infinite 값이 DLL을 언로드할 때 교착 상태가 발생하므로 DLL에서 사용해서는 안 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>CAtlAutoThread 모듈: :getdefaultThreads

이 정적 함수는 프로세서 수에 따라 EXE 모듈의 최대 스레드 수를 동적으로 계산하고 반환합니다.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Return Value

EXE 모듈에서 생성할 스레드 수입니다.

### <a name="remarks"></a>설명

스레드 수를 계산하는 다른 방법을 사용하려는 경우 이 메서드를 재정의합니다. 기본적으로 스레드 수는 프로세서 수를 기준으로 합니다.

## <a name="see-also"></a>참고 항목

[IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule 클래스](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
