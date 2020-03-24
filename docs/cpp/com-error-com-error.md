---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 4ac902f0fda90f77526ef53139ef0d523d8c22e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180786"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft 전용**

**_Com_error** 개체를 생성 합니다.

## <a name="syntax"></a>구문

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>매개 변수

*hr*<br/>
HRESULT 정보입니다.

*perrinfo*<br/>
`IErrorInfo` 개체입니다.

*fAddRef*<br/>
기본값을 설정 하면 생성자가 null이 아닌 `IErrorInfo` 인터페이스에서 AddRef를 호출 합니다. 이렇게 하면 인터페이스의 소유권이 **_com_error** 개체로 전달 되는 일반적인 경우에 올바른 참조 횟수를 얻을 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
throw _com_error(hr, perrinfo);
```

코드에서 소유권을 **_com_error** 개체로 전달 하지 않고 **_com_error** 소멸자에서 `Release`을 오프셋 하는 데 `AddRef` 필요한 경우 다음과 같이 개체를 구성 합니다.

```cpp
_com_error err(hr, perrinfo, true);
```

*않도록*<br/>
기존 **_com_error** 개체입니다.

## <a name="remarks"></a>주의

첫 번째 생성자는 HRESULT 및 선택적 `IErrorInfo` 개체를 지정 하 여 새 개체를 만듭니다. 두 번째는 기존 **_com_error** 개체의 복사본을 만듭니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_error 클래스](../cpp/com-error-class.md)
