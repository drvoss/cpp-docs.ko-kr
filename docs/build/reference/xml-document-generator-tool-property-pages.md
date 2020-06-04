---
title: XML 문서 생성기 도구 속성 페이지
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: d17913909532c5bebcac712937af00be3ad98712
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335762"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML 문서 생성기 도구 속성 페이지

XML 문서 생성기 도구 속성 페이지는 xdcmake.exe의 기능을 제공합니다. xdcmake.exe는 소스 코드에 문서 주석이 있고 [/doc(문서 주석 처리) (C/C++)](doc-process-documentation-comments-c-cpp.md)가 지정된 경우 .xdc 파일을 .xml 파일에 병합합니다. 문서 주석을 소스 코드에 추가하는 방법에 대한 내용은 [문서 주석에 권장되는 태그](recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하세요.

> [!NOTE]
> 개발 환경(속성 페이지)의 xdcmake.exe 옵션은 xdcmake.exe가 명령줄에서 사용될 때의 옵션과 다릅니다. 명령줄에서 xdcmake.exe를 사용하는 방법에 대한 자세한 내용은 [XDCMake 참조](xdcmake-reference.md)를 참조하세요.

## <a name="uielement-list"></a>UIElement 목록

- **시작 배너 표시 안 함**

   저작권 메시지를 표시하지 않습니다.

- **추가 문서 파일**

   프로젝트 시스템에서 .xdc 파일을 검색할 추가 디렉터리. xdcmake는 항상 프로젝트에서 생성한 .xdc 파일을 찾습니다. 여러 디렉터리를 지정할 수 있습니다.

- **출력 문서 파일**

   .xml 출력 파일의 이름과 디렉터리 위치. 매크로를 사용하여 디렉터리 위치를 지정하는 방법에 대한 자세한 내용은 [빌드 명령 및 속성에](common-macros-for-build-commands-and-properties.md) 대한 공통 매크로를 참조하십시오.

- **문서 라이브러리 종속성**

   프로젝트가 솔루션의 .lib 프로젝트에 종속되어 있는 경우 .lib 프로젝트의 .xdc 파일을 현재 프로젝트의 .xml 파일로 처리할 수 있습니다.

## <a name="see-also"></a>참고 항목

[C++ 프로젝트 속성 페이지 참조](property-pages-visual-cpp.md)
