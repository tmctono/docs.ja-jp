---
title: DataSet での XML の使用
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: e133da727887271af3bc5330a5779df4af58a37e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201188"
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="e62be-102">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="e62be-102">Using XML in a DataSet</span></span>

<span data-ttu-id="e62be-103">ADO.NET では、XML ストリームまたは XML ドキュメントから <xref:System.Data.DataSet> にデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="e62be-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="e62be-104"><xref:System.Data.DataSet> にデータまたはスキーマ情報を格納するには、XML ストリームまたは XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e62be-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="e62be-105">XML ストリームまたは XML ドキュメントから提供される情報を <xref:System.Data.DataSet> の既存のデータまたはスキーマ情報と組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="e62be-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="e62be-106">ADO.NET では、他のアプリケーションや XML 対応プラットフォームで <xref:System.Data.DataSet> が使用される場合に、この <xref:System.Data.DataSet> を HTTP 経由で転送するため、DataSet の XML 表現を作成できます。このとき、DataSet にスキーマが含まれていても、含まれていなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="e62be-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="e62be-107"><xref:System.Data.DataSet> の XML 表現では、データを XML で記述します。XML 表現にスキーマをインラインで含める場合は、このスキーマを XML スキーマ定義言語 (XSD) で記述します。</span><span class="sxs-lookup"><span data-stu-id="e62be-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="e62be-108">XML および XML スキーマには、リモート クライアントとの間で <xref:System.Data.DataSet> の内容を転送するための便利な書式が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e62be-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e62be-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e62be-109">In This Section</span></span>  

 [<span data-ttu-id="e62be-110">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="e62be-110">DiffGrams</span></span>](diffgrams.md)  
 <span data-ttu-id="e62be-111"><xref:System.Data.DataSet> の内容の読み取りと書き込みに使用される XML 形式である DiffGram について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62be-112">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="e62be-112">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)  
 <span data-ttu-id="e62be-113">XML ドキュメントから <xref:System.Data.DataSet> の内容を読み込むときに考慮する必要のある各種オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="e62be-114">DataSet 内容の XML データとしての書き込み</span><span class="sxs-lookup"><span data-stu-id="e62be-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="e62be-115"><xref:System.Data.DataSet> の内容を XML データとして生成する方法と、使用できる各種 XML 形式オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="e62be-116">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="e62be-116">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="e62be-117">XML から <xref:System.Data.DataSet> のスキーマを読み込むために使用される <xref:System.Data.DataSet> のメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="e62be-118">XSD としての DataSet スキーマ情報の書き込み</span><span class="sxs-lookup"><span data-stu-id="e62be-118">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="e62be-119">XML スキーマの使用方法と、<xref:System.Data.DataSet> からの XML スキーマの生成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="e62be-120">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="e62be-120">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="e62be-121">1 つのデータ セットのリレーショナル ビューおよび階層ビューの両方に同期的な方法でアクセスする .NET Framework の機能について説明し、<xref:System.Data.DataSet> と <xref:System.Xml.XmlDataDocument> の間で同期的なリレーションシップを確立する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="e62be-122">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="e62be-122">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="e62be-123"><xref:System.Data.DataRelation> の内容を XML データとして表現する場合において、入れ子になった <xref:System.Data.DataSet> オブジェクトの重要性について説明します。また、入れ子になったこれらのオブジェクトの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="e62be-124">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="e62be-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="e62be-125">XML スキーマから作成された <xref:System.Data.DataSet> のリレーショナル構造 (スキーマ) について説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="e62be-126">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="e62be-126">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="e62be-127">XML 要素から推論する際に作成される <xref:System.Data.DataSet> のリレーショナル構造 (スキーマ) について説明します。</span><span class="sxs-lookup"><span data-stu-id="e62be-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e62be-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e62be-128">Related Sections</span></span>  

 [<span data-ttu-id="e62be-129">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e62be-129">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="e62be-130">ADO.NET のアーキテクチャとコンポーネントについて説明し、それらを使用して既存のデータ ソースにアクセスしたり、アプリケーション データを管理したりする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e62be-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62be-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e62be-131">See also</span></span>

- [<span data-ttu-id="e62be-132">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="e62be-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="e62be-133">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e62be-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
