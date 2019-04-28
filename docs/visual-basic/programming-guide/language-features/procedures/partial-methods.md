---
title: 部分メソッド (Visual Basic)
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
ms.openlocfilehash: 765a667f18340c53909c3ff1e9fcc5f2ffc0f9bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791938"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="4034e-102">部分メソッド (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4034e-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="4034e-103">部分メソッドには、カスタム ロジックをコードに挿入する開発者が有効にします。</span><span class="sxs-lookup"><span data-stu-id="4034e-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="4034e-104">通常、コードには、デザイナーで生成されたクラスの一部です。</span><span class="sxs-lookup"><span data-stu-id="4034e-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="4034e-105">部分メソッドは、コード ジェネレーターによって作成される部分クラスで定義され、何かが変更されたことを通知によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="4034e-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="4034e-106">これらの変更に対応するカスタム動作を指定する、開発者が有効にします。</span><span class="sxs-lookup"><span data-stu-id="4034e-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="4034e-107">コード ジェネレーターのデザイナーは、メソッドのシグネチャとメソッドに対する 1 つまたは複数の呼び出しを定義します。</span><span class="sxs-lookup"><span data-stu-id="4034e-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="4034e-108">開発者、生成されたコードの動作をカスタマイズする場合、メソッドの実装を用意できます。</span><span class="sxs-lookup"><span data-stu-id="4034e-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="4034e-109">実装を指定しない場合、メソッドの呼び出しは追加のパフォーマンスのオーバーヘッドなしでその結果、コンパイラによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="4034e-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="4034e-110">宣言</span><span class="sxs-lookup"><span data-stu-id="4034e-110">Declaration</span></span>  
 <span data-ttu-id="4034e-111">キーワードを配置することで、生成されたコードは部分メソッドの定義をマーク`Partial`署名行の先頭。</span><span class="sxs-lookup"><span data-stu-id="4034e-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="4034e-112">定義には、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4034e-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="4034e-113">メソッドである必要があります、`Sub`ではなく、`Function`します。</span><span class="sxs-lookup"><span data-stu-id="4034e-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="4034e-114">メソッドの本体は空のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4034e-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="4034e-115">アクセス修飾子がある必要があります`Private`します。</span><span class="sxs-lookup"><span data-stu-id="4034e-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="4034e-116">実装</span><span class="sxs-lookup"><span data-stu-id="4034e-116">Implementation</span></span>  
 <span data-ttu-id="4034e-117">実装では、主に、部分メソッドの本文を入力します。</span><span class="sxs-lookup"><span data-stu-id="4034e-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="4034e-118">この実装は一般に、定義から別の部分クラスを生成されたコードを拡張する必要がある開発者によって書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4034e-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="4034e-119">前の例では、宣言内のシグネチャを正確には、重複するが、バリエーションが可能です。</span><span class="sxs-lookup"><span data-stu-id="4034e-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="4034e-120">具体的には、その他の修飾子を追加できるよう`Overloads`または`Overrides`します。</span><span class="sxs-lookup"><span data-stu-id="4034e-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="4034e-121">1 つだけ`Overrides`修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="4034e-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="4034e-122">メソッドの修飾子の詳細については、次を参照してください。 [Sub ステートメント](../../../../visual-basic/language-reference/statements/sub-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="4034e-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="4034e-123">使用</span><span class="sxs-lookup"><span data-stu-id="4034e-123">Use</span></span>  
 <span data-ttu-id="4034e-124">場合とその他の部分メソッドを呼び出す`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="4034e-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="4034e-125">メソッドが実装されている場合は、引数が評価され、メソッドの本体が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4034e-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="4034e-126">ただし、部分メソッドの実装は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4034e-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="4034e-127">メソッドが実装されていない場合は、それへの呼び出しが効果を持たず、メソッドに引数として渡される式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="4034e-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4034e-128">例</span><span class="sxs-lookup"><span data-stu-id="4034e-128">Example</span></span>  
 <span data-ttu-id="4034e-129">Product.Designer.vb という名前のファイル、定義、`Product`を持つクラス、`Quantity`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4034e-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="4034e-130">実装を提供 Product.vb という名前のファイル、`QuantityChanged`します。</span><span class="sxs-lookup"><span data-stu-id="4034e-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="4034e-131">最後に、プロジェクトの Main メソッドでは宣言を`Product`インスタンスし、指定の初期値をその`Quantity`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4034e-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="4034e-132">このメッセージを表示するメッセージ ボックスが表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4034e-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="4034e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4034e-133">See also</span></span>

- [<span data-ttu-id="4034e-134">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="4034e-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4034e-135">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4034e-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="4034e-136">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="4034e-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="4034e-137">Partial</span><span class="sxs-lookup"><span data-stu-id="4034e-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="4034e-138">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="4034e-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="4034e-139">部分メソッドによるビジネス ロジックの追加</span><span class="sxs-lookup"><span data-stu-id="4034e-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
