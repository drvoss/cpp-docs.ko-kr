---
title: 'TN064: ActiveX 컨트롤의 아파트 모델 스레딩'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: 0c6a42124b4b2b03ae7cd9277fa14d43eac7a2bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366065"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: ActiveX 컨트롤의 아파트 모델 스레딩

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트에서는 ActiveX 컨트롤에서 아파트 모델 스레딩을 활성화하는 방법을 설명합니다. 아파트 모델 스레딩은 Visual C++ 버전 4.2 이상에서만 지원됩니다.

## <a name="what-is-apartment-model-threading"></a>아파트 모델 스레딩이란 무엇입니까?

아파트 모델은 다중 스레드 컨테이너 응용 프로그램 내에서 ActiveX 컨트롤과 같은 포함된 개체를 지원하는 방법입니다. 응용 프로그램에 여러 스레드가 있을 수 있지만 포함된 개체의 각 인스턴스는 하나의 스레드에서만 실행되는 하나의 "apartment"에 할당됩니다. 즉, 컨트롤 인스턴스에 대한 모든 호출은 동일한 스레드에서 발생합니다.

그러나 동일한 유형의 컨트롤의 다른 인스턴스가 다른 아파트에 할당될 수 있습니다. 따라서 컨트롤의 여러 인스턴스가 공통의 데이터(예: 정적 또는 전역 데이터)를 공유하는 경우 이 공유 데이터에 대한 액세스는 임계 섹션과 같은 동기화 개체에 의해 보호되어야 합니다.

아파트 스레딩 모델에 대한 자세한 내용은 OLE 프로그래머 *참조의* [프로세스 및 스레드를](/windows/win32/ProcThread/processes-and-threads) 참조하십시오.

## <a name="why-support-apartment-model-threading"></a>아파트 모델 스레딩을 지원하는 이유

아파트 모델 스레딩을 지원하는 컨트롤은 아파트 모델을 지원하는 다중 스레드 컨테이너 응용 프로그램에서 사용할 수 있습니다. 아파트 모델 스레딩을 활성화하지 않으면 컨트롤을 사용할 수 있는 컨테이너의 잠재적 집합을 제한합니다.

아파트 모델 스레딩을 사용하면 대부분의 컨트롤에서 특히 공유 데이터가 거의 없거나 전혀 없는 경우 쉽게 사용할 수 있습니다.

## <a name="protecting-shared-data"></a>공유 데이터 보호

컨트롤에서 정적 멤버 변수와 같은 공유 데이터를 사용하는 경우 두 개 이상의 스레드가 동시에 데이터를 수정하지 못하도록 해당 데이터에 대한 액세스를 중요한 섹션으로 보호해야 합니다. 이 목적을 위해 임계 섹션을 설정하려면 컨트롤클래스에서 `CCriticalSection` 클래스의 정적 멤버 변수를 선언합니다. 코드가 `Lock` 공유 `Unlock` 데이터에 액세스하는 모든 위치에 이 중요 섹션 개체의 및 멤버 함수를 사용합니다.

예를 들어 모든 인스턴스에서 공유하는 문자열을 유지 관리해야 하는 컨트롤 클래스를 생각해 보십시오. 이 문자열은 정적 멤버 변수에서 유지 관리되고 임계 섹션으로 보호될 수 있습니다. 컨트롤의 클래스 선언에는 다음이 포함됩니다.

```cpp
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

클래스의 구현에는 다음 변수에 대한 정의가 포함됩니다.

```cpp
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

그런 다음 `_strShared` 정적 멤버에 대한 액세스를 임계 섹션으로 보호할 수 있습니다.

```cpp
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>아파트 모델 인식 제어 등록

아파트 모델 스레딩을 지원하는 컨트롤은 *클래스 ID*\\**InprocServer32** 키 아래의 클래스 ID 레지스트리 항목에 "Apartment" 값을 가진 명명된 값 "ThreadingModel"을 추가하여 레지스트리에서 이 기능을 나타내야 합니다. 이 키가 컨트롤에 자동으로 등록되려면 여섯 번째 매개 변수의 *afxRegApartmentThreading 플래그를* 다음으로 `AfxOleRegisterControlClass`전달합니다.

```cpp
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)
{
    if (bRegister)
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(),
    m_clsid,
    m_lpszProgID,
    IDS_SAMPLE,
    IDB_SAMPLE,
    afxRegApartmentThreading,
    _dwSampleOleMisc,
    _tlid,
    _wVerMajor,
    _wVerMinor);

else
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}
```

Visual C++ 버전 4.1 이상의 ControlWizard에서 컨트롤 프로젝트를 생성한 경우 이 플래그는 코드에 이미 있습니다. 스레딩 모델을 등록하기 위해 변경할 필요가 없습니다.

이전 버전의 ControlWizard에서 프로젝트를 생성한 경우 기존 코드에는 부울 값이 여섯 번째 매개 변수로 지정됩니다. 기존 매개 변수가 TRUE이면 *afxRegInsertable | afxRegApartmentThreading으로*변경합니다. 기존 매개 변수가 FALSE이면 *afxRegApartmentSThreading으로*변경합니다.

컨트롤이 아파트 모델 스레딩에 대한 규칙을 따르지 않는 경우 이 매개 변수에서 *afxRegApartmentThreading을* 전달해서는 안 됩니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
