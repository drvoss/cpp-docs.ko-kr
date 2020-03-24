---
title: NMAKE 심각한 오류 U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: 9c6b939c97f993e42049677292374377d825d474
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193682"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE 심각한 오류 U1051

메모리가 부족 합니다.

메이크파일이 너무 크거나 복잡 하므로 NMAKE에 가상 메모리를 포함 한 메모리가 부족 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 디스크의 공간을 확보 합니다.

1. Windows NT 페이징 파일 또는 Windows 스왑 파일의 크기를 늘립니다.

1. 메이크파일의 일부만 사용 하는 경우 메이크파일을 개별 파일로 나누고!를 사용 합니다 **.** NMAKE가 처리 해야 하는 양을 제한 하는 전처리 지시문입니다. **!** 지시문에!가 포함 되어 있는 경우  **이면**, `!IFDEF`, **! IFNDEF**, **! 그렇지 않으면** **입니다. 다른** `IFDEF`, 및 **! ELSE** `IFNDEF`합니다.
