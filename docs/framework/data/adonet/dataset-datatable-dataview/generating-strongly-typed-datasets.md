---
title: 厳密に型指定された DataSet の生成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: ce7e5ad53f7aa5dad457ca1aa6ab76716086c0c3
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833987"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="354f0-102">厳密に型指定された DataSet の生成</span><span class="sxs-lookup"><span data-stu-id="354f0-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="354f0-103">Xml スキーマ定義言語 (XSD) 標準に準拠した XML スキーマを使用すると、Windows ソフトウェア開発キット (SDK) に用意されている XSD.EXE ツールを使用して、厳密に型指定された @no__t 0 を生成できます。</span><span class="sxs-lookup"><span data-stu-id="354f0-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="354f0-104">(データベーステーブルから xsd を作成するには、「<xref:System.Data.DataSet.WriteXmlSchema%2A>」または「 [Visual Studio でのデータセットの操作](/visualstudio/data-tools/dataset-tools-in-visual-studio)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="354f0-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="354f0-105">次のコードは、このツールを使用して**データセット**を生成するための構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="354f0-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="354f0-106">この構文では、`/d` ディレクティブは**データセット**を生成するようにツールに指示し、@no__t は、使用する言語 (たとえば、 C#または Visual Basic .net) をツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="354f0-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="354f0-107">省略可能な `/eld` ディレクティブは、LINQ to DataSet を使用して、生成されたデータセットに対してクエリを実行できることを指定し**ます。**</span><span class="sxs-lookup"><span data-stu-id="354f0-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="354f0-108">このオプションは、`/d` オプションと組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="354f0-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="354f0-109">詳細については、「[型指定](../querying-typed-datasets.md)された Dataset のクエリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354f0-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="354f0-110">オプションの `/n:` ディレクティブは、 **Xsdschema. namespace**という名前の**データセット**の名前空間も生成するようにツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="354f0-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="354f0-111">コマンドの出力は XSDSchemaFileName.cs で、ADO.NET アプリケーションでコンパイルおよび使用できます。</span><span class="sxs-lookup"><span data-stu-id="354f0-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="354f0-112">生成されたコードをライブラリまたはモジュールとしてコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="354f0-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="354f0-113">C# コンパイラ (csc.exe) を使用して、生成されたコードをライブラリとしてコンパイルする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="354f0-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="354f0-114">`/t:` ディレクティブはライブラリとしてコンパイルすることをツールに知らせ、`/r:` ディレクティブはコンパイルに必要な依存ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="354f0-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="354f0-115">コマンドの出力は XSDSchemaFileName.dll で、`/r:` ディレクティブによる ADO.NET アプリケーションのコンパイル時にコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="354f0-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="354f0-116">ADO.NET アプリケーションの XSD.exe に渡された名前空間にアクセスする構文を次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="354f0-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="354f0-117">次のコード例では、顧客**データセット**という名前の型指定された**データセット**を使用して、 **Northwind**データベースから顧客のリストを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="354f0-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="354f0-118">**Fill**メソッドを使用してデータが読み込まれると、この例では、型指定された Customer **srow** (**DataRow**) オブジェクトを使用して**Customers**テーブルの各顧客をループします。</span><span class="sxs-lookup"><span data-stu-id="354f0-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="354f0-119">これにより、 **DataColumnCollection**を介してではなく、 **CustomerID**列に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="354f0-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="354f0-120">次に、この例で使用する XML スキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="354f0-120">The following is the XML Schema used for the example:</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="354f0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="354f0-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="354f0-122">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="354f0-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="354f0-123">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="354f0-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="354f0-124">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="354f0-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
