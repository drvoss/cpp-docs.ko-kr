---
title: CAtlFileMappingBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 16eebfff4330a47888d1b60eaa993ee87d120f72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748289"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase 클래스

이 클래스는 메모리 매핑된 파일을 나타냅니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAtlFileMappingBase
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtlFile 매핑 베이스::CAtlFile 매핑 베이스](#catlfilemappingbase)|생성자입니다.|
|[CAtlFile 매핑 베이스::~카틀파일매핑베이스](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlFile 매핑 베이스::복사에서](#copyfrom)|파일 매핑 개체에서 복사하려면 이 메서드를 호출합니다.|
|[CAtlFile 매핑 베이스::GetData](#getdata)|파일 매핑 개체에서 데이터를 가져옵니다이 메서드를 호출 합니다.|
|[CAtlFile 매핑 베이스::GetHandle](#gethandle)|파일 핸들을 반환하려면 이 메서드를 호출합니다.|
|[CAtlFile 매핑 베이스::GetMappingSize](#getmappingsize)|파일 매핑 개체에서 매핑 크기를 얻으려면 이 메서드를 호출합니다.|
|[CAtlFile 매핑 베이스::맵파일](#mapfile)|파일 매핑 개체를 만들려면 이 메서드를 호출합니다.|
|[카틀파일매핑베이스::맵공유밈](#mapsharedmem)|모든 프로세스에 대한 전체 액세스를 허용하는 파일 매핑 개체를 만들려면 이 메서드를 호출합니다.|
|[CAtlFile 매핑 베이스::오픈 매핑](#openmapping)|이 메서드를 호출하여 핸들을 파일 매핑 개체에 반환합니다.|
|[CAtlFile 매핑 베이스::맵 해제](#unmap)|이 메서드를 호출하여 파일 매핑 개체의 매핑을 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAtlFile매핑베이스::연산자 =](#operator_eq)|현재 파일 매핑 개체를 다른 파일 매핑 개체로 설정합니다.|

## <a name="remarks"></a>설명

파일 매핑은 프로세스의 가상 주소 공간의 일부와 파일 내용의 연결입니다. 이 클래스는 프로그램이 데이터에 쉽게 액세스하고 공유할 수 있도록 하는 파일 매핑 개체를 만드는 방법을 제공합니다.

자세한 내용은 Windows SDK의 [파일 매핑을](/windows/win32/Memory/file-mapping) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFile 매핑 베이스::CAtlFile 매핑 베이스

생성자입니다.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>매개 변수

*오리지널*<br/>
복사하여 새 개체를 만들 수 있는 원본 파일 매핑 개체입니다.

### <a name="remarks"></a>설명

선택적으로 기존 개체를 사용하여 새 파일 매핑 개체를 만듭니다. 특정 파일에 대한 파일 매핑 개체를 열거나 만들려면 [CAtlFileMappingBase::MapFile을](#mapfile) 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFile 매핑 베이스::~카틀파일매핑베이스

소멸자입니다.

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>설명

클래스에서 할당된 리소스를 해제하고 [CAtlFileMappingBase::unmap 메서드를](#unmap) 호출합니다.

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFile 매핑 베이스::복사에서

파일 매핑 개체에서 복사하려면 이 메서드를 호출합니다.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>매개 변수

*오리지널*<br/>
복사할 원래 파일 매핑 개체입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFile 매핑 베이스::GetData

파일 매핑 개체에서 데이터를 가져옵니다이 메서드를 호출 합니다.

```cpp
void* GetData() const throw();
```

### <a name="return-value"></a>Return Value

데이터에 대한 포인터를 반환합니다.

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFile 매핑 베이스::GetHandle

이 메서드를 호출하여 핸들을 파일 매핑 개체에 반환합니다.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Return Value

파일 매핑 개체에 핸들을 반환합니다.

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFile 매핑 베이스::GetMappingSize

파일 매핑 개체에서 매핑 크기를 얻으려면 이 메서드를 호출합니다.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Return Value

매핑 크기를 반환합니다.

### <a name="example"></a>예제

[CAtlFileMappingBase::CAtlFileMappingBase에](#catlfilemappingbase)대한 예제를 참조하십시오.

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFile 매핑 베이스::맵파일

지정된 파일에 대한 파일 매핑 개체를 열거나 만들려면 이 메서드를 호출합니다.

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>매개 변수

*hFile*<br/>
매핑 개체를 만들 파일을 처리합니다. *hFile은* 유효해야 하며 INVALID_HANDLE_VALUE 설정할 수 없습니다.

*n매핑 크기*<br/>
매핑 크기입니다. 0이면 파일 매핑 개체의 최대 크기는 *hFile으로* 식별된 파일의 현재 크기와 같습니다.

*n오프셋*<br/>
매핑이 시작되는 파일 오프셋입니다. 오프셋 값은 시스템의 메모리 할당 세분성의 배수여야 합니다.

*dw매핑 보호*<br/>
파일이 매핑될 때 파일 보기에 필요한 보호입니다. Windows SDK에서 [CreateFile매핑에서](/windows/win32/api/winbase/nf-winbase-createfilemappinga) *flProtect를* 참조하십시오.

*dwViewDesired액세스*<br/>
파일 보기에 대한 액세스 유형을 지정하여 파일에 매핑된 페이지의 보호를 지정합니다. 윈도우 SDK에서 [MapViewOfFileEx에서](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess를* 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

파일 매핑 개체를 만든 후에는 파일 크기가 파일 매핑 개체의 크기를 초과해서는 안 됩니다. 이 경우 파일의 모든 내용을 공유할 수 있는 것은 아닙니다. 자세한 내용은 Windows SDK에서 [파일 매핑 만들기](/windows/win32/api/winbase/nf-winbase-createfilemappinga) 및 [MapViewOfFileEx를](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) 참조하십시오.

### <a name="example"></a>예제

[CAtlFileMappingBase::CAtlFileMappingBase에](#catlfilemappingbase)대한 예제를 참조하십시오.

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>카틀파일매핑베이스::맵공유밈

모든 프로세스에 대한 전체 액세스를 허용하는 파일 매핑 개체를 만들려면 이 메서드를 호출합니다.

```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>매개 변수

*n매핑 크기*<br/>
매핑 크기입니다. 0이면 파일 매핑 개체의 최대 크기는 *szName로*식별된 파일 매핑 개체의 현재 크기와 같습니다.

*szName*<br/>
매핑 개체의 이름입니다.

*pb이미존재*<br/>
매핑 개체가 이미 있는 경우 TRUE로 설정된 BOOL 값을 가리킵니다.

*lpsa*<br/>
반환된 핸들을 자식 프로세스에 `SECURITY_ATTRIBUTES` 의해 상속할 수 있는지 여부를 결정하는 구조에 대한 포인터입니다. Windows SDK에서 [파일 매핑 생성에서](/windows/win32/api/winbase/nf-winbase-createfilemappinga) *lpAttributes를* 참조하십시오.

*dw매핑 보호*<br/>
파일이 매핑될 때 파일 뷰에 필요한 보호입니다. Windows SDK에서 `CreateFileMapping` *flProtect를* 참조하십시오.

*dwViewDesired액세스*<br/>
파일 보기에 대한 액세스 유형을 지정하여 파일에 매핑된 페이지의 보호를 지정합니다. 윈도우 SDK에서 [MapViewOfFileEx에서](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess를* 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

`MapShareMem`을 사용하면 [CreateFileMapping에서](/windows/win32/api/winbase/nf-winbase-createfilemappinga)만든 기존 파일 매핑 개체를 프로세스 간에 공유할 수 있습니다.

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFile 매핑 베이스::오픈 매핑

지정된 파일에 대해 명명된 파일 매핑 개체를 열려면 이 메서드를 호출합니다.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>매개 변수

*szName*<br/>
매핑 개체의 이름입니다. 이 이름으로 파일 매핑 개체에 열린 핸들이 있고 매핑 개체의 보안 설명자가 *dwViewDesiredAccess* 매개 변수와 충돌하지 않는 경우 열린 작업이 성공합니다.

*n매핑 크기*<br/>
매핑 크기입니다. 0이면 파일 매핑 개체의 최대 크기는 *szName로*식별된 파일 매핑 개체의 현재 크기와 같습니다.

*n오프셋*<br/>
매핑이 시작되는 파일 오프셋입니다. 오프셋 값은 시스템의 메모리 할당 세분성의 배수여야 합니다.

*dwViewDesired액세스*<br/>
파일 보기에 대한 액세스 유형을 지정하여 파일에 매핑된 페이지의 보호를 지정합니다. 윈도우 SDK에서 [MapViewOfFileEx에서](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess를* 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 입력 매개 변수가 유효하지 않은 경우 어설션 오류가 발생합니다.

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFile매핑베이스::연산자 =

현재 파일 매핑 개체를 다른 파일 매핑 개체로 설정합니다.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>매개 변수

*오리지널*<br/>
현재 파일 매핑 개체입니다.

### <a name="return-value"></a>Return Value

현재 개체에 대한 참조를 반환합니다.

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFile 매핑 베이스::맵 해제

이 메서드를 호출하여 파일 매핑 개체의 매핑을 해제합니다.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [MapViewOfFile 해제를](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile) 참조하십시오.

## <a name="see-also"></a>참조

[CAtlFileMapping 클래스](../../atl/reference/catlfilemapping-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
