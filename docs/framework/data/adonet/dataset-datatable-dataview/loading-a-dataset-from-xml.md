---
title: XML からの DataSet の読み込み
description: XML から ADO.NET DataSet にコンテンツを追加する方法について説明します。 .NET Framework では、読み込む対象と DataSet の構造を柔軟に指定できます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 77715913c24423c1dc95478977f4e3821e4c247b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545312"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="1826f-104">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="1826f-104">Loading a DataSet from XML</span></span>
<span data-ttu-id="1826f-105">ADO.NET では、XML ストリームまたは XML ドキュメントから <xref:System.Data.DataSet> の内容を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1826f-105">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="1826f-106">また、.NET Framework では、XML から読み込まれる情報と <xref:System.Data.DataSet> のスキーマまたはリレーショナル構造の作成方法を柔軟に変更できます。</span><span class="sxs-lookup"><span data-stu-id="1826f-106">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="1826f-107"><xref:System.Data.DataSet> に XML のデータを格納するには、<xref:System.Data.DataSet> オブジェクトの **ReadXml** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1826f-107">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="1826f-108">**ReadXml** メソッドは、ファイル、ストリーム、または **XmlReader** からデータを読み取り、XML のソースを引数として受け取ります。また、**XmlReadMode** 引数を受け取ることもあります。</span><span class="sxs-lookup"><span data-stu-id="1826f-108">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="1826f-109">**XmlReader** の詳細については、「[XmlTextReader による XML データの読み取り](/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1826f-109">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="1826f-110">**ReadXml** メソッドは、XML ストリームまたは XML ドキュメントの内容を読み取り、<xref:System.Data.DataSet> にデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1826f-110">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="1826f-111">また、指定されている **XmlReadMode** と、リレーショナル スキーマが既に存在しているかどうかに応じて、<xref:System.Data.DataSet> のリレーショナル スキーマも作成します。</span><span class="sxs-lookup"><span data-stu-id="1826f-111">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="1826f-112">**XmlReadMode** 引数のオプションを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1826f-112">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="1826f-113">オプション</span><span class="sxs-lookup"><span data-stu-id="1826f-113">Option</span></span>|<span data-ttu-id="1826f-114">説明</span><span class="sxs-lookup"><span data-stu-id="1826f-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1826f-115">**Auto**</span><span class="sxs-lookup"><span data-stu-id="1826f-115">**Auto**</span></span>|<span data-ttu-id="1826f-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1826f-116">This is the default.</span></span> <span data-ttu-id="1826f-117">XML を調べ、次の順序で最適なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1826f-117">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="1826f-118">-   XML が DiffGram の場合は、**DiffGram** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-118">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="1826f-119">-   <xref:System.Data.DataSet> にスキーマが含まれている場合、または XML にインライン スキーマが含まれている場合は、**ReadSchema** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-119">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="1826f-120">-   <xref:System.Data.DataSet> にスキーマが含まれておらず、XML にインライン スキーマが含まれていない場合は、**InferSchema** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-120">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="1826f-121">読み取られる XML の形式が判明している場合は、パフォーマンスを最大限に引き出すため、既定値 **Auto** を使用する代わりに、**XmlReadMode** を明示的に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1826f-121">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="1826f-122">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="1826f-122">**ReadSchema**</span></span>|<span data-ttu-id="1826f-123">インライン スキーマを読み取り、データとスキーマを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1826f-123">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="1826f-124"><xref:System.Data.DataSet> に既にスキーマが含まれている場合には、読み取るインライン スキーマの新しいテーブルが <xref:System.Data.DataSet> の既存のスキーマに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-124">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1826f-125">インライン スキーマのテーブルが既に <xref:System.Data.DataSet> に存在している場合には、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1826f-125">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="1826f-126">**XmlReadMode.ReadSchema** を使用して既存のテーブルのスキーマを修正できません。</span><span class="sxs-lookup"><span data-stu-id="1826f-126">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="1826f-127"><xref:System.Data.DataSet> にスキーマが含まれておらず、インライン スキーマが存在しない場合には、データは読み取られません。</span><span class="sxs-lookup"><span data-stu-id="1826f-127">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="1826f-128">インライン スキーマを定義するには、XML スキーマ定義言語 (XSD) スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1826f-128">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="1826f-129">インライン スキーマを XML スキーマとして記述する方法の詳細については、「[XML スキーマ (XSD) からの DataSet リレーショナル構造の派生](deriving-dataset-relational-structure-from-xml-schema-xsd.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1826f-129">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="1826f-130">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="1826f-130">**IgnoreSchema**</span></span>|<span data-ttu-id="1826f-131">インライン スキーマを無視し、データを既存の <xref:System.Data.DataSet> スキーマへ読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1826f-131">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="1826f-132">既存のスキーマに一致しないデータは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-132">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="1826f-133"><xref:System.Data.DataSet> にスキーマがない場合には、データは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="1826f-133">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="1826f-134">データが DiffGram の場合、**IgnoreSchema** は **DiffGram** と同様に機能します *。*</span><span class="sxs-lookup"><span data-stu-id="1826f-134">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="1826f-135">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="1826f-135">**InferSchema**</span></span>|<span data-ttu-id="1826f-136">インライン スキーマを無視し、XML データ構造ごとにスキーマを推論し、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1826f-136">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="1826f-137"><xref:System.Data.DataSet> に既にスキーマが含まれている場合、既存のテーブルに列を追加することによって現在のスキーマが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-137">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="1826f-138">既存のテーブルが存在しない場合、余分なテーブルは追加されません。</span><span class="sxs-lookup"><span data-stu-id="1826f-138">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="1826f-139">推論されたテーブルが他の名前空間に既に存在している場合、または推論された列と既存の列が矛盾する場合には、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1826f-139">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="1826f-140">**ReadXmlSchema** によって XML ドキュメントからスキーマが推論される方法の詳細については、「[XML からの DataSet リレーショナル構造の推論](inferring-dataset-relational-structure-from-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1826f-140">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="1826f-141">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="1826f-141">**DiffGram**</span></span>|<span data-ttu-id="1826f-142">DiffGram を読み取り、現在のスキーマへデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="1826f-142">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="1826f-143">**DiffGram** は、既存の行に対し、固有の識別子の値が一致する新しい行を結合します。</span><span class="sxs-lookup"><span data-stu-id="1826f-143">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="1826f-144">このトピックの最後にある「XML のデータの結合」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1826f-144">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="1826f-145">DiffGrams の詳細については、「[DiffGrams](diffgrams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1826f-145">For more information about DiffGrams, see [DiffGrams](diffgrams.md).</span></span>|  
|<span data-ttu-id="1826f-146">**Fragment**</span><span class="sxs-lookup"><span data-stu-id="1826f-146">**Fragment**</span></span>|<span data-ttu-id="1826f-147">ストリームの終わりに達するまで、複数 XML フラグメントの読み取りを続行します。</span><span class="sxs-lookup"><span data-stu-id="1826f-147">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="1826f-148"><xref:System.Data.DataSet> スキーマに一致するフラグメントが適切なテーブルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-148">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="1826f-149"><xref:System.Data.DataSet> スキーマに一致しないフラグメントは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-149">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1826f-150">XML ドキュメントにアクセスするためのオブジェクトである **ReadXml** に **XmlReader** を渡すと、**ReadXml** では次の要素ノードを読み取り、このノードをルート要素として処理し、このノードの終わりに到達するまで読み取ります。</span><span class="sxs-lookup"><span data-stu-id="1826f-150">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="1826f-151">**XmlReadMode.Fragment** を指定した場合は、このようになりません。</span><span class="sxs-lookup"><span data-stu-id="1826f-151">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="1826f-152">DTD エンティティ</span><span class="sxs-lookup"><span data-stu-id="1826f-152">DTD Entities</span></span>  
 <span data-ttu-id="1826f-153">ドキュメント型定義 (DTD) スキーマで定義されているエンティティが、XML に含まれている場合に、ファイル名、ストリーム、または非検証 **XmlReader** を **ReadXml** に渡して <xref:System.Data.DataSet> を読み込むと、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1826f-153">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="1826f-154">代わりに、**EntityHandling** を **EntityHandling.ExpandEntities** に設定して **XmlValidatingReader** を作成し、**XmlValidatingReader** を **ReadXml** に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1826f-154">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="1826f-155">**XmlValidatingReader** によってエンティティが展開された後で、<xref:System.Data.DataSet> がこのエンティティを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="1826f-155">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="1826f-156">XML ストリームから <xref:System.Data.DataSet> を読み込むコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1826f-156">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="1826f-157">1 番目の例では、ファイル名が **ReadXml** メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-157">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="1826f-158">2 番目の例では、XML が含まれている文字列が <xref:System.IO.StringReader> によって読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1826f-158">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
> <span data-ttu-id="1826f-159">**ReadXml** を呼び出して非常に大きなファイルを読み込んだ場合、パフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="1826f-159">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="1826f-160">大きなファイルを読み込む場合に、**ReadXml** のパフォーマンスを最大にするには、<xref:System.Data.DataSet> のテーブルごとに <xref:System.Data.DataTable.BeginLoadData%2A> メソッドを呼び出し、その後で **ReadXml** を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1826f-160">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="1826f-161">最後に、次の例に示すように、<xref:System.Data.DataTable.EndLoadData%2A> のテーブルごとに <xref:System.Data.DataSet> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1826f-161">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="1826f-162"><xref:System.Data.DataSet> の XSD スキーマに **targetNamespace** が含まれる場合、**ReadXml** を呼び出して、名前空間が修飾されていない要素を含む XML を <xref:System.Data.DataSet> に読み込もうとすると、データが読み取られず、例外が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1826f-162">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="1826f-163">この場合に、名前空間が指定されていない要素を読み込むには、XSD スキーマで **elementFormDefault** を "qualified" に設定します。</span><span class="sxs-lookup"><span data-stu-id="1826f-163">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="1826f-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1826f-164">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="1826f-165">XML のデータの結合</span><span class="sxs-lookup"><span data-stu-id="1826f-165">Merging Data from XML</span></span>  
 <span data-ttu-id="1826f-166">既に、<xref:System.Data.DataSet> にデータが含まれている場合には、<xref:System.Data.DataSet> の既存のデータに XML の新しいデータが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-166">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1826f-167">**ReadXml** では、XML の中で主キーが一致する行情報を <xref:System.Data.DataSet> に結合しません。</span><span class="sxs-lookup"><span data-stu-id="1826f-167">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="1826f-168">既存の行情報を XML の新しい情報で上書きするには、**ReadXml** を使用して新しい <xref:System.Data.DataSet> を作成してから、新しい <xref:System.Data.DataSet> を既存の <xref:System.Data.DataSet> に結合 (<xref:System.Data.DataSet.Merge%2A>) します。</span><span class="sxs-lookup"><span data-stu-id="1826f-168">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1826f-169">**XmlReadMode** が **DiffGram** の **ReadXML** を使用して DiffGram を読み込むと、同一の一意の識別子を持つ行が結合されます。</span><span class="sxs-lookup"><span data-stu-id="1826f-169">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1826f-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="1826f-170">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1826f-171">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="1826f-171">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="1826f-172">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="1826f-172">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="1826f-173">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="1826f-173">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="1826f-174">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="1826f-174">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="1826f-175">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="1826f-175">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="1826f-176">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="1826f-176">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="1826f-177">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="1826f-177">ADO.NET Overview</span></span>](../ado-net-overview.md)
