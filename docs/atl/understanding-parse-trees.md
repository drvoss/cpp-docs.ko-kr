---
title: ATL 등록자 및 구문 분석 트리
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: de2cea9b0e7b7c62236f708f9aa8217eaa5df51d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168698"
---
# <a name="understanding-parse-trees"></a>구문 분석 트리 이해

등록자 스크립트에서 구문 분석 트리를 하나 이상 정의할 수 있습니다. 각 구문 분석 트리는 다음과 같은 형태입니다.

> \<루트 키> {\<레지스트리 식>} +

여기서

> \<루트 키>:: = HKEY_CLASSES_ROOT | HKEY_CURRENT_USER | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_LOCAL_MACHINE | HKEY_USERS | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_CURRENT_CONFIG | HKCR | HKCU | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKLM | HKU | HKPD | HKDD | HKCC

> \<레지스트리 식>:: = \<Add Key> | \<키> 삭제

> \<Add key>:: = [**ForceRemove** | **NoRemove** | **val**]\<키 이름> [\<키 값>] [{\<추가 키>}]

> \<키>:: = **delete**\<키 이름>

> \<키 이름>:: = **'**\<영숫자>+**'**

> \<영숫자>:: = *NULL이 아닌 모든 문자 (예: ASCII 0* )

> \<키 값>:: = \<키 유형>\<키 이름>

> \<키 유형>:: = **s** | **d**

> \<키 값>:: = **'**\<영숫자>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT`및 `HKCR` 는 동일 합니다. `HKEY_CURRENT_USER` 및 `HKCU` 는 동일 합니다. 합니다.

구문 분석 트리는> \<루트 키에 여러 키와 하위 키를 추가할 수 있습니다. 이렇게 하면 파서가 모든 하위 키의 구문 분석을 완료할 때까지 하위 키의 핸들을 열어 둡니다. 이 방법은 다음 예제에 표시 된 것 처럼 한 번에 단일 키에서 작업 하는 것 보다 효율적입니다.

```rgs
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

여기에서 등록자는 처음에 (만들기) `HKEY_CLASSES_ROOT\MyVeryOwnKey`를 엽니다. 그런 다음에 하위 `MyVeryOwnKey` 키가 있는 것을 볼 수 있습니다. 등록자는에 대 `MyVeryOwnKey`한 키를 닫지 않고 핸들을 유지 하 고이 부모 핸들 `HasASubKey` 을 사용 하 여 (만들기)를 엽니다. 부모 핸들이 열려 있지 않으면 시스템 레지스트리 속도가 느려질 수 있습니다. 따라서를 열어서 `HKEY_CLASSES_ROOT\MyVeryOwnKey` `HasASubKey` `MyVeryOwnKey` 부모로 여는 것은 열고 `MyVeryOwnKey`닫는 `MyVeryOwnKey`다음 여 `MyVeryOwnKey\HasASubKey`는 것 보다 빠릅니다.

## <a name="see-also"></a>참고 항목

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
