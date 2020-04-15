---
title: CComSimpleThreadAllocator 클래스
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 4a3cce492db4db9f46aeb4efe738ee6a594ddcfc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327339"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator 클래스

이 클래스는 클래스에 `CComAutoThreadModule`대한 스레드 선택을 관리합니다.

## <a name="syntax"></a>구문

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComSimple스레드알로카레이터::겟스레드](#getthread)|스레드를 선택합니다.|

## <a name="remarks"></a>설명

`CComSimpleThreadAllocator`[CComAutoThreadModule에](../../atl/reference/ccomautothreadmodule-class.md)대한 스레드 선택을 관리합니다. `CComSimpleThreadAllocator::GetThread`단순히 각 스레드를 순환 하 고 시퀀스에서 다음 스레드를 반환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>CComSimple스레드알로카레이터::겟스레드

시퀀스에서 다음 스레드를 지정하여 스레드를 선택합니다.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>매개 변수

*pApt*<br/>
ATL의 기본 구현에는 사용되지 않습니다.

*n스레드*<br/>
EXE 모듈의 최대 스레드 수입니다.

### <a name="return-value"></a>Return Value

0과 *(nThreads* - 1) 사이의 정수입니다. EXE 모듈의 스레드 중 하나를 식별합니다.

### <a name="remarks"></a>설명

다른 선택 `GetThread` 방법을 제공하거나 *pApt* 매개 변수를 사용하도록 재정의할 수 있습니다.

`GetThread`[CComAutoThreadModule::Create 인스턴스](../../atl/reference/ccomautothreadmodule-class.md#createinstance)에 의해 호출됩니다.

## <a name="see-also"></a>참고 항목

[CComApartment 클래스](../../atl/reference/ccomapartment-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
