---
title: XML の DataSet スキーマ情報の読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: db0df68aa89cdd5c8bf94ad95a2b8bc9b36d5685
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786224"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="695b7-102">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="695b7-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="695b7-103">のスキーマ<xref:System.Data.DataSet> (そのテーブル、列、リレーション、および制約) は、プログラムによって定義するか、の <xref:System.Data.Common.DataAdapter>Fill メソッドまたは**FillSchema**メソッドで作成するか、または XML ドキュメントから読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="695b7-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="695b7-104">XML ドキュメントから**dataset**スキーマ情報を読み込むには、**データセット**の**readxmlschema**または**InferXmlSchema**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="695b7-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="695b7-105">**Readxmlschema**を使用すると、xml スキーマ定義言語 (XSD) スキーマを含むドキュメントまたはインライン xml スキーマを含む xml ドキュメントから、**データセット**スキーマ情報を読み込んだり、推測したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="695b7-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="695b7-106">**InferXmlSchema**を使用すると、指定した特定の xml 名前空間を無視しながら、xml ドキュメントからスキーマを推論できます。</span><span class="sxs-lookup"><span data-stu-id="695b7-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="695b7-107">Web サービスまたは XML シリアル化を使用して、XSD コンストラクト (入れ子になったリレーションなど) を使用してメモリ内に作成された**データセット**を転送する場合、**データセット**内のテーブルの順序が保持されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="695b7-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="695b7-108">この場合、**データセット**の受信者はテーブルの順序に依存しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="695b7-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="695b7-109">ただし、転送される**データセット**のスキーマが、メモリ内に作成されるのではなく、XSD ファイルから読み取られた場合、テーブルの順序は常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="695b7-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="695b7-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="695b7-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="695b7-111">データを読み込まずに XML ドキュメントから**dataset**のスキーマを読み込むには、データ**セット**の**readxmlschema**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="695b7-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="695b7-112">**Readxmlschema**は、XML スキーマ定義言語 (XSD) スキーマを使用して定義された**データセット**スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="695b7-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="695b7-113">**Readxmlschema**メソッドは、ファイル名、ストリーム、または読み込む XML ドキュメントを含んでいる**XmlReader**の1つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="695b7-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="695b7-114">この XML ドキュメントには、スキーマだけが含まれているか、またはデータのある XML 要素と共にスキーマがインラインで含まれています。</span><span class="sxs-lookup"><span data-stu-id="695b7-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="695b7-115">インラインスキーマを XML スキーマとして記述する方法の詳細については、「 [Xml スキーマ (XSD) からの DataSet リレーショナル構造の派生](deriving-dataset-relational-structure-from-xml-schema-xsd.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="695b7-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="695b7-116">**Readxmlschema**に渡された xml ドキュメントにインラインスキーマ情報が含まれていない場合、 **READXMLSCHEMA**は xml ドキュメント内の要素からスキーマを推論します。</span><span class="sxs-lookup"><span data-stu-id="695b7-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="695b7-117">**データセット**に既にスキーマが含まれている場合、新しいテーブルが存在しない場合は、新しいテーブルを追加することによって現在のスキーマが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="695b7-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="695b7-118">既存のテーブルには新しい列は追加されません。</span><span class="sxs-lookup"><span data-stu-id="695b7-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="695b7-119">追加する列が**データセット**に既に存在していても、XML で見つかった列と互換性のない型がある場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="695b7-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="695b7-120">**Readxmlschema**が xml ドキュメントからスキーマを推論する方法の詳細については、「 [Xml からの DataSet リレーショナル構造の推論](inferring-dataset-relational-structure-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="695b7-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="695b7-121">**Readxmlschema**は**データセット**のスキーマのみを読み込むか推論しますが、 **dataset**の**ReadXml**メソッドは、XML ドキュメントに含まれているスキーマとデータの両方の読み込みまたは推論を行います。</span><span class="sxs-lookup"><span data-stu-id="695b7-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="695b7-122">詳細については、「 [XML からの DataSet の読み込み](loading-a-dataset-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="695b7-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="695b7-123">次のコード例は、XML ドキュメントまたは XML ストリームから**データセット**スキーマを読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="695b7-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="695b7-124">最初の例では、XML スキーマファイル名を**Readxmlschema**メソッドに渡しています。</span><span class="sxs-lookup"><span data-stu-id="695b7-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="695b7-125">2番目の例は、 **system.object を示しています**。</span><span class="sxs-lookup"><span data-stu-id="695b7-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="695b7-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="695b7-126">InferXmlSchema</span></span>  
 <span data-ttu-id="695b7-127">データセットの**InferXmlSchema**メソッドを使用して、XML ドキュメントからスキーマを推論するように**データセット**に指示することもでき**ます。**</span><span class="sxs-lookup"><span data-stu-id="695b7-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="695b7-128">**InferXmlSchema**は、 **XmlReadMode**の**InferSchema** (データの読み込みとスキーマの推論) を使用した**ReadXml**と、読み取り中のドキュメントにインラインスキーマが含まれてい**ない場合と**同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="695b7-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="695b7-129">ただし、 **InferXmlSchema**には、スキーマが推論されるときに無視する特定の XML 名前空間を指定できる追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="695b7-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="695b7-130">**InferXmlSchema**は、ファイル名、ストリーム、または**XmlReader**によって指定された XML ドキュメントの場所である2つの必須引数を受け取ります。とは、操作によって無視される XML 名前空間の文字列配列です。</span><span class="sxs-lookup"><span data-stu-id="695b7-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="695b7-131">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="695b7-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="695b7-132">前の XML ドキュメントの要素に属性が指定されているため、 **Readxmlschema**メソッドと**XmlReadMode**の**InferSchema**を持つ**ReadXml**メソッドの両方で、ガイド**Categories**、 **CategoryID**、**区分**、 **Description**、 **Products**、 **ProductID**、 **ReorderLevel**、および**廃止**されました。</span><span class="sxs-lookup"><span data-stu-id="695b7-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="695b7-133">(詳細については、次を参照してください[推論 DataSet リレーショナル構造の XML から](inferring-dataset-relational-structure-from-xml.md)。)ただし、より適切な構造としては、 **categories**テーブルと**Products**テーブルだけを作成してから、 **categories**テーブル**に CategoryID、区分、および Description の各列を作成します。** **Products**テーブルの ProductID、 **ReorderLevel**、および**廃止**された列。</span><span class="sxs-lookup"><span data-stu-id="695b7-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="695b7-134">推論されたスキーマで XML 要素に指定されている属性が無視されるようにするには、次の例に示すように、 **InferXmlSchema**メソッドを使用して、 **officedata**の xml 名前空間を無視するように指定します。</span><span class="sxs-lookup"><span data-stu-id="695b7-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="695b7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="695b7-135">See also</span></span>

- [<span data-ttu-id="695b7-136">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="695b7-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="695b7-137">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="695b7-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="695b7-138">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="695b7-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="695b7-139">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="695b7-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="695b7-140">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="695b7-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="695b7-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="695b7-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
