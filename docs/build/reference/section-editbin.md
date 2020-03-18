---
title: /SECTION(EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section_editbin
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 770e1d1c1cf288a7fe68f5bd076791d43f5b8572
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438920"
---
# <a name="section-editbin"></a>/SECTION(EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>설명

이 옵션은 섹션의 특성을 변경 하 여 섹션의 개체 파일이 컴파일 또는 연결 되었을 때 설정 된 특성을 재정의 합니다.

콜론 ( **:** ) 뒤에 섹션의 *이름을* 지정 합니다. 섹션 이름을 변경 하려면 *이름* 에 등호 (=)를 추가 하 고 섹션의 *newname* 을 사용 합니다.

섹션의 `attributes`을 설정 하거나 변경 하려면 쉼표 ( **,** ), 하나 이상의 특성 문자를 차례로 지정 합니다. 특성을 부정 하려면 해당 문자 앞에 느낌표 (!)를 사용 합니다. 다음 문자는 메모리 특성을 지정 합니다.

|attribute|설정|
|---------------|-------------|
|c|코드|
|d|삭제 가능한|
|e|실행 개체(executable)|
|i|초기화 데이터|
|k|캐시 된 가상 메모리|
|m|링크 제거|
|o|링크 정보|
|p|페이징 가상 메모리|
|r|읽기|
|s|공유|
|u|초기화 되지 않은 데이터|
|w|쓰기|

*맞춤*을 제어 하려면 다음과 같이 문자 **A** 와 다음 문자 중 하나를 지정 하 여 맞춤 크기를 바이트 단위로 설정 합니다.

|문자|맞춤 크기 (바이트)|
|---------------|-----------------------------|
|1|1|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|x|맞춤 없음|

`attributes` 및 *맞춤* 문자를 공백이 없는 문자열로 지정 합니다. 문자는 대/소문자를 구분 하지 않습니다.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](editbin-options.md)
