---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 9ede0d3b53c975298dea3d1331bc0fb00ac246b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328253"
---
# <a name="exports"></a>EXPORTS

함수 또는 데이터의 내보낸 이름이나 서수를 지정하는 하나 이상의 내보내기 정의 섹션에 대해 소개합니다. 각 정의는 별도의 줄에 있어야 합니다.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>설명

첫 번째 *정의는* `EXPORTS` 키워드와 동일한 줄또는 후속 줄에 있을 수 있습니다. .DEF 파일에는 `EXPORTS` 문이 한 개 이상 있을 수 있습니다.

내보내기 *정의에* 대한 구문은 다음과 입니다.

> *항목 이름*\[__=__*internal_name*|*other_module.exported_name]* \[ **\@** _[이름_ \[ **없음]**] [ \[ \[ **비공개]**| \[ **데이터**]

*entryname은* 내보낼 함수 또는 변수 이름입니다. 이것은 필수입니다. 내보내는 이름이 DLL의 이름과 다른 경우 *internal_name*사용하여 DLL에서 내보내기 이름을 지정합니다. 예를 들어 DLL이 함수 `func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=func1
```

내보내는 이름이 다른 모듈에서 온 경우 *other_module.exported_name*를 사용하여 DLL에서 내보내기 이름을 지정합니다. 예를 들어 DLL이 함수 `other_module.func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=other_module.func1
```

내보내는 이름이 서수로 내보내는 다른 모듈의 이름인 경우 *other_module*를 사용하여 DLL에서 내보내기의 서수를 지정합니다. __#__ *서수*. 예를 들어 DLL이 서수 42인 다른 모듈에서 함수를 내보내는 경우 호출자가 `func2`함수를 로 사용하도록 지정합니다.

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC 컴파일러는 C++ 함수에 이름 장식을 사용하므로 internal_name 데코레이팅된 *이름을* 사용하거나 `extern "C"` 소스 코드에서 사용하여 내보낸 함수를 정의해야 합니다. 또한 컴파일러는 __stdcall [호출](../../cpp/stdcall.md) 규칙을 밑줄()\_접두사및 at sign()으로\@구성된 접미사와 인수 목록의 바이트 수(소수점)로 구성된 접미사를 사용하여 C 함수를 장식합니다.

컴파일러에서 생성된 데코레이션된 이름을 찾으려면 [DUMPBIN](dumpbin-reference.md) 도구 또는 링커 [/MAP](map-generate-mapfile.md) 옵션을 사용합니다. 데코레이팅된 이름은 컴파일러별로 다릅니다. .DEF 파일의 데코레이팅된 이름을 내보내는 경우 DLL에 연결된 실행 파일도 동일한 버전의 컴파일러를 사용하여 빌드해야 합니다. 그래야 호출자의 데코레이팅된 이름이 .DEF 파일의 내보낸 이름과 일치하게 됩니다.

\@ *ordinal을* 사용하여 함수 이름이 아닌 숫자가 DLL의 내보내기 테이블로 들어가지 않도록 지정할 수 있습니다. 많은 Windows DLL은 서수를 내보내 레거시 코드를 지원합니다. Windows DLL의 크기를 최소화할 수 있기 때문에 16비트 Windows 코드에서는 서수를 사용하는 것이 일반적입니다. DLL의 클라이언트가 레거시 지원을 위해 필요한 경우가 아니면 서수로 함수를 내보내는 것은 권장되지 않습니다. .LIB 파일에는 서수와 함수 간의 매핑이 포함되므로 DLL을 사용하는 프로젝트에서 일반적으로 하는 것처럼 함수 이름을 사용할 수 있습니다.

선택적 **NONAME** 키워드를 사용 하 여 서수만 내보낼 수 있습니다 및 결과 DLL에서 내보내기 테이블의 크기를 줄일 수 있습니다. 그러나 DLL에서 [GetProcAddress를](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 사용하려면 이름이 유효하지 않으므로 서수에 대해 알고 있어야 합니다.

선택적 키워드 **PRIVATE은** LINK에서 생성한 가져오기 라이브러리에 *엔트리 이름이* 포함되지 않도록 합니다. 이는 LINK에서도 생성한 이미지에서 내보내기에 영향을 미치지 않습니다.

선택적 키워드 **DATA는** 내보내기가 코드가 아닌 데이터임을 지정합니다. 아래 예제는 `exported_global` 데이터 변수를 내보낼 수 있는 방법을 보여줍니다.

```DEF
EXPORTS
   exported_global DATA
```

다음은 정의를 내보내는 4가지 방법으로 권장 순서대로 나열되었습니다.

1. 소스 코드의 [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) 키워드

1. .DEF 파일의 `EXPORTS` 문

1. LINK 명령의 [/EXPORT](export-exports-a-function.md) 사양

1. 소스 [comment](../../preprocessor/comment-c-cpp.md) `#pragma comment(linker, "/export: definition ")`코드의 주석 지시문입니다. 다음 예제에서는 기능 선언 앞에 #pragma comment `PlainFuncName` 지시문을 보여 주며, 여기서 데 코치되지 않은 이름과 함수의 데 코데된 `_PlainFuncName@4` 이름입니다.

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#pragma 지시문은 데코레이팅되지 않은 함수 이름을 내보내야 하고 빌드 구성(예: 32비트 또는 64비트 빌드)에 따라 내보내기가 다른 경우에 유용합니다.

4가지 메서드 모두 동일한 프로그램에서 사용할 수 있습니다. LINK가 내보내기를 포함하는 프로그램을 빌드하는 경우 빌드에서 .EXP 파일을 사용하지 않는다면 가져오기 라이브러리도 만들게 됩니다.

다음은 EXPORTS 섹션의 예입니다.

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

.DEF 파일을 사용하여 DLL에서 변수를 내보낸 경우 변수에 대해 `__declspec(dllexport)`을 지정할 필요가 없습니다. 그러나 DLL을 사용하는 모든 파일에서는 데이터 선언 시 `__declspec(dllimport)`을 계속해서 사용해야 합니다.

## <a name="see-also"></a>참고 항목

[모듈 정의 문의 규칙](rules-for-module-definition-statements.md)
