---
title: IRowsetIdentityImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: 20f558099c02d7de8a20b3cf631812b44a742a48
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210408"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl 클래스

행 id에 대 한 테스트를 사용 하는 OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) 인터페이스를 구현 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>매개 변수

*T*<br/>
`IRowsetIdentityImpl`에서 파생 된 클래스입니다.

*RowClass*<br/>
`HROW`에 대 한 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[IsSameRow](#issamerow)|두 행 핸들을 비교 하 여 동일한 행을 참조 하는지 확인 합니다.|

## <a name="irowsetidentityimplissamerow"></a><a name="issamerow"></a>IRowsetIdentityImpl:: IsSameRow

두 행 핸들을 비교 하 여 동일한 행을 참조 하는지 확인 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*에서 [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) 를 참조 하세요.

### <a name="remarks"></a>주의

행 핸들을 비교 하기 위해이 메서드는 포인터에 대 한 `HROW` 핸들을 `RowClass` 멤버 및 호출 `memcmp` 캐스팅 합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
