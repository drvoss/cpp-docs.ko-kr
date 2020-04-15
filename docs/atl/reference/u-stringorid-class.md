---
title: _U_STRINGorID 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: 4e46ceec077b8daf8ef2a76110d2fc19dd39ae26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325818"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID 클래스

이 인수 어댑터 클래스를 사용하면 호출자가 MAKEINTRESOURCE 매크로를 사용하여 ID를 문자열로 변환할 필요 없이 리소스 이름(LPCTSTRs) 또는 리소스 ID(UINT)를 함수에 전달할 수 있습니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class _U_STRINGorID
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[_U_STRINGorID:_U_STRINGorID](#_u_stringorid___u_stringorid)|생성자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[_U_STRINGorID:m_lpstr](#_u_stringorid__m_lpstr)|리소스 식별자입니다.|

## <a name="remarks"></a>설명

이 클래스는 리소스 또는 ID의 이름일 수 있는 LPCTSTR 인수를 허용하는 [FindResource,](/windows/win32/api/winbase/nf-winbase-findresourcea) [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)및 [LoadMenu](/windows/win32/api/winuser/nf-winuser-loadmenuw) 함수와 같은 Windows 리소스 관리 API에 래퍼를 구현하기 위해 설계되었습니다.

클래스는 두 개의 생성자 오버로드를 정의합니다: 하나는 LPCTSTR 인수를 받아들이고 다른 하나는 UINT 인수를 수락합니다. UINT 인수는 MAKEINTRESOURCE 매크로를 사용하여 Windows 리소스 관리 기능과 호환되는 리소스 유형으로 변환되고 클래스의 단일 데이터 멤버에 저장된 결과 [인 m_lpstr.](#_u_stringorid__m_lpstr) LPCTSTR 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID:m_lpstr

클래스는 공용 LPCTSTR 데이터 멤버로 생성자 중 하나에 전달 된 값을 보유 합니다.

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID:_U_STRINGorID

UINT 생성자는 MAKEINTRESOURCE 매크로를 사용하여 Windows 리소스 관리 기능과 호환되는 리소스 유형으로 인수를 변환하고 결과는 클래스의 단일 데이터 멤버인 [m_lpstr.](#_u_stringorid__m_lpstr)

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
리소스 ID입니다.

*lpString*<br/>
리소스 이름입니다.

### <a name="remarks"></a>설명

LPCTSTR 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
