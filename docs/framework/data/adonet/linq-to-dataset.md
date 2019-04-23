---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 92be418e38039757437e6e673f39a7baef011528
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221783"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="0ac9b-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0ac9b-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="0ac9b-103">は、<xref:System.Data.DataSet> オブジェクトにキャッシュされたデータに対するクエリをより簡単に、より高速にします。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-103">makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="0ac9b-104">具体的には、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]個別のクエリ言語を使用して、クエリの代わりに、プログラミング言語そのものを記述できるので、クエリを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="0ac9b-105">これは、コンパイル時の構文チェック、静的な型指定、およびそのクエリで Visual Studio によって提供される IntelliSense サポートのメリットを得ることができます、Visual Studio 開発者に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="0ac9b-106">また、[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] を使用すると、1 つまたは複数のデータ ソースから取得して統合したデータを照会することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="0ac9b-107">これにより、ローカルに集計されたデータのクエリや Web アプリケーションでの中間層のキャッシュなど、データの表現方法や扱いに柔軟性が要求されるさまざまなシナリオが実現します。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="0ac9b-108">特に、汎用のレポート作成、分析、ビジネス インテリジェンスを行うアプリケーションでは、この手法を用いたデータ操作が欠かせません。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="0ac9b-109">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]機能は、拡張メソッドによって主に公開されて、<xref:System.Data.DataRowExtensions>と<xref:System.Data.DataTableExtensions>クラス。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="0ac9b-110">ビルドされ、既存を使用して[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]のアーキテクチャを置き換えるものでありません[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]アプリケーション コードでします。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-110">builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="0ac9b-111">既存の ADO.NET 2.0 コードは [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] アプリケーションにおいても機能します。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="0ac9b-112">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] と [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] のリレーションシップとデータ ストアを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="0ac9b-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 ![LINQ to DataSet が ADO.NET プロバイダーに基づくされていることを示す図。](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="0ac9b-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0ac9b-114">In This Section</span></span>  
 [<span data-ttu-id="0ac9b-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="0ac9b-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="0ac9b-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0ac9b-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="0ac9b-117">参照</span><span class="sxs-lookup"><span data-stu-id="0ac9b-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="0ac9b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac9b-118">See also</span></span>

- [<span data-ttu-id="0ac9b-119">統合言語クエリ (LINQ) - C#</span><span class="sxs-lookup"><span data-stu-id="0ac9b-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="0ac9b-120">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ac9b-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="0ac9b-121">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0ac9b-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="0ac9b-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0ac9b-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
