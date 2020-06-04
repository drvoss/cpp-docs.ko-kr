---
title: CSecurityAttributes 클래스
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: e0ac813008a028bb233adfb4c7409a0ad62a6b78
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746498"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes 클래스

이 클래스는 보안 특성 구조에 대한 씬 래퍼입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C보안특성::C보안특성](#csecurityattributes)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C보안 특성::설정](#set)|`CSecurityAttributes` 이 메서드를 호출하여 개체의 특성을 설정합니다.|

## <a name="remarks"></a>설명

구조체에는 `SECURITY_ATTRIBUTES` 개체 생성에 사용되는 [보안 설명자가](/windows/win32/api/winnt/ns-winnt-security_descriptor) 포함되어 있으며 이 구조를 지정하여 검색된 핸들이 상속 가능한지 여부를 지정합니다.

Windows의 액세스 제어 모델에 대한 자세한 내용은 Windows SDK의 [액세스 제어를](/windows/win32/SecAuthZ/access-control) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a>C보안특성::C보안특성

생성자입니다.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*r보안 설명자*<br/>
보안 설명자에 대한 참조입니다.

*b상속핸들*<br/>
새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.

## <a name="csecurityattributesset"></a><a name="set"></a>C보안 특성::설정

`CSecurityAttributes` 이 메서드를 호출하여 개체의 특성을 설정합니다.

```cpp
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*r보안 설명자*<br/>
보안 설명자에 대한 참조입니다.

*b상속핸들*<br/>
새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.

### <a name="remarks"></a>설명

이 메서드는 생성자에서 `CSecurityAttributes` 개체를 초기화하는 데 사용됩니다.

## <a name="see-also"></a>참조

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[보안 설명자](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 글로벌 기능](../../atl/reference/security-global-functions.md)
