---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 4f5b662223914cbb4970188595afb52cc2500cd4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440381"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL을 바인딩할 수 있는지 여부를 지정합니다.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>설명

**/Allowbind** 옵션은 DLL의 헤더에 해당 이미지를 바인딩할 수 있음을 나타내는 비트를 설정 합니다. 바인딩을 사용 하면 로더가 참조 된 각 DLL에 대해 주소를 다시 지정 하 고 주소를 수정 하지 않아도 되는 경우 이미지를 더 빨리 로드할 수 있습니다. 디지털 서명 된 경우에는 DLL이 바인딩되지 않도록 할 수 있습니다. 바인딩에서 서명을 무효화 합니다. ASLR을 지 원하는 Windows 버전에서 **/DYNAMICBASE** 를 사용 하 여 이미지에 대해 aslr (주소 공간 레이아웃 임의 설정)을 사용 하는 경우 바인딩이 적용 되지 않습니다.

**/Allowbind: NO** 를 사용 하 여 BIND에서 DLL을 바인딩하지 않도록 합니다.

자세한 내용은 [/Allowbind](allowbind-prevent-dll-binding.md) 링커 옵션을 참조 하세요.

## <a name="see-also"></a>참고 항목

[EDITBIN 옵션](editbin-options.md)
