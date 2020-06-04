---
title: 'TN026: DDX 및 DDV 루틴'
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 711d433b51ca09836f372d09a11f86c28b82cce6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370341"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX 및 DDV 루틴

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고에서는 대화 상자 데이터 교환(DDX) 및 대화 상자 데이터 유효성 검사(DDV) 아키텍처에 대해 설명합니다. 또한 DDX_ 또는 DDV_ 절차를 작성하는 방법과 클래스 마법사를 확장하여 루틴을 사용하는 방법에 대해서도 설명합니다.

## <a name="overview-of-dialog-data-exchange"></a>대화 상자 데이터 교환 개요

모든 대화 상자 데이터 함수는 C++ 코드로 수행됩니다. 특별한 자원이나 마법 매크로는 없습니다. 메커니즘의 핵심은 대화 데이터 교환 및 유효성 검사를 수행하는 모든 대화 상자 클래스에서 재정의되는 가상 함수입니다. 항상 이 양식에서 찾을 수 있습니다.

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

특수 형식 AFX 주석을 사용하면 ClassWizard에서 이 함수 내에서 코드를 찾고 편집할 수 있습니다. ClassWizard와 호환되지 않는 코드는 특수 형식 주석 외부에 배치해야 합니다.

위의 예에서 \<data_exchange_function_call> 다음과 같은 형태로 되어 있습니다.

```cpp
DDX_Custom(pDX, nIDC, field);
```

data_validation_function_call \<> 선택 사항이며 다음과 같은 형태로 되어 있습니다.

```cpp
DDV_Custom(pDX, field, ...);
```

각 `DoDataExchange` 함수에는 둘 이상의 DDX_/DDV_ 쌍이 포함될 수 있습니다.

MFC에서 제공되는 모든 대화 상자 데이터 교환 루틴 및 대화 데이터 유효성 검사 루틴 목록은 'afxdd_.h'를 참조하십시오.

대화 상자 데이터는 클래스의 `CMyDialog` 멤버 데이터입니다. 구조체 또는 이와 유사한 것에 저장되지 않습니다.

## <a name="notes"></a>메모

이를 "대화 상자 데이터"라고 부르지만 모든 기능은 파생된 모든 클래스에서 `CWnd` 사용할 수 있으며 대화 상자로만 국한되지 않습니다.

데이터의 초기 값은 표준 C++ 생성자에서 설정되며 `//{{AFX_DATA_INIT` 일반적으로 `//}}AFX_DATA_INIT` 주석과 함께 블록에 설정됩니다.

`CWnd::UpdateData`는 호출을 둘러싼 초기화 및 오류 `DoDataExchange`처리를 수행하는 작업입니다.

언제든지 호출하여 `CWnd::UpdateData` 데이터 교환 및 유효성 검사를 수행할 수 있습니다. 기본적으로 `UpdateData`TRUE(TRUE)는 기본 `CDialog::OnOK` 처리기에서 호출되고 `UpdateData`(FALSE)는 기본값에서 `CDialog::OnInitDialog`호출됩니다.

DDV_ 루틴은 해당 *필드의*DDX_ 루틴을 즉시 따라야 합니다.

## <a name="how-does-it-work"></a>작동 방식

대화 상자 데이터를 사용하려면 다음을 이해할 필요가 없습니다. 그러나 이 작업이 숨는 방식에서 어떻게 작동하는지 이해하면 사용자 고유의 교환 또는 유효성 검사 절차를 작성하는 데 도움이 됩니다.

멤버 `DoDataExchange` 함수는 멤버 `Serialize` 함수와 매우 유사하며 클래스의 멤버 데이터에서 외부 양식(이 경우 대화 상자에서 컨트롤)에서 데이터를 얻거나 설정해야 합니다. *pDX* 매개 변수는 데이터 교환을 수행하기 위한 `CArchive` 컨텍스트이며 매개 변수와 유사합니다. `CObject::Serialize` pDX(개체)에는 방향 플래그가 있는 `CArchive` 것과 비슷합니다. *pDX* `CDataExchange`

- if `!m_bSaveAndValidate`if 는 데이터 상태를 컨트롤에 로드합니다.

- if `m_bSaveAndValidate`if 다음 컨트롤에서 데이터 상태를 설정 합니다.

