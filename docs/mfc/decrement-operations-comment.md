---
title: --Operations 주석
ms.date: 11/04/2016
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
ms.openlocfilehash: 7e4d0549d3d77916df532f105dc58ed9e9f78af2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240602"
---
# <a name="-operations-comment"></a>// Operations 주석

MFC 클래스 선언의 `// Operations` 섹션에는 개체를 호출하여 작업을 수행하거나 동작을 실행(작업 수행)할 수 있는 멤버 함수가 포함되어 있습니다. 이러한 함수는 일반적으로 부작용이 있기 때문에 **const** 속성이 아닙니다. 클래스의 필요에 따라 가상 또는 비가상이 될 수 있습니다. 일반적으로 이러한 멤버는 public입니다.	

[주석의 예제](../mfc/an-example-of-the-comments.md)의 `CStdioFile` 클래스의 예제 목록에는 주석 아래에 두 멤버 함수, `ReadString`, `WriteString`를 포함하고 있습니다.

특성과 마찬가지로 작업을 더 세분화할 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[implementation 주석](../mfc/decrement-implementation-comment.md)<br/>
[constructors 주석](../mfc/decrement-constructors-comment.md)<br/>
[attributes 주석](../mfc/decrement-attributes-comment.md)<br/>
[overridables 주석](../mfc/decrement-overridables-comment.md)
