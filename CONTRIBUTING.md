---
ms.openlocfilehash: b15a09fa450995c55cc6e7313c51db4a3ba3f48a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316622"
---
# <a name="contributing"></a>참여

Visual C++ 설명서에 기여하는 데 관심을 가져주셔서 감사합니다!

이 토픽에서는 [Visual C++ 설명서 사이트](https://docs.microsoft.com/cpp)에서 콘텐츠를 추가하거나 업데이트하는 기본 프로세스를 확인합니다.

이 항목에서는 다음을 다룹니다.

- [기여하는 프로세스](#process-for-contributing)
- [권고 및 금지](#dos-and-donts)
- [문서 빌드](#building-the-docs)
- [샘플에 기여](#contributing-to-samples)
- [기여자 라이선스 계약](#contributor-license-agreement)

## <a name="process-for-contributing"></a>기여하는 프로세스

**1단계:** 작성하려는 문서와 이 문서가 기존 콘텐츠에 어떻게 연관되는지 설명하는 문제를 엽니다.
**docs** 폴더 내의 콘텐츠를 콘텐츠 영역(예: 디버거)에서 구성된 섹션으로 구성합니다. 새 콘텐츠에 대한 올바른 폴더를 확인하려고 합니다. 제안에 대한 피드백을 가져옵니다.

작은 변경 내용은 이 첫 번째 단계를 건너뛸 수 있습니다.

**2단계:** `MicrosoftDocs/cpp-docs` 리포지토리를 포크합니다.

**3단계:** 문서에 대해 `branch`를 만듭니다.

**4단계:** 문서를 작성합니다.

새 항목인 경우 이 [템플릿 파일](./styleguide/template.md)을 시작점으로 사용할 수 있습니다. 작성 지침을 포함하고 작성자 정보 등의 각 문서에 필요한 메타데이터도 설명합니다.

1단계의 문서에 대해 결정된 TOC 위치에 해당하는 폴더로 이동합니다.
해당 폴더에는 해당 섹션에 있는 모든 문서의 Markdown 파일이 포함됩니다. 필요한 경우에 콘텐츠에 대한 파일을 배치할 새 폴더를 만듭니다.

이미지 및 다른 정적 리소스의 경우 `media`라는 하위 폴더에 추가합니다. 콘텐츠에 대한 새 폴더를 만드는 경우 새 폴더에 미디어 폴더를 추가합니다.

적절한 Markdown 구문을 수행해야 합니다. 자세한 내용은 [스타일 가이드](./styleguide/template.md)를 참조하세요.

### <a name="example-structure"></a>예제 구조

```
docs
    /standard-library
        wstring-convert-class.md
        /media
            wstring-conversion.png
```

**5단계:** 분기의 PR(끌어오기 요청)을 `MicrosoftDocs/cpp-docs/master`에 제출합니다.

PR이 기존 문제를 해결하는 경우 `Fixes #Issue_Number` 키워드를 커밋 메시지 또는 PR 설명에 추가합니다. 그러면 PR이 병합될 때 문제가 자동으로 닫힐 수 있습니다. 자세한 내용은 [커밋 메시지를 통해 문제 닫기](https://help.github.com/articles/closing-issues-via-commit-messages/)를 참조하세요.

Visual Studio 팀은 PR을 검토하고 승인하기 위해 변경 내용이 적합하거나 다른 업데이트/변경 내용이 필요한지를 알려줄 수 있습니다.

**6단계:** 팀에서 설명한 대로 분기에 필요한 모든 업데이트를 수행합니다.

피드백이 적용되고 변경 내용이 적합하면 유지 관리자는 PR을 마스터 분기에 병합합니다.

특정 주기에서는 모든 커밋을 마스터 분기에서 라이브 분기로 푸시한 다음, [docs.microsoft.com](https://docs.microsoft.com/cpp/)에서 라이브로 기여를 확인할 수 있습니다.

## <a name="dos-and-donts"></a>권고 및 금지

.NET 설명서에 기여할 때 염두해야 하는 지침 규칙의 짧은 목록은 다음과 같습니다.

- **금지** 대규모 끌어오기 요청을 제공합니다. 대신, 많은 시간을 투자하기 전에 방향에 동의할 수 있도록 문제를 저장하고 토론을 시작합니다.
- **권고**[스타일 가이드](./styleguide/template.md) 및 [어투 및 어조](./styleguide/voice-tone.md) 지침을 참고합니다.
- **권고**[템플릿](./styleguide/template.md) 파일을 작업의 시작점으로 사용합니다.
- **권고** 문서에서 작업하기 전에 포크의 별도 분기를 만듭니다.
- **권고**[GitHub 흐름 워크플로](https://guides.github.com/introduction/flow/)를 수행합니다.
- **권고** 기여에 대해 자주 블로깅하고 트윗(무엇이든)합니다.

> [!NOTE]
> 현재 일부 항목이 여기 및 [스타일 가이드](./styleguide/template.md)에 지정된 모든 지침에 따르지 않는다는 점을 확인할 수 있습니다. 사이트 전체에서 일관성을 달성하기 위해 노력하고 있습니다. 특정 목표에 대해 현재 추적 중인 [열린 문제](https://github.com/MicrosoftDocs/cpp-docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence) 목록을 확인하세요.

## <a name="building-the-docs"></a>문서 빌드

설명서는 [GitHub 버전이 지정된 Markdown](https://help.github.com/categories/writing-on-github/)에서 작성되고 [DocFX](https://dotnet.github.io/docfx/) 및 기타 내부 게시/빌드 도구를 사용하여 빌드됩니다. [docs.microsoft.com](https://docs.microsoft.com/)에서 호스팅됩니다.

문서를 로컬로 빌드하려는 경우 [DocFX](https://dotnet.github.io/docfx/)를 설치해야 합니다. 최신 버전이 가장 적합합니다.

DocFX를 사용하는 방법은 여러 가지가 있고 대부분 [DocFX 시작 가이드](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)에서 다룹니다. 다음 지침은 도구의 [명령줄 기반](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html#2-use-docfx-as-a-command-line-tool) 버전을 사용합니다. 위에 있는 링크에 나열된 다른 방법에 익숙한 경우 자유롭게 사용하세요.

**참고:** 현재 DocFX에는 Windows용 .NET Framework나 Linux 또는 macOS용 Mono가 필요합니다. 나중에 .NET Core에 이식하려고 합니다.

기본 제공 웹 서버를 사용하여 로컬로 결과 사이트를 빌드하고 미리 볼 수 있습니다. 머신의 `cpp-docs\docs` 폴더로 이동하고, 다음 명령을 입력합니다.

> docfx -t default --serve

그러면 [localhost:8080](http://localhost:8080)에서 로컬 미리 보기를 시작합니다. 그런 다음, `http://localhost:8080/cpp/visual-cpp-in-visual-studio.html`과 같은 `http://localhost:8080/[path]`으로 이동하여 변경 내용을 볼 수 있습니다.

**참고:** 현재 로컬 미리 보기에는 테마가 포함되지 않습니다. 따라서 모양과 느낌은 설명서 사이트와 동일하지 않습니다. 해당 환경을 수정하려고 노력하고 있습니다. 또한 미리 보기 상태로 표시되지 않는 포함된 비디오, 메모 및 포함된 문서에 대한 일부 사용자 지정 확장을 사용합니다.

## <a name="contributing-to-samples"></a>샘플에 기여

이제 필수 샘플 코드가 문서의 인라인 코드 블록으로 포함됩니다. 리포지토리에는 `codesnippets` 폴더가 포함되지만 공용 기여할 준비가 되지 않았습니다.

## <a name="contributor-license-agreement"></a>기여자 라이선스 계약

PR을 병합하기 전에 [CLA(기여 라이선스 계약)](LICENSE)에 서명해야 합니다. docs.microsoft.com의 프로젝트에 대한 일회성 요구 사항입니다. Wikipedia에서 [CLA(기여 라이선스 계약)](https://en.wikipedia.org/wiki/Contributor_License_Agreement)에 대해 참고할 수 있습니다.

계약서에 미리 서명할 필요가 없습니다. PR을 일반적인 방식으로 복제하고, 포크하고, 제출할 수 있습니다. PR이 만들어지면 CLA 봇에 의해 분류됩니다. 변경 내용이 간단한 경우(예: 오타 수정) PR은 CLA가 필요하지 않은 레이블로 지정됩니다. 그렇지 않으면, CLA가 필요하지 않은 것으로 분류됩니다. CLA에 서명하면 현재 및 이후의 모든 끌어오기 요청이 CLA 서명된 레이블로 지정됩니다.
