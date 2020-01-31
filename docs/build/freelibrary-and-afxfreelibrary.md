---
title: FreeLibrary 및 AfxFreeLibrary
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: 0b530aca2ab036de186ff3fdb11be23f41e12d05
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821553"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary 및 AfxFreeLibrary

Dll에 명시적으로 링크 된 프로세스는 DLL 모듈이 더 이상 필요 하지 않은 경우 [Freelibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) 함수를 호출 합니다. 이 함수는 모듈의 참조 횟수를 감소 시킵니다. 참조 횟수가 0 인 경우 프로세스의 주소 공간에서 매핑되지 않습니다.

MFC 응용 프로그램에서 `FreeLibrary` 대신 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) 를 사용 하 여 MFC 확장명 DLL을 언로드합니다. `AfxFreeLibrary`에 대 한 인터페이스 (함수 프로토타입)는 `FreeLibrary`와 동일 합니다.

## <a name="what-do-you-want-to-do"></a>원하는 옵션을 선택하세요.

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#linking-implicitly)

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>참조

[Visual Studio\C++ 에서 C/dll 만들기](dlls-in-visual-cpp.md)
[Freelibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)\
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
