---
title: Concurrency 네임스페이스 상수(AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
ms.openlocfilehash: 2d304728f5bdca8f4bfb39cdb26baad984e63097
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883730"
---
# <a name="concurrency-namespace-constants-amp"></a>Concurrency 네임스페이스 상수(AMP)

|||
|-|-|
|[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)|[MODULENAME_MAX_LENGTH](#modulename_max_length)|

## <a name="hlsl_max_num_buffers"></a>HLSL_MAX_NUM_BUFFERS 상수

DirectX에서 허용 하는 최대 버퍼 수입니다.

```cpp
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;
```

## <a name="modulename_max_length"></a>MODULENAME_MAX_LENGTH 상수

모듈 이름의 최대 길이를 저장 합니다. 이 값은 컴파일러와 런타임에서 동일해야 합니다.

```cpp
static const UINT MODULENAME_MAX_LENGTH = 1024;
```

## <a name="see-also"></a>참고 항목

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
