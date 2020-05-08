---
title: LINQ to DataSet の例
ms.date: 03/30/2017
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
ms.openlocfilehash: 68d4ed74713858a643c6db40b6982ba2775dbfa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783755"
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="85769-102">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="85769-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="85769-103">このセクションでは、標準クエリ演算子を使用する LINQ to DataSet プログラミングの例を示します。</span><span class="sxs-lookup"><span data-stu-id="85769-103">This section provides LINQ to DataSet programming examples that use the standard query operators.</span></span> <span data-ttu-id="85769-104">これらの例で使用されている <xref:System.Data.DataSet> は、`FillDataSet` メソッド (「[DataSet へのデータの読み込み](loading-data-into-a-dataset.md)」を参照) を使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="85769-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="85769-105">詳しくは、「[標準クエリ演算子の概要 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)」または「[標準クエリ演算子の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85769-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85769-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="85769-106">In This Section</span></span>  
 [<span data-ttu-id="85769-107">クエリ式の例</span><span class="sxs-lookup"><span data-stu-id="85769-107">Query Expression Examples</span></span>](query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="85769-108">次の例があります。</span><span class="sxs-lookup"><span data-stu-id="85769-108">Contains the following examples:</span></span>  
  
- [<span data-ttu-id="85769-109">射影</span><span class="sxs-lookup"><span data-stu-id="85769-109">Projection</span></span>](query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
- [<span data-ttu-id="85769-110">制限</span><span class="sxs-lookup"><span data-stu-id="85769-110">Restriction</span></span>](query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
- [<span data-ttu-id="85769-111">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="85769-111">Partitioning</span></span>](query-expression-syntax-examples-partitioning.md)  
  
- [<span data-ttu-id="85769-112">順序付け</span><span class="sxs-lookup"><span data-stu-id="85769-112">Ordering</span></span>](query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
- [<span data-ttu-id="85769-113">要素演算子</span><span class="sxs-lookup"><span data-stu-id="85769-113">Element Operators</span></span>](query-expression-syntax-examples-element-operators.md)  
  
- [<span data-ttu-id="85769-114">集計演算子</span><span class="sxs-lookup"><span data-stu-id="85769-114">Aggregate Operators</span></span>](query-expression-syntax-examples-aggregate-operators.md)  
  
- [<span data-ttu-id="85769-115">結合演算子</span><span class="sxs-lookup"><span data-stu-id="85769-115">Join Operators</span></span>](query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="85769-116">メソッド ベースのクエリ例</span><span class="sxs-lookup"><span data-stu-id="85769-116">Method-Based Query Examples</span></span>](method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="85769-117">次の例があります。</span><span class="sxs-lookup"><span data-stu-id="85769-117">Contains the following examples:</span></span>  
  
- [<span data-ttu-id="85769-118">射影</span><span class="sxs-lookup"><span data-stu-id="85769-118">Projection</span></span>](method-based-query-syntax-examples-projection.md)  
  
- [<span data-ttu-id="85769-119">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="85769-119">Partitioning</span></span>](method-based-query-syntax-examples-partitioning-linq.md)  
  
- [<span data-ttu-id="85769-120">順序付け</span><span class="sxs-lookup"><span data-stu-id="85769-120">Ordering</span></span>](method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
- [<span data-ttu-id="85769-121">集合演算子</span><span class="sxs-lookup"><span data-stu-id="85769-121">Set Operators</span></span>](method-based-query-syntax-examples-set-operators.md)  
  
- [<span data-ttu-id="85769-122">変換演算子</span><span class="sxs-lookup"><span data-stu-id="85769-122">Conversion Operators</span></span>](method-based-query-syntax-examples-conversion-operators.md)  
  
- [<span data-ttu-id="85769-123">要素演算子</span><span class="sxs-lookup"><span data-stu-id="85769-123">Element Operators</span></span>](method-based-query-syntax-examples-element-operators.md)  
  
- [<span data-ttu-id="85769-124">集計演算子</span><span class="sxs-lookup"><span data-stu-id="85769-124">Aggregate Operators</span></span>](method-based-query-syntax-examples-aggregate-operators.md)  
  
- [<span data-ttu-id="85769-125">Join</span><span class="sxs-lookup"><span data-stu-id="85769-125">Join</span></span>](method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="85769-126">DataSet 固有の演算子の例</span><span class="sxs-lookup"><span data-stu-id="85769-126">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="85769-127"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドおよび <xref:System.Data.DataRowComparer> クラスの使用例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="85769-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85769-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="85769-128">See also</span></span>

- [<span data-ttu-id="85769-129">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="85769-129">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
- [<span data-ttu-id="85769-130">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="85769-130">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
