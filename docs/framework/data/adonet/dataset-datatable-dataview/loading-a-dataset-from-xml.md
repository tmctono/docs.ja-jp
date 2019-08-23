---
title: XML からの DataSet の読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 24b962edc15c04cf1f68b73a7da960857658309c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928453"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="35231-102">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="35231-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="35231-103">ADO.NET では、XML ストリームまたは XML ドキュメントから <xref:System.Data.DataSet> の内容を作成できます。</span><span class="sxs-lookup"><span data-stu-id="35231-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="35231-104">また、.NET Framework では、XML から読み込まれる情報と <xref:System.Data.DataSet> のスキーマまたはリレーショナル構造の作成方法を柔軟に変更できます。</span><span class="sxs-lookup"><span data-stu-id="35231-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="35231-105">に XML の<xref:System.Data.DataSet>データを格納するには、 <xref:System.Data.DataSet>オブジェクトの ReadXml メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="35231-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="35231-106">**ReadXml**メソッドは、ファイル、ストリーム、または**XmlReader**から読み取り、XML のソースと省略可能な**XmlReadMode**引数を引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35231-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="35231-107">**XmlReader**の詳細については、「 [XmlTextReader を使用した XML データの読み取り](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35231-107">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="35231-108">**ReadXml**メソッドは、XML ストリームまたはドキュメントの内容を読み取り、データ<xref:System.Data.DataSet>を使用してを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35231-108">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="35231-109">また、指定された**XmlReadMode**と、 <xref:System.Data.DataSet>リレーショナルスキーマが既に存在するかどうかに応じて、のリレーショナルスキーマも作成されます。</span><span class="sxs-lookup"><span data-stu-id="35231-109">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="35231-110">次の表では、 **XmlReadMode**引数のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="35231-110">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="35231-111">オプション</span><span class="sxs-lookup"><span data-stu-id="35231-111">Option</span></span>|<span data-ttu-id="35231-112">説明</span><span class="sxs-lookup"><span data-stu-id="35231-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="35231-113">**Auto**</span><span class="sxs-lookup"><span data-stu-id="35231-113">**Auto**</span></span>|<span data-ttu-id="35231-114">既定値です。</span><span class="sxs-lookup"><span data-stu-id="35231-114">This is the default.</span></span> <span data-ttu-id="35231-115">XML を調べ、次の順序で最適なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="35231-115">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="35231-116">-XML が DiffGram の場合は、 **diffgram**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35231-116">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="35231-117">-に<xref:System.Data.DataSet>スキーマが含まれている場合、または XML にインラインスキーマが含まれている場合は、 **readschema**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35231-117">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="35231-118">-に<xref:System.Data.DataSet>スキーマが含まれておらず、XML にインラインスキーマが含まれていない場合は、 **InferSchema**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35231-118">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="35231-119">読み取り中の XML の形式がわかっている場合は、最適なパフォーマンスを得るために、**自動**既定値をそのまま使用するのではなく、明示的な**XmlReadMode**を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35231-119">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="35231-120">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="35231-120">**ReadSchema**</span></span>|<span data-ttu-id="35231-121">インライン スキーマを読み取り、データとスキーマを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35231-121">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="35231-122"><xref:System.Data.DataSet> に既にスキーマが含まれている場合には、読み取るインライン スキーマの新しいテーブルが <xref:System.Data.DataSet> の既存のスキーマに追加されます。</span><span class="sxs-lookup"><span data-stu-id="35231-122">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="35231-123">インライン スキーマのテーブルが既に <xref:System.Data.DataSet> に存在している場合には、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="35231-123">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="35231-124">**XmlReadMode**を使用して、既存のテーブルのスキーマを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="35231-124">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="35231-125"><xref:System.Data.DataSet> にスキーマが含まれておらず、インライン スキーマが存在しない場合には、データは読み取られません。</span><span class="sxs-lookup"><span data-stu-id="35231-125">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="35231-126">インライン スキーマを定義するには、XML スキーマ定義言語 (XSD) スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="35231-126">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="35231-127">インラインスキーマを XML スキーマとして記述する方法の詳細については、「 [Xml スキーマ (XSD) からの DataSet リレーショナル構造の派生](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35231-127">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="35231-128">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="35231-128">**IgnoreSchema**</span></span>|<span data-ttu-id="35231-129">インライン スキーマを無視し、データを既存の <xref:System.Data.DataSet> スキーマへ読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35231-129">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="35231-130">既存のスキーマに一致しないデータは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="35231-130">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="35231-131"><xref:System.Data.DataSet> にスキーマがない場合には、データは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="35231-131">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="35231-132">データが DiffGram の場合、 **IgnoreSchema**には**diffgram**と同じ機能があり*ます。*</span><span class="sxs-lookup"><span data-stu-id="35231-132">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="35231-133">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="35231-133">**InferSchema**</span></span>|<span data-ttu-id="35231-134">インライン スキーマを無視し、XML データ構造ごとにスキーマを推論し、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35231-134">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="35231-135"><xref:System.Data.DataSet> に既にスキーマが含まれている場合、既存のテーブルに列を追加することによって現在のスキーマが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="35231-135">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="35231-136">既存のテーブルが存在しない場合、余分なテーブルは追加されません。</span><span class="sxs-lookup"><span data-stu-id="35231-136">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="35231-137">推論されたテーブルが他の名前空間に既に存在している場合、または推論された列と既存の列が矛盾する場合には、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="35231-137">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="35231-138">**Readxmlschema**が xml ドキュメントからスキーマを推論する方法の詳細については、「 [Xml からの DataSet リレーショナル構造の推論](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35231-138">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="35231-139">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="35231-139">**DiffGram**</span></span>|<span data-ttu-id="35231-140">DiffGram を読み取り、現在のスキーマへデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="35231-140">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="35231-141">**DiffGram**では、一意の識別子の値が一致する既存の行と新しい行がマージされます。</span><span class="sxs-lookup"><span data-stu-id="35231-141">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="35231-142">このトピックの最後にある「XML のデータの結合」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35231-142">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="35231-143">Diffgram の詳細については、「 [Diffgram グラム](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35231-143">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="35231-144">**抜粋**</span><span class="sxs-lookup"><span data-stu-id="35231-144">**Fragment**</span></span>|<span data-ttu-id="35231-145">ストリームの終わりに達するまで、複数 XML フラグメントの読み取りを続行します。</span><span class="sxs-lookup"><span data-stu-id="35231-145">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="35231-146"><xref:System.Data.DataSet> スキーマに一致するフラグメントが適切なテーブルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="35231-146">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="35231-147"><xref:System.Data.DataSet> スキーマに一致しないフラグメントは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="35231-147">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="35231-148">XML ドキュメントに配置されている**readxml**に**XmlReader**を渡すと、 **readxml**は次の要素ノードを読み取り、それをルート要素として扱い、要素ノードの最後まで読み取ります。</span><span class="sxs-lookup"><span data-stu-id="35231-148">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="35231-149">**XmlReadMode**を指定した場合、この設定は適用されません。</span><span class="sxs-lookup"><span data-stu-id="35231-149">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="35231-150">DTD エンティティ</span><span class="sxs-lookup"><span data-stu-id="35231-150">DTD Entities</span></span>  
 <span data-ttu-id="35231-151">XML にドキュメント型定義 (DTD) スキーマで定義されているエンティティが含まれている場合、ファイル名、ストリーム<xref:System.Data.DataSet> 、または非検証**XmlReader**を**ReadXml**に渡すことによってを読み込もうとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="35231-151">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="35231-152">代わりに、 **Entityhandling**を**Entityhandling. expandentities**に設定して、 **XmlValidatingReader**を**ReadXml**に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="35231-152">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="35231-153">**XmlValidatingReader**は、 <xref:System.Data.DataSet>によって読み取られる前にエンティティを拡張します。</span><span class="sxs-lookup"><span data-stu-id="35231-153">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="35231-154">XML ストリームから <xref:System.Data.DataSet> を読み込むコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="35231-154">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="35231-155">最初の例は、 **ReadXml**メソッドに渡されるファイル名を示しています。</span><span class="sxs-lookup"><span data-stu-id="35231-155">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="35231-156">2 番目の例では、XML が含まれている文字列が <xref:System.IO.StringReader> によって読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="35231-156">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> <span data-ttu-id="35231-157">**ReadXml**を呼び出して非常に大きなファイルを読み込むと、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35231-157">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="35231-158">**Readxml**で最適なパフォーマンスを得るには、大きなファイルで、 <xref:System.Data.DataTable.BeginLoadData%2A>の<xref:System.Data.DataSet>各テーブルに対してメソッドを呼び出し、 **readxml**を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="35231-158">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="35231-159">最後に、次の例に示すように、<xref:System.Data.DataTable.EndLoadData%2A> のテーブルごとに <xref:System.Data.DataSet> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="35231-159">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> <span data-ttu-id="35231-160">の<xref:System.Data.DataSet> XSD スキーマに**targetNamespace**が含まれている場合は、 **ReadXml**を呼び出して、 <xref:System.Data.DataSet>修飾された名前空間を持たない要素を含む XML を読み込むと、データが読み取られず、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35231-160">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="35231-161">この場合、修飾されていない要素を読み取るには、XSD スキーマで**elementFormDefault**を "qualified" に設定します。</span><span class="sxs-lookup"><span data-stu-id="35231-161">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="35231-162">例:</span><span class="sxs-lookup"><span data-stu-id="35231-162">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="35231-163">XML のデータの結合</span><span class="sxs-lookup"><span data-stu-id="35231-163">Merging Data from XML</span></span>  
 <span data-ttu-id="35231-164">既に、<xref:System.Data.DataSet> にデータが含まれている場合には、<xref:System.Data.DataSet> の既存のデータに XML の新しいデータが追加されます。</span><span class="sxs-lookup"><span data-stu-id="35231-164">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="35231-165">**ReadXml**では、XML から、一致する<xref:System.Data.DataSet>主キーを持つ行情報にはマージされません。</span><span class="sxs-lookup"><span data-stu-id="35231-165">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="35231-166">既存の行情報を XML の新しい情報で上書きするには、 **ReadXml**を<xref:System.Data.DataSet>使用して<xref:System.Data.DataSet.Merge%2A>新しいを作成した<xref:System.Data.DataSet>後、 <xref:System.Data.DataSet>既存のに新しいを作成します。</span><span class="sxs-lookup"><span data-stu-id="35231-166">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="35231-167">**XmlReadMode**が**diffgram**の**ReadXML**を使用して diffgram を読み込むと、同じ一意の識別子を持つ行がマージされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="35231-167">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35231-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="35231-168">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="35231-169">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="35231-169">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="35231-170">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="35231-170">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [<span data-ttu-id="35231-171">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="35231-171">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="35231-172">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="35231-172">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="35231-173">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="35231-173">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="35231-174">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="35231-174">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="35231-175">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="35231-175">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
