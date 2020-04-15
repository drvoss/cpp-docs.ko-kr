---
title: WinModule 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 3d7d001a2835514cc5385a7069c0bcda58cdd88e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329355"
---
# <a name="winmodule-global-functions"></a>WinModule 전역 함수

이러한 함수는 구조 `_AtlCreateWndData` 작업에 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 표에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>아틀윈 모듈애드생성WndData

이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>매개 변수

*pWin모듈*<br/>
모듈의 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조에 대한 포인터입니다.

*Pdata*<br/>
[초기화되고](../../atl/reference/atlcreatewnddata-structure.md) 현재 모듈에 추가할 _AtlCreateWndData 구조에 대한 포인터입니다.

*pObject*<br/>
개체의 **이** 포인터에 대한 포인터입니다.

### <a name="remarks"></a>설명

클래스 인스턴스를 `_AtlCreateWndData` 참조하는 데 사용되는 **이** 포인터를 저장하는 데 사용되는 구조를 초기화하고 모듈 의 `_ATL_WIN_MODULE70` 구조에서 참조하는 목록에 추가합니다. [CAtlWinModule에 의해 호출 ::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata).

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>아틀윈 모듈 추출생성데이터 생성

기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>매개 변수

*pWin모듈*<br/>
모듈의 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

이 함수는 모듈의 `_AtlCreateWndData` `_ATL_WIN_MODULE70` 구조에서 참조하는 목록에서 기존 구조를 추출합니다.

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)
