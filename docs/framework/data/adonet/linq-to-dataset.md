---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783789"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="5fd88-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5fd88-102">LINQ to DataSet</span></span>
<span data-ttu-id="5fd88-103">LINQ to DataSet を使用すると、オブジェクトにキャッシュされた<xref:System.Data.DataSet>データに対するクエリを簡単かつ迅速に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5fd88-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="5fd88-104">具体的には、LINQ to DataSet は、開発者が個別のクエリ言語を使用するのではなく、プログラミング言語自体からクエリを作成できるようにすることで、クエリを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="5fd88-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="5fd88-105">これは、visual studio 開発者にとって特に便利です。これにより、Visual Studio がクエリで提供するコンパイル時の構文チェック、静的な型指定、IntelliSense サポートを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5fd88-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="5fd88-106">また、LINQ to DataSet を使用して、1つまたは複数のデータソースから統合されたデータを照会することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fd88-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="5fd88-107">これにより、ローカルに集計されたデータのクエリや Web アプリケーションでの中間層のキャッシュなど、データの表現方法や扱いに柔軟性が要求されるさまざまなシナリオが実現します。</span><span class="sxs-lookup"><span data-stu-id="5fd88-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="5fd88-108">特に、汎用のレポート作成、分析、ビジネス インテリジェンスを行うアプリケーションでは、この手法を用いたデータ操作が欠かせません。</span><span class="sxs-lookup"><span data-stu-id="5fd88-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="5fd88-109">LINQ to DataSet 機能は、主におよび<xref:System.Data.DataRowExtensions> <xref:System.Data.DataTableExtensions>クラスの拡張メソッドを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="5fd88-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="5fd88-110">LINQ to DataSet は、既存の ADO.NET アーキテクチャを使用してをビルドし、アプリケーションコードの ADO.NET を置き換えることを意図していません。</span><span class="sxs-lookup"><span data-stu-id="5fd88-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="5fd88-111">既存の ADO.NET コードは、LINQ to DataSet アプリケーションで引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="5fd88-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="5fd88-112">次の図は、ADO.NET とデータストアの LINQ to DataSet の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fd88-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![LINQ to DataSet が ADO.NET プロバイダーに基づいていることを示す図。](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="5fd88-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5fd88-114">In This Section</span></span>  
 [<span data-ttu-id="5fd88-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="5fd88-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="5fd88-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5fd88-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="5fd88-117">参照</span><span class="sxs-lookup"><span data-stu-id="5fd88-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="5fd88-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fd88-118">See also</span></span>

- [<span data-ttu-id="5fd88-119">統合言語クエリ (LINQ) - C#</span><span class="sxs-lookup"><span data-stu-id="5fd88-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5fd88-120">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5fd88-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5fd88-121">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fd88-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="5fd88-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fd88-122">ADO.NET</span></span>](index.md)
