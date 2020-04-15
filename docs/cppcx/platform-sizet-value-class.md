---
title: Platform::SizeT 값 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 5add9212dc2655bc37cd357741073f855b009bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322157"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT 값 클래스

개체의 크기를 나타냅니다. SizeT는 부호 없는 데이터 형식입니다.

## <a name="syntax"></a>구문

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>멤버

|멤버|Description|
|------------|-----------------|
|[SizeT::SizeT 생성자](#ctor)|지정된 값을 사용하여 클래스의 새 인스턴스를 초기화합니다.|

### <a name="requirements"></a>요구 사항

**지원되는 최소 클라이언트:** 윈도우 8

**지원되는 최소 서버:** 윈도우 서버 2012

**네임스페이스:** Platform

**메타데이터:** 플랫폼.winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a>SizeT::SizeT 생성자

지정된 값을 사용하여 SizeT의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>매개 변수

*값1*<br/>
부호 없는 32비트 값입니다.

*Value2*<br/>
부호 없는 32비트 값에 대한 포인터입니다.

## <a name="see-also"></a>참고 항목

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
