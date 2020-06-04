---
title: COM 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 191a0ba0aeda6ad18cdac7ba14f7ab5f3b2282f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326596"
---
# <a name="com-map-macros"></a>COM 맵 매크로

이러한 매크로는 COM 인터페이스 맵을 정의합니다.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM 인터페이스 맵 항목의 시작 부분을 표시합니다.|
|[END_COM_MAP](#end_com_map)|COM 인터페이스 맵 항목의 끝을 표시합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="begin_com_map"></a><a name="begin_com_map"></a>BEGIN_COM_MAP

COM 맵은 을 통해 `QueryInterface`개체의 인터페이스를 클라이언트에 노출시키는 메커니즘입니다.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 인터페이스를 노출하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

[CComObjectRootEx::InternalQueryInterface는](ccomobjectrootex-class.md#internalqueryinterface) COM 맵의 인터페이스에 대한 포인터만 반환합니다. BEGIN_COM_MAP 매크로로 인터페이스 맵을 [시작하고, COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 매크로 또는 변형 중 하나를 사용하여 각 인터페이스에 대한 항목을 [추가하고, END_COM_MAP](#end_com_map) 매크로로 맵을 완성합니다.

### <a name="example"></a>예제

ATL [비퍼](../../overview/visual-cpp-samples.md) 샘플에서:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a>END_COM_MAP

COM 인터페이스 맵의 정의를 종료합니다.

```
END_COM_MAP()
```

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)<br/>
[COM 맵 전역 함수](../../atl/reference/com-map-global-functions.md)
