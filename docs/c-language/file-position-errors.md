---
title: 파일 위치 오류
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: 3d581d86d6f08eee564feb6373a623512085ccca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233659"
---
# <a name="file-position-errors"></a>파일 위치 오류

**ANSI 4.9.9.1, 4.9.9.4** 실패 시 `errno` 매크로가 `fgetpos` 또는 `ftell` 함수를 통해 설정되는 값

`fgetpos` 또는 `ftell`이 실패할 때 `errno`는 위치가 유효하지 않은 경우 매니페스트 상수 `EINVAL`로 설정되고 파일 번호가 잘못된 경우 `EBADF`로 설정됩니다. 상수는 ERRNO.H에서 정의됩니다.

## <a name="see-also"></a>참조

[라이브러리 함수](../c-language/library-functions.md)
