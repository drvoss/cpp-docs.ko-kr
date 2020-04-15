---
title: com::ptr 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: e494285f33cf282d7b7515aac374ec86ef3036b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372483"
---
# <a name="comptr-class"></a>com::ptr 클래스

CLR 클래스의 멤버로 사용할 수 있는 COM 개체에 대한 래퍼입니다.  이 래퍼는 또한 COM 개체의 수명 주기 관리를 자동화하여 소멸자가 호출될 때 개체에서 모든 소유 참조를 해제합니다. [CComPtr 클래스와](../atl/reference/ccomptr-class.md)유사합니다.

## <a name="syntax"></a>구문

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>매개 변수

*_interface_type*<br/>
COM 인터페이스.

## <a name="remarks"></a>설명

또한 `com::ptr`은 로컬 함수 변수로 사용하여 여러 COM 작업을 간소화하고 수명 주기 관리를 자동화할 수 있습니다.

A는 `com::ptr` 함수 매개 변수로 직접 사용할 수 없습니다. 대신 [추적 참조 연산자](../extensions/tracking-reference-operator-cpp-component-extensions.md) 또는 [개체에 대한 핸들(^)을](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) 사용합니다.

함수에서 `com::ptr` 직접 반환할 수 없습니다. 대신 핸들을 사용합니다.

