---
title: 厳密に型指定された DataSet の生成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 1c65389c8c5664f86f3f0c04829a2422908d72d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202293"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="74bb8-102">厳密に型指定された DataSet の生成</span><span class="sxs-lookup"><span data-stu-id="74bb8-102">Generating Strongly Typed DataSets</span></span>

<span data-ttu-id="74bb8-103">XML スキーマ定義言語 (XSD) 標準に準拠する XML スキーマがあれば、Windows ソフトウェア開発キット (SDK) に付属する XSD.exe ツールを使用して、厳密に型指定された <xref:System.Data.DataSet> を生成できます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="74bb8-104">(データベース テーブルから xsd を作成するには、<xref:System.Data.DataSet.WriteXmlSchema%2A> に関するトピック、または「[Visual Studio でのデータセットの操作](/visualstudio/data-tools/dataset-tools-in-visual-studio)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="74bb8-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="74bb8-105">次のコードでは、このツールを使用して **DataSet** を生成する構文を示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="74bb8-106">この構文の `/d` ディレクティブでは、**DataSet** を生成することをツールに指示し、`/l:` では使用する言語 (C#、Visual Basic .NET など) をツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="74bb8-107">オプションの `/eld` ディレクティブを指定すると、生成された **DataSet** に対し、LINQ to DataSet を使用してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="74bb8-108">このオプションは、`/d` オプションと組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="74bb8-109">詳しくは、「[型指定された DataSet のクエリ](../querying-typed-datasets.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74bb8-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="74bb8-110">オプションの `/n:` ディレクティブでは、**XSDSchema.Namespace** という名前の名前空間も **DataSet** に対して生成することをツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="74bb8-111">コマンドの出力は XSDSchemaFileName.cs で、ADO.NET アプリケーションでコンパイルおよび使用できます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="74bb8-112">生成されたコードをライブラリまたはモジュールとしてコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="74bb8-113">C# コンパイラ (csc.exe) を使用して、生成されたコードをライブラリとしてコンパイルする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```console  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="74bb8-114">`/t:` ディレクティブはライブラリとしてコンパイルすることをツールに知らせ、`/r:` ディレクティブはコンパイルに必要な依存ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="74bb8-115">コマンドの出力は XSDSchemaFileName.dll で、`/r:` ディレクティブによる ADO.NET アプリケーションのコンパイル時にコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="74bb8-116">ADO.NET アプリケーションの XSD.exe に渡された名前空間にアクセスする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="74bb8-117">次のコード例では、**CustomerDataSet** という名前の型指定された **DataSet** を使用して、**Northwind** データベースから顧客リストを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="74bb8-118">**Fill** メソッドを使用してデータを読み込んだ後、例では、型指定された **CustomersRow** (**DataRow**) オブジェクトを使用して、**Customers** テーブルの各顧客をループします。</span><span class="sxs-lookup"><span data-stu-id="74bb8-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="74bb8-119">このようにすると、**DataColumnCollection** による場合とは異なり、**CustomerID** 列に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="74bb8-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 <span data-ttu-id="74bb8-120">例に使用された XML スキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="74bb8-120">The following is the XML Schema used for the example:</span></span>
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74bb8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="74bb8-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="74bb8-122">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="74bb8-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="74bb8-123">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="74bb8-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="74bb8-124">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="74bb8-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
