---
title: IRunnableObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 2843c0c25a5c104ffbdff72255ac5d85cf53b1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329454"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl 클래스

이 클래스는 `IUnknown` [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) 인터페이스의 기본 구현을 구현하고 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IRunnableObjectImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunning클래스](#getrunningclass)|실행 중인 컨트롤의 CLSID를 반환합니다. ATL 구현은 CLSID를 GUID_NULL 설정하고 E_UNEXPECTED 반환합니다.|
|[IRunnable개체임플::실행 중](#isrunning)|컨트롤이 실행 되고 있는지 확인 합니다. ATL 구현TRUE를 반환합니다.|
|[IRunnable개체임플::잠금 실행](#lockrunning)|컨트롤을 실행 중인 상태로 잠그습니다. ATL 구현은 S_OK 반환합니다.|
|[IRunnable개체임플::실행](#run)|컨트롤을 강제로 실행합니다. ATL 구현은 S_OK 반환합니다.|
|[IRunnable 개체 임플::집합포함 개체](#setcontainedobject)|컨트롤이 포함되어 있음을 나타냅니다. ATL 구현은 S_OK 반환합니다.|

## <a name="remarks"></a>설명

[IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) 인터페이스를 사용하면 컨테이너가 컨트롤이 실행 중인지 확인하거나 강제로 실행하거나 실행 중인 상태로 잠글 수 있습니다. 클래스는 `IRunnableObjectImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>IRunnableObjectImpl::GetRunning클래스

실행 중인 컨트롤의 CLSID를 반환합니다.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>Return Value

ATL 구현은 \* *lpClsid를* GUID_NULL 설정하고 E_UNEXPECTED 반환합니다.

### <a name="remarks"></a>설명

[IRunnable 개체::GetRunning클래스](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) Windows SDK에서 를 참조하십시오.

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a>IRunnable개체임플::실행 중

컨트롤이 실행 되고 있는지 확인 합니다.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>Return Value

ATL 구현TRUE를 반환합니다.

### <a name="remarks"></a>설명

[IRunnable 개체::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) SDK에서 실행 중입니다.

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>IRunnable개체임플::잠금 실행

컨트롤을 실행 중인 상태로 잠그습니다.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>Return Value

ATL 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

[IRunnable개체::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) SDK에서 잠금 실행 을 참조하십시오.

## <a name="irunnableobjectimplrun"></a><a name="run"></a>IRunnable개체임플::실행

컨트롤을 강제로 실행합니다.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>Return Value

ATL 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

[IRunnable개체::Windows](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) SDK에서 실행을 참조하십시오.

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>IRunnable 개체 임플::집합포함 개체

컨트롤이 포함되어 있음을 나타냅니다.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>Return Value

ATL 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

[IRunnable 개체::집합포함된 개체](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) 를 Windows SDK에서 참조 합니다.

## <a name="see-also"></a>참고 항목

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
