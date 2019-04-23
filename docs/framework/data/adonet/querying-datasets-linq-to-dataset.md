---
title: DataSet のクエリ (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: a1c316811ce08141999bcec4c9c8504f86c2e285
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165244"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="3818e-102">DataSet のクエリ (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="3818e-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="3818e-103"><xref:System.Data.DataSet> オブジェクトへのデータの読み込みが完了すると、そのデータセットに対してクエリを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3818e-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="3818e-104">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] を使ったクエリの作成方法は、他の [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 対応データ ソースに対して [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] を使用する方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="3818e-104">Formulating queries with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="3818e-105">ただしを使用すると[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]クエリを実行、<xref:System.Data.DataSet>オブジェクトの列挙クエリを実行する<xref:System.Data.DataRow>カスタム型の列挙体ではなく、オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3818e-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="3818e-106">つまりのメンバーのいずれかを使用できます、<xref:System.Data.DataRow>クラス、[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]クエリ。</span><span class="sxs-lookup"><span data-stu-id="3818e-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="3818e-107">これにより、高度で複雑なクエリの作成が可能となります。</span><span class="sxs-lookup"><span data-stu-id="3818e-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="3818e-108">他の実装と同様[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]、作成することができます[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]2 つの異なる形式でのクエリ: クエリ式の構文とメソッド ベースのクエリ構文。</span><span class="sxs-lookup"><span data-stu-id="3818e-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="3818e-109">クエリ式の構文またはメソッド ベースのクエリ構文を使用して、<xref:System.Data.DataSet> 内の単一テーブル、<xref:System.Data.DataSet> 内の複数テーブル、または、型指定された <xref:System.Data.DataSet> 内のテーブルを対象にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3818e-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3818e-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3818e-110">In This Section</span></span>  
 [<span data-ttu-id="3818e-111">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="3818e-111">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="3818e-112">単一テーブルのクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3818e-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="3818e-113">複数テーブルにまたがるクエリ</span><span class="sxs-lookup"><span data-stu-id="3818e-113">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="3818e-114">複数テーブルにまたがるクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3818e-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="3818e-115">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="3818e-115">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 <span data-ttu-id="3818e-116">型指定された <xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3818e-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3818e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3818e-117">See also</span></span>

- [<span data-ttu-id="3818e-118">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="3818e-118">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="3818e-119">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="3818e-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
