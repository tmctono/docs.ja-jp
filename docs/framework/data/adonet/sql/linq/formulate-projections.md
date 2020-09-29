---
title: 射影の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194402"
---
# <a name="formulate-projections"></a><span data-ttu-id="07322-102">射影の作成</span><span class="sxs-lookup"><span data-stu-id="07322-102">Formulate Projections</span></span>

<span data-ttu-id="07322-103">以下の例では、C# の `select` ステートメントおよび Visual Basic の `Select` ステートメントを他の機能と組み合わせて、クエリの射影を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="07322-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07322-104">例</span><span class="sxs-lookup"><span data-stu-id="07322-104">Example</span></span>  

 <span data-ttu-id="07322-105">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) を使用して、`Customers` の連絡先の名前のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="07322-106">例</span><span class="sxs-lookup"><span data-stu-id="07322-106">Example</span></span>  

 <span data-ttu-id="07322-107">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*匿名型*" を使用して、`Customers` の連絡先名と電話番号のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="07322-108">例</span><span class="sxs-lookup"><span data-stu-id="07322-108">Example</span></span>  

 <span data-ttu-id="07322-109">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*匿名型*" を使用して、従業員の名前と電話番号のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="07322-110">結果のシーケンスでは、`FirstName` フィールドと `LastName` フィールドは 1 つのフィールド (`Name`) に結合され、`HomePhone` フィールドは `Phone` という名前に変更されます。</span><span class="sxs-lookup"><span data-stu-id="07322-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="07322-111">例</span><span class="sxs-lookup"><span data-stu-id="07322-111">Example</span></span>  

 <span data-ttu-id="07322-112">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*匿名型*" を使用して、すべての `ProductID` および `HalfPrice` という名前の計算値のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="07322-113">この値は、`UnitPrice` を 2 で割った値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="07322-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="07322-114">例</span><span class="sxs-lookup"><span data-stu-id="07322-114">Example</span></span>  

 <span data-ttu-id="07322-115">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*条件付きステートメント*" を使用して、製品名と製品の購入可能性のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="07322-116">例</span><span class="sxs-lookup"><span data-stu-id="07322-116">Example</span></span>  

 <span data-ttu-id="07322-117">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*既知の型*" (Name) を使用して、従業員の名前のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="07322-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="07322-118">例</span><span class="sxs-lookup"><span data-stu-id="07322-118">Example</span></span>  

 <span data-ttu-id="07322-119">次の例では、Visual Basic の `Select` と `Where` (C# では `select` と `where`) を使用して、London の顧客の連絡先の名前の、"*フィルター処理されたシーケンス*" を返します。</span><span class="sxs-lookup"><span data-stu-id="07322-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="07322-120">例</span><span class="sxs-lookup"><span data-stu-id="07322-120">Example</span></span>  

 <span data-ttu-id="07322-121">次の例では、Visual Basic の `Select` 句 (C# では `select` 句) と "*匿名型*" を使用して、顧客に関するデータの "*成型されたサブセット*" を返します。</span><span class="sxs-lookup"><span data-stu-id="07322-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="07322-122">例</span><span class="sxs-lookup"><span data-stu-id="07322-122">Example</span></span>  

 <span data-ttu-id="07322-123">次の例では、入れ子になったクエリを使用して以下の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="07322-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="07322-124">すべての注文および対応する `OrderID` のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="07322-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="07322-125">注文内で割引のある項目から成るサブシーケンス。</span><span class="sxs-lookup"><span data-stu-id="07322-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="07322-126">出荷コストが含まれない場合に節約される費用。</span><span class="sxs-lookup"><span data-stu-id="07322-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="07322-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="07322-127">See also</span></span>

- [<span data-ttu-id="07322-128">クエリの例</span><span class="sxs-lookup"><span data-stu-id="07322-128">Query Examples</span></span>](query-examples.md)
