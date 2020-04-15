---
title: HTML 기초
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 6d3a692eab47a1309ee0248b51ab8563fb077d5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377242"
---
# <a name="html-basics"></a>HTML 기초

대부분의 브라우저에는 탐색하는 페이지의 HTML 소스를 검사하는 기능이 있습니다. 소스를 보면 텍스트와 함께 산재된 각도 대괄호(<>)로 둘러싸인 여러 HTML(하이퍼텍스트 태그 언어) 태그가 표시됩니다.

아래 단계는 HTML 태그를 사용하여 간단한 웹 페이지를 빌드합니다. 이 단계에서는 메모장의 파일에 일반 텍스트를 입력하고, 몇 가지 변경 사항을 변경하고, 파일을 저장하고, 브라우저에서 페이지를 다시 로드하여 변경 내용을 확인합니다.

#### <a name="to-create-an-html-file"></a>HTML 파일을 만들려면

1. 메모장 또는 일반 텍스트 편집기 열기.

1. **파일** 메뉴에서 새 을 **선택합니다.**

1. 다음 줄을 입력합니다.

    ```html
    <HTML>
    <HEAD>
    <TITLE>Top HTML Tags</TITLE>
    </HEAD>
    </HTML>
    ```

1. **파일** 메뉴에서 **저장을**선택하고 파일을 c:\webpages\First.htm으로 저장합니다. 편집기에서 파일을 열어 둡니다.

1. 브라우저로 전환하고 **파일** 메뉴에서 **열기를**선택하거나 브라우저의 URL 편집 상자에서 *file://C:/webpages/first.htm* 입력합니다. "맨 위 HTML 태그"라는 창 캡션이 있는 빈 페이지가 표시됩니다.

   태그가 페어링되어 있으며 각도 대괄호에 포함되어 있습니다. 태그는 대/소문자를 구분하지 않지만 태그를 돋보이게 하는 데 대소문자를 사용하는 경우가 많습니다.

   태그 \<HTML> 문서를 시작 하 \<고 태그/HTML> 종료 합니다. 종료 태그(항상 필요한 것은 아님)는 시작 태그와 동일하지만 태그 앞에 앞으로 슬래시(/)가 있습니다. 각도 대괄호(<)와 태그 시작 사이에 공백이 없어야 합니다.

1. 메모장으로 다시 전환하고 /HEAD> 줄 다음에 다음을 \<입력합니다.

    ```html
    <BODY>
        HTML is swell.
        Life is good.
    </BODY>
    ```

1. **파일** 메뉴에서 **저장을**선택합니다.

1. 브라우저로 다시 전환하고 페이지를 새로 고칩니다.

   단어는 브라우저 창의 클라이언트 영역에 나타납니다. 캐리지 반납은 무시됩니다. 줄 바그(줄 바그)를 지정하려면 첫 번째 줄 옆에 `<BR>` 태그를 포함해야 합니다.

   다음의 모든 단계에 대해 BODY> \</BODY \<> 사이의 아무 곳에나 텍스트를 삽입하여 문서 본문에 추가합니다.

1. 헤더 추가:

    ```html
    <H3>Here's the big picture</H3>
    ```

1. 페이지와 동일한 디렉터리에 저장된 .gif 파일을 사용하여 이미지를 추가합니다.

    ```html
    <IMG src="yourfile.gif">
    ```

1. 목록 추가:

    ```html
    <UL>Make me an unordered list.
    <LI>One programmer</LI>
    <LI>Ten SDKs</LI>
    <LI>Great Internet Apps</LI>
    </UL>
    ```

1. 대신 목록에 번호를 매기려면 \< \< \<UL> 및 \</UL> 태그 대신 페어링된 OL> 및 /OL> 태그를 사용합니다.

즉, 당신이 시작해야합니다. 웹 페이지에 훌륭한 기능이 표시되면 HTML 소스를 검사하여 이 기능이 어떻게 만들어졌는지 확인할 수 있습니다. Microsoft 프론트 페이지와 같은 HTML 편집기를 사용하여 단순 및 고급 페이지를 만들 수 있습니다.

빌드한 파일의 전체 HTML 소스는 다음과 같습니다.

```html
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
<BODY>
HTML is swell.<BR>
Life is good.
<H3>Here's the big picture</H3>
<IMG src="yourfile.gif">
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
</BODY>
</HTML>
```

태그, 특성 및 확장에 대한 전체 설명은 HTML(하이퍼텍스트 태그 언어) 사양을 참조하십시오.

W3C.org [HTML의 최신 게시 버전.](https://www.w3.org/TR/html/)

## <a name="see-also"></a>참고 항목

[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)
