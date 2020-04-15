---
title: IAxWinAmbientDispatchEx 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: f4816846801e388619db62998ec979a1100916ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329987"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx 인터페이스

이 인터페이스는 호스트된 컨트롤에 대한 추가 주변 속성을 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[세트 앰비언트 디스패치](#setambientdispatch)|이 메서드는 사용자 정의 인터페이스와 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.|

## <a name="remarks"></a>설명

ATL 및 호스트 ActiveX 컨트롤, 특히 주변 속성이 있는 ActiveX 컨트롤에 정적으로 연결된 ATL 응용 프로그램에 이 인터페이스를 포함합니다. 이 인터페이스를 포함하지 않으면 "LIBID를 CComModule::Init에 전달하는 것을 잊어 버렸습니까?"

이 인터페이스는 ATL의 ActiveX 컨트롤 호스팅 개체에 의해 노출됩니다. [IAxWinAmbientDispatch에서](../../atl/reference/iaxwinambientdispatch-interface.md)파생된 `IAxWinAmbientDispatchEx` 이 메서드는 ATL에서 제공하는 주변 속성 인터페이스를 사용자 고유의 인터페이스로 보완할 수 있는 메서드를 추가합니다.

<xref:System.Windows.Forms.AxHost>코드가 포함된 형식 `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` 라이브러리에 대한 형식 정보를 로드하려고 합니다.

ATL90.dll에 연결하는 경우 **AXHost는** DLL의 형식 라이브러리에서 형식 정보를 로드합니다.

자세한 내용은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의는 다음 표와 같이 여러 형태로 제공됩니다.

|정의 유형|파일|
|---------------------|----------|
|Idl|아틀리페이스.idl|
|형식 라이브러리|ATL.dll|
|C++|atliface.h (ATLBase.h에도 포함)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWin 앰비언트 디스패치Ex::세트앰비언트 디스패치

이 메서드는 사용자 정의 인터페이스와 기본 앰비언트 속성 인터페이스를 보완 하기 위해 호출 됩니다.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>매개 변수

*p디스패치*<br/>
새 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

새 `SetAmbientDispatch` 인터페이스에 대한 포인터로 호출될 때 이 새 인터페이스는 [IAxWinAmbientDispatch에서](../../atl/reference/iaxwinambientdispatch-interface.md)해당 속성이 아직 제공되지 않은 경우 호스팅 컨트롤에서 요청한 모든 속성 또는 메서드를 호출하는 데 사용됩니다.

## <a name="see-also"></a>참고 항목

[IAxWinAmbientDispatch 인터페이스](../../atl/reference/iaxwinambientdispatch-interface.md)
