---
title: 部分メソッド
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: 61a1398ba7de8dab005fa1e9efa13dc2ba18cc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364124"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="4918f-102">部分メソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4918f-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="4918f-103">部分メソッドを使用すると、開発者はカスタム ロジックをコードに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="4918f-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="4918f-104">通常、このコードはデザイナーによって生成されるクラスの一部です。</span><span class="sxs-lookup"><span data-stu-id="4918f-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="4918f-105">部分メソッドは、コード ジェネレーターによって作成された部分クラスで定義され、何かが変更されたことを通知するためによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="4918f-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="4918f-106">部分メソッドにより、開発者は変更に対応するためのカスタム動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4918f-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="4918f-107">コード ジェネレーターのデザイナーは、メソッド シグネチャとメソッドの 1 つ以上の呼び出しのみを定義します。</span><span class="sxs-lookup"><span data-stu-id="4918f-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="4918f-108">開発者は、生成されたコードの動作をカスタマイズする場合にメソッドの実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="4918f-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="4918f-109">実装が提供されていない場合、メソッドの呼び出しはコンパイラによって削除されるため、パフォーマンスの追加のオーバーヘッドは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4918f-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="4918f-110">宣言</span><span class="sxs-lookup"><span data-stu-id="4918f-110">Declaration</span></span>  
 <span data-ttu-id="4918f-111">生成されたコードでは、シグネチャ行の先頭に `Partial` キーワードを配置することによって部分メソッドの定義をマークします。</span><span class="sxs-lookup"><span data-stu-id="4918f-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="4918f-112">定義は次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4918f-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="4918f-113">メソッドは `Function` ではなく、`Sub` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4918f-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="4918f-114">メソッドの本体は空のままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4918f-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="4918f-115">アクセス修飾子は `Private` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4918f-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="4918f-116">実装</span><span class="sxs-lookup"><span data-stu-id="4918f-116">Implementation</span></span>  
 <span data-ttu-id="4918f-117">実装は、部分メソッドの本体の入力で主に構成されます。</span><span class="sxs-lookup"><span data-stu-id="4918f-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="4918f-118">通常、実装は定義とは別の部分クラスにあり、生成されたコードを拡張する開発者が記述します。</span><span class="sxs-lookup"><span data-stu-id="4918f-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="4918f-119">上記の例では、宣言のシグネチャを正確に複製していますが、バリエーションが可能です。</span><span class="sxs-lookup"><span data-stu-id="4918f-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="4918f-120">具体的には、`Overloads` や `Overrides` などの他の修飾子を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4918f-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="4918f-121">`Overrides` 修飾子は 1 つだけ許可されます。</span><span class="sxs-lookup"><span data-stu-id="4918f-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="4918f-122">メソッド修飾子の詳細については、「[Sub Statement (Sub ステートメント)](../../../language-reference/statements/sub-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4918f-122">For more information about method modifiers, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="4918f-123">使用</span><span class="sxs-lookup"><span data-stu-id="4918f-123">Use</span></span>  
 <span data-ttu-id="4918f-124">他の `Sub` プロシージャを呼び出す場合と同様に、部分メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4918f-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="4918f-125">メソッドが実装されている場合、引数が評価され、メソッドの本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4918f-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="4918f-126">ただし、部分メソッドの実装は省略可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4918f-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="4918f-127">メソッドが実装されていない場合、その呼び出しは無効であり、メソッドに引数として渡された式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="4918f-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4918f-128">例</span><span class="sxs-lookup"><span data-stu-id="4918f-128">Example</span></span>  
 <span data-ttu-id="4918f-129">Product.Designer.vb という名前のファイルで、`Quantity` プロパティを持つ `Product` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="4918f-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="4918f-130">Product.vb という名前のファイルで、`QuantityChanged` の実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="4918f-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="4918f-131">最後に、プロジェクトの Main メソッドで、`Product`インスタンスを宣言し、その `Quantity` プロパティの初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4918f-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="4918f-132">次のメッセージが示されたメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4918f-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="4918f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4918f-133">See also</span></span>

- [<span data-ttu-id="4918f-134">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="4918f-134">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4918f-135">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4918f-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="4918f-136">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="4918f-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="4918f-137">Partial</span><span class="sxs-lookup"><span data-stu-id="4918f-137">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="4918f-138">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="4918f-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="4918f-139">部分メソッドによるビジネス ロジックの追加</span><span class="sxs-lookup"><span data-stu-id="4918f-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
