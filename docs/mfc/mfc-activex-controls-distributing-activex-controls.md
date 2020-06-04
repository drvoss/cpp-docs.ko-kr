---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 배포'
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
ms.openlocfilehash: 1ada1c801b2d9d62f1cc4cd5bf72a2995225b3de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364621"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 배포

이 문서에서는 ActiveX 컨트롤 재배포와 관련된 몇 가지 문제에 대해 설명합니다.

- [ANSI 또는 유니코드 제어 버전](#_core_ansi_or_unicode_control_versions)

- [액티브X 컨트롤 및 재배포 가능 DLL 설치](#_core_installing_activex_controls_and_redistributable_dlls)

- [컨트롤 등록](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a>ANSI 또는 유니코드 제어 버전

ANSI 또는 유니코드 버전의 컨트롤을 제공할지 아니면 둘 다 를 제공할지 결정해야 합니다. 이 결정은 ANSI 및 유니코드 문자 집합에 내재된 이식성 요소를 기반으로 합니다.

모든 Win32 운영 체제에서 작동하는 ANSI 컨트롤은 다양한 Win32 운영 체제 간의 최대 이식성을 허용합니다. 유니코드 컨트롤은 Windows NT(버전 3.51 이상)에서만 작동하지만 Windows 95 또는 Windows 98에서는 작동하지 않습니다. 휴대성이 주요 관심사인 경우 ANSI 제어를 제공합니다. 컨트롤이 Windows NT에서만 실행되는 경우 유니코드 컨트롤을 발송할 수 있습니다. 둘 다 제공하도록 선택하고 응용 프로그램에서 사용자의 운영 체제에 가장 적합한 버전을 설치하도록 할 수도 있습니다.

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a>액티브X 컨트롤 및 재배포 가능 DLL 설치

ActiveX 컨트롤과 함께 제공하는 설치 프로그램은 Windows 디렉터리의 특별한 하위 디렉터리를 만들고 컨트롤을 설치해야 합니다. OCX 파일.

> [!NOTE]
> 설치 프로그램에서 `GetWindowsDirectory` Windows API를 사용하여 Windows 디렉터리 이름을 가져옵니다. 회사 또는 제품의 이름에서 하위 디렉터리 이름을 파생할 수 있습니다.

설치 프로그램은 Windows 시스템 디렉토리에 필요한 재배포 가능한 DLL 파일을 설치해야 합니다. 사용자 컴퓨터에 이미 있는 DLL이 있는 경우 설치 프로그램에서 해당 버전을 설치 중인 버전과 비교해야 합니다. 버전 번호가 이미 설치된 파일보다 높은 경우에만 파일을 다시 설치합니다.

ActiveX 컨트롤은 OLE 컨테이너 응용 프로그램에서만 사용할 수 있으므로 전체 OLE DLL 집합을 컨트롤에 배포할 필요가 없습니다. 포함된 응용 프로그램(또는 운영 체제 자체)에 표준 OLE DLL이 설치되어 있다고 가정할 수 있습니다.

## <a name="registering-controls"></a><a name="_core_registering_controls"></a>컨트롤 등록

컨트롤을 사용하려면 먼저 Windows 등록 데이터베이스에서 컨트롤에 대한 적절한 항목을 만들어야 합니다. 일부 ActiveX 제어 컨테이너는 사용자가 새 컨트롤을 등록할 수 있는 메뉴 항목을 제공하지만 이 기능은 일부 컨테이너에서 사용하지 못할 수 있습니다. 따라서 설치 프로그램이 설치된 컨트롤을 등록할 수 있습니다.

원하는 경우 설치 프로그램을 작성하여 컨트롤을 직접 등록할 수 있습니다.

Windows `LoadLibrary` API를 사용하여 컨트롤 DLL을 로드합니다. 다음으로, `GetProcAddress` "DllRegisterServer" 함수의 주소를 가져오는 데 사용합니다. 마지막으로 함수를 `DllRegisterServer` 호출합니다. 다음 코드 샘플에서는 컨트롤 라이브러리의 `hLib` 핸들을 저장하고 `lpDllEntryPoint` "DllRegisterServer" 함수의 주소를 저장하는 한 가지 가능한 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

컨트롤을 직접 등록하면 별도의 프로세스(즉, REGSVR32)를 호출하고 로드할 필요가 없으므로 설치 시간이 단축된다는 장점이 있습니다. 또한 등록은 내부 프로세스이므로 설치 프로그램은 외부 프로세스보다 오류 및 예기치 않은 상황을 더 잘 처리할 수 있습니다.

> [!NOTE]
> 설치 프로그램에서 ActiveX 컨트롤을 설치하기 전에 `OleInitialize`을 호출해야 합니다. 설치 프로그램이 완료되면 에 전화하십시오. `OleUnitialize` 이렇게 하면 OLE 시스템 DLL이 ActiveX 컨트롤을 등록하기 위한 적절한 상태에 있게 됩니다.

MFCx0.DLL을 등록해야 합니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
