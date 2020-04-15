---
title: 세팅스토어SP 클래스
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 9e22184a4081762a3d505645752e514315146981
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318449"
---
# <a name="csettingsstoresp-class"></a>세팅스토어SP 클래스

클래스는 `CSettingsStoreSP` [CSettingsStore](../../mfc/reference/csettingsstore-class.md)클래스의 인스턴스를 만드는 데 사용할 수 있는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```
class CSettingsStoreSP
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[설정스토어SP:::세팅스토어SP](#csettingsstoresp)|`CSettingsStoreSP` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[설정저장소SP:만들기](#create)|`CSettingsStore`에서 파생 된 클래스의 인스턴스를 만듭니다.|
|[설정저장소SP::셋런타임클래스](#setruntimeclass)|런타임 클래스를 설정합니다. 메서드는 `Create` 런타임 클래스를 사용하여 만들 개체의 클래스를 결정합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|`m_dwUserData`|개체에 `CSettingsStoreSP` 저장된 사용자 지정 사용자 데이터입니다. 개체의 생성자에서 이 데이터를 `CSettingsStoreSP` 제공 합니다.|
|`m_pRegistry`|메서드가 `CSettingsStore` `Create` 만드는 -derive된 개체입니다.|

## <a name="remarks"></a>설명

클래스를 `CSettingsStoreSP` 사용하여 모든 MFC 레지스트리 작업을 XML 파일이나 데이터베이스와 같은 다른 위치로 리디렉션할 수 있습니다. 이렇게 하려면 다음 단계를 수행하세요.

1. 클래스(예: `CMyStore`)를 만들고 `CSettingsStore`에서 파생합니다.

1. 사용자 지정 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) `CSettingsStore` 클래스와 함께 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) 및 IMPLEMENT_DYNCREATE 매크로를 사용하여 동적 생성을 활성화합니다.

1. 가상 함수를 재정의하고 `Read` 사용자 `Write` 지정 클래스에서 및 함수를 구현합니다. 원하는 위치에 데이터를 읽고 쓰는 다른 기능을 구현합니다.

1. 응용 프로그램에서 클래스에서 가져온 `CSettingsStoreSP::SetRuntimeClass` [CRuntimeClass 구조에](../../mfc/reference/cruntimeclass-structure.md) 대한 포인터를 호출하고 전달합니다.

프레임워크가 일반적으로 레지스트리에 액세스할 때마다 이제 사용자 지정 클래스를 동적으로 인스턴스화하고 데이터를 읽거나 쓰는 데 사용합니다.

`CSettingsStoreSP::SetRuntimeClass`에서는 전역 정적 변수를 사용합니다. 따라서 한 번에 하나의 사용자 지정 저장소만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxsettingsstore.h

## <a name="csettingsstorespcreate"></a><a name="create"></a>설정저장소SP:만들기

[CSettingsStore 클래스에서](../../mfc/reference/csettingsstore-class.md)파생 된 개체의 새 인스턴스를 만듭니다.

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>매개 변수

*bAdmin*<br/>
【인】 `CSettingsStore` 개체가 관리자 모드에서 생성되는지 여부를 결정하는 부울 매개 변수입니다.

*bReadOnly*<br/>
【인】 읽기 전용 액세스를 위해 개체가 `CSettingsStore` 만들어지는지 여부를 결정하는 부울 매개 변수입니다.

### <a name="return-value"></a>Return Value

새로 생성된 `CSettingsStore` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) 메서드를 사용하여 만들 개체 `CSettingsStoreSP::Create` 유형을 결정할 수 있습니다. 기본적으로 이 메서드는 `CSettingsStore` 개체를 만듭니다.

관리자 모드에서 `CSettingsStore` 개체를 만드는 경우 모든 레지스트리 액세스의 기본 위치가 HKEY_LOCAL_MACHINE. 그렇지 않으면 모든 레지스트리 액세스의 기본 위치가 HKEY_CURRENT_USER.

*bAdmin이* TRUE이면 응용 프로그램에 관리 권한이 있어야 합니다. 그렇지 않으면 레지스트리에 액세스하려고 하면 실패합니다.

### <a name="example"></a>예제

다음 예제에서는 `Create` `CSettingsStoreSP` 클래스의 메서드를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>설정스토어SP:::세팅스토어SP

[CSettingsStoreSP 클래스](../../mfc/reference/csettingsstoresp-class.md) 개체를 생성합니다.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*dw사용자 데이터*<br/>
【인】 개체가 `CSettingsStoreSP` 저장하는 사용자 정의 데이터입니다.

### <a name="remarks"></a>설명

개체는 `CSettingsStoreSP` 보호된 멤버 변수에 `m_dwUserData` *dwUserData의* 데이터를 저장합니다.

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>설정저장소SP::셋런타임클래스

런타임 클래스를 설정합니다. [CSettingsStoreSP:Create](#create) 메서드는 런타임 클래스를 사용하여 만들 개체 유형을 결정합니다.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>매개 변수

*pRTI*<br/>
【인】 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)클래스에서 파생 된 클래스에 대 한 런타임 클래스 정보에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE; *false pRTI로* 식별된 클래스가 에서 `CSettingsStore`파생되지 않은 경우.

### <a name="remarks"></a>설명

[CSettingsStoreSP 클래스를](../../mfc/reference/csettingsstoresp-class.md) 사용하여 에서 `CSettingsStore`클래스를 파생할 수 있습니다. 에서 파생 `SetRuntimeClass` 된 사용자 지정 클래스의 개체를 만들려면 `CSettingsStore`메서드를 사용 합니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)
