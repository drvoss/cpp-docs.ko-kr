---
title: Platform::CallbackContext 열거형
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 1daa3988fcb985dab9d3083233a3703a20cc2fdb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214277"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext 열거형

콜백 함수(이벤트 처리기)가 실행되는 스레드 컨텍스트를 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>멤버

|형식 코드|설명|
|---------------|-----------------|
|Any|콜백 함수가 모든 스레드 컨텍스트에서 실행될 수 있습니다.|
|동일|콜백 함수가 비동기 작업을 시작한 스레드 컨텍스트에서만 실행될 수 있습니다.|

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** Platform

**메타데이터:** platform.winmd
