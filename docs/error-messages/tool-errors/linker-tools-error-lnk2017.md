---
title: 링커 도구 오류 LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: 02e80de5c34809a331003f3b0fb28d32e138a531
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194735"
---
# <a name="linker-tools-error-lnk2017"></a>링커 도구 오류 LNK2017

/LARGEADDRESSAWARE 없이 ' segment '로의 ' 기호 ' 재배치가 잘못 되었습니다.

32 비트 주소를 사용 하 여 64 비트 이미지를 빌드하려고 합니다. 이렇게 하려면 다음을 수행 해야 합니다.

- 고정 로드 주소를 사용 합니다.

- 이미지를 3gb로 제한 합니다.

- [/Largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)를 지정 합니다.
