---
title: DataSet と XmlDataDocument の同期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 7763e7065e74d99ee5521ea1e4f48fa0108f235a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623393"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="1cd77-102">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="1cd77-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="1cd77-103">ADO.NET の <xref:System.Data.DataSet> には、データのリレーショナル表現があります。</span><span class="sxs-lookup"><span data-stu-id="1cd77-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="1cd77-104">階層データにアクセスするには、.NET Framework で使用できる XML クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="1cd77-105">従来、この 2 つのデータ表現は個別に使用されていました。</span><span class="sxs-lookup"><span data-stu-id="1cd77-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="1cd77-106">ただし、.NET Framework により、リアルタイムの同期のアクセスを使用してデータのリレーショナルで階層的な表現の両方に、**データセット**オブジェクトと<xref:System.Xml.XmlDataDocument>オブジェクトに、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="1cd77-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="1cd77-107">ときに、**データセット**と同期されて、 **XmlDataDocument**、1 つのセットのデータの両方のオブジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="1cd77-108">つまり、変更する場合、**データセット**、変更の反映で、 **XmlDataDocument**、またはその逆。</span><span class="sxs-lookup"><span data-stu-id="1cd77-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="1cd77-109">間のリレーションシップ、**データセット**と**XmlDataDocument**構築されたサービスのスイート全体にアクセスするデータの 1 つのセットを使用して、1 つのアプリケーションを許可することで優れた柔軟性を作成します。周囲、**データセット**(Web フォームと Windows フォームのコントロールや Visual Studio .NET デザイナーを使用)、Extensible Stylesheet Language (XSL)、XSL Transformations (XSLT)、および XML のパスを含む XML サービスのスイートと言語 (XPath)。</span><span class="sxs-lookup"><span data-stu-id="1cd77-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="1cd77-110">アプリケーションでアクセス対象とするサービス セットを選択する必要はありません。どちらのサービス セットにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="1cd77-111">同期するいくつかの方法がある、**データセット**で、 **XmlDataDocument**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="1cd77-112">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-112">You can:</span></span>  
  
