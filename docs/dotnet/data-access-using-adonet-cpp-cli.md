---
title: ADO.NET을 사용하여 데이터 액세스(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
ms.openlocfilehash: 35633449c4c01f5c103dcd54b81c0d6aa7c08cdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364420"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET을 사용하여 데이터 액세스(C++/CLI)

ADO.NET 데이터 액세스를 위한 .NET Framework API이며 이전 데이터 액세스 솔루션과 비교할 수 없는 사용 능력과 사용 편의성을 제공합니다. 이 섹션에서는 네이티브 형식 마샬링과 같이 Visual C++ 사용자에게 고유한 ADO.NET 관련된 몇 가지 문제에 대해 설명합니다.

ADO.NET 공통 언어 런타임(CLR)에서 실행됩니다. 따라서 ADO.NET 상호 작용하는 모든 응용 프로그램도 CLR을 대상으로 해야 합니다. 그러나 네이티브 응용 프로그램이 ADO.NET 사용할 수 없다는 의미는 아닙니다. 이 예제에서는 네이티브 코드에서 ADO.NET 데이터베이스와 상호 작용하는 방법을 보여 줍니다.

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a>ADO.NET ANSI 문자열 마샬링

데이터베이스에 네이티브 문자열 ()`char *`을 추가하는 방법과 데이터베이스에서 <xref:System.String?displayProperty=fullName> 네이티브 문자열로 a를 마샬링하는 방법을 보여 줍니다.

### <a name="example"></a>예제

이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 클래스 DatabaseClass가 만들어집니다. 이 클래스는 기본 C++(or와 `class` `ref class` `value class`비교)입니다. 네이티브 코드에서 이 클래스를 사용하려는 경우 네이티브 코드에서 관리되는 형식을 사용할 수 없으므로 이 클래스가 필요합니다. 이 클래스는 클래스 선언 앞의 `#pragma managed` 지시문에 표시된 대로 CLR을 대상으로 컴파일됩니다. 이 지시문에 대한 자세한 내용은 [관리되지 않는 관리되지 않는](../preprocessor/managed-unmanaged.md)을 참조하십시오.

DatabaseClass 클래스의 개인 멤버를 `gcroot<DataTable ^> table`기록합니다. 네이티브 형식에는 관리되는 형식을 `gcroot` 포함할 수 없으므로 키워드가 필요합니다. 자세한 내용은 네이티브 [형식의 핸들 선언 방법을](../dotnet/how-to-declare-handles-in-native-types.md)참조하십시오. `gcroot`

이 예제의 나머지 코드는 기본 C++ 코드이며, `#pragma unmanaged` 앞에 오는 `main`지시문에 의해 표시됩니다. 이 예제에서는 DatabaseClass의 새 인스턴스를 만들고 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다. 네이티브 C++ 문자열은 데이터베이스 열 StringCol의 값으로 전달됩니다. DatabaseClass 내에서 이러한 문자열은 네임스페이스에 있는 마샬링 기능을 <xref:System.Runtime.InteropServices?displayProperty=fullName> 사용하여 관리되는 문자열로 마샬링됩니다. 특히 <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> 메서드는 a를 `char *` 마샬링하는 <xref:System.String>데 사용되며 메서드는 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> <xref:System.String> `char *`a를 마샬링하는 데 사용됩니다.

> [!NOTE]
> 할당된 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 메모리는 <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> 호출하거나 `GlobalFree`에 의해 할당할당되어야 합니다.

```cpp
// adonet_marshal_string_native.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(char *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringAnsi(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(char *dataColumn, char **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringAnsi(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a char *.
            values[i] = (char *)Marshal::StringToHGlobalAnsi(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();
    db->AddRow("This is string 1.");
    db->AddRow("This is string 2.");

    // Now retrieve the rows and display their contents.
    char *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        "StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        cout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalAnsi.
        GlobalFree(values[i]);
    }

    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_native.cpp라는 파일에 코드 예제를 저장하고 다음 문을 입력합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a>ADO.NET 대한 원수 BSTR 문자열

COM 문자열 ()을`BSTR`데이터베이스에 추가하는 방법과 데이터베이스에서 <xref:System.String?displayProperty=fullName> `BSTR`에 a를 마샬링하는 방법을 보여 줍니다.

### <a name="example"></a>예제

이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 클래스 DatabaseClass가 만들어집니다. 이 클래스는 기본 C++(or와 `class` `ref class` `value class`비교)입니다. 네이티브 코드에서 이 클래스를 사용하려는 경우 네이티브 코드에서 관리되는 형식을 사용할 수 없으므로 이 클래스가 필요합니다. 이 클래스는 클래스 선언 앞의 `#pragma managed` 지시문에 표시된 대로 CLR을 대상으로 컴파일됩니다. 이 지시문에 대한 자세한 내용은 [관리되지 않는 관리되지 않는](../preprocessor/managed-unmanaged.md)을 참조하십시오.

DatabaseClass 클래스의 개인 멤버를 `gcroot<DataTable ^> table`기록합니다. 네이티브 형식에는 관리되는 형식을 `gcroot` 포함할 수 없으므로 키워드가 필요합니다. 자세한 내용은 네이티브 [형식의 핸들 선언 방법을](../dotnet/how-to-declare-handles-in-native-types.md)참조하십시오. `gcroot`

이 예제의 나머지 코드는 기본 C++ 코드이며, `#pragma unmanaged` 앞에 오는 `main`지시문에 의해 표시됩니다. 이 예제에서는 DatabaseClass의 새 인스턴스를 만들고 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다. COM 문자열은 데이터베이스 열 StringCol의 값으로 전달되고 있습니다. DatabaseClass 내에서 이러한 문자열은 네임스페이스에 있는 마샬링 기능을 <xref:System.Runtime.InteropServices?displayProperty=fullName> 사용하여 관리되는 문자열로 마샬링됩니다. 특히 <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> 메서드는 a를 `BSTR` 마샬링하는 <xref:System.String>데 사용되며 메서드는 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> <xref:System.String> `BSTR`a를 마샬링하는 데 사용됩니다.

> [!NOTE]
> 할당된 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 메모리는 <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> 호출하거나 `SysFreeString`에 의해 할당할당되어야 합니다.

``` cpp
// adonet_marshal_string_bstr.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(BSTR stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringBSTR(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(BSTR dataColumn, BSTR *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringBSTR(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a BSTR.
            values[i] = (BSTR)Marshal::StringToBSTR(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    BSTR str1 = SysAllocString(L"This is string 1.");
    db->AddRow(str1);

    BSTR str2 = SysAllocString(L"This is string 2.");
    db->AddRow(str2);

    // Now retrieve the rows and display their contents.
    BSTR values[MAXCOLS];
    BSTR str3 = SysAllocString(L"StringCol");
    int len = db->GetValuesForColumn(
        str3, values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToBSTR.
        SysFreeString(values[i]);
    }

    SysFreeString(str1);
    SysFreeString(str2);
    SysFreeString(str3);
    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_native.cpp라는 파일에 코드 예제를 저장하고 다음 문을 입력합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a>ADO.NET 대한 유니코드 문자열 마샬링

데이터베이스에 네이티브 유니코드 문자열()을`wchar_t *`추가하는 방법과 데이터베이스에서 네이티브 <xref:System.String?displayProperty=fullName> 유니코드 문자열로 a를 마샬링하는 방법을 보여 줍니다.

### <a name="example"></a>예제

이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 클래스 DatabaseClass가 만들어집니다. 이 클래스는 기본 C++(or와 `class` `ref class` `value class`비교)입니다. 네이티브 코드에서 이 클래스를 사용하려는 경우 네이티브 코드에서 관리되는 형식을 사용할 수 없으므로 이 클래스가 필요합니다. 이 클래스는 클래스 선언 앞의 `#pragma managed` 지시문에 표시된 대로 CLR을 대상으로 컴파일됩니다. 이 지시문에 대한 자세한 내용은 [관리되지 않는 관리되지 않는](../preprocessor/managed-unmanaged.md)을 참조하십시오.

DatabaseClass 클래스의 개인 멤버를 `gcroot<DataTable ^> table`기록합니다. 네이티브 형식에는 관리되는 형식을 `gcroot` 포함할 수 없으므로 키워드가 필요합니다. 자세한 내용은 네이티브 [형식의 핸들 선언 방법을](../dotnet/how-to-declare-handles-in-native-types.md)참조하십시오. `gcroot`

이 예제의 나머지 코드는 기본 C++ 코드이며, `#pragma unmanaged` 앞에 오는 `main`지시문에 의해 표시됩니다. 이 예제에서는 DatabaseClass의 새 인스턴스를 만들고 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다. 유니코드 C++ 문자열은 데이터베이스 열 StringCol의 값으로 전달되고 있습니다. DatabaseClass 내에서 이러한 문자열은 네임스페이스에 있는 마샬링 기능을 <xref:System.Runtime.InteropServices?displayProperty=fullName> 사용하여 관리되는 문자열로 마샬링됩니다. 특히 <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 메서드는 a를 `wchar_t *` 마샬링하는 <xref:System.String>데 사용되며 메서드는 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> <xref:System.String> `wchar_t *`a를 마샬링하는 데 사용됩니다.

> [!NOTE]
> 할당된 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 메모리는 <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> 호출하거나 `GlobalFree`에 의해 할당할당되어야 합니다.

```cpp
// adonet_marshal_string_wide.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(wchar_t *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringUni(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a wchar_t *.
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();
    db->AddRow(L"This is string 1.");
    db->AddRow(L"This is string 2.");

    // Now retrieve the rows and display their contents.
    wchar_t *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalUni.
        GlobalFree(values[i]);
    }

    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_wide.cpp라는 파일에 코드 예제를 저장하고 다음 문을 입력합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a>ADO.NET 대한 변형 마샬링

데이터베이스에 네이티브를 `VARIANT` 추가하는 방법과 데이터베이스에서 네이티브로 <xref:System.Object?displayProperty=fullName> a를 마샬링하는 `VARIANT`방법을 보여 줍니다.

### <a name="example"></a>예제

이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 클래스 DatabaseClass가 만들어집니다. 이 클래스는 기본 C++(or와 `class` `ref class` `value class`비교)입니다. 네이티브 코드에서 이 클래스를 사용하려는 경우 네이티브 코드에서 관리되는 형식을 사용할 수 없으므로 이 클래스가 필요합니다. 이 클래스는 클래스 선언 앞의 `#pragma managed` 지시문에 표시된 대로 CLR을 대상으로 컴파일됩니다. 이 지시문에 대한 자세한 내용은 [관리되지 않는 관리되지 않는](../preprocessor/managed-unmanaged.md)을 참조하십시오.

DatabaseClass 클래스의 개인 멤버를 `gcroot<DataTable ^> table`기록합니다. 네이티브 형식에는 관리되는 형식을 `gcroot` 포함할 수 없으므로 키워드가 필요합니다. 자세한 내용은 네이티브 [형식의 핸들 선언 방법을](../dotnet/how-to-declare-handles-in-native-types.md)참조하십시오. `gcroot`

이 예제의 나머지 코드는 기본 C++ 코드이며, `#pragma unmanaged` 앞에 오는 `main`지시문에 의해 표시됩니다. 이 예제에서는 DatabaseClass의 새 인스턴스를 만들고 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다. 네이티브 `VARIANT` 형식은 데이터베이스 열 ObjectCol의 값으로 전달됩니다. DatabaseClass 내에서 `VARIANT` 이러한 형식은 네임스페이스에 있는 마샬링 <xref:System.Runtime.InteropServices?displayProperty=fullName> 기능을 사용하여 관리되는 개체로 마샬링됩니다. 특히 <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> 메서드는 a를 `VARIANT` 마샬링하는 <xref:System.Object>데 사용되며 메서드는 <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> <xref:System.Object> `VARIANT`a를 마샬링하는 데 사용됩니다.

```cpp
// adonet_marshal_variant.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(VARIANT *objectColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(
            IntPtr(objectColValue));
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",
            Type::GetType("System.Object"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed object
            // to a VARIANT.
            Marshal::GetNativeVariantForObject(
                rows[i][columnStr], IntPtr(&values[i]));
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");
    VARIANT v1;
    v1.vt = VT_BSTR;
    v1.bstrVal = bstr1;
    db->AddRow(&v1);

    int i = 42;
    VARIANT v2;
    v2.vt = VT_I4;
    v2.lVal = i;
    db->AddRow(&v2);

    // Now retrieve the rows and display their contents.
    VARIANT values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"ObjectCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        switch (values[i].vt)
        {
            case VT_BSTR:
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;
                break;
            case VT_I4:
                cout << "ObjectCol: " << values[i].lVal << endl;
                break;
            default:
                break;
        }

    }

    SysFreeString(bstr1);
    delete db;

    return 0;
}
```

```Output
ObjectCol: This is a BSTR in a VARIANT.
ObjectCol: 42
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 코드 예제를 adonet_marshal_variant.cpp라는 파일에 저장하고 다음 문을 입력합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a>ADO.NET 대한 안전 배열 마샬링

데이터베이스에 네이티브를 `SAFEARRAY` 추가하는 방법과 데이터베이스에서 네이티브로 관리되는 배열을 마샬링하는 방법을 보여 줍니다. `SAFEARRAY`

### <a name="example"></a>예제

이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 클래스 DatabaseClass가 만들어집니다. 이 클래스는 기본 C++(or와 `class` `ref class` `value class`비교)입니다. 네이티브 코드에서 이 클래스를 사용하려는 경우 네이티브 코드에서 관리되는 형식을 사용할 수 없으므로 이 클래스가 필요합니다. 이 클래스는 클래스 선언 앞의 `#pragma managed` 지시문에 표시된 대로 CLR을 대상으로 컴파일됩니다. 이 지시문에 대한 자세한 내용은 [관리되지 않는 관리되지 않는](../preprocessor/managed-unmanaged.md)을 참조하십시오.

DatabaseClass 클래스의 개인 멤버를 `gcroot<DataTable ^> table`기록합니다. 네이티브 형식에는 관리되는 형식을 `gcroot` 포함할 수 없으므로 키워드가 필요합니다. 자세한 내용은 네이티브 [형식의 핸들 선언 방법을](../dotnet/how-to-declare-handles-in-native-types.md)참조하십시오. `gcroot`

이 예제의 나머지 코드는 기본 C++ 코드이며, `#pragma unmanaged` 앞에 오는 `main`지시문에 의해 표시됩니다. 이 예제에서는 DatabaseClass의 새 인스턴스를 만들고 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다. 네이티브 `SAFEARRAY` 형식은 데이터베이스 열 ArrayIntsCol의 값으로 전달됩니다. DatabaseClass 내에서 `SAFEARRAY` 이러한 형식은 네임스페이스에 있는 마샬링 <xref:System.Runtime.InteropServices?displayProperty=fullName> 기능을 사용하여 관리되는 개체로 마샬링됩니다. 특히 이 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 메서드는 관리되는 `SAFEARRAY` 정수 배열에 a를 마샬링하는 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 데 사용되며, 메서드는 관리되는 정수 배열을 에 `SAFEARRAY`마샬링하는 데 사용됩니다.

```cpp
// adonet_marshal_safearray.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(SAFEARRAY *arrayIntsColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        int len = arrayIntsColValue->rgsabound[0].cElements;
        array<int> ^arr = gcnew array<int>(len);

        int *pData;
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);
        Marshal::Copy(IntPtr(pData), arr, 0, len);
        SafeArrayUnaccessData(arrayIntsColValue);

        row["ArrayIntsCol"] = arr;
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",
            Type::GetType("System.Int32[]"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed array
            // of Int32s to a SAFEARRAY of type VT_I4.
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);
            int *pData;
            SafeArrayAccessData(values[i], (void **)&pData);
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,
                IntPtr(pData), 10);
            SafeArrayUnaccessData(values[i]);
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    // Create a standard array.
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    // Create a SAFEARRAY.
    SAFEARRAY *psa;
    psa = SafeArrayCreateVector(VT_I4, 0, 10);

    // Copy the data from the original array to the SAFEARRAY.
    int *pData;
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);
    memcpy(pData, &originalArray, 40);
    SafeArrayUnaccessData(psa);
    db->AddRow(psa);

    // Now retrieve the rows and display their contents.
    SAFEARRAY *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"ArrayIntsCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        int *pData;
        SafeArrayAccessData(values[i], (void **)&pData);
        for (int j = 0; j < 10; j++)
        {
            cout << pData[j] << " ";
        }
        cout << endl;
        SafeArrayUnaccessData(values[i]);

        // Deallocate the memory allocated using
        // SafeArrayCreateVector.
        SafeArrayDestroy(values[i]);
    }

    SafeArrayDestroy(psa);
    delete db;

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 코드 예제를 adonet_marshal_safearray.cpp라는 파일에 저장하고 다음 문을 입력합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework 보안

ADO.NET 관련된 보안 문제에 대한 자세한 내용은 [응용 프로그램 보안을](/dotnet/framework/data/adonet/securing-ado-net-applications)ADO.NET.

## <a name="related-sections"></a>관련 단원

|섹션|Description|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|데이터 액세스 서비스를 .NET 프로그래머에게 노출하는 클래스 집합인 ADO.NET 대한 개요를 제공합니다.|

## <a name="see-also"></a>참고 항목

[C++/CLI를 갖춘 .NET 프로그래밍(시각적 C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[상호 운용성](/dotnet/framework/interop/index)
