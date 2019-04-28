---
title: XML の DataSet スキーマ情報の読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 06dcbbedf8c1533b3da52b447c121746ce705083
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785451"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="5c379-102">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="5c379-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="5c379-103">スキーマを<xref:System.Data.DataSet>(そのテーブル、列、リレーション、および制約) はプログラムによって作成された、**入力**または**FillSchema**のメソッド、<xref:System.Data.Common.DataAdapter>から読み込まれたまたは、XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="5c379-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="5c379-104">読み込めません**データセット**スキーマ情報を XML ドキュメントから、いずれかを使用できます、 **ReadXmlSchema**または**InferXmlSchema**のメソッド、**データセット**.</span><span class="sxs-lookup"><span data-stu-id="5c379-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="5c379-105">**ReadXmlSchema**を使用すると、読み込みまたは推論**データセット**XML スキーマ定義言語 (XSD) スキーマ、またはインライン XML スキーマを持つ XML ドキュメントを含むドキュメントからスキーマ情報。</span><span class="sxs-lookup"><span data-stu-id="5c379-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="5c379-106">**InferXmlSchema**指定した特定の XML 名前空間を無視しているときに、XML ドキュメントからスキーマを推論することができます。</span><span class="sxs-lookup"><span data-stu-id="5c379-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c379-107">テーブルの順序で、**データセット**を転送する Web サービスまたは XML シリアル化を使用する場合は保持されませんが、**データセット**インメモリ (入れ子になったリレーション) などの XSD コンス トラクターを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="5c379-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="5c379-108">そのための受信者、**データセット**ここでのテーブルの順序に依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="5c379-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="5c379-109">ただし、テーブルの順序は常に保持される場合のスキーマ、**データセット**メモリ内に作成されているのではなく、XSD ファイルから読み取られた転送されています。</span><span class="sxs-lookup"><span data-stu-id="5c379-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="5c379-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="5c379-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="5c379-111">スキーマを読み込む、**データセット**任意のデータを読み込むことがなく、XML ドキュメントから使用することができます、 **ReadXmlSchema**のメソッド、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="5c379-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="5c379-112">**ReadXmlSchema**作成**データセット**XML スキーマ定義言語 (XSD) スキーマを使用して定義されているスキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c379-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="5c379-113">**ReadXmlSchema**メソッドは、ストリーム、ファイル名の 1 つの引数または**XmlReader**読み込む XML ドキュメントを格納しています。</span><span class="sxs-lookup"><span data-stu-id="5c379-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="5c379-114">この XML ドキュメントには、スキーマだけが含まれているか、またはデータのある XML 要素と共にスキーマがインラインで含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c379-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="5c379-115">XML スキーマとしてのインライン スキーマを書き込む方法の詳細については、次を参照してください。[派生 DataSet リレーショナル構造の XML スキーマ (XSD) から](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c379-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="5c379-116">XML ドキュメントが渡された場合**ReadXmlSchema**インライン スキーマの情報が含まれていない**ReadXmlSchema**は XML ドキュメント内の要素からスキーマを推論します。</span><span class="sxs-lookup"><span data-stu-id="5c379-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="5c379-117">場合、**データセット**既にスキーマを含む現在のスキーマがまだ存在しない場合は、新しいテーブルを追加することによって拡張されます。</span><span class="sxs-lookup"><span data-stu-id="5c379-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="5c379-118">既存のテーブルには新しい列は追加されません。</span><span class="sxs-lookup"><span data-stu-id="5c379-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="5c379-119">既に追加されている列が存在する場合、**データセット**が互換性のない型の列が見つかりません、XML で例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c379-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="5c379-120">方法の詳細について**ReadXmlSchema**スキーマの推論、XML ドキュメントから、次を参照してください。[への推論からの DataSet リレーショナル構造 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c379-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="5c379-121">**ReadXmlSchema**読み込みまたは推論のスキーマのみ、**データセット**、 **ReadXml**のメソッド、**データセット**読み込まれるかまたは両方の推論スキーマと XML ドキュメントに含まれるデータ。</span><span class="sxs-lookup"><span data-stu-id="5c379-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="5c379-122">詳細については、次を参照してください。 [XML からの DataSet の読み込み](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c379-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="5c379-123">次のコード例を読み込む方法を表示する、**データセット**を XML ドキュメントまたはストリームからのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c379-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="5c379-124">最初の例に渡される XML スキーマ ファイル名、 **ReadXmlSchema**メソッド。</span><span class="sxs-lookup"><span data-stu-id="5c379-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="5c379-125">2 番目の例を示します、 **System.IO.StreamReader**します。</span><span class="sxs-lookup"><span data-stu-id="5c379-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="5c379-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="5c379-126">InferXmlSchema</span></span>  
 <span data-ttu-id="5c379-127">指示することも、**データセット**による XML ドキュメントからスキーマを推論する、 **InferXmlSchema**のメソッド、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="5c379-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="5c379-128">**InferXmlSchema**両方を行うと、同じように機能**ReadXml**で、 **XmlReadMode**の**InferSchema** (データを読み込むし、スキーマを推論)、および**ReadXmlSchema**読み取られるドキュメントにインライン スキーマが含まれていない場合。</span><span class="sxs-lookup"><span data-stu-id="5c379-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="5c379-129">ただし、 **InferXmlSchema**スキーマを推論するときに無視する特定の XML 名前空間を指定できる追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c379-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="5c379-130">**InferXmlSchema**は 2 つの必須引数を受け取ります。 ファイル名、ストリーム、で指定された、XML ドキュメントの場所または**XmlReader**; と操作によって無視される XML 名前空間の文字列配列。</span><span class="sxs-lookup"><span data-stu-id="5c379-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="5c379-131">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="5c379-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="5c379-132">上記の XML ドキュメント内の要素に指定された属性のため両方、 **ReadXmlSchema**メソッドと**ReadXml**メソッドを**XmlReadMode**の**InferSchema**テーブルのすべての要素のドキュメントを作成します。**カテゴリ**、 **CategoryID**、 **CategoryName**、**説明**、**製品**、 **ProductID**、 **ReorderLevel**、および**廃止**します。</span><span class="sxs-lookup"><span data-stu-id="5c379-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="5c379-133">(詳細については、次を参照してください[推論 DataSet リレーショナル構造の XML から](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。)ただしより適切な構造は、のみを作成すると、**カテゴリ**と**製品**テーブルを作成し、 **CategoryID**、 **CategoryName**、および**説明**内の列、**カテゴリ**テーブル、および**ProductID**、 **ReorderLevel**と**Discontinued**内の列、**製品**テーブル。</span><span class="sxs-lookup"><span data-stu-id="5c379-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="5c379-134">推論されたスキーマが XML 要素で指定された属性を無視することを確認するを使用して、 **InferXmlSchema**メソッドの XML 名前空間を指定して**officedata**が無視されるように、次の例です。</span><span class="sxs-lookup"><span data-stu-id="5c379-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c379-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c379-135">See also</span></span>

- [<span data-ttu-id="5c379-136">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="5c379-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="5c379-137">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="5c379-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="5c379-138">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="5c379-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="5c379-139">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="5c379-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="5c379-140">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="5c379-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="5c379-141">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="5c379-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
