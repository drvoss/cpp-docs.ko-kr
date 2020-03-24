---
title: IDBCreateCommandImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 4a4978401ba90e3a7a91ac40cc1b0668adf12ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210719"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl 클래스

[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85)) 인터페이스의 구현을 제공 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>매개 변수

*T*<br/>
`IDBCreateCommandImpl`에서 파생 된 세션 개체입니다.

*CommandClass*<br/>
명령 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[CreateCommand](#createcommand)|새 명령을 만듭니다.|

## <a name="remarks"></a>주의

새 명령을 얻기 위한 session 개체의 선택적 인터페이스입니다.

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a>IDBCreateCommandImpl:: CreateCommand

새 명령을 만들고 요청 된 인터페이스를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>매개 변수

*OLE DB 프로그래머 참조*에서 [IDBCreateCommand:: CreateCommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) 를 참조 하세요.

일부 매개 변수는 `IDBCreateCommand::CreateCommand`에서 설명 하는 다양 한 이름의 *프로그래머 참조* 매개 변수 OLE DB에 해당 합니다.

|OLE DB 템플릿 매개 변수|*OLE DB 프로그래머 참조* 매개 변수|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)
