---
title: 射影の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793820"
---
# <a name="formulate-projections"></a><span data-ttu-id="c4cc9-102">射影の作成</span><span class="sxs-lookup"><span data-stu-id="c4cc9-102">Formulate Projections</span></span>
<span data-ttu-id="c4cc9-103">次の例では、 `select` Visual Basic のC#ステートメント`Select`とステートメントを他の機能と組み合わせることによってクエリの射影を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4cc9-104">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-104">Example</span></span>  
 <span data-ttu-id="c4cc9-105">次の例では`Select` 、Visual Basic (`select`の句句C#) で句を使用して、の`Customers`一連の連絡先名を返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-106">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-106">Example</span></span>  
 <span data-ttu-id="c4cc9-107">次の例では`Select` 、句を使用`select`してC#Visual Basic (の句) と*匿名型*の一連の連絡先名と電話`Customers`番号を返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-108">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-108">Example</span></span>  
 <span data-ttu-id="c4cc9-109">次の例では`Select` 、句を使用`select`してC#Visual Basic (の句) と*匿名型*の一連の名前と電話番号を返します従業員です。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="c4cc9-110">`Phone` `Name` `HomePhone`フィールドとフィールドが1つのフィールド()に結合され、結果のシーケンスでフィールドの名前がに変更されます。`LastName` `FirstName`</span><span class="sxs-lookup"><span data-stu-id="c4cc9-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-111">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-111">Example</span></span>  
 <span data-ttu-id="c4cc9-112">次の例では`Select` 、句を使用`select`してC#Visual Basic (の句) と*匿名型*は、 `ProductID`すべてののシーケンスとと`HalfPrice`いう名前の計算された値を返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="c4cc9-113">この値は、`UnitPrice` を 2 で割った値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-114">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-114">Example</span></span>  
 <span data-ttu-id="c4cc9-115">次の例では`Select` 、句を使用`select`してC#Visual Basic (の句) と*条件付きステートメント*を使用して、製品名と製品の可用性のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-116">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-116">Example</span></span>  
 <span data-ttu-id="c4cc9-117">次の例では、 `Select` Visual Basic 句`select` (でC#は句) と*既知の型*(名前) を使用して、従業員の名前のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-118">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-118">Example</span></span>  
 <span data-ttu-id="c4cc9-119">次の例で`Select`は`Where` 、Visual Basic (`select`と`where` C#) のおよびを使用して、ロンドンの顧客の連絡先名の*フィルター処理*されたシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-120">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-120">Example</span></span>  
 <span data-ttu-id="c4cc9-121">次の例では`Select` 、句を使用`select`してC#Visual Basic (の句) と*匿名型*は、顧客に関するデータの整形された*サブセット*を返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="c4cc9-122">例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-122">Example</span></span>  
 <span data-ttu-id="c4cc9-123">次の例では、入れ子になったクエリを使用して以下の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="c4cc9-124">すべての注文および対応する `OrderID` のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="c4cc9-125">注文内で割引のある項目から成るサブシーケンス。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="c4cc9-126">出荷コストが含まれない場合に節約される費用。</span><span class="sxs-lookup"><span data-stu-id="c4cc9-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="c4cc9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4cc9-127">See also</span></span>

- [<span data-ttu-id="c4cc9-128">クエリの例</span><span class="sxs-lookup"><span data-stu-id="c4cc9-128">Query Examples</span></span>](query-examples.md)
