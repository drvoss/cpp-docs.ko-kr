---
title: C캐시드데이터패스속성 클래스
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: ebab34433f23b119e3444b3eaa8b0ad6313555af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352359"
---
# <a name="ccacheddatapathproperty-class"></a>C캐시드데이터패스속성 클래스

비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.

## <a name="syntax"></a>구문

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C캐시드데이터패스속성::C캐시드데이터패스속성](#ccacheddatapathproperty)|`CCachedDataPathProperty` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C캐시데이터패스속성::m_Cache](#m_cache)|`CMemFile`데이터를 캐시할 개체입니다.|

## <a name="remarks"></a>설명

메모리 파일은 디스크가 아닌 RAM에 저장되며 빠른 임시 전송에 유용합니다.

와 `CAysncMonikerFile` 함께 `CDataPathProperty` `CCachedDataPathProperty` 및 ,을 통해 OLE 컨트롤에서 비동기 모니커를 사용할 수 있는 기능을 제공합니다. 개체를 사용하면 `CCachedDataPathProperty` URL 또는 파일 소스에서 비동기적으로 데이터를 전송하고 `m_Cache` public 변수를 통해 메모리 파일에 저장할 수 있습니다. 모든 데이터는 메모리 파일에 저장되며 알림을 보고 응답하지 않는 한 [OnDataAvailable을](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 재정의할 필요가 없습니다. 예를 들어 큰 을 전송하는 경우 . GIF 파일과 더 많은 데이터가 도착하고 그 자체를 다시 그려야한다는 것을 제어에 알리고 싶어, 알림을 만들기 위해 재정의. `OnDataAvailable`

클래스는 `CCachedDataPathProperty` 에서 `CDataPathProperty`파생됩니다.

인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.

- [인터넷 첫 번째 단계: 액티브X 컨트롤](../../mfc/activex-controls-on-the-internet.md)

- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>C캐시드데이터패스속성::C캐시드데이터패스속성

`CCachedDataPathProperty` 개체를 생성합니다.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
이 `CCachedDataPathProperty` 개체와 연결될 ActiveX 컨트롤 개체에 대한 포인터입니다.

*lpszPath*<br/>
절대 또는 상대경로는 속성의 실제 절대 위치를 참조하는 비동기 모니커를 만드는 데 사용됩니다. `CCachedDataPathProperty`는 파일 이름이 아닌 URL을 사용합니다. 파일에 대한 `CCachedDataPathProperty` 개체를 원하는 경우 경로에 file:// 준비합니다.

### <a name="remarks"></a>설명

`COleControl` *pControl이* 가리키는 개체는 [Open에서](../../mfc/reference/cdatapathproperty-class.md#open) 사용하고 파생 클래스에서 검색됩니다. *pControl이* NULL이면 함께 `Open` 사용되는 컨트롤을 [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)로 설정해야 합니다. *lpszPath가* NULL인 경우 경로를 통과하거나 `Open` [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)로 설정할 수 있습니다.

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a>C캐시데이터패스속성::m_Cache

데이터가 캐시되는 메모리 파일의 클래스 이름을 포함합니다.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>설명

메모리 파일은 디스크가 아닌 RAM에 저장됩니다.

## <a name="see-also"></a>참고 항목

[CDataPath속성 클래스](../../mfc/reference/cdatapathproperty-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDataPath속성 클래스](../../mfc/reference/cdatapathproperty-class.md)
