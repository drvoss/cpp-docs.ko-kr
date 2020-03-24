---
title: 프로젝트를 혼합 모드에서 순수 IL로 변환
ms.date: 08/19/2019
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
ms.openlocfilehash: 8b22f3aaf706fa096f6c25ab8e9fdab6dc512cd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208811"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>프로젝트를 혼합 모드에서 순수 IL로 변환

모든 Visual C++ CLR 프로젝트는 기본적으로 C 런타임 라이브러리에 연결 됩니다. 따라서 이러한 프로젝트는 공용 언어 런타임 (관리 코드)을 대상으로 하는 코드와 네이티브 코드를 결합 하기 때문에 혼합 모드 응용 프로그램으로 분류 됩니다. 컴파일된 경우 MSIL (Microsoft 중간 언어)이 라고도 하는 IL (중간 언어)로 컴파일됩니다.

> [!IMPORTANT]
> Visual Studio 2015은 더 이상 사용 되지 않으며 Visual Studio 2017에서는 CLR 응용 프로그램에 대 한 **/clr: pure** 또는 **/clr: safe** 코드 생성을 더 이상 지원 하지 않습니다. 순수한 또는 safe 어셈블리가 필요한 경우 응용 프로그램을로 C#변환 하는 것이 좋습니다.

**/Clr: pure** 또는 **/clr: safe**를 지 원하는 C++ 이전 버전의 Microsoft 컴파일러 도구 집합을 사용 하는 경우 다음 절차를 사용 하 여 코드를 순수 MSIL로 변환할 수 있습니다.

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>혼합 모드 응용 프로그램을 순수 중간 언어로 변환 하려면

1. CRT ( [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md) )에 대 한 링크를 제거 합니다.

   1. 응용 프로그램의 진입점을 정의 하는 .cpp 파일에서 진입점을 `Main()`변경 합니다. `Main()`를 사용 하면 프로젝트가 CRT에 연결 되지 않습니다.

   2. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **속성** 을 선택 하 여 응용 프로그램에 대 한 속성 페이지를 엽니다.

   3. **링커에**대 한 **고급** 프로젝트 속성 페이지에서 **진입점** 을 선택한 다음이 필드에 **Main** 을 입력 합니다.

   4. 콘솔 응용 프로그램의 경우 **링커에**대 한 **시스템** 프로젝트 속성 페이지에서 **하위 시스템** 필드를 선택 하 고 **콘솔 (/SUBSYSTEM: console)** 로 변경 합니다.

      > [!NOTE]
      > **하위 시스템** 필드는 기본적으로 **windows (/SUBSYSTEM: windows)** 로 설정 되어 있기 때문에 Windows Forms 응용 프로그램에 대해이 속성을 설정할 필요가 없습니다.

   5. *Stdafx.h*에서 모든 `#include` 문을 주석 처리 합니다. 예를 들어 콘솔 응용 프로그램에서 다음을 수행 합니다.

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       -또는-

       예를 들어 Windows Forms 응용 프로그램에서 다음을 수행 합니다.

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Windows Forms 응용 프로그램의 경우, `#include`를 참조 하는 문을 주석으로 처리 합니다. 예를 들면 다음과 같습니다.

      ```cpp
      // #include <windows.h>
      ```

2. Stdafx.h에 다음 코드를 추가 *합니다*.

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. 모든 관리 되지 않는 형식 제거:

   해당 하는 경우 관리 되지 않는 형식을 [System](/dotnet/api/system) 네임 스페이스의 구조체에 대 한 참조로 바꿉니다. 다음 표에서는 일반적인 관리 되는 형식을 나열 합니다.

   |구조체|설명|
   |---------------|-----------------|
   |[Boolean](/dotnet/api/system.boolean)|부울 값을 나타냅니다.|
   |[Byte](/dotnet/api/system.byte)|부호 없는 8비트 정수를 나타냅니다.|
   |[Char](/dotnet/api/system.char)|유니코드 문자를 나타냅니다.|
   |[DateTime](/dotnet/api/system.datetime)|일반적으로 날짜와 시간으로 표시된 시간을 나타냅니다.|
   |[Decimal](/dotnet/api/system.decimal)|10진수를 나타냅니다.|
   |[Double](/dotnet/api/system.double)|배정밀도 부동 소수점 숫자를 나타냅니다.|
   |[Guid](/dotnet/api/system.guid)|GUID(Globally Unique Identifier)를 나타냅니다.|
   |[Int16](/dotnet/api/system.int16)|부호 있는 16비트 정수를 나타냅니다.|
   |[Int32](/dotnet/api/system.int32)|부호 있는 32비트 정수를 나타냅니다.|
   |[Int64](/dotnet/api/system.int64)|부호 있는 64비트 정수를 나타냅니다.|
   |[IntPtr](/dotnet/api/system.intptr)|포인터나 핸들을 나타내는 데 사용되는 플랫폼별 형식입니다.|
   |[SByte](/dotnet/api/system.byte)|8비트 부호 있는 정수를 나타냅니다.|
   |[단일](/dotnet/api/system.single)|단정밀도 부동 소수점 숫자를 나타냅니다.|
   |[TimeSpan](/dotnet/api/system.timespan)|시간 간격을 나타냅니다.|
   |[UInt16](/dotnet/api/system.uint16)|16비트 부호 없는 정수를 나타냅니다.|
   |[UInt32](/dotnet/api/system.uint32)|32비트 부호 없는 정수를 나타냅니다.|
   |[UInt64](/dotnet/api/system.uint64)|64비트 부호 없는 정수를 나타냅니다.|
   |[UIntPtr](/dotnet/api/system.uintptr)|포인터나 핸들을 나타내는 데 사용되는 플랫폼별 형식입니다.|
   |[Void](/dotnet/api/system.void)|값을 반환 하지 않는 메서드를 나타냅니다. 즉, 메서드에 void 반환 형식이 있습니다.|