유효성 검사는 `m_bSaveAndValidate` 설정된 경우에만 발생합니다. `m_bSaveAndValidate` 값은 BOOL 매개 변수에 `CWnd::UpdateData`의해 결정됩니다.

세 가지 흥미로운 `CDataExchange` 멤버가 있습니다.

- `m_pDlgWnd`: 컨트롤이 포함된 창(일반적으로 대화 상자)입니다. 이는 DDX_ 및 DDV_ 글로벌 함수의 호출자는 모든 DDX/DDV 루틴에 'this'를 전달하지 못하도록 하기 위한 것입니다.

- `PrepareCtrl``PrepareEditCtrl`및 : 데이터 교환을 위한 대화 상자 컨트롤을 준비합니다. 유효성 검사가 실패할 경우 포커스를 설정하기 위해 컨트롤의 핸들을 저장합니다. `PrepareCtrl`은 편집되지 않은 컨트롤에 `PrepareEditCtrl` 사용되며 편집 컨트롤에 사용됩니다.

- `Fail`: 입력 오류에 대해 사용자에게 경고하는 메시지 상자를 불러온 후 호출됩니다. 이 루틴은 마지막 컨트롤(마지막 호출 `PrepareCtrl` 또는)으로 `PrepareEditCtrl`포커스를 복원하고 예외를 throw합니다. 이 멤버 함수는 DDX_ 및 DDV_ 루틴 모두에서 호출될 수 있습니다.

## <a name="user-extensions"></a>사용자 확장

기본 DDX/DDV 메커니즘을 확장하는 방법에는 여러 가지가 있습니다. 다음을 수행할 수 있습니다.

- 새 데이터 형식을 추가합니다.

    ```cpp
    CTime
    ```

