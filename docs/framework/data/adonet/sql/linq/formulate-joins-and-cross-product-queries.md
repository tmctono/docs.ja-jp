---
title: 結合およびクロス積クエリの作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 002a644ff5d48b25351228dcd74330707491d6c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782096"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="ea53c-102">結合およびクロス積クエリの作成</span><span class="sxs-lookup"><span data-stu-id="ea53c-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="ea53c-103">次の例は、複数のテーブルからの結果を組み合わせる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea53c-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea53c-104">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-104">Example</span></span>  
 <span data-ttu-id="ea53c-105">次の例では、Visual Basic ( `From` `from`のC#句) の句で外部キーナビゲーションを使用して、ロンドンの顧客のすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-106">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-106">Example</span></span>  
 <span data-ttu-id="ea53c-107">次の例`Where`で`Supplier`は、Visual Basic (`where`のC#句) の句で外部キーナビゲーションを使用して、米国内`Products`にがある在庫切れをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-108">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-108">Example</span></span>  
 <span data-ttu-id="ea53c-109">次の例では、Visual Basic ( `From` `from`のC#句) の句で外部キーナビゲーションを使用して、シアトルの従業員をフィルター処理し、その担当区域を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-110">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-110">Example</span></span>  
 <span data-ttu-id="ea53c-111">次の例で`Select`は、句で外部キーナビゲーションを使用して、Visual Basic (`select`のC#句) では、1人の従業員が別の従業員を報告し、両方`City`の従業員が同じである従業員のペアをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-112">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-112">Example</span></span>  
 <span data-ttu-id="ea53c-113">次の Visual Basic 例では、すべての顧客と注文を検索し、注文が顧客と一致していることを確認し、そのリスト内のすべての顧客に対して連絡先名が提供されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-114">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-114">Example</span></span>  
 <span data-ttu-id="ea53c-115">次の例は、2 つのテーブルを明示的に結合し、両方のテーブルからの結果を投影します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-116">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-116">Example</span></span>  
 <span data-ttu-id="ea53c-117">次の例は、3 つのテーブルを明示的に結合し、各テーブルからの結果を投影します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-118">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-118">Example</span></span>  
 <span data-ttu-id="ea53c-119">次の例は、`LEFT OUTER JOIN` を使用して、`DefaultIfEmpty()` を実現する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea53c-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="ea53c-120">`DefaultIfEmpty()` に `Order` がない場合は、`Employee` メソッドから null が返されます。</span><span class="sxs-lookup"><span data-stu-id="ea53c-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-121">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-121">Example</span></span>  
 <span data-ttu-id="ea53c-122">次の例は、結合の結果の `let` 式を投影します。</span><span class="sxs-lookup"><span data-stu-id="ea53c-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-123">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-123">Example</span></span>  
 <span data-ttu-id="ea53c-124">次の例は、複合キーを使用する `join` を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea53c-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="ea53c-125">例</span><span class="sxs-lookup"><span data-stu-id="ea53c-125">Example</span></span>  
 <span data-ttu-id="ea53c-126">次の例は、一方が null 許容で他方がそうでない `join` の作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea53c-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="ea53c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea53c-127">See also</span></span>

- [<span data-ttu-id="ea53c-128">クエリの例</span><span class="sxs-lookup"><span data-stu-id="ea53c-128">Query Examples</span></span>](query-examples.md)