- <span data-ttu-id="1cd77-113">設定、**データセット**スキーマ (つまり、リレーショナル構造) およびデータを使用し、それを新しい同期**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="1cd77-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="1cd77-114">この方法では、既存のリレーショナル データの階層ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="1cd77-115">例:</span><span class="sxs-lookup"><span data-stu-id="1cd77-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="1cd77-116">設定、**データセット**スキーマのみを使用 (など、厳密に型指定された**データセット**) と同期する**XmlDataDocument**、し、ロード、 **XmlDataDocument** XML ドキュメントから。</span><span class="sxs-lookup"><span data-stu-id="1cd77-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="1cd77-117">この方法では、既存の階層データのリレーショナル ビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="1cd77-118">テーブル名と列名、**データセット**スキーマは同期をとる XML 要素の名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd77-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="1cd77-119">この名前の一致では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="1cd77-120">注意のスキーマ、**データセット**のみ、リレーショナル ビューで公開する、XML 要素との一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd77-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="1cd77-121">つまり、このドキュメント上に非常に大きい XML ドキュメントと非常に小さなリレーショナル ウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="1cd77-122">**XmlDataDocument**場合でも、XML ドキュメント全体を保持、**データセット**のみの一部を公開します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="1cd77-123">(この詳細な例についてを参照してください[DataSet と XmlDataDocument の同期](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)。)。</span><span class="sxs-lookup"><span data-stu-id="1cd77-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="1cd77-124">次のコード例を作成するための手順を示しています、**データセット**と同期し、そのスキーマを読み込み、 **XmlDataDocument**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="1cd77-125">なお、**データセット**スキーマがのみから要素を対応付ける必要があります、 **XmlDataDocument**を使用して公開する、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="1cd77-126">読み込むことはできません、 **XmlDataDocument**と同期されている場合、**データセット**データを格納します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="1cd77-127">読み込もうとすると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="1cd77-128">新規作成**XmlDataDocument** 、XML ドキュメントからそれを読み込むしを使用して、データのリレーショナル ビューにアクセスし、**データセット**のプロパティ、 **XmlDataDocument**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="1cd77-129">スキーマを設定する必要がある、**データセット**内のデータのいずれかを表示する前に、 **XmlDataDocument**を使用して、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="1cd77-130">テーブル名と列の名前、もう一度、**データセット**スキーマは同期をとる XML 要素の名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd77-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="1cd77-131">この名前の一致では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="1cd77-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="1cd77-132">次のコード例のデータのリレーショナル ビューにアクセスする方法を示しています、 **XmlDataDocument**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="1cd77-133">同期のもう 1 つの利点、 **XmlDataDocument**で、**データセット**は XML ドキュメントの忠実性を保持します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="1cd77-134">場合、**データセット**は使用して XML ドキュメントから取得されます**ReadXml**による XML ドキュメントとして返されます、データが書き込まれるときに、 **WriteXml**から大幅に異なる場合があります、元の XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="1cd77-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="1cd77-135">これは、ため、**データセット**、空白文字、または XML ドキュメントからの要素の順序などの階層情報などの書式設定は維持されません。</span><span class="sxs-lookup"><span data-stu-id="1cd77-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="1cd77-136">**データセット**も XML ドキュメントからのスキーマが一致しなかったため無視された要素を含んでいない、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="1cd77-137">同期、 **XmlDataDocument**で、**データセット**によりで管理する元の XML ドキュメントの書式設定で階層的な要素の構造、 **XmlDataDocument**中、**データセット**だけデータとスキーマに対応する情報が含まれています、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="1cd77-138">同期するときに、**データセット**で、 **XmlDataDocument**、結果がかどうかに応じて異なる場合があります、<xref:System.Data.DataRelation>オブジェクトが入れ子にします。</span><span class="sxs-lookup"><span data-stu-id="1cd77-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="1cd77-139">詳細については、次を参照してください。 [Datarelation の入れ子](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1cd77-140">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1cd77-140">In This Section</span></span>  
 [<span data-ttu-id="1cd77-141">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="1cd77-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="1cd77-142">厳密に型指定された同期を示して**データセット**、最小限のスキーマで、 **XmlDataDocument**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="1cd77-143">DataSet に対する XPath クエリの実行</span><span class="sxs-lookup"><span data-stu-id="1cd77-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="1cd77-144">内容に対する XPath クエリの実行を示します、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="1cd77-145">DataSet への XSLT 変換の適用</span><span class="sxs-lookup"><span data-stu-id="1cd77-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="1cd77-146">内容に XSLT 変換の適用を示して、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1cd77-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cd77-147">Related Sections</span></span>  
 [<span data-ttu-id="1cd77-148">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="1cd77-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="1cd77-149">について説明しますが、どのように**データセット**の内容を保存したりするなど、データ ソースとして XML と対話を**データセット**XML データとして。</span><span class="sxs-lookup"><span data-stu-id="1cd77-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="1cd77-150">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="1cd77-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="1cd77-151">重要性について説明します入れ子になった**DataRelation**オブジェクトの内容を表すときに、**データセット**を XML データとしてこれらのリレーションシップを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1cd77-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="1cd77-152">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="1cd77-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="1cd77-153">について説明します、**データセット**とアプリケーション データを管理し、リレーショナル データベースや XML などのデータ ソースと対話する方法。</span><span class="sxs-lookup"><span data-stu-id="1cd77-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="1cd77-154">に関するリファレンス情報を含む、 **XmlDataDocument**クラス。</span><span class="sxs-lookup"><span data-stu-id="1cd77-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd77-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cd77-155">See also</span></span>

- [<span data-ttu-id="1cd77-156">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="1cd77-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
