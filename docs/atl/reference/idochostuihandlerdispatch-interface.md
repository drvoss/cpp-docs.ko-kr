---
title: IDocHostUIHandlerDispatch 인터페이스
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: b7072b80b738aa12635427a2604b38fb3585b452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329718"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch 인터페이스

Microsoft HTML 구문 분석 및 렌더링 엔진에 대한 인터페이스입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

> [!NOTE]
> 다음 표의 링크는 [IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) 인터페이스의 멤버에 대한 INet SDK 참조 항목에 대한 링크입니다. `IDocHostUIHandlerDispatch``IDocUIHostHandler`와 동일한 기능을 가지고 있으며, `IDocHostUIHandlerDispatch` 그 차이는 dispinterface인 반면 `IDocUIHostHandler` 사용자 지정 인터페이스입니다.

|||
|-|-|
|[사용 모드 없는](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|[IOleInPlaceActiveObject::EnableModeless의](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)MSHTML 구현에서 호출 . MSHTML이 모달 UI를 표시할 때라고도 합니다.|
|[필터데이터오브젝트](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|호스트가 MSHTML의 데이터 개체를 대체할 수 있도록 MSHTML에서 호스트를 호출합니다.|
|[겟드롭타겟](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|호스트가 대체 [IDropTarget을](/windows/win32/api/oleidl/nn-oleidl-idroptarget)제공할 수 있도록 드롭 대상으로 사용될 때 MSHTML에서 호출합니다.|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|호스트의 IDispatch 인터페이스를 가져오려면 MSHTML에서 호출합니다.|
|[겟호스트정보](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML 호스트의 UI 기능을 검색합니다.|
|[겟옵션키패스](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML이 사용자 기본 설정을 저장하는 레지스트리 키를 반환합니다.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML이 메뉴와 도구 모음을 제거할 때 호출됩니다.|
|[온닥윈도우활성화](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|[IOleInPlaceActiveObject::OnDocWindowActivate의](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)MSHTML 구현에서 호출됩니다.|
|[온프레임 윈도우활성화](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|[IOleInPlaceActiveObject::OnFrameWindowActivate의](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)MSHTML 구현에서 호출됩니다.|
|[크기 조정테두리](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|[IOleInPlaceActiveObject::ResizeBorder의](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)MSHTML 구현에서 호출 .|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|컨텍스트 메뉴를 표시하려면 MSHTML에서 호출됩니다.|
|[쇼이 (것)이](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|호스트가 MSHTML 메뉴 및 도구 모음을 대체할 수 있습니다.|
|[번역가속기](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|[IOleInPlaceActiveObject::번역가속기](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) 또는 [IOleControlSite::TranslateAccelerator가](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) 호출될 때 MSHTML에 의해 호출됩니다.|
|[번역Url](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|호스트가 로드할 URL을 수정할 수 있도록 MSHTML에서 호출합니다.|
|[업데이트 UI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|명령 상태가 변경되었음을 호스트에 알립니다.|

## <a name="remarks"></a>설명

호스트는 이 인터페이스를 구현하여 Microsoft HTML 구문 분석 및 렌더링 엔진(MSHTML)에서 사용하는 메뉴, 도구 모음 및 컨텍스트 메뉴를 대체할 수 있습니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의는 아래와 같이 IDL 또는 C++로 사용할 수 있습니다.

|정의 유형|파일|
|---------------------|----------|
|Idl|아틀리페이스.아이들|
|C++|ATLIFace.h (ATLBase.h에도 포함)|

## <a name="see-also"></a>참고 항목

[이도위호스트핸들러](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
