---
title: 레지스트리 스크립팅 예제
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 7bcdb7076982e2f0bd08f4fd82bb45f21e61ef20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329337"
---
# <a name="registry-scripting-examples"></a>레지스트리 스크립팅 예제

이 항목의 스크립팅 예제에서는 시스템 레지스트리에 키를 추가하고, 등록자 COM 서버를 등록하고, 여러 구문 분석 트리를 지정하는 방법을 보여 줍니다.

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER 키 추가

다음 구문 분석 트리는 시스템 레지스트리에 단일 키를 추가하는 간단한 스크립트를 보여 줍니다. 특히 스크립트는 에 키를 `MyVeryOwnKey`추가합니다. `HKEY_CURRENT_USER` 또한 새 키의 기본 `HowGoesIt` 문자열 값을 할당합니다.

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

이 스크립트를 쉽게 확장하여 다음과 같이 여러 하위 키를 정의할 수 있습니다.

```
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

이제 스크립트는 에 하위 `HasASubkey`키를 `MyVeryOwnKey`추가합니다. 이 하위 키에 하위 `PrettyCool` `DWORD` 키(기본값 55)와 명명된 `ANameValue` 값(문자열 `WithANamedValue`값)을 모두 추가합니다.

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>레지스트라 COM 서버 등록

다음 스크립트는 레지스트라 COM 서버 자체를 등록합니다.

```
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

런타임에 이 구문 분석 `ATL.Registrar` 트리는 `HKEY_CLASSES_ROOT`에 키를 추가합니다. 이 새 키에 다음을 수행합니다.

- 키의 `ATL Registrar Class` 기본 문자열 값으로 지정합니다.

- 하위 `CLSID` 키로 추가합니다.

- 을 지정합니다. `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` `CLSID` (이 값은 등록기관의 CLSID와 함께 `CoCreateInstance`사용할 수 있는 값입니다.)

`CLSID` 공유되므로 등록 취소 모드에서 제거하면 안 됩니다. 문은 `NoRemove CLSID`레지스터 모드에서 열고 등록 `CLSID` 취소 모드에서 무시해야 한다는 것을 나타내므로 이 작업을 수행합니다.

이 `ForceRemove` 문은 키를 다시 만들기 전에 키와 모든 하위 키를 제거하여 하우스키핑 기능을 제공합니다. 하위 키의 이름이 변경된 경우 유용할 수 있습니다. 이 스크립팅 `ForceRemove` 예제에서는 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 이미 있는지 확인합니다. 이 경우: `ForceRemove`

- 재귀적으로 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 삭제하고 모든 하위 키를 삭제합니다.

- 을 다시 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`만듭니다.

- 에 `ATL Registrar Class` 대한 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`기본 문자열 값으로 추가됩니다.

구문 분석 트리는 이제 에 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`두 개의 새 하위 키를 추가합니다. 첫 번째 `ProgID`키는 ProgID인 기본 문자열 값을 가져옵니다. 두 번째 `InprocServer32`키 , " 기본 `%MODULE%`문자열 값을 가져옵니다. [Using Replaceable Parameters (The Registrar's Preprocessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) `InprocServer32`또한 의 문자열 `ThreadingModel`값을 가진 명명된 `Apartment`값( 및 )을 가져옵니다.

## <a name="specify-multiple-parse-trees"></a>여러 구문 분석 트리 지정

스크립트에서 두 개 이상의 구문 분석 트리를 지정하려면 한 트리를 다른 트리의 끝에 배치하기만 하면 됩니다. 예를 들어 다음 스크립트는 키, `MyVeryOwnKey`및 `HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER`다음에 대한 구문 분석 트리에 추가합니다.

```
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> 레지스트라 스크립트에서 4K는 최대 토큰 크기입니다. 토큰은 구문에서 인식할 수 있는 요소입니다. 이전 스크립팅 예제에서 `HKEY_CURRENT_USER` `'MyVeryOwnKey'` `HKCR`" `'HowGoesIt'` 및 모든 토큰입니다.

## <a name="see-also"></a>참고 항목

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