## <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  클래스의 공용 메서드를 호출하면 포함된 `IXMLDOMDocument` 개체가 호출됩니다.  이 샘플은 XML 문서의 인스턴스를 만들고, 여기에 일부 간단한 XML을 채우고, 구문 분석된 문서 트리에서 간소화된 노드 작업을 수행하고 XML을 콘솔에 출력합니다.

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|---------|-----------|
|[ptr::ptr](#ptr)|COM 개체를 래핑하는 a를 `com::ptr` 생성합니다.|
|[ptr::~ptr](#tilde-ptr)|을 소멸시 `com::ptr`|

### <a name="public-methods"></a>public 메서드

|속성|Description|
|---------|-----------|
|[ptr::Attach](#attach)|COM 개체를 `com::ptr`에 연결합니다.|
|[ptr::CreateInstance](#createInstance)|에서 COM 개체의 인스턴스를 `com::ptr`만듭니다.|
|[ptr::Detach](#detach)|COM 개체의 소유권을 포기하고 개체에 대한 포인터를 반환합니다.|
|[ptr::GetInterface](#getInterface)|에서 COM 개체의 인스턴스를 `com::ptr`만듭니다.|
|[ptr::QueryInterface](#queryInterface)|인터페이스에 대해 소유한 COM 개체를 쿼리하고 결과를 `com::ptr`다른 에 연결합니다.|
|[ptr::Release](#release)|COM 개체에서 소유한 모든 참조를 해제합니다.|

### <a name="public-operators"></a>공공 사업자

|속성|Description|
|---------|-----------|
|[ptr::연산자-&gt;](#operator-arrow)|멤버 액세스 연산자(소유 COM 개체에서 메서드를 호출하는 데 사용)입니다.|
|[ptr::operator=](#operator-assign)|COM 개체를 `com::ptr`에 연결합니다.|
|[ptr::연산자&nbsp;불](#operator-bool)|조건식에서 `com::ptr` 사용하기 위한 연산자입니다.|
|[ptr::연산자!](#operator-logical-not)|운영자가 소유한 COM 개체가 유효하지 않은지 확인합니다.|

## <a name="requirements"></a>요구 사항

**헤더 파일** \<msclr\com\ptr.h>

**네임스페이스** msclr::com

## <a name="ptrptr"></a><a name="ptr"></a>ptr::ptr

소유한 COM 개체에 대한 포인터를 반환합니다.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
COM 인터페이스 포인터.

### <a name="remarks"></a>설명

인수 없음 생성자는 기본 `nullptr` 개체 핸들에 할당됩니다. 에 대한 `com::ptr` 이후 호출은 내부 개체의 유효성을 검사하고 개체가 만들어지거나 첨부될 때까지 자동으로 실패합니다.

1인수 생성자는 COM 개체에 대한 참조를 추가하지만 호출자의 참조를 해제하지 않으므로 `Release` 호출자는 COM 개체를 호출하여 제어를 진정으로 포기해야 합니다. `com::ptr`'의 소멸자가 호출되면 자동으로 COM 개체에 해당 참조를 해제합니다.

이 `NULL` 생성자로 전달하는 것은 인수 없음 버전을 호출하는 것과 동일합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 생성자의 두 버전 의 사용을 보여 줍니다.

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrptr"></a><a name="tilde-ptr"></a>Ptr:~ptr

을 소멸시 `com::ptr`

```cpp
~ptr();
```

### <a name="remarks"></a>설명

소멸시, `com::ptr` COM 개체에 대한 모든 참조를 해제합니다. COM 개체에 대한 다른 참조가 없다고 가정하면 COM 개체가 삭제되고 해당 메모리가 해제됩니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  함수에서 `main` 두 `XmlDocument` 개체의 소멸자는 `try` 블록의 범위를 벗어날 때 호출되어 기본 `com::ptr` 소멸자가 호출되어 COM 개체에 대한 모든 소유 참조를 해제합니다.

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrattach"></a><a name="attach"></a>ptr::연결

COM 개체를 `com::ptr`에 연결합니다.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>매개 변수

*_right*<br/>
연결할 COM 인터페이스 포인터입니다.

### <a name="exceptions"></a>예외

COM `com::ptr` 개체에 대한 참조를 이미 `Attach` 소유하고 <xref:System.InvalidOperationException>있는 경우 을 throw합니다.

### <a name="remarks"></a>설명

COM 개체를 참조하지만 `Attach` 호출자의 참조를 해제하지 않는 호출입니다.

`NULL` 전달하면 `Attach` 아무 작업도 수행되지 않습니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 멤버 `ReplaceDocument` 함수는 `Release` 먼저 이전에 소유한 개체를 `Attach` 호출한 다음 새 문서 개체를 연결하기 위해 호출합니다.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>ptr::만들기 인스턴스

에서 COM 개체의 인스턴스를 `com::ptr`만듭니다.

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>매개 변수

*Progid*<br/>
`ProgID` 문자열입니다.

*푸터*<br/>
집계 개체의 I알 수 없는 인터페이스(제어 IUnknown)에 대한 포인터입니다. 지정되지 않은 `pouter` 경우 `NULL` 사용됩니다.

*cls_context*<br/>
새로 만든 개체를 관리하는 코드가 실행되는 컨텍스트입니다. 값은 열거형에서 `CLSCTX` 가져온 값입니다. 지정하지 않으면 `cls_context` CLSCTX_ALL 값이 사용됩니다.

*rclsid*<br/>
`CLSID`개체를 만드는 데 사용할 데이터 및 코드와 연결됩니다.

### <a name="exceptions"></a>예외

COM `com::ptr` 개체에 대한 참조를 이미 `CreateInstance` 소유하고 <xref:System.InvalidOperationException>있는 경우 을 throw합니다.

이 함수는 `CoCreateInstance` <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 오류를 `HRESULT` 적절한 예외로 변환하는 데 사용합니다.

### <a name="remarks"></a>설명

`CreateInstance`을 `CoCreateInstance` 사용하여 ProgID 또는 CLSID에서 식별된 지정된 개체의 새 인스턴스를 만듭니다. 새로 `com::ptr` 만든 개체를 참조하고 소멸 시 소유한 모든 참조를 자동으로 해제합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 클래스 생성자는 ProgID 또는 `CreateInstance` CLSID와 CLSCTX에서 문서 개체를 만들기 위해 두 가지 형식을 사용합니다.

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="ptrdetach"></a><a name="detach"></a>ptr::D에타치

COM 개체의 소유권을 포기하고 개체에 대한 포인터를 반환합니다.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>반환 값

COM 개체에 대한 포인터입니다.

개체가 소유되지 않으면 NULL이 반환됩니다.

### <a name="exceptions"></a>예외

내부적으로 소유 `QueryInterface` 된 COM 개체에서 호출 `HRESULT` 되며 모든 오류에 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>의해 예외로 변환 됩니다.

### <a name="remarks"></a>설명

`Detach`먼저 호출자 대신 COM 개체에 대한 참조를 추가한 다음 `com::ptr`에서 소유한 모든 참조를 해제합니다.  호출자는 궁극적으로 반환된 개체를 해제하여 삭제해야 합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  멤버 `DetachDocument` 함수는 `Detach` COM 개체의 소유권을 포기하고 호출자에게 포인터를 반환하기 위해 호출합니다.

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="ptrgetinterface"></a><a name="getInterface"></a>ptr::GetInterface

소유한 COM 개체에 대한 포인터를 반환합니다.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>반환 값

소유된 COM 개체에 대한 포인터입니다.

### <a name="exceptions"></a>예외

내부적으로 소유 `QueryInterface` 된 COM 개체에서 호출 `HRESULT` 되며 모든 오류에 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>의해 예외로 변환 됩니다.

### <a name="remarks"></a>설명

는 `com::ptr` 호출자 대신 COM 개체에 대한 참조를 추가하고 COM 개체에 자체 참조를 유지합니다. 호출자는 궁극적으로 반환된 개체에서 참조를 해제해야 하거나 삭제되지 않습니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 멤버 `GetDocument` 함수는 `GetInterface` COM 개체에 대한 포인터를 반환하는 데 사용합니다.

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>ptr::쿼리 인터페이스

인터페이스에 대해 소유한 COM 개체를 쿼리하고 결과를 `com::ptr`다른 에 연결합니다.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
즉, `com::ptr` 인터페이스를 얻을 것이다.

### <a name="exceptions"></a>예외

내부적으로 소유 `QueryInterface` 된 COM 개체에서 호출 `HRESULT` 되며 모든 오류에 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>의해 예외로 변환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 현재 래퍼가 소유 하는 COM 개체의 다른 인터페이스에 대 한 COM 래퍼를 만듭니다. 이 메서드는 소유 된 COM 개체를 `QueryInterface` 호출하여 COM 개체의 특정 인터페이스에 대한 포인터를 `com::ptr`요청하고 반환 된 인터페이스 포인터를 전달된 에 연결합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 멤버 `WriteTopLevelNode` 함수는 `QueryInterface` 로컬을 `com::ptr` a로 `IXMLDOMNode` 채운 `com::ptr` 다음 (참조추적을 통해) 노드의 이름과 텍스트 속성을 콘솔에 기록하는 개인 멤버 함수에 전달합니다.

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="ptrrelease"></a><a name="release"></a>ptr::릴리스

COM 개체에서 소유한 모든 참조를 해제합니다.

```cpp
void Release();
```

### <a name="remarks"></a>설명

이 함수를 호출하면 COM 개체에서 소유한 모든 참조가 해제되고 내부 핸들을 COM 개체로 설정합니다. `nullptr`  COM 개체에 대한 다른 참조가 없으면 삭제됩니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  멤버 `ReplaceDocument` 함수는 `Release` 새 문서를 첨부하기 전에 이전 문서 개체를 해제하는 데 사용합니다.

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>ptr::연산자-&gt;

멤버 액세스 연산자(소유 COM 개체에서 메서드를 호출하는 데 사용)입니다.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>반환 값

COM `smart_com_ptr` 개체에 대한 A입니다.

### <a name="exceptions"></a>예외

내부적으로 소유 `QueryInterface` 된 COM 개체에서 호출 `HRESULT` 되며 모든 오류에 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>의해 예외로 변환 됩니다.

### <a name="remarks"></a>설명

이 연산자는 소유한 COM 개체의 메서드를 호출할 수 있습니다. 자동으로 자체 `smart_com_ptr` `AddRef` 및 `Release`을 처리하는 임시를 반환합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 함수는 `WriteDocument` `operator->` 문서 개체의 멤버를 `get_firstChild` 호출하는 데 사용합니다.

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="ptroperator"></a><a name="operator-assign"></a>ptr::연산자=

COM 개체를 `com::ptr`에 연결합니다.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>매개 변수

*_right*<br/>
연결할 COM 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

의 추적 참조입니다. `com::ptr`

### <a name="exceptions"></a>예외

COM `com::ptr` 개체에 대한 참조를 이미 `operator=` 소유하고 <xref:System.InvalidOperationException>있는 경우 을 throw합니다.

### <a name="remarks"></a>설명

COM 개체를 `com::ptr` 참조에 할당하는 COM 개체는 COM 개체이지만 호출자의 참조를 해제하지는 않습니다.

이 연산자는 `Attach`와 동일한 효과를 가짐을 가짐을 가짐

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  멤버 `ReplaceDocument` 함수는 `Release` 먼저 이전에 소유한 개체를 `operator=` 호출한 다음 새 문서 개체를 연결하는 데 사용합니다.

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>ptr::연산자 불

조건식에서 `com::ptr` 사용하기 위한 연산자입니다.

```cpp
operator bool();
```

### <a name="return-value"></a>반환 값

`true`소유한 COM 개체가 유효한 경우; `false` 그렇지 않으면.

### <a name="remarks"></a>설명

소유된 COM 개체가 그렇지 않은 `nullptr`경우 유효합니다.

이 연산자는 `_detail_class::_safe_bool` 정수 `bool` 유형으로 변환할 수 없기 때문에 보다 안전한 것으로 변환합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 멤버 `CreateInstance` 함수는 `operator bool` 새 문서 개체를 만든 후 유효한지 확인하고 해당 개체가 있는 경우 콘솔에 씁니다.

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="ptroperator"></a><a name="operator-logical-not"></a>ptr::연산자!

운영자가 소유한 COM 개체가 유효하지 않은지 확인합니다.

```cpp
bool operator!();
```

### <a name="return-value"></a>반환 값

`true`소유한 COM 개체가 유효하지 않은 경우; `false` 그렇지 않으면.

### <a name="remarks"></a>설명

소유된 COM 개체가 그렇지 않은 `nullptr`경우 유효합니다.

### <a name="example"></a>예제

이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  멤버 `CreateInstance` 함수는 `operator!` 문서 개체가 이미 소유되어 있는지 확인하고 개체가 유효하지 않은 경우에만 새 인스턴스를 만듭니다.

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