- 새 교환 절차(DDX_)를 추가합니다.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- 새 유효성 검사 절차(DDV_)를 추가합니다.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- 임의의 식을 유효성 검사 프로시저에 전달합니다.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > 이러한 임의의 표현식은 ClassWizard에서 편집할 수 없으므로 특수 형식 주석(/{{AFX_DATA_MAP(CMyClass)) 외부로 이동해야 합니다.

멤버 `DoDialogExchange` 함수에 조건부 또는 상호 혼합된 교환 및 유효성 검사 함수 호출이 있는 기타 유효한 C++ 문이 포함됩니다.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> 위에서 보여 준 것처럼 이러한 코드는 ClassWizard에서 편집할 수 없으며 특수 형식 주석 외부에서만 사용해야 합니다.

## <a name="classwizard-support"></a>클래스 마법사 지원

ClassWizard는 자신의 DDX_ 및 DDV_ 루틴을 ClassWizard 사용자 인터페이스에 통합할 수 있도록 하여 DDX/DDV 사용자 정의의 하위 집합을 지원합니다. 이 작업을 수행하는 것은 프로젝트 또는 많은 프로젝트에서 특정 DDX 및 DDV 루틴을 재사용하려는 경우에만 비용 에게 유용합니다.

이를 위해 DDX에서 특별 항목을 입력합니다. CLW(이전 버전의 Visual C++는 이 정보를 APSTUDIO에 저장했습니다. INI) 또는 프로젝트의 . CLW 파일입니다. 특별 항목은 프로젝트의 [일반 정보] 섹션에서 입력할 수 있습니다. CLW 파일 또는 DDX의 [ExtraDDX] 섹션에 있습니다. \프로그램 파일\Microsoft 비주얼 스튜디오\비주얼 C++\빈 디렉토리의 CLW 파일입니다. DDX를 만들어야 할 수도 있습니다. CLW 파일이 아직 존재하지 않는 경우. 특정 프로젝트에서만 사용자 지정 DDX_/DDV_ 루틴을 사용하려는 경우 프로젝트의 [일반 정보] 섹션에 항목을 추가합니다. 대신 CLW 파일. 많은 프로젝트에서 루틴을 사용하려는 경우 DDX의 [ExtraDDX] 섹션에 항목을 추가합니다. Clw.

이러한 특별 항목의 일반적인 형식은 다음과 입니다.

> 엑스트라DX카운트=*n*

*여기서 n은* ExtraDDX의 수입니까? 따라야 할 선, 양식

> ExtraDDX?=*키;* *vb-키;* *프롬프트;* *유형;* *initValue;* *DDX_Proc* [; *DDV_Proc;* *프롬프트1;* *arg1* [; *프롬프트2;* *fmt2*[]

어디? 는 숫자 1 - *n이* 정의되는 목록에서 어떤 DDX 유형을 나타내는지 나타냅니다.

각 필드는 ';' 문자로 구분됩니다. 필드와 그 목적은 아래에 설명되어 있습니다.

- *키*

  이 변수 형식을 제어하는 대화 상자를 나타내는 단일 문자 목록입니다.

  |문자|허용된 제어|
  |-|-|
  E | 편집
  C | 2상태 확인란
  c | 트라이 상태 확인란
  R | 그룹의 첫 번째 라디오 버튼
  L | 정렬되지 않은 목록 상자
  l | 정렬된 목록 상자
  M | 콤보 상자(편집 항목 있음)
  N | 정렬되지 않은 드롭 목록
  n | 정렬된 드롭 목록
  1 | DDX 인서트를 목록의 헤드에 추가해야 하는 경우(기본값은 꼬리에 추가) 일반적으로 'Control' 속성을 전송하는 DDX 루틴에 사용됩니다.

- *vb-키*

  이 필드는 VBX 컨트롤의 16비트 제품에서만 사용됩니다(VBX 컨트롤은 32비트 제품에서 지원되지 않음).

- *프롬프트*

  속성 콤보 상자에 배치할 문자열(따옴표 없음)

- *종류*

  헤더 파일에서 내보를 내할 형식의 단일 식별자입니다. 위의 DDX_Time 이 예제에서는 CTime으로 설정됩니다.

- *vb-키*

  이 버전에서는 사용되지 않으며 항상 비어 있어야 합니다.

- *initValue*

  초기 값 - 0 또는 공백. 비어 있으면 구현 파일의 /{{AFX_DATA_INIT 섹션에 초기화 줄이 기록되지 않습니다. 올바른 초기화를 보장하는 생성자가 있는 C++ 개체(예: `CString`및 `CTime`기타)에는 빈 항목을 사용해야 합니다.

- *DDX_Proc*

  DDX_ 프로시저에 대한 단일 식별자입니다. C++ 함수 이름은 "DDX_"로 시작해야 하지만 DDX_Proc> 식별자에는 "DDX_"를 \<포함하지 마십시오. 위의 예에서 \<DDX_Proc> 식별자는 시간입니다. ClassWizard는 {{AFX_DATA_MAP 섹션에서 구현 파일에 함수 호출을 작성하면 이 이름을 DDX_ 더하여 DDX_Time 도착합니다.

- *comment*

  이 DDX를 사용하여 변수에 대한 대화 상자에 표시할 주석을 참조하십시오. 여기에 원하는 텍스트를 배치하고 일반적으로 DDX/DDV 쌍에서 수행하는 작업을 설명하는 작업을 제공합니다.

- *DDV_Proc*

  항목의 DDV 부분은 선택 사항입니다. 모든 DDX 루틴에 해당 DDV 루틴이 있는 것은 아닙니다. 종종 전송의 필수적인 부분으로 유효성 검사 단계를 포함 하는 것이 더 편리 합니다. ClassWizard는 매개 변수없이 DDV 루틴을 지원하지 않기 때문에 DDV 루틴에 매개 변수가 필요하지 않은 경우가 많습니다.

- *Arg*

  DDV_ 프로시저의 단일 식별자입니다. C++ 함수 이름은 "DDV_"으로 시작해야 하지만 DDX_Proc> 식별자에는 "DDX_"를 \<포함하지 않아야 합니다.

  *아르그* 뒤에 는 1 또는 2 개의 DDV 아르그가 있습니다.

  - *프롬프트 N*

      편집 항목 위에 배치할 문자열(가속기의 & 있음).

  - *fmtN*

      아르그 유형의 형식 문자는 다음 중 하나입니다.

      |문자|Type|
      |-|-|
      |d | int|
      |u | 부호 없는 정수|
      |D | 긴 int (즉, 긴)|
      |U | 긴 서명되지 않은 (즉, DWORD)|
      |f | float|
      |F | double|
      |s | 문자열|

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
