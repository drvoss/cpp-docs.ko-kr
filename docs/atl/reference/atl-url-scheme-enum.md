---
title: ATL_URL_SCHEME 열거형
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 6d8307d6ea51c5ec7e63735360b8628a4c1ed782
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168581"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

이 열거형의 멤버는 [말아](curl-class.md)가 이해 하는 체계에 대 한 상수를 제공 합니다.

## <a name="syntax"></a>구문

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>요구 사항

**헤더:**

## <a name="see-also"></a>참고 항목

[개념](../active-template-library-atl-concepts.md)<br/>
[말아 넘기기:: SetScheme](curl-class.md#setscheme)<br/>
[말아 넘기기:: GetScheme](curl-class.md#getscheme)
