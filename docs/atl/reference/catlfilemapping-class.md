---
title: CAtlFileMapping 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: ca46ccdacf5ea24f1de26cdc75bf808c4ecfaa40
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318954"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping 클래스

이 클래스는 [CAtlFileMappingBase의](../../atl/reference/catlfilemappingbase-class.md)메서드에 캐스트 연산을 추가하는 메모리 매핑 된 파일을 나타냅니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
캐스트 연산자에 사용되는 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAtlFile매핑::연산자 T*](#operator_t_star)|개체를 `CAtlFileMapping` 에 대한 `T*`암시적 변환을 허용합니다.|

## <a name="remarks"></a>설명

이 클래스는 `CAtlFileMapping` 개체를 에 대한 암시적 `T*`변환을 허용하는 단일 캐스트 연산을 추가합니다. 다른 멤버는 기본 클래스인 [CAtlFileMappingBase에서](../../atl/reference/catlfilemappingbase-class.md)제공됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFile매핑::연산자 T*

개체를 `CAtlFileMapping` 에 대한 `T*`암시적 변환을 허용합니다.

```
operator T*() const throw();
```

### <a name="return-value"></a>Return Value

메모리 `T*` 매핑된 파일의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[CAtlFileMappingBase::GetData를](../../atl/reference/catlfilemappingbase-class.md#getdata) 호출하고 반환된 포인터를 `T*` 이 클래스의 템플릿 매개 변수로 사용되는 T *형식인* 위치로 재해석합니다.

## <a name="see-also"></a>참고 항목

[CAtlFileMappingBase 클래스](../../atl/reference/catlfilemappingbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
