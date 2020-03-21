---
title: XML の DataSet スキーマ情報の読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151053"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="2a0e9-102">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="2a0e9-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="2a0e9-103">の<xref:System.Data.DataSet>スキーマ (テーブル、列、リレーション、および制約) は、プログラムで定義するか<xref:System.Data.Common.DataAdapter>、または**の Fill**メソッドまたは**FillSchema**メソッドによって作成するか、XML ドキュメントから読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="2a0e9-104">XML ドキュメントから**データセット**スキーマ情報を読み込むには、データセットの**ReadXml スキーマ**または**メソッド\*\*\*\*を使用**できます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2a0e9-105">**ReadXmlSchema**を使用すると、XML スキーマ定義言語 (XSD) スキーマを含むドキュメント、またはインライン XML スキーマを持つ XML ドキュメントから**DataSet**スキーマ情報を読み込んだり、推論したりできます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="2a0e9-106">**InferXmlSchema**を使用すると、指定した特定の XML 名前空間を無視しながら、XML ドキュメントからスキーマを推論できます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a0e9-107">Web サービスまたは XML シリアル化を使用して、XSD 構成要素 (入れ子になった関係など) を使用してメモリ内で作成された**DataSet**を転送する場合 **、DataSet**内のテーブルの順序が保持されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="2a0e9-108">したがって **、DataSet**の受信者は、この場合、テーブルの順序に依存しないでください。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="2a0e9-109">ただし、転送される**DataSet**のスキーマが XSD ファイルから読み取られた場合、テーブルの順序は常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="2a0e9-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="2a0e9-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="2a0e9-111">データを読み込まずに XML ドキュメントから**データセット**のスキーマを読み込むには、 **DataSet**の**ReadXmlSchema**メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2a0e9-112">**XML スキーマ定義**言語 (XSD) スキーマを使用して定義された**データセット**スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="2a0e9-113">**ReadXmlSchema**メソッドは、読み込まれる XML ドキュメントを含むファイル名、ストリーム、または**XmlReader**の引数を 1 つ受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="2a0e9-114">この XML ドキュメントには、スキーマだけが含まれているか、またはデータのある XML 要素と共にスキーマがインラインで含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="2a0e9-115">XML スキーマとしてのインライン スキーマの作成の詳細については、「 [XML スキーマ (XSD) からのデータセット リレーショナル構造の派生](deriving-dataset-relational-structure-from-xml-schema-xsd.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="2a0e9-116">**ReadXmlSchema**に渡された XML ドキュメントにインライン スキーマ情報が含まれている場合 **、Xml**ドキュメント内の要素からスキーマが推論されます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="2a0e9-117">**DataSet**にスキーマが既に含まれている場合、現在のスキーマは、存在しない場合は新しいテーブルを追加して拡張されます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="2a0e9-118">既存のテーブルには新しい列は追加されません。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="2a0e9-119">追加される列が**DataSet**に既に存在するが、XML 内で見つかった列と互換性のない型を持つ場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="2a0e9-120">**ReadXmlSchema**が XML ドキュメントからスキーマを推論する方法の詳細については、「 [XML からのデータセット リレーショナル構造の推論](inferring-dataset-relational-structure-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="2a0e9-121">**読み**込むか、**データセット**のスキーマのみを推論するが、**データセット**の**ReadXml**メソッドは、スキーマと XML ドキュメントに含まれるデータの両方を読み込むか推論します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="2a0e9-122">詳細については、「 [XML からのデータセットの読み込み](loading-a-dataset-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="2a0e9-123">次のコード例は、XML ドキュメントまたはストリームから**DataSet**スキーマを読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="2a0e9-124">最初の例では、**メソッド**に渡される XML スキーマ ファイル名を示します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="2a0e9-125">2 番目の例は **、System.IO.StreamReader**を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a><span data-ttu-id="2a0e9-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="2a0e9-126">InferXmlSchema</span></span>  
 <span data-ttu-id="2a0e9-127">また、**データセット**のメソッドを使用して、XML ドキュメントから**スキーマを推論**するように**DataSet に**指示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2a0e9-128">**InferXmlSchema 関数**は、読み取り対象のドキュメントにインライン**スキーマ\*\*\*\*ReadXmlSchema**が含まれていなくても **、ReadXml**と同じです。 **XmlReadMode**</span><span class="sxs-lookup"><span data-stu-id="2a0e9-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="2a0e9-129">ただし **、InferXmlSchema**には、スキーマが推論されるときに無視する特定の XML 名前空間を指定できる追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="2a0e9-130">**InferXmlSchema は**、ファイル名、ストリーム、または**XmlReader**で指定された XML ドキュメントの場所という 2 つの必須引数を受け取ります。XML 名前空間の文字列配列を操作によって無視します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="2a0e9-131">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-131">For example, consider the following XML:</span></span>  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>
  <Description od:adotype="203">Soft drinks and teas</Description>
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>
  <ReorderLevel od:adotype="3">10</ReorderLevel>
  <Discontinued od:adotype="11">0</Discontinued>
</Products>  
</NewDataSet>  
```  
  
 <span data-ttu-id="2a0e9-132">前の XML ドキュメントの要素に指定された属性のため **、ReadXmlSchema**メソッドと**ProductID\*\*\*\*InferSchema**の**CategoryName\*\*\*\*XmlReadMode**を持つ**ReadXml**メソッドの両方**が、ドキュメント**内のすべての要素**CategoryID**に対してテーブルを作成**Description\*\*\*\*します**。 **Products** **Discontinued**</span><span class="sxs-lookup"><span data-stu-id="2a0e9-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="2a0e9-133">(詳細については[、「XML からのデータセットリレーショナル構造の推論](inferring-dataset-relational-structure-from-xml.md)」を参照してください。ただし、より適切な構造としては、[**商品] テーブル**と [**商品**] テーブルのみを作成し、[商品] テーブルに **[カテゴリ** **ID]、[\*\*\*\*カテゴリ名**]、および **[説明**] 列、および **[商品**] テーブルの [**商品]** 列 、[**受注レベル]** 列、[中止 **]** 列を作成します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="2a0e9-134">推論されたスキーマが XML 要素で指定された属性を確実に無視するようにするには、次の例に示すように **、InferXmlSchema**メソッドを使用して、無視する**office データ**の XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a0e9-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a0e9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a0e9-135">See also</span></span>

- [<span data-ttu-id="2a0e9-136">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="2a0e9-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="2a0e9-137">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="2a0e9-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="2a0e9-138">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="2a0e9-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="2a0e9-139">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="2a0e9-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="2a0e9-140">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="2a0e9-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="2a0e9-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="2a0e9-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
