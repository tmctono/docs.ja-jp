---
title: XSD としての DataSet スキーマ情報の書き込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: f9664d8e7bc221da68492140f30419ea8fb0d316
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204366"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="03dcc-102">XSD としての DataSet スキーマ情報の書き込み</span><span class="sxs-lookup"><span data-stu-id="03dcc-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="03dcc-103"><xref:System.Data.DataSet> のスキーマを XML スキーマ定義言語 (XSD) スキーマとして書き込むと、このスキーマを XML ドキュメントに転送できます。このとき関連データを含む定義、または関連データを含まない定義ができます。</span><span class="sxs-lookup"><span data-stu-id="03dcc-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="03dcc-104">XML スキーマは、ファイル、ストリーム、 <xref:System.Xml.XmlWriter>、または文字列に書き込むことができます。厳密に型指定された**データセット**を生成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="03dcc-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="03dcc-105">厳密に型指定された**dataset**オブジェクトの詳細については、「[型付き dataset](typed-datasets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03dcc-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="03dcc-106">テーブルの列を XML スキーマで表す方法は、 <xref:System.Data.DataColumn>オブジェクトの**ColumnMapping**プロパティを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="03dcc-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="03dcc-107">詳細については、「 [DataSet の内容を Xml データとして書き込む](writing-dataset-contents-as-xml-data.md)」の「xml 要素、属性、およびテキストへの列のマッピング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03dcc-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="03dcc-108">**Dataset**のスキーマを XML スキーマとして、ファイル、ストリーム、または**XmlWriter**に書き込むには、**データセット**の**WriteXmlSchema**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="03dcc-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="03dcc-109">**WriteXmlSchema**は、結果の XML スキーマの出力先を指定するパラメーターを1つ受け取ります。</span><span class="sxs-lookup"><span data-stu-id="03dcc-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="03dcc-110">次のコード例では、ファイル名と<xref:System.IO.StreamWriter>オブジェクトを含む文字列を渡すことによって、**データセット**の XML スキーマをファイルに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="03dcc-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="03dcc-111">**DataSet**のスキーマを取得し、XML スキーマ文字列として書き込むには、次の例に示すように、 **getxmlschema**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="03dcc-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="03dcc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="03dcc-112">See also</span></span>

- [<span data-ttu-id="03dcc-113">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="03dcc-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="03dcc-114">DataSet 内容の XML データとしての書き込み</span><span class="sxs-lookup"><span data-stu-id="03dcc-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="03dcc-115">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="03dcc-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="03dcc-116">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="03dcc-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="03dcc-117">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="03dcc-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
