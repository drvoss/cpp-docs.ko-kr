---
title: MFC ActiveX 컨트롤 마법사, 컨트롤 이름
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: eff7b537e7fe5c19d10cce8766557a3d1ff49342
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077513"
---
# <a name="control-names-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사, 컨트롤 이름

컨트롤 클래스 및 속성 페이지 클래스의 이름과 컨트롤의 형식 이름 및 형식 식별자를 지정 합니다. **짧은 이름을**제외 하 고 다른 모든 필드는 독립적으로 편집할 수 있습니다. **짧은 이름**에 대 한 텍스트를 변경 하면이 페이지에 있는 다른 모든 필드의 이름에 변경 내용이 반영 됩니다. 이 명명 동작은 컨트롤을 개발할 때 모든 이름을 쉽게 식별할 수 있도록 설계되었습니다.

- **짧은 이름**

   컨트롤에 약식 이름을 제공 합니다. 기본적으로이 이름은 **새 프로젝트** 대화 상자에서 제공한 프로젝트 이름을 기반으로 합니다. 사용자가 제공 하는 이름에 따라 해당 필드를 개별적으로 변경 하지 않는 한 클래스 이름, 형식 이름 및 형식 식별자가 결정 됩니다.

- **컨트롤 클래스 이름**

   기본적으로 컨트롤 클래스의 이름은 짧은 이름을 기반으로 하며 `C` 접두사와 `Ctrl` 접미사로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`이면 컨트롤 클래스 이름이 `CPriceCtrl`됩니다.

- **컨트롤 .h 파일**

   기본적으로 헤더 파일의 이름은 짧은 이름을 기반으로 하며 `Ctrl` 접미사와 `.h` 파일 확장명으로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`경우 헤더 파일 이름은 `PriceCtrl.h`됩니다. 이 필드의 이름은 컨트롤 클래스 이름과 일치 해야 합니다.

- **컨트롤 .cpp 파일**

   기본적으로 헤더 파일의 이름은 짧은 이름을 기반으로 하며 `Ctrl` 접미사와 `.cpp` 파일 확장명으로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`경우 헤더 파일 이름은 `PriceCtrl.cpp`됩니다. 이 필드의 이름은 헤더 이름과 일치 해야 합니다.

- **컨트롤 형식 이름**

   기본적으로 컨트롤 형식의 이름은 약식 이름과 `Control`를 기준으로 합니다. 예를 들어 컨트롤의 약식 이름이 `Price`경우 컨트롤 클래스 형식 이름은 `Price Control`됩니다. 이 필드의 값을 변경 하는 경우 이름이 상속을 표시 하는지 확인 합니다.

- **컨트롤 형식 ID**

   컨트롤 클래스의 컨트롤 형식 ID를 설정 합니다. 컨트롤은 프로젝트에 추가 될 때이 문자열을 레지스트리에 씁니다. 컨테이너 응용 프로그램은이 문자열을 사용 하 여 컨트롤의 인스턴스를 만듭니다.

   기본적으로 컨트롤 형식 ID는 **새 프로젝트** 대화 상자에 표시 된 프로젝트 이름과 약식 이름에 따라 달라 집니다. 이 이름은 형식 이름과 일치 해야 합니다.

   기본적으로 컨트롤 형식 ID는 다음과 같이 표시 됩니다.

   *짧은 이름* Ctrl. 1

   이 대화 상자에서 짧은 이름을 변경 하면 컨트롤 형식 ID가 다음과 같이 표시 됩니다.

   *NewShortName* Ctrl. 1

- **PropPage 클래스 이름**

   기본적으로 속성 페이지 클래스의 이름은 짧은 이름을 기반으로 하며 `C` 접두사 및 `PropPage` 접미사로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`이면 속성 페이지 클래스 이름이 `CPricePropPage`됩니다. 이 이름은 `PropPage`에 추가 된 컨트롤 클래스 이름과 일치 해야 합니다.

- **PropPage 파일**

   기본적으로 속성 페이지 헤더 파일의 이름은 짧은 이름을 기반으로 하며, `PropPage` 접미사 및 `.h` 파일 확장명으로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`이면 속성 페이지 헤더 파일 이름이 `PricePropPage.h`됩니다. 이 이름은 클래스 이름과 일치 해야 합니다.

- **PropPage 파일**

   기본적으로 속성 페이지 구현 파일의 이름은 짧은 이름을 기반으로 하며, `PropPage` 접미사 및 `.cpp` 파일 확장명으로 사용 됩니다. 예를 들어 컨트롤의 약식 이름이 `Price`이면 속성 페이지 헤더 파일 이름이 `PricePropPage.cpp`됩니다. 이 이름은 헤더 파일 이름과 일치 해야 합니다.

- **PropPage 형식 이름**

   기본적으로 속성 페이지 유형 이름은 짧은 이름을 기반으로 하며 그 뒤에 `Property Page`합니다. 예를 들어 컨트롤의 약식 이름이 `Price`이면 속성 페이지 형식 이름이 `Price Property Page`됩니다. 이 필드의 값을 변경 하는 경우 이름이 컨트롤 클래스를 표시 하는지 확인 합니다.

- **PropPage 형식 ID**

   속성 페이지 클래스의 ID를 설정 합니다. 컨트롤은 프로젝트에 적용 될 때 레지스트리에이 문자열을 씁니다. 컨테이너 응용 프로그램은이 문자열을 사용 하 여 컨트롤의 속성 페이지 인스턴스를 만듭니다.

   기본적으로 속성 페이지 유형 ID는 **새 프로젝트** 대화 상자에 표시 된 프로젝트 이름 및 짧은 이름에 따라 달라 집니다. 이 이름은 형식 이름과 일치 해야 합니다.

   기본적으로 속성 페이지 유형 ID는 다음과 같이 표시 됩니다.

   *짧은 이름* PropPage. 1

   이 대화 상자에서 짧은 이름을 변경 하면 속성 페이지 유형 ID가 다음과 같이 표시 됩니다.

   *NewShortName* PropPage. 1

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[애플리케이션 설정, MFC ActiveX 컨트롤 마법사](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[MFC ActiveX 컨트롤 마법사, 컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Visual Studio C++ 프로젝트용으로 만든 파일 형식](../../build/reference/file-types-created-for-visual-cpp-projects.md)
