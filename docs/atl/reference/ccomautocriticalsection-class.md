---
title: CComAutoCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 8cbf08082fd24ef2cf0e8794e2944a799baec084
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321085"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection 클래스

`CComAutoCriticalSection`에서는 임계 섹션 개체의 소유권을 가져오고 해제하는 방법을 제공합니다.

## <a name="syntax"></a>구문

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComAutoCriticalsection::CComAutoCriticalsection](#ccomautocriticalsection)|생성자입니다.|
|[CComAutoCriticalsection::~CComAutoCriticalSection](#dtor)|소멸자입니다.|

## <a name="remarks"></a>설명

`CComAutoCriticalSection`는 생성자에서 임계영역 개체를 자동으로 초기화 하는 것을 `CComAutoCriticalSection`제외하고는 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 클래스와 유사합니다.

일반적으로 이름 [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection)`typedef`을 통해 `CComAutoCriticalSection`를 사용합니다. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 사용하는 경우 이 이름은 `CComAutoCriticalSection`를 참조합니다.

이 `Init` `Term` 클래스를 사용할 때 [CComCriticalSection의](../../atl/reference/ccomcriticalsection-class.md) 메서드와 메서드를 사용할 수 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>CComAutoCriticalsection::CComAutoCriticalsection

생성자입니다.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>설명

Win32 함수를 호출 [초기화임계 섹션,](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)이는 임계 섹션 개체를 초기화.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>CComAutoCriticalsection::~CComAutoCriticalSection

소멸자입니다.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>설명

소멸자는 임계 섹션 개체에서 사용하는 모든 시스템 리소스를 해제하는 [DeleteCriticalSection을](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)호출합니다.

## <a name="see-also"></a>참고 항목

[CComFake임계 섹션 클래스](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComCriticalsection 클래스](../../atl/reference/ccomcriticalsection-class.md)
