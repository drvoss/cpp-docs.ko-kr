---
title: Backward Compatibility
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: 2c2b4570e5e3131911e7f424280f16e9977f047e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438568"
---
# <a name="backward-compatibility"></a>Backward Compatibility

제품 버전 간의 호환성을 위해 OLDNAMES.LIB 라이브러리는 이전 이름을 새 이름에 매핑합니다. 예를 들어 `open`은 `_open`에 매핑됩니다. 다음 명령줄 옵션 조합을 사용하여 컴파일할 때는 OLDNAMES.LIB를 명시적으로 링크해야 합니다.

- `/Zl`(개체 파일에서 기본 라이브러리 이름 생략)과 `/Ze`(기본값, Microsoft 확장 사용)

- `/link`(링커 컨트롤), `/NOD`(기본 라이브러리 검색 없음) 및 `/Ze`

컴파일러 명령줄 옵션에 대한 자세한 내용은 [컴파일러 참조](../build/reference/compiler-options.md)를 확인하세요.

## <a name="see-also"></a>참고 항목

[호환성](../c-runtime-library/compatibility.md)
