---
title: CVTRES 심각한 오류 CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: b7e67df24d41b1e8826673146fcc27fd93d143fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196549"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES 심각한 오류 CVT1100

중복 리소스-유형: 유형, 이름: 이름, 언어: 언어, 플래그: 플래그, 크기: 크기

지정 된 리소스가 두 번 이상 지정 되었습니다.

링커가 형식 라이브러리를 만들고 [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) 를 지정 하지 않았고 프로젝트의 리소스가 이미 1을 사용 하는 경우이 오류가 발생할 수 있습니다. 이 경우/TLBID를 지정 하 고 다른 숫자를 65535까지 지정 합니다.
