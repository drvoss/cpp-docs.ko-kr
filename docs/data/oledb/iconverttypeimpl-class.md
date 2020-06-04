---
title: IConvertTypeImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: e3b76be2a1f1edfcdc1139a3dd396835923c2b4a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210693"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl 클래스

[가 iconverttype](/previous-versions/windows/desktop/ms715926(v=vs.85)) 인터페이스의 구현을 제공 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>매개 변수

*T*<br/>
`IConvertTypeImpl`에서 파생 된 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[CanConvert](#canconvert)|명령 또는 행 집합에 대 한 형식 변환의 가용성에 대 한 정보를 제공 합니다.|

## <a name="remarks"></a>주의

이 인터페이스는 명령, 행 집합 및 인덱스 행 집합에 필수적입니다. `IConvertTypeImpl` OLE DB에서 제공 하는 변환 개체에 위임 하 여 인터페이스를 구현 합니다.

## <a name="iconverttypeimplcanconvert"></a><a name="canconvert"></a>IConvertTypeImpl:: CanConvert

명령 또는 행 집합에 대 한 형식 변환의 가용성에 대 한 정보를 제공 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*에서 [가 iconverttype:: canconvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) 를 참조 하세요.

### <a name="remarks"></a>주의

`MSADC.DLL`에서 OLE DB 데이터 변환을 사용 합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
