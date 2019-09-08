---
title: プログラミング ガイド (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: c971f0a92829df40a14631aaff353a268f277f11
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783205"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="9afde-102">プログラミング ガイド (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9afde-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="9afde-103">このセクションでは、LINQ to DataSet を使用したプログラミングの概念と例について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9afde-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9afde-104">In This Section</span></span>  
 [<span data-ttu-id="9afde-105">LINQ to DataSet でのクエリ</span><span class="sxs-lookup"><span data-stu-id="9afde-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="9afde-106">LINQ to DataSet クエリの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="9afde-107">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="9afde-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="9afde-108"><xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="9afde-109">DataRow の比較</span><span class="sxs-lookup"><span data-stu-id="9afde-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="9afde-110"><xref:System.Data.DataRowComparer> オブジェクトを使用してデータ行を比較する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="9afde-111">クエリによる DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="9afde-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="9afde-112">メソッドを使用して<xref:System.Data.DataTable> LINQ to DataSet クエリからを作成する方法について説明します。 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A></span><span class="sxs-lookup"><span data-stu-id="9afde-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="9afde-113">方法: ジェネリック型 T が\<DataRow ではない copytodatatable T > を実装します。</span><span class="sxs-lookup"><span data-stu-id="9afde-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="9afde-114">`CopyToDataTable<T>` 型以外のジェネリック パラメーター T を持つカスタム <xref:System.Data.DataRow> メソッドの実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="9afde-115">ジェネリック メソッド Field および SetField</span><span class="sxs-lookup"><span data-stu-id="9afde-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="9afde-116">ジェネリック メソッド <xref:System.Data.DataRowExtensions.Field%2A> および <xref:System.Data.DataRowExtensions.SetField%2A> に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9afde-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="9afde-117">データ バインディングと LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9afde-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="9afde-118"><xref:System.Data.DataView> オブジェクトを使ったデータ バインドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="9afde-119">LINQ to DataSet クエリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="9afde-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="9afde-120">LINQ to DataSet クエリのデバッグとトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="9afde-121">Security</span><span class="sxs-lookup"><span data-stu-id="9afde-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="9afde-122">LINQ to DataSet のセキュリティの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="9afde-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="9afde-123">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="9afde-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="9afde-124">[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 演算子を使ったクエリの例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9afde-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9afde-125">参照</span><span class="sxs-lookup"><span data-stu-id="9afde-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="9afde-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9afde-126">See also</span></span>

- [<span data-ttu-id="9afde-127">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9afde-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="9afde-128">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9afde-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
