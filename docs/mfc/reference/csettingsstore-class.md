---
title: CSettingsStore Class
ms.date: 11/04/2016
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
ms.openlocfilehash: b1acf959c371aa23ac55ace7fea9466f0e20813f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318462"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class

Windows API 함수를 래핑하여 레지스트리에 액세스하는 데 사용할 수 있는 개체 지향 인터페이스를 제공합니다.

## <a name="syntax"></a>구문

```
class CSettingsStore : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[설정 저장소::설정 스토어](#csettingsstore)|`CSettingsStore` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[설정 저장소::닫기](#close)|열린 레지스트리 키를 닫습니다.|
|[CSettingsStore::만들기키](#createkey)|지정된 키를 열거나 존재하지 않는 경우 키를 만듭니다.|
|[설정 스토어::DeleteKey키](#deletekey)|지정된 키와 모든 자식을 삭제합니다.|
|[CSettingsStore::DeleteValue](#deletevalue)|열려 있는 키의 지정된 값을 삭제합니다.|
|[설정 저장소::열기](#open)|지정된 키를 엽니다.|
|[설정 저장소::읽기](#read)|지정된 키 값에 대한 데이터를 검색합니다.|
|[설정 저장소::쓰기](#write)|열려 있는 키 아래 레지스트리에 값을 씁니다.|

## <a name="remarks"></a>설명

멤버는 `CreateKey` 기능하며 `Open` 매우 유사합니다. 레지스트리 키가 이미 있는 `CreateKey` 경우 `Open` 동일한 방식으로 작동합니다. 그러나 레지스트리 키가 없으면 레지스트리 키가 `CreateKey` `Open` 생성되지만 오류 값이 반환됩니다.

## <a name="example"></a>예제

다음 예제에서는 `CSettingsStore` 클래스의 열기 및 읽기 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 도구 [설명 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>요구 사항

**헤더:** afxsettingsstore.h

## <a name="csettingsstoreclose"></a><a name="close"></a>설정 저장소::닫기

열린 레지스트리 키를 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 [CSettingsStore 클래스의](../../mfc/reference/csettingsstore-class.md)소멸자에서 호출됩니다.

## <a name="csettingsstorecreatekey"></a><a name="createkey"></a>CSettingsStore::만들기키

레지스트리 키가 열리거나 없는 경우 레지스트리 키를 만듭니다.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
【인】 만들거나 열 수 있는 키의 이름을 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0; 그렇지 않으면 영하지 않은 값입니다.

### <a name="remarks"></a>설명

`CreateKey`레지스트리 `m_hKey` 문의의 루트로 사용합니다. 의 하위 키로 *pszPath를* `m_hKey`검색합니다. 키가 없으면 `CreateKey` 키를 만듭니다. 그렇지 않으면 키가 열립니다. `CreateKey`그런 `m_hKey` 다음 생성하거나 열린 키로 설정합니다.

## <a name="csettingsstorecsettingsstore"></a><a name="csettingsstore"></a>설정 저장소::설정 스토어

`CSettngsStore` 개체를 만듭니다.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>매개 변수

*bAdmin*<br/>
【인】 `CSettingsStore` 개체가 관리자 모드에서 작동하는지 여부를 지정하는 부울 매개 변수입니다.

*bReadOnly*<br/>
【인】 `CSettingsStore` 개체가 읽기 전용 모드에서 만들어지는지 여부를 지정하는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

*bAdmin이* TRUE로 설정된 `m_hKey` 경우 멤버 변수는 **HKEY_LOCAL_MACHINE.** *bAdmin을* FALSE로 `m_hKey` 설정하면 **HKEY_CURRENT_USER.**

보안 액세스는 *bReadOnly* 매개 변수에 따라 다릅니다. *bReadonly가* FALSE이면 보안 액세스가 **KEY_ALL_ACCESS.** *bReadyOnly* TRUE인 경우 보안 액세스는 **KEY_QUERY_VALUE, KEY_NOTIFY** 및 **KEY_ENUMERATE_SUB_KEYS**조합으로 설정됩니다. 레지스트리와 함께 보안 액세스에 대한 자세한 내용은 [레지스트리 키 보안 및 액세스 권한](/windows/win32/SysInfo/registry-key-security-and-access-rights)을 참조하십시오.

릴리스의 `CSettingsStore` 소멸자가 자동으로 `m_hKey` 해제됩니다.

## <a name="csettingsstoredeletekey"></a><a name="deletekey"></a>설정 스토어::DeleteKey키

레지스트리에서 키와 모든 자식을 삭제합니다.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
【인】 삭제할 키의 이름입니다.

*bAdmin*<br/>
【인】 삭제할 키의 위치를 지정하는 스위치입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

개체가 읽기 전용 `CSettingsStore` 모드인 경우 이 메서드가 실패합니다.

매개 변수 *bAdmin이* `DeleteKey` 0이면 **HKEY_CURRENT_USER**에서 삭제할 키를 검색합니다. *bAdmin이* 0이 `DeleteKey` 아닌 경우 **HKEY_LOCAL_MACHINE**에서 삭제할 키를 검색합니다.

## <a name="csettingsstoredeletevalue"></a><a name="deletevalue"></a>CSettingsStore::DeleteValue

에서 `m_hKey`값을 삭제합니다.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>매개 변수

*psz값*<br/>
【인】 제거할 값 필드를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="csettingsstoreopen"></a><a name="open"></a>설정 저장소::열기

레지스트리 키를 엽니다.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
【인】 레지스트리 키의 이름입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드가 지정된 키를 성공적으로 `m_hKey` 연 후 이 키의 핸들로 설정됩니다.

## <a name="csettingsstoreread"></a><a name="read"></a>설정 저장소::읽기

레지스트리의 키에서 값을 읽습니다.

```
virtual BOOL Read(
    LPCTSTR pszKey,
    int& iVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    DWORD& dwVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CString& sVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Read(
    LPCTSTR pszKey,
    CRect& rect);

virtual BOOL Read(
    LPCTSTR pszKey,
    BYTE** ppData,
    UINT* pBytes);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject*& pObj);
