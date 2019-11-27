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
ms.openlocfilehash: 7abf0565a985f1fb44fcf2bb91b9220d57a10f20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352636"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="2a998-102">部分メソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a998-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="2a998-103">部分メソッドを使用すると、開発者はカスタムロジックをコードに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="2a998-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="2a998-104">通常、このコードはデザイナーによって生成されるクラスの一部です。</span><span class="sxs-lookup"><span data-stu-id="2a998-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="2a998-105">部分メソッドは、コードジェネレーターによって作成される部分クラスで定義され、通常は、何らかの変更が行われたことを通知するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="2a998-106">これにより、開発者は、変更に応じてカスタム動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a998-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="2a998-107">コードジェネレーターのデザイナーは、メソッドシグネチャと、メソッドの1つ以上の呼び出しのみを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a998-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="2a998-108">開発者は、生成されたコードの動作をカスタマイズする場合に、メソッドの実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="2a998-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="2a998-109">実装が指定されていない場合、メソッドの呼び出しはコンパイラによって削除され、その結果、追加のパフォーマンスオーバーヘッドが発生しません。</span><span class="sxs-lookup"><span data-stu-id="2a998-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="2a998-110">宣言</span><span class="sxs-lookup"><span data-stu-id="2a998-110">Declaration</span></span>  
 <span data-ttu-id="2a998-111">生成されたコードは、署名行の先頭に `Partial` キーワードを配置することで、部分メソッドの定義をマークします。</span><span class="sxs-lookup"><span data-stu-id="2a998-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="2a998-112">定義は、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a998-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="2a998-113">メソッドは、`Function`ではなく、`Sub`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a998-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="2a998-114">メソッドの本体は空のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a998-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="2a998-115">アクセス修飾子は `Private`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a998-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="2a998-116">実装</span><span class="sxs-lookup"><span data-stu-id="2a998-116">Implementation</span></span>  
 <span data-ttu-id="2a998-117">実装は、主に部分メソッドの本体を埋めることによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="2a998-118">実装は、通常、定義とは別の部分クラスにあり、生成されたコードを拡張する開発者によって記述されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="2a998-119">前の例では、宣言のシグネチャを正確に複製しますが、バリエーションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a998-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="2a998-120">特に、`Overloads` や `Overrides`などの他の修飾子を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a998-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="2a998-121">1つの `Overrides` 修飾子のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="2a998-122">メソッド修飾子の詳細については、「 [Sub ステートメント](../../../../visual-basic/language-reference/statements/sub-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a998-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="2a998-123">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="2a998-123">Use</span></span>  
 <span data-ttu-id="2a998-124">部分メソッドは、他の `Sub` プロシージャと同じように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2a998-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="2a998-125">メソッドが実装されている場合は、引数が評価され、メソッドの本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="2a998-126">ただし、部分メソッドの実装は省略可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a998-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="2a998-127">メソッドが実装されていない場合、その呼び出しは無効であり、メソッドに引数として渡された式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="2a998-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a998-128">例</span><span class="sxs-lookup"><span data-stu-id="2a998-128">Example</span></span>  
 <span data-ttu-id="2a998-129">.Vb という名前のファイルで、`Quantity` プロパティを持つ `Product` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a998-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="2a998-130">Product .vb という名前のファイルに、`QuantityChanged`の実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a998-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="2a998-131">最後に、プロジェクトの Main メソッドで、`Product` インスタンスを宣言し、その `Quantity` プロパティの初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a998-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="2a998-132">メッセージボックスが表示され、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a998-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="2a998-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a998-133">See also</span></span>

- [<span data-ttu-id="2a998-134">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="2a998-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2a998-135">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="2a998-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="2a998-136">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="2a998-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="2a998-137">Partial</span><span class="sxs-lookup"><span data-stu-id="2a998-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="2a998-138">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="2a998-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="2a998-139">部分メソッドによるビジネス ロジックの追加</span><span class="sxs-lookup"><span data-stu-id="2a998-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
