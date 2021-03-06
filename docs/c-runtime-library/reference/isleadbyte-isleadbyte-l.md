---
title: "isleadbyte, _isleadbyte_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
apilocation:
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82c8f6eb81e96527c0955d9b19fd8ce931e8d7fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
문자가 멀티바이트 문자의 선행 바이트인지 여부를 결정합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## <a name="return-value"></a>반환 값  
 `isleadbyte`는 인수가 테스트 조건을 충족할 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. "C" 로캘 및 SBCS(싱글바이트 문자 집합) 로캘에서 `isleadbyte` 는 항상 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `isleadbyte` 매크로는 인수가 멀티바이트 문자의 첫 번째 바이트인 경우 0이 아닌 값을 반환합니다. `isleadbyte` -1에서 모든 정수 인수에 대 한 의미 있는 결과 생성 (`EOF`)를 `UCHAR_MAX` (0xFF) (포함).  
  
 `isleadbyte` 의 예상 인수 형식은 `int`입니다. 부호 있는 문자가 전달되는 경우 컴파일러에서 부호 확장을 통해 정수로 변환하여 예측할 수 없는 결과를 생성할 수 있습니다.  
  
 `_l` 접미사가 있는 이 함수의 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘을 사용한다는 점을 제외하고는 동일합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|항상 false를 반환합니다.|**_** `isleadbyte`|항상 false를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)