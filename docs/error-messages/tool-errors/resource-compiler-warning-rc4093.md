---
title: 리소스 컴파일러 경고 RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 29d24f1e380f5c531e170e5dc23cf5c77eefb874
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182294"
---
# <a name="resource-compiler-warning-rc4093"></a>리소스 컴파일러 경고 RC4093

비활성 코드에서 문자 상수의 이스케이프 되지 않은 줄 바꿈

`#if`, `#elif`, **#ifdef**또는 **#ifndef** 전처리기 지시문의 상수 식이 0으로 계산 되어 비활성 상태로 코드를 만듭니다. 해당 비활성 코드 내에서 줄 바꿈 문자는 작은따옴표 또는 큰따옴표 집합 안에 표시 됩니다.

다음 큰따옴표로 묶인 모든 텍스트는 문자 상수 내에 있는 것으로 간주 됩니다.
