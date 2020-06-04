---
title: /ERRORREPORT(editbin.exe)
description: Microsoft EDITBIN 유틸리티/ERRORREPORT 명령줄 옵션에 대 한 참조입니다.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT_editbin
helpviewer_keywords:
- -ERRORREPORT editbin option
- ERRORREPORT editbin option
- /ERRORREPORT editbin option
ms.assetid: eca66ac3-b754-4bd7-9dd4-e04fc79a71b6
ms.openlocfilehash: 4456a49cc53b21bd24c616852159ca299181071b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439907"
---
# <a name="errorreport-editbinexe"></a>/ERRORREPORT(editbin.exe)

> [!NOTE]
> /ERRORREPORT 옵션은 사용 되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

## <a name="syntax"></a>구문

> **/ERRORREPORT** \[ **NONE** \| **프롬프트** \| **QUEUE** \| **SEND** ]

## <a name="remarks"></a>설명

**/ERRORREPORT** 인수는 Windows 오류 보고 서비스 설정에 의해 재정의 됩니다. Windows 오류 보고에서 보고를 사용 하도록 설정한 경우 EDITBIN은 내부 오류에 대 한 보고서를 Microsoft에 자동으로 보냅니다. Windows 오류 보고에서 사용 하지 않도록 설정한 경우 보고서가 전송 되지 않습니다.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](editbin-options.md)
