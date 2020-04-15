---
title: /OPT(최적화)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: b25db4d6c260c3c6751de293aa2a82df8aa05e7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336218"
---
# <a name="opt-optimizations"></a>/OPT(최적화)

LINK가 빌드하는 동안 수행할 최적화를 제어합니다.

## <a name="syntax"></a>구문

> **/OPT:**{**REF** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_반복_] | **NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>인수

**REF** &#124; **노레프**

**/OPT:REF는** 참조되지 않는 함수와 데이터를 제거합니다. **/OPT:NOREF는** 참조되지 않는 함수와 데이터를 유지합니다.

/OPT:REF가 활성화되면 LINK는 *COMDAT로*알려진 참조되지 않은 패키지 함수 및 데이터를 제거합니다. 이러한 최적화를 전이적 COMDAT 제거라고 합니다. **/OPT:REF** 옵션은 증분 연결을 비활성화합니다.

클래스 선언 내에 정의된 인라인 된 함수 및 멤버 함수는 항상 COMDAT입니다. [/Gy](gy-enable-function-level-linking.md) 옵션을 사용하여 컴파일되는 경우 개체 파일의 모든 함수가 COMDAT로 만들어집니다. COMDAT에 **const** 데이터를 배치하려면 을 사용하여 `__declspec(selectany)`선언해야 합니다. 제거 또는 접을 데이터를 지정하는 방법에 대한 자세한 내용은 [selectany](../../cpp/selectany.md)를 참조하십시오.

기본적으로 **/OPT:REF는** **/OPT:NOREF** 또는 [/DEBUG를](debug-generate-debug-info.md) 지정하지 않는 한 링커에서 사용할 수 있습니다. 이 기본값을 재정의하고 프로그램에서 참조되지 않은 COMDAT를 유지하려면 **/OPT:NOREF**를 지정합니다. [/INCLUDE](include-force-symbol-references.md) 옵션을 사용하여 특정 기호의 제거를 재정의할 수 있습니다.

[/DEBUG를](debug-generate-debug-info.md) 지정하면 **/OPT의** 기본값은 **NOREF이며**모든 함수는 이미지에 유지됩니다. 이 기본값을 재정의하고 디버그 빌드를 최적화하려면 **/OPT:REF**를 지정합니다. 이렇게 하면 실행 수의 크기를 줄일 수 있으며 디버그 빌드에서도 유용한 최적화가 될 수 있습니다. 디버그 빌드에서 동일한 기능을 보존하려면 **/OPT:NOICF를** 지정하는 것이 좋습니다. 이렇게 하면 스택 추적을 읽고 다른 방식으로는 함께 정리될 함수에서 중단점을 쉽게 설정할 수 있습니다.

**ICF**\[**=**_반복]_&#124; **NOICF**

**ICF**\[**=**_반복]을_사용하여 동일한 COMDAT 폴링을 수행합니다. 중복 COMDAT는 링커 출력에서 제거될 수 있습니다. 선택적 *반복* 매개 변수는 중복에 대한 기호를 통과하는 횟수를 지정합니다. 기본 반복 수는 1입니다. 추가 반복에서 이전 반복의 정리를 통해 발견되지 않은 중복 항목을 더 많이 찾을 수도 있습니다.

기본적으로 **/OPT:ICF는** **/OPT:NOICF** 또는 [/DEBUG를](debug-generate-debug-info.md) 지정하지 않는 한 링커에서 사용할 수 있습니다. 이 기본값을 재정의하고 COMDA가 프로그램에서 접히지 않도록 하려면 **/OPT:NOICF**를 지정합니다.

디버그 빌드에서 COMDAT 폴딩을 사용하도록 하려면 **/OPT:ICF를** 명시적으로 지정해야 합니다. 그러나 **/OPT:ICF는** 동일한 데이터 나 함수를 병합할 수 있으므로 스택 추적에 나타나는 함수 이름을 변경할 수 있습니다. 또한 특정 함수에서 중단점을 설정하거나 디버거에서 일부 데이터를 검사하는 것이 불가능할 수 있으며 코드를 단일 단계로 수행할 때 예기치 않은 함수로 안내할 수 있습니다. 코드의 동작은 동일하지만 디버거 프레젠테이션은 매우 혼란스러울 수 있습니다. 따라서 작은 코드의 장점이 이러한 단점보다 크지 않으면 디버그 빌드에서 **/OPT:ICF를** 사용하지 않는 것이 좋습니다.

