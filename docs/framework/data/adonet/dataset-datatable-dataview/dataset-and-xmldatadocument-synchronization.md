---
title: DataSet と XmlDataDocument の同期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: e76e81153cb7d074fe975744c6b6041ee04be90f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785430"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="4bf7a-102">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="4bf7a-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="4bf7a-103">ADO.NET の <xref:System.Data.DataSet> には、データのリレーショナル表現があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="4bf7a-104">階層データにアクセスするには、.NET Framework で使用できる XML クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="4bf7a-105">従来、この 2 つのデータ表現は個別に使用されていました。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="4bf7a-106">ただし、.NET Framework では、データ**セット**オブジェクトと<xref:System.Xml.XmlDataDocument>オブジェクトを使用して、データのリレーショナル表現と階層表現の両方に対してリアルタイムの同期アクセスを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="4bf7a-107">データ**セット**が**XmlDataDocument**と同期されると、両方のオブジェクトが1つのデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="4bf7a-108">これは、**データセット**に変更が加えられた場合、変更が**XmlDataDocument**に反映されることを意味します。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="4bf7a-109">データセットと XmlDataDocument**の間**の関係により、1つのデータセットを使用して1つのアプリケーションでデータ**セット**を中心に構築されたサービススイート全体にアクセスできるようになり (Web フォームやWindows フォームコントロール、および Visual Studio .NET デザイナー) に加えて、拡張スタイルシート言語 (XSL)、XSL transformation (XSLT)、XML Path Language (XPath) などの XML サービス群が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="4bf7a-110">アプリケーションでアクセス対象とするサービス セットを選択する必要はありません。どちらのサービス セットにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="4bf7a-111">**データセット**を**XmlDataDocument**と同期するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="4bf7a-112">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-112">You can:</span></span>  
  
- <span data-ttu-id="4bf7a-113">データ**セット**にスキーマ (リレーショナル構造) とデータを設定し、新しい**XmlDataDocument**と同期します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="4bf7a-114">この方法では、既存のリレーショナル データの階層ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="4bf7a-115">例:</span><span class="sxs-lookup"><span data-stu-id="4bf7a-115">For example:</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
- <span data-ttu-id="4bf7a-116">**データセット**にスキーマのみ (厳密に型指定された**データセット**など) を設定し、それを**XmlDataDocument**と同期してから、XML ドキュメントから**XmlDataDocument**を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="4bf7a-117">この方法では、既存の階層データのリレーショナル ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="4bf7a-118">**データセット**スキーマ内のテーブル名と列名は、同期する XML 要素の名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="4bf7a-119">この名前の一致では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="4bf7a-120">**データセット**のスキーマは、リレーショナルビューで公開する XML 要素とのみ一致する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="4bf7a-121">つまり、このドキュメント上に非常に大きい XML ドキュメントと非常に小さなリレーショナル ウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="4bf7a-122">**XmlDataDocument**では、**データセット**が公開している部分がごくわずかでも、XML ドキュメント全体が保持されます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="4bf7a-123">(詳細な例については、「XmlDataDocument を使用した[データセットの同期](synchronizing-a-dataset-with-an-xmldatadocument.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="4bf7a-124">次のコード例は、**データセット**を作成してそのスキーマを設定し、 **XmlDataDocument**と同期する手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="4bf7a-125">**データセット**スキーマは、**データセット**を使用して公開する**XmlDataDocument**の要素とのみ一致する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     <span data-ttu-id="4bf7a-126">データが含まれているデータ**セット**と同期されている場合、 **XmlDataDocument**を読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="4bf7a-127">読み込もうとすると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="4bf7a-128">新しい**XmlDataDocument**を作成して XML ドキュメントから読み込み、 **XmlDataDocument**のデータ**セット**プロパティを使用してデータのリレーショナルビューにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="4bf7a-129">データセットを使用して**XmlDataDocument**内のデータを表示するには、データ**セット**のスキーマを設定する必要が**あります。**</span><span class="sxs-lookup"><span data-stu-id="4bf7a-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="4bf7a-130">ここでも、**データセット**スキーマ内のテーブル名と列名は、同期する XML 要素の名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="4bf7a-131">この名前の一致では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="4bf7a-132">次のコード例では、 **XmlDataDocument**内のデータのリレーショナルビューにアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 <span data-ttu-id="4bf7a-133">**XmlDataDocument**を**データセット**と同期するもう1つの利点は、XML ドキュメントの忠実性が維持されることです。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="4bf7a-134">**ReadXml**を使用して xml ドキュメントからデータ**セット**を作成した場合、データが**WRITEXML**を使用して xml ドキュメントとして書き戻されると、元の xml ドキュメントとは大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="4bf7a-135">これは、**データセット**が XML ドキュメントからの空白などの書式設定や要素の順序などの階層情報を保持しないためです。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="4bf7a-136">**データ**セットには、**データセット**のスキーマと一致しなかったために無視された XML ドキュメントの要素も含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="4bf7a-137">**XmlDataDocument**と**データセット**を同期すると、元の XML ドキュメントの書式設定と階層要素構造が**XmlDataDocument**に保持されますが、データ**セット**にはデータのみが含まれ、**データセット**に適したスキーマ情報。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="4bf7a-138">**データセット**を**XmlDataDocument**と同期する場合、 <xref:System.Data.DataRelation>オブジェクトが入れ子になっているかどうかによって結果が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="4bf7a-139">詳細については、「 [datarelation の入れ子](nesting-datarelations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bf7a-140">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4bf7a-140">In This Section</span></span>  
 [<span data-ttu-id="4bf7a-141">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="4bf7a-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="4bf7a-142">**XmlDataDocument**を使用して、厳密に型指定された**データセット**と最小スキーマを同期する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="4bf7a-143">DataSet に対する XPath クエリの実行</span><span class="sxs-lookup"><span data-stu-id="4bf7a-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="4bf7a-144">**データセット**の内容に対して XPath クエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="4bf7a-145">DataSet への XSLT 変換の適用</span><span class="sxs-lookup"><span data-stu-id="4bf7a-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="4bf7a-146">XSLT 変換を**DataSet**の内容に適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bf7a-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bf7a-147">Related Sections</span></span>  
 [<span data-ttu-id="4bf7a-148">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="4bf7a-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="4bf7a-149">データセットの内容を XML**データとし**て読み込み、永続化するなど、データ**セット**をデータソースとして xml と対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="4bf7a-150">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="4bf7a-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="4bf7a-151">**DataSet**の内容を XML データとして表す場合に、入れ子になった**DataRelation**オブジェクトの重要性について説明し、これらの関係を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="4bf7a-152">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="4bf7a-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="4bf7a-153">データ**セット**と、それを使用してアプリケーションデータを管理し、リレーショナルデータベースや XML などのデータソースと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="4bf7a-154">**XmlDataDocument**クラスに関する参照情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4bf7a-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf7a-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bf7a-155">See also</span></span>

- [<span data-ttu-id="4bf7a-156">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="4bf7a-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
