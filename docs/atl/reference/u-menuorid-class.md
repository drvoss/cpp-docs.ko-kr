---
title: _U_MENUorID 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 419c9e79178db12efe278838ec8630e04ac3c461
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325832"
---
# <a name="_u_menuorid-class"></a>_U_MENUorID 클래스

이 클래스는 에 `CreateWindow` `CreateWindowEx`대한 래퍼를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class _U_MENUorID
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[_U_MENUorID:_U_MENUorID](#_u_menuorid___u_menuorid)|생성자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[_U_MENUorID:m_hMenu](#_u_menuorid__m_hmenu)|메뉴에 대한 핸들입니다.|

## <a name="remarks"></a>설명

이 인수 어댑터 클래스를 사용하면 호출자의 부분에 명시적 캐스트를 요구하지 않고도 ID(UINT) 또는 메뉴 핸들(HMENUs)을 함수에 전달할 수 있습니다.

이 클래스는 메뉴 핸들이 아닌 자식 창 식별자(UINT)일 수 있는 HMENU 인수를 허용하는 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 및 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 함수와 같은 Windows API에 래퍼를 구현하기 위해 설계되었습니다. 예를 들어 이 클래스가 [CWindowImpl::Create의](cwindowimpl-class.md#create)매개 변수로 사용 중이라고 볼 수 있습니다.

클래스는 두 개의 생성자 오버로드를 정의합니다. UINT 인수는 생성자의 HMENU에 캐스팅되고 결과는 클래스의 단일 데이터 멤버에 저장되어 [m_hMenu.](#_u_menuorid__m_hmenu) HMENU 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a>_U_MENUorID:m_hMenu

클래스는 공용 HMENU 데이터 멤버로 생성자 중 하나에 전달 된 값을 보유 합니다.

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a>_U_MENUorID:_U_MENUorID

UINT 인수는 생성자의 HMENU에 캐스팅되고 결과는 클래스의 단일 데이터 멤버에 저장되어 [m_hMenu.](#_u_menuorid__m_hmenu)

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
자식 창 식별자입니다.

*Hmenu*<br/>
메뉴 핸들입니다.

### <a name="remarks"></a>설명

HMENU 생성자에 대한 인수는 변환 없이 직접 저장됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
