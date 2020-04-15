---
title: /MANIFESTINPUT(매니페스트 입력 지정)
ms.date: 07/24/2019
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: d7c8351c915f5666ada9939df686c81c86ab89ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337503"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT(매니페스트 입력 지정)

이미지에 포함된 매니페스트에 포함되도록 매니페스트 입력 파일을 지정합니다.

## <a name="syntax"></a>구문

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>매개 변수

*파일*<br/>
포함된 매니페스트에 포함할 매니페스트 파일입니다.

## <a name="remarks"></a>설명

**/MANIFESTINPUT** 옵션은 실행 파일 이미지에서 포함된 매니페스트를 만드는 데 사용할 입력 파일의 경로를 지정합니다. 매니페스트 입력 파일이 여러 개인 경우 각 입력 파일에 대해 한 번씩 스위치를 여러 번 사용합니다. 매니페스트 입력 파일은 병합되어 포함된 매니페스트를 만듭니다. 이 옵션에는 **/MANIFEST:EMBED** 옵션이 필요합니다.

이 옵션은 Visual Studio에서 직접 설정할 수 없습니다. 대신 프로젝트의 **추가 매니페스트 파일** 속성을 사용하여 포함할 추가 매니페스트 파일을 지정합니다. 자세한 내용은 [매니페스트 도구 속성 페이지를](manifest-tool-property-pages.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
