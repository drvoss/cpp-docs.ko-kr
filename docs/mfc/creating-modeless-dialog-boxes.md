---
title: 모덜리스 대화 상자 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7a6125e84438b0ef2ad541c26bda33051d483c8d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619633"
---
# <a name="creating-modeless-dialog-boxes"></a>모덜리스 대화 상자 만들기

모덜리스 대화 상자의 경우 대화 상자 클래스에 고유한 공용 생성자를 제공 해야 합니다. 모덜리스 대화 상자를 만들려면 public 생성자를 호출한 다음 dialog 개체의 [create](reference/cdialog-class.md#create) member 함수를 호출 하 여 대화 상자 리소스를 로드 합니다. 생성자 호출 중 또는 이후에 **Create** 를 호출할 수 있습니다. 대화 상자 리소스에 **WS_VISIBLE**속성이 있는 경우이 대화 상자는 즉시 표시 됩니다. 그렇지 않으면 해당 [ShowWindow](reference/cwnd-class.md#showwindow) 멤버 함수를 호출 해야 합니다.

## <a name="see-also"></a>참고 항목

[MFC에서 대화 상자를 통해 작업](life-cycle-of-a-dialog-box.md)
