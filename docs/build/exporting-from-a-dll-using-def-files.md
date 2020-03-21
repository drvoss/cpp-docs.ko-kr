---
title: DEF 파일을 사용하여 DLL에서 내보내기
ms.date: 05/06/2019
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: 6f7d58bcb42edd89527fff41b08a15321722a6cf
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078516"
---
# <a name="exporting-from-a-dll-using-def-files"></a>DEF 파일을 사용하여 DLL에서 내보내기

모듈 정의 또는 DEF 파일 (* .def)은 DLL의 다양 한 특성을 설명 하는 하나 이상의 모듈 문을 포함 하는 텍스트 파일입니다. **__Declspec (dllexport)** 키워드를 사용 하 여 dll의 함수를 내보내는 경우 dll에는 DEF 파일이 필요 합니다.

최소 DEF 파일에는 다음 모듈 정의 문이 포함 되어야 합니다.

- 파일의 첫 번째 문은 LIBRARY 문 이어야 합니다. 이 문은 DEF 파일을 DLL에 속하는 것으로 식별 합니다. LIBRARY 문에는 DLL 이름이 나옵니다. 링커는이 이름을 DLL의 가져오기 라이브러리에 배치 합니다.

- EXPORTS 문은 DLL에서 내보낸 함수의 이름 및 서 수 값 (옵션)을 나열 합니다. 함수 이름 뒤에 @ 기호 및 숫자를 사용 하 여 함수를 서 수 값에 할당 합니다. 서 수 값을 지정 하는 경우 1에서 N 사이의 범위에 있어야 합니다. 여기서 N은 DLL에서 내보낸 함수 수입니다. 서 수로 함수를 내보내려는 경우이 항목 뿐만 [아니라 이름 대신 서 수로 DLL에서 함수 내보내기](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) 를 참조 하세요.

예를 들어 이진 검색 트리를 구현 하는 코드를 포함 하는 DLL은 다음과 같을 수 있습니다.

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Mfc [Dll 마법사](../mfc/reference/mfc-dll-wizard.md) 를 사용 하 여 mfc dll을 만드는 경우 마법사에서 자동으로 기본 정의 파일을 만들고 프로젝트에 자동으로 추가 합니다. 이 파일에 내보낼 함수의 이름을 추가 합니다. 비 MFC Dll의 경우 직접 DEF 파일을 만들고 프로젝트에 추가 합니다. 그런 다음 **프로젝트** > **속성** > **링커** > **입력** > **모듈 정의 파일** 로 이동 하 여 DEF 파일의 이름을 입력 합니다. 각 구성 및 플랫폼에 대해이 단계를 반복 하거나 **구성 = 모든 구성**및 **플랫폼 = 모든 플랫폼**을 선택 하 여 모든 구성 및 플랫폼에 대해이 단계를 수행 합니다.

C++ 파일에서 함수를 내보내는 경우 .def 파일에 데코레이팅된 이름을 추가 하거나 Extern "C"를 사용 하 여 표준 C 링크로 내보낸 함수를 정의 해야 합니다. .DEF 파일에 데코레이팅된 이름을 삽입 해야 하는 경우 [DUMPBIN](../build/reference/dumpbin-reference.md) 도구를 사용 하거나 링커 [/map](../build/reference/map-generate-mapfile.md) 옵션을 사용 하 여 가져올 수 있습니다. 컴파일러에서 생성 된 데코레이팅된 이름은 컴파일러 마다 다릅니다. Microsoft C++ 컴파일러 (MSVC)에서 생성 한 데코레이팅된 이름을 DEF 파일에 저장 하는 경우 호출 하는 응용 프로그램의 데코레이팅된 이름이 DLL의 DEF 파일에 있는 내보낸 이름과 일치 하도록 dll에 연결 된 응용 프로그램은 동일한 버전의 MSVC를 사용 하 여 빌드해야 합니다.

> [!NOTE]
> Visual studio 2015로 빌드된 DLL은 visual Studio 2017 또는 Visual Studio 2019로 빌드된 응용 프로그램에서 사용 될 수 있습니다.

[확장 DLL](../build/extension-dlls-overview.md)을 빌드하고 DEF 파일을 사용 하 여 내보내는 경우 내보낸 클래스를 포함 하는 헤더 파일의 시작과 끝에 다음 코드를 추가 합니다.

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

이러한 줄은 내부적으로 사용 되거나 클래스에 추가 되는 MFC 변수를 MFC 확장명 DLL에서 내보내거나 가져옵니다. 예를 들어 `DECLARE_DYNAMIC`를 사용 하 여 클래스를 파생 시키는 경우 매크로가 확장 되어 `CRuntimeClass` 멤버 변수를 클래스에 추가 합니다. 이러한 4 개 줄을 벗어나면 DLL이 올바르게 컴파일 또는 연결 되지 않거나 클라이언트 응용 프로그램이 DLL에 연결 될 때 오류가 발생할 수 있습니다.

DLL을 빌드할 때 링커는 DEF 파일을 사용 하 여 내보내기 파일 (.exp) 및 가져오기 라이브러리 파일 (.lib)을 만듭니다. 그런 다음 링커는 내보내기 파일을 사용 하 여 DLL 파일을 빌드합니다. DLL에 암시적으로 링크 되는 실행 파일은 빌드 시 가져오기 라이브러리에 연결 합니다.

MFC 자체는 DEF 파일을 사용 하 여 MFCx0에서 함수와 클래스를 내보냅니다.

## <a name="what-do-you-want-to-do"></a>원하는 옵션을 선택하세요.

- [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS를 사용 하 여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [C C++ 언어 실행 파일에서 사용할 함수 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C 함수를 C 또는 C++언어 실행 파일에 사용 하기 위해 내보내기](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 애플리케이션으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [.def 파일](reference/module-definition-dot-def-files.md)

- [모듈 정의 문의 규칙](reference/rules-for-module-definition-statements.md)

- [데코레이팅된 이름](reference/decorated-names.md)

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

## <a name="see-also"></a>참고 항목

[DLL에서 내보내기](exporting-from-a-dll.md)
