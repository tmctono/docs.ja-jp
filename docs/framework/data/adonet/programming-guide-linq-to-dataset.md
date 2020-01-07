---
title: プログラミング ガイド (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: dc13af06cf6c439d739d76904f206ebc50ba3187
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634808"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="1ebec-102">プログラミング ガイド (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="1ebec-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="1ebec-103">このセクションでは、LINQ to DataSet を使用したプログラミングの概念と例について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ebec-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ebec-104">In This Section</span></span>  
 [<span data-ttu-id="1ebec-105">LINQ to DataSet でのクエリ</span><span class="sxs-lookup"><span data-stu-id="1ebec-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-106">LINQ to DataSet クエリの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="1ebec-107">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="1ebec-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-108"><xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="1ebec-109">DataRow の比較</span><span class="sxs-lookup"><span data-stu-id="1ebec-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-110"><xref:System.Data.DataRowComparer> オブジェクトを使用してデータ行を比較する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="1ebec-111">クエリによる DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="1ebec-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-112"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドを使用して LINQ to DataSet クエリから <xref:System.Data.DataTable> を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="1ebec-113">方法: CopyToDataTable\<T > 実装する (ジェネリック型 T が DataRow ではない場合)</span><span class="sxs-lookup"><span data-stu-id="1ebec-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="1ebec-114">`CopyToDataTable<T>` 型以外のジェネリック パラメーター T を持つカスタム <xref:System.Data.DataRow> メソッドの実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="1ebec-115">ジェネリック メソッド Field および SetField</span><span class="sxs-lookup"><span data-stu-id="1ebec-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-116">ジェネリック メソッド <xref:System.Data.DataRowExtensions.Field%2A> および <xref:System.Data.DataRowExtensions.SetField%2A> に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="1ebec-117">データ バインディングと LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="1ebec-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-118"><xref:System.Data.DataView> オブジェクトを使ったデータ バインドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="1ebec-119">LINQ to DataSet クエリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="1ebec-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="1ebec-120">LINQ to DataSet クエリのデバッグとトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="1ebec-121">Security</span><span class="sxs-lookup"><span data-stu-id="1ebec-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="1ebec-122">LINQ to DataSet のセキュリティの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="1ebec-123">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="1ebec-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="1ebec-124">LINQ 演算子を使ったクエリの例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="1ebec-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1ebec-125">参照先</span><span class="sxs-lookup"><span data-stu-id="1ebec-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="1ebec-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ebec-126">See also</span></span>

- [<span data-ttu-id="1ebec-127">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ebec-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="1ebec-128">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="1ebec-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
