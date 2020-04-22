---
title: CSnapInPropertyPageImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: 3f09e8500eadd36eec53db95f10261834d672101
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747586"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl 클래스

이 클래스는 스냅인 속성 페이지 개체를 구현하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSnapInPropertyPageimpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSnapInPropertyPageimpl::취소토클로즈](#canceltoclose)|**확인** 및 **취소** 단추의 상태를 변경합니다.|
|[CSnapIn속성 페이지 임플::만들기](#create)|새로 만든 개체를 `CSnapInPropertyPageImpl` 초기화합니다.|
|[CSnapInPropertyPageimpl::적용](#onapply)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **지금 적용** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CSnapInPropertyPageimpl::OnHelp](#onhelp)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **도움말** 단추를 클릭할 때 프레임워크에서 호출합니다.|
|[CSnapInPropertyPageimpl::온킬액티브](#onkillactive)|현재 페이지가 더 이상 활성 상태가 아니면 프레임워크에서 호출됩니다.|
|[CSnapIn속성 페이지 임플::온쿼리취소](#onquerycancel)|사용자가 **취소** 단추를 클릭하고 취소가 발생하기 전에 프레임워크에서 호출합니다.|
|[CSnapInPropertyPageimpl::온리셋](#onreset)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **재설정** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CSnapIn속성 페이지 임플::온셋](#onsetactive)|현재 페이지가 활성화될 때 프레임워크에서 호출됩니다.|
|[CSnapInPropertyPageimpl::온위저백](#onwizardback)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **뒤로** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CSnapInPropertyPageimpl::온위저피니](#onwizardfinish)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **완료** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CSnapInPropertyPageimpl::OnWizardNext](#onwizardnext)|사용자가 마법사 형식 속성 시트를 사용하는 동안 **다음** 단추를 클릭할 때 프레임워크에서 호출됩니다.|
|[CSnapIn속성 페이지 임플::쿼리 형제](#querysiblings)|현재 메시지를 속성 시트의 모든 페이지로 전달합니다.|
|[CSnapIn속성 페이지 임플::집합수정](#setmodified)|**지금 적용** 버튼을 활성화하거나 비활성화하려면 전화를 걸수 있습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CSnapInPropertyPageimpl::m_psp](#m_psp)|개체에서 `PROPSHEETPAGE` 사용하는 Windows `CSnapInPropertyPageImpl` 구조입니다.|

## <a name="remarks"></a>설명

`CSnapInPropertyPageImpl`는 스냅인 속성 페이지 개체에 대한 기본 구현을 제공합니다. 스냅인 속성 페이지의 기본 기능은 여러 가지 인터페이스와 맵 유형을 사용하여 구현됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsnap.h

## <a name="csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageimpl::취소토클로즈

복구할 수 없는 변경이 모달 속성 시트 페이지의 데이터에 대해 변경된 후 이 함수를 호출합니다.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>설명

이 함수는 **확인** 버튼을 **닫고** **취소** 단추를 비활성화하도록 변경합니다. 이렇게 변경하면 변경 사항이 영구적이며 수정을 취소할 수 없음을 사용자에게 알릴 수 있습니다.

모덜리스 속성 시트에는 `CancelToClose` 기본적으로 **취소** 단추가 없기 때문에 멤버 함수는 모덜리스 속성 시트에서 아무 것도 수행하지 않습니다.

## <a name="csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageimpl::CSnapInPropertyPageImpl

`CSnapInPropertyPageImpl` 개체를 생성합니다.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszTitle*<br/>
【인】 속성 페이지의 제목입니다.

### <a name="remarks"></a>설명

기본 구조를 초기화하려면 [CSnapInPropertyPageImpl::Create를](#create)호출합니다.

## <a name="csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapIn속성 페이지 임플::만들기

이 함수를 호출하여 속성 페이지의 기본 구조를 초기화합니다.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Return Value

새로 만든 `PROPSHEETPAGE` 속성 시트의 특성을 포함하는 구조체에 대한 핸들입니다.

### <a name="remarks"></a>설명

먼저 이 함수를 호출하기 전에 [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl을](#csnapinpropertypageimpl) 호출해야 합니다.

## <a name="csnapinpropertypageimplm_psp"></a><a name="m_psp"></a>CSnapInPropertyPageimpl::m_psp

`m_psp`의 특성을 저장하는 `PROPSHEETPAGE`구조입니다.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>설명

이 구조를 사용하여 생성된 후 속성 페이지의 모양을 초기화합니다.

멤버 목록을 포함하여 이 구조에 대한 자세한 내용은 Windows SDK의 [PROPSHEETPAGE를](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3) 참조하십시오.

## <a name="csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageimpl::적용

이 멤버 함수는 사용자가 **확인** 또는 **지금 적용** 단추를 클릭할 때 호출됩니다.

```
BOOL OnApply();
```

### <a name="return-value"></a>Return Value

변경이 수락되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

프레임워크에서 호출하기 전에 `OnApply` 해당 매개 `SetModified` 변수를 TRUE로 호출하고 설정해야 합니다. 이렇게 하면 사용자가 속성 페이지에서 변경하는 즉시 **지금 적용** 버튼이 활성화됩니다.

이 멤버 함수를 재정의하여 사용자가 **지금 적용** 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다. 재정의 할 때 함수는 변경 내용을 수락하기 위해 TRUE를 반환하고 FALSE는 변경 사항이 적용되지 않도록해야합니다.

TRUE를 반환하는 `OnApply` 기본 구현입니다.

## <a name="csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageimpl::OnHelp

이 멤버 함수는 사용자가 속성 페이지에 대한 **도움말** 단추를 클릭할 때 호출됩니다.

```cpp
void OnHelp();
```

### <a name="remarks"></a>설명

속성 페이지에 대한 도움말을 표시하려면 이 멤버 함수를 재정의합니다.

## <a name="csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageimpl::온킬액티브

이 멤버 함수는 페이지가 더 이상 활성 페이지가 아니면 호출됩니다.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Return Value

데이터가 성공적으로 업데이트된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 특수 데이터 유효성 검사 작업을 수행합니다.

## <a name="csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapIn속성 페이지 임플::온쿼리취소

이 멤버 함수는 사용자가 **취소** 단추를 클릭하고 취소 작업이 수행되기 전에 호출됩니다.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Return Value

취소 작업을 허용하는 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 사용자가 **취소** 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다.

TRUE를 반환하는 `OnQueryCancel` 기본 구현입니다.

## <a name="csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageimpl::온리셋

이 멤버 함수는 사용자가 **취소** 단추를 클릭할 때 호출됩니다.

```cpp
void OnReset();
```

### <a name="remarks"></a>설명

이 함수가 호출되면 사용자가 이전에 **지금 적용** 단추를 클릭한 모든 속성 페이지의 변경 내용이 삭제되고 속성 시트에 포커스가 유지됩니다.

이 멤버 함수를 재정의하여 사용자가 **취소** 단추를 클릭할 때 프로그램에서 수행되는 작업을 지정합니다.

## <a name="csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapIn속성 페이지 임플::온셋

이 멤버 함수는 사용자가 페이지를 선택하고 활성 페이지가 될 때 호출됩니다.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Return Value

페이지가 성공적으로 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

페이지가 활성화될 때 작업을 수행하도록 이 멤버 함수를 재정의합니다. 이 멤버 함수의 재정의는 다른 처리가 완료되기 전에 기본 버전을 호출해야 합니다.

기본 구현은 TRUE를 반환합니다.

## <a name="csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageimpl::온위저백

이 멤버 함수는 사용자가 마법사에서 **뒤로** 단추를 클릭할 때 호출됩니다.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Return Value

- 0을 사용하여 자동으로 이전 페이지로 이동합니다.

- -1 페이지가 변경 되지 않도록 합니다.

다음 페이지가 아닌 다른 페이지로 이동하려면 표시할 대화 상자의 식별자를 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 **뒤로** 단추를 클릭할 때 사용자가 수행해야 하는 일부 작업을 지정합니다.

## <a name="csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageimpl::온위저피니

이 멤버 함수는 사용자가 마법사에서 **완료** 단추를 클릭할 때 호출됩니다.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Return Value

마법사가 완료될 때 속성 시트가 소멸되는 경우 비영입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 **완료** 단추를 클릭할 때 사용자가 수행해야 하는 일부 작업을 지정합니다.

## <a name="csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageimpl::OnWizardNext

이 멤버 함수는 사용자가 마법사에서 **다음** 단추를 클릭할 때 호출됩니다.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Return Value

- 0을 사용하여 자동으로 다음 페이지로 이동합니다.

- -1 페이지가 변경 되지 않도록 합니다.

다음 페이지가 아닌 다른 페이지로 이동하려면 표시할 대화 상자의 식별자를 반환합니다.

### <a name="remarks"></a>설명

다음 **단추를** 클릭할 때 사용자가 수행해야 하는 일부 작업을 지정하려면 이 멤버 함수를 재정의합니다.

## <a name="csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapIn속성 페이지 임플::쿼리 형제

이 멤버 함수를 호출하여 속성 시트의 각 페이지에 메시지를 전달합니다.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*wParam*<br/>
【인】 추가 메시지 종속 정보를 지정합니다.

*lParam*<br/>
【인】 추가 메시지 종속 정보를 지정합니다.

### <a name="return-value"></a>Return Value

메시지가 다음 속성 페이지로 전달되지 않아야 하는 경우 0이 아님을 그렇지 않으면 0.

### <a name="remarks"></a>설명

페이지가 영하지 않은 값을 반환하는 경우 속성 시트는 후속 페이지로 메시지를 보내지 않습니다.

## <a name="csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapIn속성 페이지 임플::집합수정

속성 페이지의 설정을 적절한 외부 개체에 적용해야 하는지 여부에 따라 이 멤버 함수를 호출하여 **지금 적용** 단추를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>매개 변수

*b 변경되었습니다.*<br/>
【인】 TRUE는 속성 페이지 설정이 마지막으로 적용된 이후 수정되었음을 나타냅니다. false는 속성 페이지 설정이 적용되었거나 무시되어야 함을 나타냅니다.

### <a name="remarks"></a>설명

속성 시트는 호출한 속성 페이지즉"인 페이지를 `SetModified( TRUE )`추적합니다. 페이지 **Apply Now** 중 하나를 호출하면 `SetModified( TRUE )` 지금 적용 버튼이 항상 활성화됩니다. **페이지** 중 하나를 호출할 `SetModified( FALSE )` 때 지금 적용 단추는 비활성화되지만 다른 페이지중 어느 페이지도 "더럽지 않은" 경우에만 사용할 수 없습니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
