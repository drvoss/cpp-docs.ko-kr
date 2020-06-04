---
title: '&lt;codecvt&gt; 열거형'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: e67290d8de0b8251191c4a93b66b7e19a293ed61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371935"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; 열거형

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a>codecvt_mode 열거

[로캘](../standard-library/locale-class.md) 면에 대한 구성 정보를 지정합니다.

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>설명

열거형은 [ \<codecvt>](../standard-library/codecvt.md)선언된 로캘 면에 구성 정보를 제공하는 세 개의 상수를 정의합니다. 고유 값은 다음과 같습니다.

- `consume_header` - 멀티바이트 시퀀스를 읽을 때 초기 헤더 시퀀스를 사용하고, 읽을 후속 멀티바이트 시퀀스의 엔디언(Endianness)을 결정할 경우

- `generate_header` - 멀티바이트 시퀀스를 작성할 때 초기 헤더 시퀀스를 생성하고, 작성할 후속 멀티바이트 시퀀스의 엔디언(Endianness)을 보급할 경우

- `little_endian` - 기본 big endian 순서와는 대조적으로 little endian 순서로 멀티바이트 시퀀스를 생성할 경우

이러한 상수는 임의 조합에서 함께 OR 처리될 수 있습니다.

## <a name="see-also"></a>참고 항목

[\<코덱트>](../standard-library/codecvt.md)
