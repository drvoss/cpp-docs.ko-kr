---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: f455e855e782a939e79898ee46e445f65d25d37a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170594"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 전용**

캡슐화 된 인터페이스 포인터에 `IUnknown`의 **릴리스** 멤버 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
void Release( );
```

## <a name="remarks"></a>주의

캡슐화 된 인터페이스 포인터에 대 한 `IUnknown::Release`를 호출 하 여이 인터페이스 포인터가 NULL 인 경우 `E_POINTER` 오류를 발생 시킵니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
