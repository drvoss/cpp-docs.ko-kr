---
title: /CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 19930591c2d0406c68b1a408622a49c9e8b1d551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322269"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)

**/CLRSUPPORTLASTERROR는**기본적으로 사용 중이며 P/Invoke 메커니즘을 통해 호출된 함수의 마지막 오류 코드를 유지하며, 이를 통해 **/clr로**컴파일된 코드에서 DLLS의 네이티브 함수를 호출할 수 있습니다.

## <a name="syntax"></a>구문

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>설명

마지막 오류 코드를 유지하면 성능이 저하됩니다.  마지막 오류 코드를 보존하는 성능 에러 코드를 유지하지 않으려면 **/CLRSUPPORTLASTERROR:NO로**연결합니다.

시스템 DLL의 함수에 대한 마지막 오류 코드만 보존하는 **/CLRSUPPORTLASTERROR:SYSTEMDLL과**연결하여 성능 영향을 최소화할 수 있습니다.  시스템 DLL은 다음 중 하나로 정의됩니다.

|||||
|-|-|-|-|
|ACLUI. Dll|ACTIVEDS 합니다. DLL|ADPTIF. Dll|ADVAPI32 합니다. DLL|
|아시필트. Dll|오츠. Dll|아비캡32. Dll|아비필32. Dll|
|캐비닛. Dll|CLUSAPI. Dll|COMCTL32. Dll|COMDLG32. Dll|
|COMSVCS. Dll|크레두이. Dll|CRYPT32. Dll|크립토넷. Dll|
|크립투이. Dll|D3D8THK. Dll|DBGENG. Dll|DBGHELP. Dll|
|DCIMAN32. Dll|DNSAPI. Dll|DSPROP. Dll|DSUIEXT. Dll|
|GDI32. Dll|GLU32. Dll|HLINK. Dll|ICM32. Dll|
|이미지HLP. Dll|IMM32. Dll|IPHLPAPI 합니다. DLL|IPROP. Dll|
|KERNEL32 합니다. DLL|KSUSER. Dll|로드퍼. Dll|LZ32. Dll|
|MAPI32. Dll|MGMTAPI. Dll|MOBSYNC. Dll|MPR 합니다. DLL|
|MPRAPI. Dll|MQRT. Dll|MSACM32. Dll|Mscms. Dll|
|MSI입니다. DLL|MSIMG32. Dll|MSRATING. Dll|MSTASK. Dll|
|MSVFW32. Dll|MSWSOCK. Dll|MTXEX. Dll|NDDEAPI. Dll|
|NETAPI32 합니다. DLL|NPPTOOLS. Dll|NTDSAPI. Dll|NTDSBCLI. Dll|
|NTMSAPI. Dll|ODBC32. Dll|ODBCBCP. Dll|OLE32 합니다. DLL|
|OLEACC. Dll|OLEAUT32 합니다. DLL|OLEDLG. Dll|오픈GL32. Dll|
|Pdh. Dll|POWRPROF 합니다. DLL|QOSNAME. Dll|쿼리. Dll|
|RASAPI32. Dll|RASDLG. Dll|RASSAPI. Dll|RESUTILS. Dll|
|RICHED20. Dll|RPCNS4. Dll|RPCRT4 합니다. DLL|Rtm. Dll|
|RTUTILS. Dll|카드DLG. Dll|SECUR32 합니다. DLL|센사피. Dll|
|SETUPAPI 합니다. DLL|Sfc. Dll|SHELL32 합니다. DLL|SHFOLDER. Dll|
|SHLWAPI 합니다. DLL|SISBKUP. Dll|SNMPAPI. Dll|SRCLIENT. Dll|
|Sti. Dll|타피32. Dll|트래픽을. Dll|Url. Dll|
|URLMON. Dll|USER32 합니다. DLL|USERENV 합니다. DLL|USP10. Dll|
|UXTHEME. Dll|VDMDBG. Dll|버전. DLL|Winfax. Dll|
|윈HTTP. Dll|Wininet. Dll|윈MM. Dll|윈스 카드. Dll|
|윈트러스트. Dll|WLDAP32 합니다. DLL|와우32. Dll|WS2_32.DLL|
|WSNMP32. Dll|WSOCK32.DLL|WTSAPI32 합니다. DLL|솔레HLP. Dll|

> [!NOTE]
> CLR 코드에서 동일한 모듈에서 사용되는 관리되지 않는 함수에는 마지막 오류를 보존하는 것이 지원되지 않습니다.

- 자세한 내용은 [/clr (Common Language Runtime Compilation)](clr-common-language-runtime-compilation.md)을 참조하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **Linker** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 옵션을 입력합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 마지막 오류를 수정하는 하나의 내보낸 함수를 사용하여 네이티브 DLL을 정의합니다.

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>예제

다음 샘플에서는 DLL을 사용하여 **/CLRSUPPORTLASTERROR**를 사용하는 방법을 보여 주며.

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
