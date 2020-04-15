---
title: 문자열 편집기(C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.string.F1
- vc.editors.string
helpviewer_keywords:
- String editor
- string tables
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
- strings [C++], searching
- strings [C++]
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
ms.openlocfilehash: b0fb077752cf1912e07175c68cdc8acfe758b0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370234"
---
# <a name="string-editor-c"></a>문자열 편집기(C++)

문자열 테이블은 애플리케이션의 모든 문자열에 대한 ID, 값 및 캡션 목록이 포함된 Windows 리소스입니다. 예를 들어 상태 표시줄 프롬프트는 문자열 테이블에 있습니다.

애플리케이션을 개발하는 동안 각 언어 또는 조건에 하나씩 여러 문자열 테이블을 만들 수 있습니다. 그러나 실행 가능 모듈에는 문자열 테이블이 하나만 포함됩니다. 테이블을 서로 다른 DLL에 삽입하면 실행 중인 애플리케이션이 여러 문자열 테이블을 참조할 수 있습니다.

문자열 테이블을 사용하면 애플리케이션을 여러 언어로 쉽게 지역화할 수 있습니다. 모든 문자열이 한 문자열 테이블에 있으면 소스 코드를 변경하지 않고 문자열과 기타 리소스를 번역하여 애플리케이션을 지역화할 수 있습니다. 이 상황은 소스 파일에서 다양한 문자열을 수동으로 찾고 대체하는 것보다 더 바람직합니다.

> [!NOTE]
> Windows에서 빈 문자열 테이블을 만들 수 없습니다. 항목 없이 문자열 테이블을 만들면 리소스 파일을 저장할 때 해당 테이블이 자동으로 삭제됩니다.

## <a name="how-to"></a>방법

**문자열 편집기는** 다음을 수행할 수 있습니다.

### <a name="to-find-a-string-resource-in-the-string-table"></a>문자열 테이블에서 문자열 리소스를 찾으려면

1. [리소스 보기에서](how-to-create-a-resource-script-file.md#create-resources)아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.

1. 찾기**및 바꾸기** 메뉴 **편집으로** > 이동하여 **찾기를**선택합니다.

1. **찾기** 상자에서 드롭다운 목록에서 이전 검색 문자열을 선택하거나 찾으려는 문자열의 캡션 텍스트 또는 리소스 식별자를 입력합니다.

1. 찾기 옵션 중 에서 **다음** **찾기를**선택합니다.

> [!TIP]
> 파일을 [검색할 때 정규식을](/visualstudio/ide/using-regular-expressions-in-visual-studio) 사용하려면 **편집** **메뉴에서 파일에서 찾기** 명령을 사용합니다.
>
> 패턴과 일치하도록 정규식을 입력하거나 **제목 찾기** 상자 오른쪽에 있는 단추를 선택하여 정규 검색 식 목록을 표시합니다. 이 목록에서 표현식을 선택하면 **찾기** 상자의 검색 텍스트로 대체됩니다.
>
> 정규식을 사용하는 경우 **정규식 사용 확인란이** 선택되어 있는지 확인합니다.

### <a name="to-add-or-delete-a-string-resource"></a>문자열 리소스를 추가하거나 삭제하려면

**문자열 편집기**를 사용하여 문자열 테이블에 항목을 빠르게 삽입하거나 삭제할 수 있습니다. 새 문자열은 테이블 끝에 배치되고 사용 가능한 다음 식별자가 제공됩니다. 필요에 따라 [속성 창에서](/visualstudio/ide/reference/properties-window) **ID,** **값**또는 **캡션** 속성을 편집할 수 있습니다.

**문자열 편집기는** 이미 사용 중이던 ID를 사용하지 않도록 합니다. 이미 사용 중이던 ID를 선택하면 **문자열 편집기에서** 사용자에게 알리고 제네릭 고유 ID(예: `IDS_STRING58113`.)를 할당합니다.

#### <a name="to-add-a-string-table-entry"></a>문자열 테이블 항목을 추가하려면

1. [리소스 보기에서](how-to-create-a-resource-script-file.md#create-resources)아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.

1. 문자열 테이블 내에서 마우스 오른쪽 단추를 클릭하고 **새 문자열을**선택합니다.

1. 문자열 **편집기에서** **ID** 드롭다운 목록에서 **ID를** 선택하거나 *ID를* 직접 입력합니다.

1. 필요한 경우 **값**편집합니다.

1. **캡션**에 대한 항목을 입력합니다.

   > [!NOTE]
   > Null 문자열은 Windows 문자열 테이블에서 허용되지 않습니다. null 문자열인 문자열 테이블에 항목을 만드는 경우 **이 테이블 항목에 대한 문자열을 입력하라는**메시지가 표시됩니다.

#### <a name="to-delete-a-string-table-entry"></a>문자열 테이블 항목을 삭제하려면

삭제할 항목을 선택하고 다음 중 하나를 수행합니다.

- 메뉴로 이동**삭제** **편집** > .

- 문자열을 마우스 오른쪽 단추로 클릭하여 삭제하고 **삭제를**선택합니다.

- **삭제** 키를 누릅니다.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>문자열을 한 리소스 스크립트 파일에서 다른 리소스 스크립트 파일로 이동하려면

1. [두 .rc 파일 모두에서 문자열 테이블을 엽니다.](../windows/how-to-create-a-resource-script-file.md)

1. 문자열을 마우스 오른쪽 단추로 클릭하여 이동하고 **잘라내기를**선택합니다.

1. 대상 **문자열 편집기** 창에 커서를 배치합니다.

1. 문자열을 이동하려는 *.rc* 파일에서 마우스 오른쪽 단추를 클릭하고 **붙여 넣기를**선택합니다.

> [!NOTE]
> 이동된 문자열의 **ID** 또는 **값이** 대상 파일의 기존 **ID** 또는 **값과** 충돌하는 경우 해당 **ID** 또는 이동된 문자열의 **값이** 변경됩니다.

### <a name="to-change-the-properties-of-a-string-resource"></a>문자열 리소스의 속성을 변경하려면

현재 편집을 사용하여 **ID,** **값**및 **캡션** 속성을 변경할 수 있습니다.

> [!NOTE]
> [속성 창에서](/visualstudio/ide/reference/properties-window)문자열의 속성을 편집할 수도 있습니다.

#### <a name="to-change-a-string-or-its-identifier"></a>문자열 또는 해당 식별자를 변경하려면

1. [리소스 보기에서](how-to-create-a-resource-script-file.md#create-resources)아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.

1. 편집할 문자열을 선택하고 **ID,** **값**또는 **캡션** 열을 두 번 클릭한 다음 다음을 수행할 수 있습니다.

   - **ID** 드롭다운 목록에서 **ID를** 선택하거나 *ID를* 직접 입력합니다.

   - **값** 열에 다른 숫자를 입력합니다.

   - **캡션** 열에 편집을 입력합니다.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>여러 문자열 리소스의 캡션 속성을 변경하려면

1. [리소스 보기에서](how-to-create-a-resource-script-file.md#create-resources)아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.

1. 각 문자열을 선택할 때 **Ctrl** 키를 누르고 있으면 변경할 문자열을 선택합니다.

1. 속성 [창에서](/visualstudio/ide/reference/properties-window)변경하려는 속성에 대한 새 값을 입력합니다.

1. **Enter** 키를 누릅니다.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>문자열 리소스에 서식 또는 특수 문자를 추가하려면

1. [리소스 보기에서](how-to-create-a-resource-script-file.md#create-resources)아이콘을 두 번 클릭하여 문자열 테이블을 엽니다.

1. 수정할 문자열을 선택합니다.

1. 속성 [창에서](/visualstudio/ide/reference/properties-window) **캡션** 상자의 텍스트에 아래에 나열된 표준 이스케이프 시퀀스를 추가하고 **Enter**를 누릅니다.

   |이 것을 얻으려면 ...|이 것을 입력합니다...|
   |-----------------|---------------|
   | 새 줄 | \\n |
   | 캐리지 리턴 | \\R |
   | 탭 | \\t |
   | 백슬래시(\\) | \\\\ |
   | 아시이 캐릭터 | \\ddd (팔각 표기형) |
   | 경고(종) | \\a |

   > [!NOTE]
   > **문자열 편집기는** 이스케이프된 ASCI 문자의 전체 집합을 지원하지 않습니다. 위에 나열된 것만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고 항목

[리소스 편집기](../windows/resource-editors.md)
[문자열](/windows/win32/menurc/strings)<br/>
[문자열 정보](/windows/win32/menurc/about-strings)<br/>
[창 레이아웃 사용자 지정](/visualstudio/ide/customizing-window-layouts-in-visual-studio)
