---
title: DataSet のクエリ (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634782"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="03ce2-102">DataSet のクエリ (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="03ce2-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="03ce2-103"><xref:System.Data.DataSet> オブジェクトへのデータの読み込みが完了すると、そのデータセットに対してクエリを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="03ce2-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="03ce2-104">LINQ to DataSet でクエリを設定することは、他の LINQ 対応データソースに対して統合言語クエリ (LINQ) を使用することと似ています。</span><span class="sxs-lookup"><span data-stu-id="03ce2-104">Formulating queries with LINQ to DataSet is similar to using Language-Integrated Query (LINQ) against other LINQ-enabled data sources.</span></span> <span data-ttu-id="03ce2-105">ただし、<xref:System.Data.DataSet> オブジェクトに対して LINQ クエリを使用する場合は、カスタム型の列挙型ではなく、<xref:System.Data.DataRow> オブジェクトの列挙体に対してクエリを実行していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="03ce2-105">Remember, however, that when you use LINQ queries over a <xref:System.Data.DataSet> object, you're querying an enumeration of <xref:System.Data.DataRow> objects instead of an enumeration of a custom type.</span></span> <span data-ttu-id="03ce2-106">これは、LINQ クエリで <xref:System.Data.DataRow> クラスの任意のメンバーを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="03ce2-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your LINQ queries.</span></span> <span data-ttu-id="03ce2-107">これにより、高度で複雑なクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="03ce2-107">This lets you create rich, complex queries.</span></span>  
  
 <span data-ttu-id="03ce2-108">LINQ の他の実装と同様に、クエリ式の構文とメソッドベースのクエリ構文という2つの異なる形式で LINQ to DataSet のクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="03ce2-108">As with other implementations of LINQ, you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="03ce2-109">クエリ式の構文またはメソッド ベースのクエリ構文を使用して、<xref:System.Data.DataSet> 内の単一テーブル、<xref:System.Data.DataSet> 内の複数テーブル、または、型指定された <xref:System.Data.DataSet> 内のテーブルを対象にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="03ce2-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03ce2-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03ce2-110">In This Section</span></span>  
 [<span data-ttu-id="03ce2-111">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="03ce2-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="03ce2-112">単一テーブルのクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03ce2-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="03ce2-113">複数テーブルにまたがるクエリ</span><span class="sxs-lookup"><span data-stu-id="03ce2-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="03ce2-114">複数テーブルにまたがるクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03ce2-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="03ce2-115">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="03ce2-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="03ce2-116">型指定された <xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03ce2-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ce2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="03ce2-117">See also</span></span>

- [<span data-ttu-id="03ce2-118">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="03ce2-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="03ce2-119">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="03ce2-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
