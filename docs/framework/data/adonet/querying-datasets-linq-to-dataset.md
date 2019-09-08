---
title: DataSet のクエリ (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783052"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="aea04-102">DataSet のクエリ (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="aea04-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="aea04-103"><xref:System.Data.DataSet> オブジェクトへのデータの読み込みが完了すると、そのデータセットに対してクエリを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="aea04-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="aea04-104">LINQ to DataSet を使用したクエリの設定[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]は、 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]他の対応データソースに対してを使用する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="aea04-104">Formulating queries with LINQ to DataSet is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="aea04-105">ただし、オブジェクトに[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] <xref:System.Data.DataSet>対してクエリを使用する場合は、カスタム型の列挙型<xref:System.Data.DataRow>ではなく、オブジェクトの列挙型にクエリを実行することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="aea04-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="aea04-106">これは、 <xref:System.Data.DataRow> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]クエリでクラスの任意のメンバーを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="aea04-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="aea04-107">これにより、高度で複雑なクエリの作成が可能となります。</span><span class="sxs-lookup"><span data-stu-id="aea04-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="aea04-108">の他の実装と[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]同様に、クエリ式の構文とメソッドベースのクエリ構文という2つの異なる形式で LINQ to DataSet のクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aea04-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="aea04-109">クエリ式の構文またはメソッド ベースのクエリ構文を使用して、<xref:System.Data.DataSet> 内の単一テーブル、<xref:System.Data.DataSet> 内の複数テーブル、または、型指定された <xref:System.Data.DataSet> 内のテーブルを対象にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="aea04-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aea04-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aea04-110">In This Section</span></span>  
 [<span data-ttu-id="aea04-111">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="aea04-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="aea04-112">単一テーブルのクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea04-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="aea04-113">複数テーブルにまたがるクエリ</span><span class="sxs-lookup"><span data-stu-id="aea04-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="aea04-114">複数テーブルにまたがるクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea04-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="aea04-115">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="aea04-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="aea04-116">型指定された <xref:System.Data.DataSet> オブジェクトに対してクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea04-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea04-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="aea04-117">See also</span></span>

- [<span data-ttu-id="aea04-118">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="aea04-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="aea04-119">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="aea04-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
