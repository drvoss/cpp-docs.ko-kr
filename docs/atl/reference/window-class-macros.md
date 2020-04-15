---
title: 창 클래스 매크로
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: 18c0912c506bc52421b18d36346204b557c0fc5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325729"
---
# <a name="window-class-macros"></a>창 클래스 매크로

이러한 매크로는 창 클래스 유틸리티를 정의합니다.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|새 창 클래스의 이름을 지정할 수 있습니다.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(비주얼 스튜디오 2017) 새 창 클래스의 이름과 새 클래스가 사용할 창 프로시저인 둘러싸는 클래스를 지정할 수 있습니다.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|새 창 클래스의 기반이 되는 기존 창 클래스의 이름을 지정할 수 있습니다.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|클래스의 매개 변수를 지정할 수 있습니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS

새 창 클래스의 이름을 지정할 수 있습니다. 이 매크로를 ATL ActiveX 컨트롤의 컨트롤 클래스에 배치합니다.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>매개 변수

*WndClassName*<br/>
【인】 새 창 클래스의 이름입니다. NULL이면 ATL은 창 클래스 이름을 생성합니다.

### <a name="remarks"></a>설명

/허용 컴파일러 옵션을 사용하는 경우 DECLARE_WND_CLASS 컴파일러 오류가 발생합니다. 대신 DECLARE_WND_CLASS2 사용합니다.

DECLARE_WND_CLASS [CWndClassInfo에서](cwndclassinfo-class.md)정보를 관리할 새 창 클래스의 이름을 지정할 수 있습니다. DECLARE_WND_CLASS 다음과 같은 정적 함수를 구현하여 새 창 클래스를 정의합니다.

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS 새 창에 대해 다음 스타일을 지정합니다.

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS 기본 창의 배경색도 지정합니다. [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) 매크로를 사용하여 고유한 스타일과 배경색을 제공합니다.

[CWindowImpl은](cwindowimpl-class.md) DECLARE_WND_CLASS 매크로를 사용하여 새 창 클래스를 기반으로 창을 만듭니다. 이 동작을 재정의하려면 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) 매크로를 사용하거나 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수의 고유한 구현을 제공합니다.

ATL에서 창 사용에 대 한 자세한 내용은 [ATL 창 클래스](../../atl/atl-window-classes.md)문서를 참조 하십시오.

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2

(비주얼 스튜디오 2017) DECLARE_WND_CLASS 비슷하지만 /permissive- 옵션을 사용하여 컴파일 할 때 종속 이름 오류를 피할 수있는 추가 매개 변수가 있습니다.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>매개 변수

*WndClassName*<br/>
【인】 새 창 클래스의 이름입니다. NULL이면 ATL은 창 클래스 이름을 생성합니다.

*클래스 를 둘러싸는*<br/>
【인】 새 창 클래스를 둘러싸는 창 클래스의 이름입니다. NULL이 될 수 없습니다.

### <a name="remarks"></a>설명

/permissive-옵션을 사용하는 경우 DECLARE_WND_CLASS 종속 이름을 포함하기 때문에 컴파일 오류가 발생합니다. DECLARE_WND_CLASS2 이 매크로가 사용되고 /permissive-플래그 에서 오류를 일으키지 않는 클래스의 이름을 명시적으로 지정해야 합니다.
그렇지 않으면 이 매크로는 [DECLARE_WND_CLASS.](#declare_wnd_class)

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS

클래스의 매개 변수를 지정할 수 있습니다. 이 매크로를 ATL ActiveX 컨트롤의 컨트롤 클래스에 배치합니다.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>매개 변수

*WndClassName*<br/>
【인】 *OrigWndClassName을*수퍼클래스로 지정하는 창 클래스의 이름입니다. NULL이면 ATL은 창 클래스 이름을 생성합니다.

*오리그웬드클래스이름*<br/>
【인】 기존 창 클래스의 이름입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하면 기존 창 클래스를 수퍼클래스로 지정할 수 있습니다. [CWndClassInfo는](cwndclassinfo-class.md) 슈퍼 클래스의 정보를 관리합니다.

DECLARE_WND_SUPERCLASS 다음과 같은 정적 함수를 구현합니다.

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

기본적으로 [CWindowImpl은](cwindowimpl-class.md) [DECLARE_WND_CLASS](#declare_wnd_class) 매크로를 사용하여 새 창 클래스를 기반으로 창을 만듭니다. -derived 클래스에서 DECLARE_WND_SUPERCLASS `CWindowImpl`매크로를 지정하면 window 클래스는 기존 클래스를 기반으로 하지만 창 프로시저를 사용합니다. 이 기술을 수퍼 클래스링이라고 합니다.

DECLARE_WND_CLASS 및 DECLARE_WND_SUPERCLASS 매크로를 사용하는 것 외에도 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) 함수를 사용자 고유의 구현으로 재정의할 수 있습니다.

ATL에서 창 사용에 대 한 자세한 내용은 [ATL 창 클래스](../../atl/atl-window-classes.md)문서를 참조 하십시오.

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX

새 창 클래스의 기반이 되는 기존 창 클래스의 이름을 지정할 수 있습니다. 이 매크로를 ATL ActiveX 컨트롤의 컨트롤 클래스에 배치합니다.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>매개 변수

*WndClassName*<br/>
【인】 새 창 클래스의 이름입니다. NULL이면 ATL은 창 클래스 이름을 생성합니다.

*스타일*<br/>
【인】 창의 스타일입니다.

*bkgnd*<br/>
【인】 창의 배경색입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하면 [CWndClassInfo](cwndclassinfo-class.md)에서 정보를 관리하는 새 창 클래스의 클래스 매개 변수를 지정할 수 있습니다. DECLARE_WND_CLASS_EX 다음과 같은 정적 함수를 구현하여 새 창 클래스를 정의합니다.

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

기본 스타일과 배경색을 사용하려면 [DECLARE_WND_CLASS](#declare_wnd_class) 매크로를 사용합니다. ATL에서 창 사용에 대 한 자세한 내용은 [ATL 창 클래스](../../atl/atl-window-classes.md)문서를 참조 하십시오.

## <a name="see-also"></a>참고 항목

[매크로](atl-macros.md)
