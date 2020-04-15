---
title: 범주 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 1d8bbae4608aa661bbc612604f7d85855f325f5f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321592"
---
# <a name="category-macros"></a>범주 매크로

이러한 매크로는 범주 맵을 정의합니다.

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|범주 맵의 시작 부분을 표시합니다.|
|[END_CATEGORY_MAP](#end_category_map)|범주 맵의 끝을 표시합니다.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM 개체에 의해 구현되는 범주를 나타냅니다.|
|[REQUIRED_CATEGORY](#required_category)|COM 개체에서 컨테이너에 필요한 범주를 나타냅니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="begin_category_map"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP

범주 맵의 시작 부분을 표시합니다.

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
【인】 범주 맵을 포함하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

범주 맵은 COM 클래스가 구현할 구성 요소 범주와 해당 컨테이너에서 필요한 범주를 지정하는 데 사용됩니다.

COM 클래스에서 구현한 각 범주에 대한 [IMPLEMENTED_CATEGORY](#implemented_category) 항목을 맵에 추가합니다. 클래스에서 구현해야 하는 각 범주에 대한 [REQUIRED_CATEGORY](#required_category) 항목을 맵에 추가합니다. [END_CATEGORY_MAP](#end_category_map) 매크로로 맵의 끝을 표시합니다.

맵에 나열된 구성 요소 범주는 클래스에 연결된 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)경우 모듈이 등록될 때 자동으로 등록됩니다.

> [!NOTE]
> ATL은 표준 구성 요소 범주 관리자를 사용하여 구성 요소 범주를 등록합니다. 모듈이 등록될 때 관리자가 시스템에 없는 경우 등록이 성공하지만 구성 요소 범주는 해당 클래스에 등록되지 않습니다.

구성 요소 범주에 대한 자세한 내용은 [구성 요소 범주란 무엇이며](/windows/win32/com/component-categories-and-how-they-work) Windows SDK에서 어떻게 작동하는지 를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a>END_CATEGORY_MAP

범주 맵의 끝을 표시합니다.

```
END_CATEGORY_MAP()
```

### <a name="example"></a>예제

[BEGIN_CATEGORY_MAP](#begin_category_map)에 대한 예제를 참조하십시오.

## <a name="implemented_category"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY

구성 요소의 [범주 맵에](#begin_category_map) IMPLEMENTED_CATEGORY 매크로를 추가하여 *catID* 매개 변수로 식별된 범주를 구현으로 등록하도록 지정합니다.

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>매개 변수

*Catid*<br/>
【인】 구현된 범주에 대한 전역 고유 식별자(GUID)를 보유하는 CATID 상수 또는 변수입니다. *catID의* 주소가 이동하여 맵에 추가됩니다. 주식 카테고리의 선택은 아래 표를 참조하십시오.

### <a name="remarks"></a>설명

맵에 나열된 구성 요소 범주는 클래스에 연결된 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로가 있는 경우 모듈이 등록될 때 자동으로 등록됩니다.

클라이언트는 클래스에 등록된 범주 정보를 사용하여 인스턴스를 만들지 않고도 클래스의 기능 및 요구 사항을 결정할 수 있습니다.

구성 요소 범주에 대한 자세한 내용은 [구성 요소 범주란 무엇이며](/windows/win32/com/component-categories-and-how-they-work) Windows SDK에서 어떻게 작동하는지 를 참조하십시오.

### <a name="a-selection-of-stock-categories"></a>주식 카테고리 의 선택

|Description|기호|레지스트리 GUID|
|-----------------|------------|-------------------|
|스크립팅에 안전함|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C4C4}|
|초기화에 안전함|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C4C4}|
|간단한 프레임 사이트 봉쇄|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|단순 데이터 바인딩|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|고급 데이터 바인딩|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|창 없는 컨트롤|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|인터넷 인식 개체|샘플 목록은 Windows SDK의 [인터넷 인식 개체를](/windows/win32/com/internet-aware-objects) 참조하십시오.||

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a>REQUIRED_CATEGORY

구성 요소의 [범주 맵에](#begin_category_map) REQUIRED_CATEGORY 매크로를 추가하여 *catID* 매개 변수로 식별된 범주를 요구하는 범주로 등록하도록 지정합니다.

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>매개 변수

*Catid*<br/>
【인】 필수 범주에 대한 전역 고유 식별자(GUID)를 보유하는 CATID 상수 또는 변수입니다. *catID의* 주소가 이동하여 맵에 추가됩니다. 주식 카테고리의 선택은 아래 표를 참조하십시오.

### <a name="remarks"></a>설명

맵에 나열된 구성 요소 범주는 클래스에 연결된 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로가 있는 경우 모듈이 등록될 때 자동으로 등록됩니다.

클라이언트는 클래스에 등록된 범주 정보를 사용하여 인스턴스를 만들지 않고도 클래스의 기능 및 요구 사항을 결정할 수 있습니다. 예를 들어, 컨트롤은 컨테이너가 데이터 바인딩을 지원하도록 요구할 수 있다. 컨테이너는 해당 컨트롤에 필요한 범주에 대한 범주 관리자를 쿼리하여 컨트롤을 호스트하는 데 필요한 기능이 있는지 확인할 수 있습니다. 컨테이너가 필요한 기능을 지원하지 않는 경우 COM 개체 호스트를 거부할 수 있습니다.

샘플 목록을 포함한 구성 요소 범주에 대한 자세한 내용은 [구성 요소 범주란 무엇이며](/windows/win32/com/component-categories-and-how-they-work) Windows SDK에서 어떻게 작동하는지 를 참조하십시오.

### <a name="a-selection-of-stock-categories"></a>주식 카테고리 의 선택

|Description|기호|레지스트리 GUID|
|-----------------|------------|-------------------|
|스크립팅에 안전함|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C4C4}|
|초기화에 안전함|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C4C4}|
|간단한 프레임 사이트 봉쇄|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|단순 데이터 바인딩|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|고급 데이터 바인딩|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|창 없는 컨트롤|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|인터넷 인식 개체|샘플 목록은 Windows SDK의 [인터넷 인식 개체를](/windows/win32/com/internet-aware-objects) 참조하십시오.||

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
