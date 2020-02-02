---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: a84ca6da22825ca3fa7ab43e43a574fb05caa1a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689833"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE 또는 UTF-16BE로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

*Elem* \
와이드 문자 요소 형식입니다.

*Maxcode* \
로캘 패싯에 대한 최대 문자 수입니다.

*Mode* \
로캘 패싯에 대한 구성 정보입니다.

## <a name="remarks"></a>주의

이 클래스 템플릿에서는 UTF-2 또는 UCF-4로 인코드된 와이드 문자와 UTF-UTF-16LE로 인코딩된 바이트 스트림 (모드 &little_endian 또는 UTF-16이 아닌 경우) 사이를 변환 합니다.

바이트 스트림은 이진 파일에 작성해야 하며, 텍스트 파일에 작성하는 경우 손상될 수 있습니다.

## <a name="requirements"></a>요구 사항

헤더: \<codecvt>

네임 스페이스: std
