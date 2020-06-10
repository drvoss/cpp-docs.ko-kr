---
title: CObject에서 새 클래스를 파생시켜야 합니까?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 371ede0f0921182c066b4cb224e66b18eb6f1208
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616736"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject에서 새 클래스를 파생시켜야 합니까?

아니요, 수행하지 않습니다.

Serialization 또는 동적 creatability 같이 제공 하는 기능이 필요한 경우 [CObject](reference/cobject-class.md) 에서 클래스를 파생 시킵니다. 많은 데이터 클래스는 파일에 대해 serialize되어야 하므로 `CObject`에서 해당 클래스를 파생하는 것이 좋습니다. 에서 파생 된 클래스의 예제는 `CObject` [Scribble 샘플](../overview/visual-cpp-samples.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[CObject 클래스: 질문과 대답](cobject-class-frequently-asked-questions.md)
