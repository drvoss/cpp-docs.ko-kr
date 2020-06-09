---
title: 'ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 애플리케이션에 컨트롤 삽입'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 1d2fc82628b3bcf842a6efb1d36ab9e8389fc0ba
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618488"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 애플리케이션에 컨트롤 삽입

Activex 컨트롤 컨테이너 응용 프로그램에서 ActiveX 컨트롤에 액세스할 수 있으려면 activex [컨트롤 삽입](../windows/insert-activex-control-dialog-box.md) 대화 상자를 사용 하 여 컨테이너 응용 프로그램에 activex 컨트롤을 추가 해야 합니다.

Activex 컨트롤을 activex 컨트롤 컨테이너 프로젝트에 추가 하려면 activex 컨트롤 [보기 및 대화 상자에 추가](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)를 참조 하세요.

컨트롤을 추가한 후에는 대화 상자 클래스에 멤버 변수 (ActiveX 컨트롤 형식)를 추가 해야 합니다. 이 절차에 대 한 자세한 내용은 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)를 참조 하세요.

멤버 변수를 추가 하면 래퍼 클래스 라고 하는 클래스가 자동으로 생성 되어 프로젝트에 추가 됩니다. 이 클래스는 컨트롤 컨테이너와 포함 된 컨트롤 간의 인터페이스로 사용 됩니다.

## <a name="see-also"></a>참고 항목

[ActiveX 컨트롤 컨테이너](activex-control-containers.md)
