---
title: 예외 처리 매크로
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 2beffbbed0efee799005190bd7fd071a2087e4d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330081"
---
# <a name="exception-handling-macros"></a>예외 처리 매크로

이러한 매크로는 예외 처리를 지원합니다.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|연결된 `_ATLTRY`에서 발생하는 오류를 처리하는 명령문 .|
|[_ATLCATCHALL](#_atlcatchall)|연결된 `_ATLTRY`에서 발생하는 오류를 처리하는 명령문 .|
|[_ATLTRY](#_atltry)|오류가 발생할 수 있는 보호된 코드 섹션을 표시합니다.|

## <a name="requirements"></a>요구 사항:

**헤더:** atldef.h

## <a name="_atlcatch"></a><a name="_atlcatch"></a>_ATLCATCH

연결된 `_ATLTRY`에서 발생하는 오류를 처리하는 명령문 .

```
_ATLCATCH(e)
```

### <a name="parameters"></a>매개 변수

*전자*<br/>
잡을 예외.

### <a name="remarks"></a>설명

와 `_ATLTRY`함께 사용 됩니다. 지정된 유형의 C++ 예외를 처리하기 위해 C++ [catch(CAtlException e)로](../../cpp/try-throw-and-catch-statements-cpp.md) 확인합니다.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a>_ATLCATCHALL

연결된 `_ATLTRY`에서 발생하는 오류를 처리하는 명령문 .

```
_ATLCATCHALL
```

### <a name="remarks"></a>설명

와 `_ATLTRY`함께 사용 됩니다. 모든 유형의 C++ 예외를 처리하기 위해 C++ [catch(...)로](../../cpp/try-throw-and-catch-statements-cpp.md) 확인합니다.

## <a name="_atltry"></a><a name="_atltry"></a>_ATLTRY

오류가 발생할 수 있는 보호된 코드 섹션을 표시합니다.

```
_ATLTRY
```

### <a name="remarks"></a>설명

[_ATLCATCH](#_atlcatch) 또는 [_ATLCATCHALL](#_atlcatchall)함께 사용됩니다. C ++ 기호 로 확인 [시도합니다.](../../cpp/try-throw-and-catch-statements-cpp.md)

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)
