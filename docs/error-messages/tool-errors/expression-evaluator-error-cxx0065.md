---
title: 식 계산기 오류 CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: b4120deec3c8e7ce14e381f782904cf83a588e43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184426"
---
# <a name="expression-evaluator-error-cxx0065"></a>식 계산기 오류 CXX0065

변수에 스택 프레임이 필요 합니다.

현재 범위 내에 있지만 아직 만들지 않은 변수가 식에 포함 되어 있습니다.

이 오류는 함수에 대 한 작업을 수행 하는 동안에는 함수에 대 한 스택 프레임을 아직 설정 하지 않은 경우 또는 함수의 종료 코드를 한 단계씩 실행 한 경우에 발생할 수 있습니다.

식을 계산 하기 전에 스택 프레임이 설정 될 때까지 프롤로그 코드를 단계별로 실행 합니다.

이 오류는 CAN0065와 동일 합니다.