```

### <a name="parameters"></a>매개 변수

*pszKey*<br/>
【인】 레지스트리에서 읽을 값의 이름을 포함 하는 null-종료 된 문자열에 대 한 포인터입니다.

*아이발 (것)이 발*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 정수 변수를 참조합니다.

*dwVal*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 32비트 이중 단어 변수를 참조합니다.

*스발 (것)들*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 문자열 변수를 참조합니다.

*scStringList*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 문자열 목록 변수에 대한 참조입니다.

*scArray*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 문자열 배열 변수에 대한 참조입니다.

*dwcArray*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 32비트 이중 단어 배열 변수를 참조합니다.

*wcArray*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 16비트 단어 배열 변수를 참조합니다.

*bcArray*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 바이트 배열 변수에 대한 참조입니다.

*lpPoint*<br/>
【아웃】 레지스트리 키에서 읽은 `POINT` 값을 받는 구조에 대한 포인터를 참조합니다.

*rect*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 변수를 참조합니다.

*ppData*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 데이터에 대한 포인터를 포인터로 합니다.

*p바이트*<br/>
【아웃】 서명되지 않은 정수 변수에 대한 포인터입니다. 이 변수는 *ppData가* 가리키는 버퍼의 크기를 받습니다.

*list*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 [CObList](../../mfc/reference/coblist-class.md) 변수를 참조합니다.

*obj*<br/>
【아웃】 레지스트리 키에서 읽은 값을 받는 [CObject](../../mfc/reference/cobject-class.md) 변수를 참조합니다.

*포지 (것)와 함께*<br/>
【아웃】 레지스트리 키에서 읽은 `CObject` 값을 받는 변수에 대한 포인터를 참조합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Read`의 하위 키로 *pszKey를* `m_hKey`확인합니다.

## <a name="csettingsstorewrite"></a><a name="write"></a>설정 저장소::쓰기

열려 있는 키 아래 레지스트리에 값을 씁니다.

```
virtual BOOL Write(
    LPCTSTR pszKey,
    int iVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    DWORD dwVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPCTSTR pszVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Write(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    const CRect& rect);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPBYTE pData,
    UINT nBytes);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject* pObj);
```

### <a name="parameters"></a>매개 변수

*pszKey*<br/>
【인】 설정할 값의 이름이 포함된 문자열에 대한 포인터입니다.

*아이발 (것)이 발*<br/>
【인】 저장할 데이터가 포함된 정수 변수를 참조합니다.

*dwVal*<br/>
【인】 저장할 데이터가 포함된 32비트 이중 단어 변수를 참조합니다.

*pszVal*<br/>
【인】 저장할 데이터가 포함된 null-종단 문자열 변수에 대한 포인터입니다.

*scStringList*<br/>
【인】 저장할 데이터가 포함된 [CStringList](../../mfc/reference/cstringlist-class.md) 변수에 대한 참조입니다.

*bcArray*<br/>
【인】 저장할 데이터가 포함된 바이트 배열 변수에 대한 참조입니다.

*scArray*<br/>
【인】 저장할 데이터가 포함된 문자열 배열 변수에 대한 참조입니다.

*dwcArray*<br/>
【인】 저장할 데이터가 포함된 32비트 이중 단어 배열 변수를 참조합니다.

*wcArray*<br/>
【인】 저장할 데이터가 포함된 16비트 단어 배열 변수를 참조합니다.

*rect*<br/>
【인】 저장할 데이터가 포함된 [CRect](../../atl-mfc-shared/reference/crect-class.md) 변수를 참조합니다.

*lpPoint*<br/>
【인】 저장할 데이터가 포함된 `POINT` 변수에 대한 포인터를 참조합니다.

*Pdata*<br/>
【인】 저장할 데이터가 포함된 버퍼에 대한 포인터입니다.

*n바이트*<br/>
【인】 *pData* 매개 변수가 가리키는 데이터의 크기를 바이트별로 지정합니다.

*list*<br/>
【인】 저장할 데이터가 포함된 [CObList](../../mfc/reference/coblist-class.md) 변수를 참조합니다.

*obj*<br/>
【인】 저장할 데이터가 포함된 [CObject](../../mfc/reference/cobject-class.md) 변수에 대한 참조입니다.

*포지 (것)와 함께*<br/>
【인】 저장할 데이터가 포함된 `CObject` 변수에 대한 포인터를 포인터로 합니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

레지스트리에 쓰려면 [CSettingsStore](../../mfc/reference/csettingsstore-class.md) 개체를 만들 때 *bReadOnly를* 영하지 않은 값으로 설정해야 합니다. 자세한 내용은 [CSettingsStore::CSettingsStore](#csettingsstore)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
