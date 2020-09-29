---
title: 一連の数値の中の最小値の検出
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 2ffff8b69839d5c1e70e81f9fc6f3a97f57ac6c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155979"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="67321-102">一連の数値の中の最小値の検出</span><span class="sxs-lookup"><span data-stu-id="67321-102">Find the Minimum Value in a Numeric Sequence</span></span>

<span data-ttu-id="67321-103">一連の数値の中から最小値を返すには、<xref:System.Linq.Enumerable.Min%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="67321-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67321-104">例</span><span class="sxs-lookup"><span data-stu-id="67321-104">Example</span></span>  

 <span data-ttu-id="67321-105">次の例では、製品の最低単価を見つけます。</span><span class="sxs-lookup"><span data-stu-id="67321-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="67321-106">Northwind サンプル データベースに対してこのクエリを実行した場合の出力は、`2.5000` です。</span><span class="sxs-lookup"><span data-stu-id="67321-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="67321-107">例</span><span class="sxs-lookup"><span data-stu-id="67321-107">Example</span></span>  

 <span data-ttu-id="67321-108">次の例では、注文の最低配送料を見つけます。</span><span class="sxs-lookup"><span data-stu-id="67321-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="67321-109">Northwind サンプル データベースに対してこのクエリを実行した場合の出力は、`0.0200` です。</span><span class="sxs-lookup"><span data-stu-id="67321-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="67321-110">例</span><span class="sxs-lookup"><span data-stu-id="67321-110">Example</span></span>  

 <span data-ttu-id="67321-111">次の例では、Min を使用して、各カテゴリ内で単価が最も安い `Products` を見つけます。</span><span class="sxs-lookup"><span data-stu-id="67321-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="67321-112">出力はカテゴリごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="67321-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="67321-113">Northwind サンプル データベースに対してこのクエリを実行すると、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="67321-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="67321-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="67321-114">See also</span></span>

- [<span data-ttu-id="67321-115">集計クエリ</span><span class="sxs-lookup"><span data-stu-id="67321-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="67321-116">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="67321-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
