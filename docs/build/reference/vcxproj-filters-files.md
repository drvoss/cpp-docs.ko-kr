---
title: .Vcxproj 파일 필터
ms.date: 09/25/2019
description: Visual Studio C++ 프로젝트의 필터 파일을 사용 하 여의 파일에 대 한 사용자 지정 논리 폴더 정의 솔루션 탐색기
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: bdf40708a70d841cb3d3144fa8fa73a71e9e9ef2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078269"
---
# <a name="vcxprojfilters-files"></a>.Vcxproj 파일 필터

*필터* 파일 (\*.vcxproj)은 루트 프로젝트 폴더에 있는 MSBUILD 형식의 XML 파일입니다. **솔루션 탐색기**의 논리적 폴더로 이동할 파일 형식을 지정 합니다. 다음 그림에서 *.cpp* 파일은 **소스 파일** 노드 아래에 있습니다. *.h* 파일은 **헤더 파일** 노드 아래에 있고 *.Ico* 및 *.rc* 파일은 **리소스 파일**아래에 있습니다. 이 배치는 필터 파일에 의해 제어 됩니다.

![솔루션 탐색기의 논리적 폴더](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>사용자 지정 필터 파일 만들기

Visual Studio에서이 파일을 자동으로 만듭니다. 데스크톱 응용 프로그램의 경우 미리 정의 된 논리 폴더 (필터)는 **원본 파일**, **헤더 파일** 및 **리소스 파일**입니다. UWP와 같은 다른 프로젝트 형식에는 다른 기본 폴더 집합이 있을 수 있습니다. Visual Studio는 알려진 파일 형식을 각 폴더에 자동으로 할당 합니다. 사용자 지정 이름이 나 사용자 지정 파일 형식을 포함 하는 필터를 사용 하 여 필터를 만들려는 경우 프로젝트의 루트 폴더 또는 기존 필터에서 사용자 고유의 필터 파일을 만들 수 있습니다. **참조** 및 **외부 종속성** 은 필터링에 참여 하지 않는 특수 폴더입니다.

## <a name="example"></a>예제

다음 예제에서는 앞에서 보여 주는 예제에 대 한 필터 파일을 보여 줍니다. 여기에는 플랫 계층이 있습니다. 즉, 중첩 된 논리적 폴더가 없습니다. `UniqueIdentifier` 노드는 선택 사항입니다. 이를 통해 Visual Studio 자동화 인터페이스에서 필터를 찾을 수 있습니다. `Extensions`도 선택적입니다. 프로젝트에 새 파일이 추가 되 면 파일 확장명이 일치 하는 최상위 필터에 추가 됩니다. 특정 필터에 파일을 추가 하려면 필터를 마우스 오른쪽 단추로 클릭 하 고 **새 항목 추가**를 선택 합니다.

`ClInclude` 노드를 포함 하는 `ItemGroup`는 프로젝트가 처음 시작 될 때 생성 됩니다. 사용자 고유의 .vcxproj 파일을 생성 하는 경우 모든 프로젝트 항목에도 필터 파일에 항목이 있는지 확인 합니다. `ClInclude` 노드의 값은 파일 확장명에 따라 기본 필터링을 재정의 합니다. Visual Studio를 사용 하 여 프로젝트에 새 항목을 추가 하는 경우 IDE는 필터 파일에 개별 파일 항목을 추가 합니다. 파일의 확장명을 변경 하는 경우 필터가 자동으로 다시 할당 되지 않습니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <Filter Include="Source Files">
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier>
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions>
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
    <Filter Include="Resource Files">
      <UniqueIdentifier>{67DA6AB6-F800-4c08-8B7A-83BB121AAD01}</UniqueIdentifier>
      <Extensions>rc;ico;cur;bmp;dlg;rc2;rct;bin;rgs;gif;jpg;jpeg;jpe;resx;tiff;tif;png;wav;mfcribbon-ms</Extensions>
    </Filter>
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="MFCApplication1.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="MFCApplication1Dlg.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="stdafx.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="targetver.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="Resource.h">
      <Filter>Header Files</Filter>
    </ClInclude>
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="MFCApplication1.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="MFCApplication1Dlg.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="stdafx.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
  </ItemGroup>
  <ItemGroup>
    <ResourceCompile Include="MFCApplication1.rc">
      <Filter>Resource Files</Filter>
    </ResourceCompile>
  </ItemGroup>
  <ItemGroup>
    <None Include="res\MFCApplication1.rc2">
      <Filter>Resource Files</Filter>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Image Include="res\MFCApplication1.ico">
      <Filter>Resource Files</Filter>
    </Image>
  </ItemGroup>
</Project>
```

중첩 된 논리적 폴더를 만들려면 아래와 같이 필터 `ItemGroup` 모든 노드를 선언 합니다. 각 자식 노드는 최상위 부모에 대 한 전체 논리적 경로를 선언 해야 합니다. 다음 예에서는 빈 `ParentFilter`를 이후 노드에서 참조 하므로 선언 해야 합니다.

```xml
  <ItemGroup>
    <Filter Include="ParentFilter">
    </Filter>
    <Filter Include="ParentFilter\Source Files"> <!-- Full path to topmost parent.-->  
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier> <!--  Optional-->
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions> <!-- Optional -->
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
  </ItemGroup>
```
