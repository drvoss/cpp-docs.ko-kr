---
title: LIB 입력 파일
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: de81f79eecf3fc73c02894747f4b97cb107cf892
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328223"
---
# <a name="lib-input-files"></a>LIB 입력 파일

LIB에서 예상하는 입력 파일은 다음 표와 같이 사용 중인 모드에 따라 달라집니다.

|Mode|입력|
|----------|-----------|
|기본값(라이브러리 작성 또는 수정)|COFF 개체(.obj) 파일, COFF 라이브러리(.lib), 32비트 객체 모델 형식(OMF) 개체(.obj) 파일|
|/extract를 가진 멤버 추출|COFF 라이브러리(.lib)|
|내보내기 파일 빌드 및 가져오기 라이브러리/DEF|모듈 정의 (.def) 파일, COFF 개체 (.obj) 파일, COFF 라이브러리 (.lib), 32 비트 OMF 개체 (.obj) 파일|

> [!NOTE]
> LIB의 16비트 버전에서 만든 OMF 라이브러리는 32비트 버전의 LIB에 대한 입력으로 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

[LIB 개요](overview-of-lib.md)
