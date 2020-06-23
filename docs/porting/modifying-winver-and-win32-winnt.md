---
title: WINVER 및 _WIN32_WINNT 업데이트
description: 업그레이드 된 Visual Studio c + + 프로젝트에서 WINVER 및 _WIN32_WINNT 매크로를 업데이트 하는 시기와 방법을 설명 합니다.
ms.date: 06/19/2020
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a0faed612517bf26cd89473e1aef248fb9e7b33e
ms.sourcegitcommit: 493fd8747f832e1facb9a76c437a25a5c9fb55f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141056"
---
# <a name="update-winver-and-_win32_winnt"></a>WINVER 및 _WIN32_WINNT 업데이트

Windows SDK를 사용 하는 경우 코드를 실행할 수 있는 Windows 버전을 지정할 수 있습니다. 전처리기 매크로 **WINVER** 및 **_WIN32_WINNT** 코드에서 지 원하는 최소 운영 체제 버전을 지정 합니다. Visual Studio 및 Microsoft c + + 컴파일러는 Windows 7 SP1 이상 버전을 대상으로 지원 합니다. 이전 도구 집합에는 Windows XP SP2, Windows Server 2003 SP1, Vista 및 Windows Server 2008에 대 한 지원이 포함 됩니다. Windows 95, Windows 98, Windows ME, Windows NT 및 Windows 2000은 지원 되지 않습니다.

이전 프로젝트를 업그레이드 하는 경우 **WINVER** 또는 **_WIN32_WINNT** 매크로를 업데이트 해야 할 수 있습니다. 지원 되지 않는 버전의 Windows에 대 한 값이 할당 된 경우 이러한 매크로와 관련 된 컴파일 오류가 표시 될 수 있습니다.

## <a name="remarks"></a>설명

매크로를 수정 하려면 헤더 파일 (예: Windows를 대상으로 하는 일부 프로젝트 템플릿에 포함 된 *targetver. h*)에서 다음 줄을 추가 합니다.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

이 예제의 매크로는 모든 버전의 Windows 10 운영 체제를 대상으로 하도록 설정 되어 있습니다. 가능한 값은 Windows 헤더 파일 *sdkddkver.h 포함*에 나열 되며, 각 주요 windows 버전에 대 한 매크로를 정의 합니다. 이전 Windows 플랫폼을 지원 하기 위해 응용 프로그램을 빌드하려면 *sdkddkver.h*를 포함 합니다. 그런 다음 *sdkddkver.h 포함*를 포함 하기 전에 **WINVER** 및 **_WIN32_WINNT** 매크로를 가장 오래 된 지원 되는 플랫폼으로 설정 합니다. Windows의 각 주 버전에 대 한 값을 인코딩하는 Windows 10 SDK 버전 *sdkddkver.h 포함* 의 줄은 다음과 같습니다.

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

버전 관리에 대 한 보다 세분화 된 접근 방식을 위해 *sdkddkver.h 포함*에서 ntddi 버전 상수를 사용할 수 있습니다. 다음은 Windows 10 SDK 버전 10.0.18362.0에서 *sdkddkver.h 포함* 에 의해 정의 된 매크로 중 일부입니다.

```C
//
// NTDDI version constants
//
#define NTDDI_WIN7                          0x06010000
#define NTDDI_WIN8                          0x06020000
#define NTDDI_WINBLUE                       0x06030000
#define NTDDI_WINTHRESHOLD                  0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10                         0x0A000000  /* ABRACADABRA_THRESHOLD */
#define NTDDI_WIN10_TH2                     0x0A000001  /* ABRACADABRA_WIN10_TH2 */
#define NTDDI_WIN10_RS1                     0x0A000002  /* ABRACADABRA_WIN10_RS1 */
#define NTDDI_WIN10_RS2                     0x0A000003  /* ABRACADABRA_WIN10_RS2 */
#define NTDDI_WIN10_RS3                     0x0A000004  /* ABRACADABRA_WIN10_RS3 */
#define NTDDI_WIN10_RS4                     0x0A000005  /* ABRACADABRA_WIN10_RS4 */
#define NTDDI_WIN10_RS5                     0x0A000006  /* ABRACADABRA_WIN10_RS5 */
#define NTDDI_WIN10_19H1                    0x0A000007  /* ABRACADABRA_WIN10_19H1*/

#define WDK_NTDDI_VERSION                   NTDDI_WIN10_19H1 /* ABRACADABRA_WIN10_19H1 */

//
// masks for version macros
//
#define OSVERSION_MASK      0xFFFF0000
#define SPVERSION_MASK      0x0000FF00
#define SUBVERSION_MASK     0x000000FF

//
// macros to extract various version fields from the NTDDI version
//
#define OSVER(Version)  ((Version) & OSVERSION_MASK)
#define SPVER(Version)  (((Version) & SPVERSION_MASK) >> 8)
#define SUBVER(Version) (((Version) & SUBVERSION_MASK) )
```

코드에서 **Osver**, **Spver**및 **subver** 매크로를 사용 하 여 다양 한 수준의 API 지원에 대 한 조건부 컴파일을 제어할 수 있습니다.

*Sdkddkver.h 포함* 에 나열 된 이러한 Windows 버전 중 일부가 표시 되지 않을 수 있습니다. 즉, 이전 버전의 Windows SDK을 사용 하 고 있는 것입니다. 기본적으로 Visual Studio의 새 Windows 프로젝트는 Windows 10 SDK를 사용 합니다.

> [!NOTE]
> 내부 MFC 헤더를 애플리케이션에 포함하는 경우에는 값 작동 여부가 보장되지 않습니다.

`/D` 컴파일러 옵션을 사용하여 이 매크로를 정의할 수도 있습니다. 자세한 내용은 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)을 참조하세요.

이러한 매크로의 의미에 대한 자세한 내용은 [Windows 헤더 사용](/windows/win32/WinProg/using-the-windows-headers)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
