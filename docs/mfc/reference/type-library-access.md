---
title: 형식 라이브러리 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 1794e16489ab48d919bbd4116588fba4b74b88d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372880"
---
# <a name="type-library-access"></a>형식 라이브러리 액세스

형식 라이브러리는 OLE 컨트롤의 인터페이스를 다른 OLE 인식 응용 프로그램에 노출시다. 하나 이상의 인터페이스를 노출하려면 각 OLE 컨트롤에 형식 라이브러리가 있어야 합니다.

다음 매크로를 사용하면 OLE 컨트롤에서 자체 형식 라이브러리에 대한 액세스를 제공할 수 있습니다.

### <a name="type-library-access"></a>형식 라이브러리 액세스

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|OLE 컨트롤의 `GetTypeLib` 멤버 함수를 선언합니다(클래스 선언에 사용해야 합니다).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|OLE 컨트롤의 `GetTypeLib` 멤버 함수를 구현합니다(클래스 구현에서 사용해야 합니다).|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

컨트롤 클래스의 `GetTypeLib` 멤버 함수를 선언합니다.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
형식 라이브러리와 관련된 컨트롤 클래스의 이름입니다.

### <a name="remarks"></a>설명

컨트롤 클래스 헤더 파일에서 이 매크로를 사용합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

컨트롤의 `GetTypeLib` 멤버 함수를 구현합니다.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
형식 라이브러리와 관련된 컨트롤 클래스의 이름입니다.

*tlid*<br/>
형식 라이브러리의 ID 번호입니다.

*wVerMajor*<br/>
형식 라이브러리 주 버전 번호입니다.

*wVerMinor*<br/>
형식 라이브러리 부 버전 번호입니다.

### <a name="remarks"></a>설명

이 매크로는 DECLARE_OLETYPELIB 매크로를 사용하는 모든 컨트롤 클래스의 구현 파일에 나타나야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
