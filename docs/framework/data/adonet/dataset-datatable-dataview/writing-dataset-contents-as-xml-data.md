---
title: DataSet 内容の XML データとしての書き込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: 9a63e79b2fce137ba9d21db861850a471cb42b9f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833963"
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="003e8-102">DataSet 内容の XML データとしての書き込み</span><span class="sxs-lookup"><span data-stu-id="003e8-102">Writing DataSet Contents as XML Data</span></span>
<span data-ttu-id="003e8-103">ADO.NET では、<xref:System.Data.DataSet> の XML 表現を記述することができます。このとき、 にスキーマが含まれていても、含まれていなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="003e8-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="003e8-104">XML にインラインで含まれているスキーマ情報は、XML スキーマ定義言語 (XSD) を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="003e8-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="003e8-105">スキーマには、リレーション定義および制約定義と、<xref:System.Data.DataSet> のテーブル定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="003e8-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="003e8-106"><xref:System.Data.DataSet> が XML データとして書き込まれると、<xref:System.Data.DataSet> の行は現在のバージョンで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="003e8-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="003e8-107">ただし、行の現在の値と元の値の両方を含めるには、<xref:System.Data.DataSet> を DiffGram として書き込みます。</span><span class="sxs-lookup"><span data-stu-id="003e8-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="003e8-108">@No__t 0 の XML 表現は、ファイル、ストリーム、 **XmlWriter**、または文字列に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="003e8-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="003e8-109">複数の書き込み先があることから、<xref:System.Data.DataSet> の XML 表現の転送方法を柔軟に変更できます。</span><span class="sxs-lookup"><span data-stu-id="003e8-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="003e8-110">@No__t 0 の XML 表現を文字列として取得するには、次の例に示すように、 **GetXml**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="003e8-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="003e8-111">**GetXml**は、スキーマ情報を含まない <xref:System.Data.DataSet> の XML 表現を返します。</span><span class="sxs-lookup"><span data-stu-id="003e8-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="003e8-112">@No__t-0 (XML スキーマ) から文字列にスキーマ情報を書き込むには、 **Getxmlschema**を使用します。</span><span class="sxs-lookup"><span data-stu-id="003e8-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="003e8-113">ファイル、ストリーム、または**XmlWriter**に @no__t 0 を書き込むには、 **WriteXml**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="003e8-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="003e8-114">**WriteXml**に渡す最初のパラメーターは、XML 出力の変換先です。</span><span class="sxs-lookup"><span data-stu-id="003e8-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="003e8-115">たとえば、ファイル名を含む文字列、また**は、system.servicemodel オブジェクトなど**を渡します。</span><span class="sxs-lookup"><span data-stu-id="003e8-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="003e8-116">**XmlWriteMode**の省略可能な2番目のパラメーターを渡して、XML 出力の書き込み方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="003e8-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="003e8-117">次の表は、 **XmlWriteMode**のオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="003e8-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="003e8-118">XmlWriteMode のオプション</span><span class="sxs-lookup"><span data-stu-id="003e8-118">XmlWriteMode option</span></span>|<span data-ttu-id="003e8-119">説明</span><span class="sxs-lookup"><span data-stu-id="003e8-119">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="003e8-120">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="003e8-120">**IgnoreSchema**</span></span>|<span data-ttu-id="003e8-121"><xref:System.Data.DataSet> の現在の内容を XML スキーマを含まない XML データとして書き込みます。</span><span class="sxs-lookup"><span data-stu-id="003e8-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="003e8-122">既定値です。</span><span class="sxs-lookup"><span data-stu-id="003e8-122">This is the default.</span></span>|  
|<span data-ttu-id="003e8-123">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="003e8-123">**WriteSchema**</span></span>|<span data-ttu-id="003e8-124"><xref:System.Data.DataSet> の現在の内容を XML データとして書き込みます。このとき、リレーショナル構造がインライン XML スキーマとして書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="003e8-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="003e8-125">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="003e8-125">**DiffGram**</span></span>|<span data-ttu-id="003e8-126">元の値と現在の値を含め、<xref:System.Data.DataSet> 全体を DiffGram として書き込みます。</span><span class="sxs-lookup"><span data-stu-id="003e8-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="003e8-127">詳細については、「 [Diffgram グラム](diffgrams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003e8-127">For more information, see [DiffGrams](diffgrams.md).</span></span>|  
  
 <span data-ttu-id="003e8-128">**DataRelation**オブジェクトを含む @no__t 0 の xml 表現を記述する場合、ほとんどの場合、その結果の xml に、関連する親要素内に入れ子になった各リレーションシップの子行が含まれるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="003e8-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="003e8-129">これを実現するには **、datarelation を**<xref:System.Data.DataSet> に追加するときに、 **datarelation**の**Nested**プロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="003e8-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="003e8-130">詳細については、「 [datarelation の入れ子](nesting-datarelations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003e8-130">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="003e8-131">@No__t-0 の XML 表現をファイルに書き込む方法の2つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="003e8-131">The following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="003e8-132">最初の例では、結果の XML のファイル名を文字列として**WriteXml**に渡します。</span><span class="sxs-lookup"><span data-stu-id="003e8-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="003e8-133">2番目の例**では、system.servicemodel オブジェクトを**渡します。</span><span class="sxs-lookup"><span data-stu-id="003e8-133">The second example passes a **System.IO.StreamWriter** object.</span></span>
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="003e8-134">XML 要素、属性、およびテキストへの列の割り当て</span><span class="sxs-lookup"><span data-stu-id="003e8-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  
 <span data-ttu-id="003e8-135">テーブルの列を XML で表現する方法は、 **DataColumn**オブジェクトの**ColumnMapping**プロパティを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="003e8-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="003e8-136">次の表は、テーブルの列の**ColumnMapping**プロパティのさまざまな**mappingtype**値と、結果の XML を示しています。</span><span class="sxs-lookup"><span data-stu-id="003e8-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="003e8-137">MappingType の値</span><span class="sxs-lookup"><span data-stu-id="003e8-137">MappingType value</span></span>|<span data-ttu-id="003e8-138">説明</span><span class="sxs-lookup"><span data-stu-id="003e8-138">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="003e8-139">**要素**</span><span class="sxs-lookup"><span data-stu-id="003e8-139">**Element**</span></span>|<span data-ttu-id="003e8-140">既定値です。</span><span class="sxs-lookup"><span data-stu-id="003e8-140">This is the default.</span></span> <span data-ttu-id="003e8-141">列が XML 要素として書き込まれます。このとき、ColumnName は要素名になり、列の内容は要素のテキストとして書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="003e8-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="003e8-142">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="003e8-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="003e8-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="003e8-143">**Attribute**</span></span>|<span data-ttu-id="003e8-144">列が、現在の行の XML 要素の XML 属性として書き込まれます。このとき、ColumnName は属性名になり、列の内容は属性の値として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="003e8-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="003e8-145">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="003e8-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="003e8-146">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="003e8-146">**SimpleContent**</span></span>|<span data-ttu-id="003e8-147">列の内容が、現在の行の XML 要素のテキストとして書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="003e8-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="003e8-148">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="003e8-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="003e8-149">**要素**列または入れ子になったリレーションを含むテーブルの列には、 **SimpleContent**を設定できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="003e8-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="003e8-150">**[非表示]**</span><span class="sxs-lookup"><span data-stu-id="003e8-150">**Hidden**</span></span>|<span data-ttu-id="003e8-151">列は XML 出力に書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="003e8-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="003e8-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="003e8-152">See also</span></span>

- [<span data-ttu-id="003e8-153">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="003e8-153">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="003e8-154">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="003e8-154">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="003e8-155">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="003e8-155">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="003e8-156">XSD としての DataSet スキーマ情報の書き込み</span><span class="sxs-lookup"><span data-stu-id="003e8-156">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)
- [<span data-ttu-id="003e8-157">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="003e8-157">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="003e8-158">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="003e8-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
