---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: b2ff9929de74d99fbc45e4f4ff38fd6b939697bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373829"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

실행 가능 이미지가 높은 엔트로피 64비트 ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 지정합니다.

## <a name="syntax"></a>구문

> **/HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>설명

이 옵션은 *실행 가능한 이미지*(.dll 파일 또는 .exe 파일)의 헤더를 수정 하 여 64 비트 주소에 대 한 ASLR이 지원 되는지 여부를 나타냅니다. 실행 파일과 해당 파일이 종속된 모든 모듈에 대해 이 옵션을 설정하면 64비트 ASLR을 지원하는 운영 체제가 64비트 가상 주소 공간에서 임의 주소를 사용하여 로그 시에 실행 가능 이미지의 세그먼트 기준 주소를 다시 지정할 수 있습니다. 이처럼 큰 주소 공간을 사용하는 경우 공격자가 특정 메모리 영역의 위치를 추측하기가 어려워집니다.

기본적으로 링커는 64 비트 실행 가능 이미지에 대해 **/HIGHENTROPYVA** 를 사용 하도록 설정 합니다. 이 옵션을 사용 하려면 [/LARGEADDRESSAWARE](largeaddressaware.md)가 필요 하며,이는 기본적으로 64 비트 이미지에도 사용 됩니다. **/HIGHENTROPYVA** 는 32 비트 실행 가능 이미지에 적용할 수 없으며,이 옵션은 무시 됩니다. 이 옵션을 명시적으로 사용 하지 않도록 설정 하려면 **/HIGHENTROPYVA: NO**를 사용 합니다. 이 옵션을 적용 하려면 [/DYNAMICBASE](dynamicbase.md) 옵션도 설정 해야 합니다.

## <a name="see-also"></a>참조

- [EDITBIN 옵션](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Windows ISV 소프트웨어 보안 방어](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
