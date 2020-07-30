---
title: BufferCommand 열거형
description: 'CMemFile:: GetBufferPtr ()을 통해 메모리 파일을 작업 하는 데 사용 되는 BufferCommand 열거형에 대해 설명 합니다.'
ms.date: 07/23/2020
f1_keywords:
- afx/buffercommand
helpviewer_keywords:
- buffercommand enumeration [MFC]
ms.openlocfilehash: f2f553df56fadd99b65b04cce9a97917425ed70b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212075"
---
# <a name="buffercommand-enumeration"></a>BufferCommand 열거형

[Cmemfile:: GetBufferPtr](cmemfile-class.md#getbufferptr) 에서 파일 지원 메모리 버퍼에 대해 수행할 작업을 결정 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

``` cpp
public enum BufferCommand
{
   bufferRead,
   bufferWrite,
   bufferCommit,
   bufferCheck
};
```

## <a name="members"></a>멤버

|Name|설명|
|-|-|
| `bufferRead` | 파일 지원 메모리 버퍼를 읽습니다. |
| `bufferWrite` | 파일 지원 메모리 버퍼에 씁니다. |
| `bufferCommit` | 파일 지원 메모리 버퍼의 현재 위치를 커밋된 버퍼의 끝으로 이동 합니다. |
| `bufferCheck` | 파일 지원 메모리 버퍼의 크기가 증가할 수 있는지 여부를 확인 합니다. |

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의 됨)
