---
title: 射影の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: e1f7a7da1ab2ce0ad7d7908ecd1f896d229b8e1a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223304"
---
# <a name="formulate-projections"></a><span data-ttu-id="ed50e-102">射影の作成</span><span class="sxs-lookup"><span data-stu-id="ed50e-102">Formulate Projections</span></span>
<span data-ttu-id="ed50e-103">次の例に示す方法、`select`ステートメントC#と`Select`Visual Basic でのステートメントは、クエリ射影を作成するには、その他の機能と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="ed50e-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed50e-104">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-104">Example</span></span>  
 <span data-ttu-id="ed50e-105">次の例では、 `Select` Visual Basic での句 (`select`句C#) 連絡先の名前のシーケンスを返します`Customers`します。</span><span class="sxs-lookup"><span data-stu-id="ed50e-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-106">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-106">Example</span></span>  
 <span data-ttu-id="ed50e-107">次の例では、 `Select` Visual Basic での句 (`select`句C#) と*匿名型*に連絡先の名前のシーケンスを返すし、電話番号の`Customers`します。</span><span class="sxs-lookup"><span data-stu-id="ed50e-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-108">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-108">Example</span></span>  
 <span data-ttu-id="ed50e-109">次の例では、 `Select` Visual Basic での句 (`select`句C#) と*匿名型*名前のシーケンスを返すし、従業員の電話番号にします。</span><span class="sxs-lookup"><span data-stu-id="ed50e-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="ed50e-110">`FirstName`と`LastName`フィールドが 1 つのフィールドに結合されます (`Name`)、および`HomePhone`フィールドの名前を変更する`Phone`結果のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="ed50e-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-111">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-111">Example</span></span>  
 <span data-ttu-id="ed50e-112">次の例では、 `Select` Visual Basic での句 (`select`句C#) と*匿名型*すべてのシーケンスを返します`ProductID`という名前の計算値と`HalfPrice`します。</span><span class="sxs-lookup"><span data-stu-id="ed50e-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="ed50e-113">この値は、`UnitPrice` を 2 で割った値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ed50e-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-114">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-114">Example</span></span>  
 <span data-ttu-id="ed50e-115">次の例では、 `Select` Visual Basic での句 (`select`句C#) と*条件付きステートメント*製品名および製品の可用性のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="ed50e-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-116">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-116">Example</span></span>  
 <span data-ttu-id="ed50e-117">次のコードの例では、Visual Basic`Select`句 (`select`句C#) と*既知の型*従業員の名前のシーケンスを返します (名前)。</span><span class="sxs-lookup"><span data-stu-id="ed50e-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-118">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-118">Example</span></span>  
 <span data-ttu-id="ed50e-119">次の例では使用`Select`と`Where`Visual basic (`select`と`where`でC#) を返す、*フィルター処理されたシーケンス*ロンドン在住の顧客の連絡先の名の。</span><span class="sxs-lookup"><span data-stu-id="ed50e-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-120">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-120">Example</span></span>  
 <span data-ttu-id="ed50e-121">次の例では、 `Select` Visual Basic での句 (`select`句C#) と*匿名型*を返す、*成型されたサブセット*の顧客に関するデータ。</span><span class="sxs-lookup"><span data-stu-id="ed50e-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="ed50e-122">例</span><span class="sxs-lookup"><span data-stu-id="ed50e-122">Example</span></span>  
 <span data-ttu-id="ed50e-123">次の例では、入れ子になったクエリを使用して以下の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="ed50e-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="ed50e-124">すべての注文および対応する `OrderID` のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="ed50e-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="ed50e-125">注文内で割引のある項目から成るサブシーケンス。</span><span class="sxs-lookup"><span data-stu-id="ed50e-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="ed50e-126">出荷コストが含まれない場合に節約される費用。</span><span class="sxs-lookup"><span data-stu-id="ed50e-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="ed50e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed50e-127">See also</span></span>

- [<span data-ttu-id="ed50e-128">クエリの例</span><span class="sxs-lookup"><span data-stu-id="ed50e-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
