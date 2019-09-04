---
title: 部分メソッドによるビジネス ロジックの追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 251d7a05971ff7940f85ec9d555d26f2e57067c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248137"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="eecea-102">部分メソッドによるビジネス ロジックの追加</span><span class="sxs-lookup"><span data-stu-id="eecea-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="eecea-103">*部分メソッド*を使用しC#て、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]プロジェクト内の Visual Basic および生成されたコードをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="eecea-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="eecea-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] から生成されるコードでは、シグネチャが部分メソッドの一部として定義されています。</span><span class="sxs-lookup"><span data-stu-id="eecea-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="eecea-105">このメソッドを実装する場合に、独自の部分メソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="eecea-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="eecea-106">独自の実装を追加しない場合は、コンパイラで部分メソッドのシグネチャが破棄され、既定のメソッドが [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eecea-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eecea-107">Visual Studio を使用している場合は、オブジェクトリレーショナルデザイナーを使用して、検証やその他のカスタマイズをエンティティクラスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="eecea-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="eecea-108">たとえば、Northwind サンプル データベースの `Customer` クラスに対する既定の対応付けには次の部分メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eecea-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="eecea-109">次のようなコードを独自の部分 `Customer` クラスに追加することで、独自のメソッドを実装できます。</span><span class="sxs-lookup"><span data-stu-id="eecea-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="eecea-110">この方法は、通常、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 、、 `Delete`、およびの`Insert`既定`Update`のメソッドをオーバーライドして、オブジェクトのライフサイクルイベント時にプロパティを検証するために、で使用されます。</span><span class="sxs-lookup"><span data-stu-id="eecea-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="eecea-111">詳細については、「[部分メソッド](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)(Visual Basic)」または「 [partial (メソッド) (C#参照)](../../../../../csharp/language-reference/keywords/partial-method.md) 」 (C#) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eecea-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eecea-112">例</span><span class="sxs-lookup"><span data-stu-id="eecea-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="eecea-113">説明</span><span class="sxs-lookup"><span data-stu-id="eecea-113">Description</span></span>  
 <span data-ttu-id="eecea-114">次の例では、SQLMetal などのコード生成ツールによって定義される `ExampleClass` を最初に示し、次に 2 つのメソッドの 1 つだけを実装できることを示します。</span><span class="sxs-lookup"><span data-stu-id="eecea-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="eecea-115">コード</span><span class="sxs-lookup"><span data-stu-id="eecea-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="eecea-116">例</span><span class="sxs-lookup"><span data-stu-id="eecea-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="eecea-117">説明</span><span class="sxs-lookup"><span data-stu-id="eecea-117">Description</span></span>  
 <span data-ttu-id="eecea-118">次の例では、`Shipper` エンティティと `Order` エンティティのリレーションシップを使用します。</span><span class="sxs-lookup"><span data-stu-id="eecea-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="eecea-119">メソッドには部分メソッドの `InsertShipper` と `DeleteShipper` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eecea-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="eecea-120">これらのメソッドは、マッピングによって[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]提供される既定の部分メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="eecea-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="eecea-121">コード</span><span class="sxs-lookup"><span data-stu-id="eecea-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eecea-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="eecea-122">See also</span></span>

- [<span data-ttu-id="eecea-123">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="eecea-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="eecea-124">挿入、更新、および削除の各操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="eecea-124">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
