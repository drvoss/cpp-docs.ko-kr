---
title: 액티브 기술 및 DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: f67fb9548601ac705ceda08d20d3049f0bf1e0a5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221008"
---
# <a name="active-technology-and-dlls"></a>액티브 기술 및 DLL

액티브 기술은 DLL 내에서 개체 서버가 완전히 구현되도록 합니다. 관련 형식의 서버를 in-process 서버라고 합니다. MFC는 모든 바로 편집 기능에 대해 in-process 서버를 완전히 지원하지는 않습니다. 그 주된 이유는 서버가 컨테이너의 기본 메시지 루프로 후크될 수 있는 방법이 액티브 기술에 없기 때문입니다. MFC에서 액셀러레이터 키 및 유휴 시간 프로세스를 처리하기 위해서는 컨테이너 애플리케이션의 메시지 루프에 액세스해야 합니다.

사용자 인터페이스가 없는 자동화 서버를 작성하는 경우에는 해당 서버를 in-process 서버로 만든 다음 DLL에 완전히 포함시킬 수 있습니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [자동화 서버](../mfc/automation-servers.md)

## <a name="see-also"></a>참조

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
