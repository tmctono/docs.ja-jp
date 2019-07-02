---
title: プログラミング ガイド (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: d454448771e14b1a540b5a066683bd4c747991ec
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504775"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="9e952-102">プログラミング ガイド (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9e952-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="9e952-103">ここでは概念情報と例をデータセットに LINQ を使用したプログラミングを示します。</span><span class="sxs-lookup"><span data-stu-id="9e952-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e952-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9e952-104">In This Section</span></span>  
 [<span data-ttu-id="9e952-105">LINQ to DataSet でのクエリ</span><span class="sxs-lookup"><span data-stu-id="9e952-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="9e952-106">Linq TO DataSet のクエリを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="9e952-107">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="9e952-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="9e952-108"><xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="9e952-109">DataRow の比較</span><span class="sxs-lookup"><span data-stu-id="9e952-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="9e952-110"><xref:System.Data.DataRowComparer> オブジェクトを使用してデータ行を比較する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="9e952-111">クエリによる DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="9e952-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="9e952-112">作成する方法について説明します、 <xref:System.Data.DataTable> LINQ to DataSet クエリを使用してから、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9e952-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="9e952-113">方法: 実装 CopyToDataTable\<T > ジェネリック型 T が DataRow ではありません</span><span class="sxs-lookup"><span data-stu-id="9e952-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="9e952-114">`CopyToDataTable<T>` 型以外のジェネリック パラメーター T を持つカスタム <xref:System.Data.DataRow> メソッドの実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="9e952-115">ジェネリック メソッド Field および SetField</span><span class="sxs-lookup"><span data-stu-id="9e952-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="9e952-116">ジェネリック メソッド <xref:System.Data.DataRowExtensions.Field%2A> および <xref:System.Data.DataRowExtensions.SetField%2A> に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9e952-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="9e952-117">データ バインディングと LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9e952-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="9e952-118"><xref:System.Data.DataView> オブジェクトを使ったデータ バインドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="9e952-119">LINQ to DataSet クエリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="9e952-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="9e952-120">デバッグとトラブルシューティングの LINQ to DataSet クエリについてを説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="9e952-121">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9e952-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="9e952-122">LINQ to DataSet でのセキュリティの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e952-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="9e952-123">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="9e952-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="9e952-124">[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 演算子を使ったクエリの例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9e952-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9e952-125">参照</span><span class="sxs-lookup"><span data-stu-id="9e952-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="9e952-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e952-126">See also</span></span>

- [<span data-ttu-id="9e952-127">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e952-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="9e952-128">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9e952-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
