---
title: _getdiskfree
ms.date: 4/2/2020
api_name:
- _getdiskfree
- _o__getdiskfree
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getdiskfree
- _getdiskfree
helpviewer_keywords:
- diskfree_t type
- _getdiskfree function
- _diskfree_t type
- disk size
- getdiskfree function
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
ms.openlocfilehash: 095a272e1dd85c1b61e1970a1b881737acbb739d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344316"
---
# <a name="_getdiskfree"></a>_getdiskfree

디스크 드라이브에 대한 정보를 사용하여 **_diskfree_t** 구조를 채웁니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned _getdiskfree(
   unsigned drive,
   struct _diskfree_t * driveinfo
);
```

### <a name="parameters"></a>매개 변수

*드라이브*<br/>
정보를 표시할 디스크 드라이브입니다.

*Driveinfo*<br/>
드라이브에 대한 정보로 채워질 **_diskfree_t** 구조입니다.

## <a name="return-value"></a>Return Value

함수가 성공할 경우 반환 값은 0입니다. 함수가 실패할 경우 반환 값은 오류 코드입니다. 운영 체제에서 반환되는 모든 오류에 대해 **errno** 값이 설정됩니다. **errno로**표시되는 오류 조건에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하십시오.

## <a name="remarks"></a>설명

**_diskfree_t** 구조는 Direct.h에 정의되어 있습니다.

```C
struct _diskfree_t {
   unsigned total_clusters;      // The total number of clusters, both used and available, on the disk.
   unsigned avail_clusters;      // The number of unused clusters on the disk.
   unsigned sectors_per_cluster; // The number of sectors in each cluster.
   unsigned bytes_per_sector;    // The size of each sector in bytes.
};
```

이 함수는 해당 매개 변수의 유효성을 검사합니다. *driveinfo* 포인터가 **NULL이거나** *드라이브가* 잘못된 드라이브를 지정하는 경우 이 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 함수는 **EINVAL을** 반환하고 **errno를** **EINVAL로**설정합니다. 올바른 드라이브의 범위는 0에서 26 사이입니다. *드라이브* 값이 0이면 현재 드라이브를 지정합니다. 그 후 숫자는 영어 알파벳 문자로 매핑되므로 1은 드라이브 A를, 3은 드라이브 C를 나타냅니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getdiskfree**|\<direct.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getdiskfree.c
// compile with: /c
#include <windows.h>
#include <direct.h>
#include <stdio.h>
#include <tchar.h>

TCHAR   g_szBorder[] = _T("======================================================================\n");
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");

void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);

int main(int argc, char* argv[]) {
   TCHAR szMsg[4200];
   struct _diskfree_t df = {0};
   ULONG uDriveMask = _getdrives();
   unsigned uErr, uLen, uDrive;

   printf(g_szBorder);
   printf(g_szTitle1);
   printf(g_szTitle2);

   for (uDrive=1; uDrive<=26; ++uDrive) {
      if (uDriveMask & 1) {
         uErr = _getdiskfree(uDrive, &df);
         memcpy(szMsg, g_szLine, sizeof(g_szLine));
         szMsg[3] = uDrive + 'A' - 1;

         if (uErr == 0) {
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);
         }
         else {
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,
                            uErr, 0, szMsg+8, 4100, NULL);
            szMsg[uLen+6] = ' ';
            szMsg[uLen+7] = ' ';
            szMsg[uLen+8] = ' ';
         }

         printf(szMsg);
      }

      uDriveMask >>= 1;
   }

   printf(g_szBorder);
}

void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {
   TCHAR* szCur = szRight;
   int nComma = 0;

   if (uVal) {
      while (uVal && (szCur >= szLeft)) {
         if   (nComma == 3) {
            *szCur = ',';
            nComma = 0;
         }
         else {
            *szCur = (uVal % 10) | 0x30;
            uVal /= 10;
            ++nComma;
         }

         --szCur;
      }
   }
   else {
      *szCur = '0';
      --szCur;
   }

   if (uVal) {
      szCur = szLeft;

      while   (szCur <= szRight) {
         *szCur = '*';
         ++szCur;
      }
   }
}
```

```Output
======================================================================
|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|
|=====|==============|==============|=================|==============|
|  A: | The device is not ready.    |                 |              |
|  C: |    4,721,093 |    3,778,303 |               8 |          512 |
|  D: |    1,956,097 |    1,800,761 |               8 |          512 |
|  E: | The device is not ready.    |                 |              |
======================================================================
```

## <a name="see-also"></a>참고 항목

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
