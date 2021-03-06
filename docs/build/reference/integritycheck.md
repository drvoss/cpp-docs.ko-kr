---
title: /INTEGRITYCHECK | Microsoft Docs
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99caec18162a7506b8b7a467eb7374b6fe4a38d9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

로드할 때 이진 이미지의 디지털 서명을 검사 해야 않도록 지정 합니다.

> **/INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>설명

DLL 파일이 나 실행 파일의 헤더에이 옵션에서 Windows 이미지를 로드할 메모리 관리자에 의해 디지털 서명 확인이 필요한 하는 플래그를 설정 합니다. 버전의 Windows Vista 이전 버전의 Windows는이 플래그를 무시합니다. 이 옵션은 커널 모드 코드를 구현 하 고 모든 장치 드라이버에 대 한 권장 하는 64 비트 Dll에 대 한 설정 되어야 합니다. 자세한 내용은 참조 [커널 모드 코드 서명 요구 사항](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)합니다.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](../../build/reference/editbin-options.md)  