> [!NOTE]
> **/OPT:ICF는** 동일한 주소가 다른 함수 또는 읽기 전용 데이터 **멤버(즉,/Gy를**사용하여 컴파일될 때 **const** 변수)에 할당될 수 있기 때문에 함수 또는 읽기 전용 데이터 멤버에 대한 고유 주소에 의존하는 프로그램을 중단시킬 수 있습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](gy-enable-function-level-linking.md)를 참조하세요.

**LBR** &#124; **놀브르**

**/OPT:LBR** 및 **/OPT:NOLBR** 옵션은 ARM 바이너리에만 적용됩니다. 특정 ARM 프로세서 분기 명령은 범위가 제한되어 있으므로 링커가 범위를 벗어난 주소로 이동하는 경우 분기 명령의 대상 주소를 실제 대상을 대상으로 하는 분기 명령이 포함된 코드 "island"의 주소로 바꿉니다. **/OPT:LBR을** 사용하여 긴 분기 명령의 검색과 중간 코드 아일랜드의 배치를 최적화하여 전체 코드 크기를 최소화할 수 있습니다. **/OPT:NOLBR은** 링커가 최적화 없이 긴 분기 지침에 대해 코드 섬을 생성하도록 지시합니다.

기본적으로 증분 연결을 사용할 수 없는 경우 **/OPT:LBR** 옵션이 설정됩니다. 비증분 링크를 원하지만 분기 최적화가 길지 않은 경우 **/OPT:NOLBR을**지정합니다. **/OPT:LBR** 옵션은 증분 연결을 비활성화합니다.

## <a name="remarks"></a>설명

명령줄에서 사용하면 링커기본값은 **/OPT:REF, ICF, LBR**. **/DEBUG를** 지정하면 기본값은 **/OPT:NOREF, NOICF, NOLBR입니다.**

**/OPT** 최적화는 일반적으로 이미지 크기를 줄이고 프로그램 속도를 증가시킵니다. 이러한 개선 은 큰 프로그램에서 상당한 수 있습니다., 그래서 그들은 소매 빌드에 대 한 기본적으로 사용 됩니다.

링커 최적화는 미리 시간이 걸리지만, 최적화된 코드는 링커가 수정할 재배치 횟수가 적고 최종 이미지를 작게 만들 때 시간을 절약하며 PDB에 처리하고 쓸 디버그 정보가 적을 때 더 많은 시간을 절약할 수 있습니다. 최적화를 사용하도록 설정하면 링커가 작은 바이너리를 통과하는 시간 절약으로 인해 분석의 작은 추가 비용이 상쇄될 수 있으므로 전체적으로 연결 시간이 빨라질 수 있습니다.

**/OPT** 인수는 쉼표로 구분하여 함께 지정될 수 있습니다. 예를 들어 **/OPT:REF/OPT:NOICF**대신 **/OPT:REF, NOICF를**지정할 수 있습니다.

[/VERBOSE](verbose-print-progress-messages.md) 링커 옵션을 사용하여 **/OPT:REF로** 제거된 함수와 **/OPT:ICF로**접힌 함수를 볼 수 있습니다.

**/OPT** 인수는 Visual Studio IDE에서 **새 프로젝트** 대화 상자를 사용하여 만든 프로젝트에 대해 설정되는 경우가 많으며 일반적으로 디버그 및 릴리스 구성에 대해 서로 다른 값을 갖습니다. 프로젝트에서 이러한 링커 옵션에 대해 값을 설정하지 않으면 명령줄에서 링커가 사용하는 기본값과 다를 수 있는 프로젝트 기본값을 얻을 수 있습니다.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:ICF 또는 OPT:REF 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **링커** > **최적화** 속성 페이지를 선택합니다.

1. 다음 속성 중 하나를 수정합니다.

   - **COMDAT 정리 사용**

   - **참조 항목**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:LBR 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **링커** > 명령줄 속성 페이지를**선택합니다.**

1. **추가 옵션에**옵션을 입력합니다.

   `/opt:lbr` 또는 `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> 속성을 참조하십시오.

## <a name="see-also"></a>참고 항목

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
