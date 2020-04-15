---
title: AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 95c72f8251a8a59833483eb948709c80a69d03d7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328605"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기

[MFC 확장 DLL은](extension-dlls-overview.md) 매크로 **AFX_EXT_CLASS** 사용하여 클래스를 내보냅니다. MFC 확장 DLL에 링크하는 실행 프로그램은 매크로를 사용하여 클래스를 가져옵니다. **AFX_EXT_CLASS** 매크로를 사용하면 MFC 확장자 DLL을 빌드하는 데 사용되는 동일한 헤더 파일을 DLL에 연결하는 실행 파일과 함께 사용할 수 있습니다.

DLL의 헤더 파일에서 **AFX_EXT_CLASS** 키워드를 클래스 선언에 다음과 같이 추가합니다.

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

이 매크로는 MFC에 `__declspec(dllexport)` 의해 전처리기 `_AFXDLL` `_AFXEXT` 기호가 정의되고 정의될 때로 정의됩니다. 그러나 매크로는 정의되고 `_AFXDLL` 정의되지 `_AFXEXT` 않은 경우로 `__declspec(dllimport)` 정의됩니다. 프리프로세서 기호가 `_AFXDLL` 정의되면 대상 실행(DLL 또는 응용 프로그램)에서 MFC의 공유 버전이 사용되고 있음을 나타냅니다. 둘 `_AFXDLL` 다 `_AFXEXT` 정의되면 대상 실행 프로그램이 MFC 확장 DLL임을 나타냅니다.

MFC 확장 `__declspec(dllexport)` DLL에서 내보낼 때로 `AFX_EXT_CLASS` 정의되므로 .def 파일에 해당 클래스의 모든 기호에 대해 장식된 이름을 배치하지 않고 전체 클래스를 내보낼 수 있습니다.

이 메서드를 사용하여 .def 파일과 클래스에 대해 장식된 모든 이름을 만들지 않아도 되지만 이름을 서수로 내보낼 수 있으므로 .def 파일을 만드는 것이 더 효율적입니다. 내보내기의 .def 파일 방법을 사용하려면 헤더 파일의 시작과 끝에 다음 코드를 배치합니다.

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> 인라인 함수를 내보낼 때는 버전 충돌이 발생할 수 있으므로 주의해야 합니다. 인라인 함수는 응용 프로그램 코드로 확장됩니다. 따라서 나중에 함수를 다시 작성하면 응용 프로그램 자체가 다시 컴파일되지 않는 한 업데이트되지 않습니다. 일반적으로 DLL 함수를 사용하는 응용 프로그램을 다시 빌드하지 않고 업데이트할 수 있습니다.

## <a name="exporting-individual-members-in-a-class"></a>클래스에서 개별 멤버 내보내기

경우에 따라 클래스의 개별 멤버를 내보낼 수 있습니다. 예를 들어 -derived 클래스를 `CDialog`내보내는 경우 생성자와 `DoModal` 호출만 내보내야 할 수 있습니다. 내보내야 `AFX_EXT_CLASS` 하는 개별 멤버에서 사용할 수 있습니다.

다음은 그 예입니다.

```cpp
class CExampleDialog : public CDialog
{
public:
   AFX_EXT_CLASS CExampleDialog();
   AFX_EXT_CLASS int DoModal();
   ...
   // rest of class definition
   ...
};
```

더 이상 클래스의 모든 멤버를 내보내지 않으므로 MFC 매크로가 작동하는 방식으로 인해 추가 문제가 발생할 수 있습니다. MFC의 도우미 매크로 중 일부는 실제로 데이터 멤버를 선언하거나 정의합니다. 따라서 이러한 데이터 멤버는 DLL에서 내보내야 합니다.

예를 들어 `DECLARE_DYNAMIC` 매크로는 MFC 확장 DLL을 빌드할 때 다음과 같이 정의됩니다.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

정적으로 `AFX_DATA` 시작하는 선은 클래스 내부의 정적 개체를 선언하는 것입니다. 이 클래스를 올바르게 내보내고 클라이언트 실행 에서 런타임 정보에 액세스하려면 이 정적 개체를 내보내야 합니다. 정적 `AFX_DATA`개체는 수정자와 함께 선언되므로 `AFX_DATA` DLL을 작성할 `__declspec(dllexport)` 때 정의하고 클라이언트 실행 `__declspec(dllimport)` 파일을 작성할 때로 정의하기만 하면 됩니다. 이러한 `AFX_EXT_CLASS` 방식으로 이미 정의되어 있으므로 클래스 `AFX_DATA` `AFX_EXT_CLASS` 정의와 동일하게 재정의하기만 하면 됩니다.

다음은 그 예입니다.

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS

class CExampleView : public CView
{
   DECLARE_DYNAMIC()
   // ... class definition ...
};

#undef  AFX_DATA
#define AFX_DATA
```

MFC는 `AFX_DATA` 매크로 내에서 정의하는 데이터 항목에 항상 기호를 사용하므로 이 기술은 이러한 모든 시나리오에서 작동합니다. 예를 들어 에 `DECLARE_MESSAGE_MAP`대해 작동합니다.

> [!NOTE]
> 클래스의 선택된 멤버가 아닌 전체 클래스를 내보내는 경우 정적 데이터 멤버가 자동으로 내보내됩니다.

### <a name="what-do-you-want-to-do"></a>수행 작업

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)를 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [C 언어 실행 어에 사용할 수 있는 C++ 함수 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C 또는 C++언어 실행 어에 사용할 C 함수 내보내기](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 애플리케이션으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 초기화](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [데코레이팅된 이름](reference/decorated-names.md)

- [인라인 함수 가져오기 및 내보내기](importing-and-exporting-inline-functions.md)

- [상호 가져오기](mutual-imports.md)

## <a name="see-also"></a>참고 항목

[DLL에서 내보내기](exporting-from-a-dll.md)
