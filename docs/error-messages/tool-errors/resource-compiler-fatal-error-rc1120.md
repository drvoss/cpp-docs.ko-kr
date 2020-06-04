---
title: 리소스 컴파일러 심각한 오류 RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: 855a76ff63145695a7063944701d7acc684e0084
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173012"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>리소스 컴파일러 심각한 오류 RC1120

메모리 부족, 필요한 바이트 수

리소스 컴파일러는 힙에 저장 하는 항목에 대 한 저장소 부족을 실행 했습니다. 일반적으로 기호가 너무 많은 경우에 발생 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. Windows 스왑 파일 공간을 늘립니다. 스왑 파일 공간을 높이는 방법에 대 한 자세한 내용은 Windows 도움말의 가상 메모리를 참조 하십시오.

1. 불필요 한 포함 파일, 특히 불필요 한 `#define`s 및 함수 프로토타입을 제거 합니다.

1. 현재 파일을 둘 이상의 파일로 분할 하 고 별도로 컴파일합니다.

1. 시스템에서 실행 되는 다른 프로그램 또는 드라이버를 제거 합니다 .이로 인해 많은 양의 메모리가 소비 될 수 있습니다.
