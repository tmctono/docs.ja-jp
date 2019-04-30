---
title: ローカル型の推論 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: e6214938262b987a1bae4a9ca1d5c945f8b7fe6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052587"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="5325a-102">ローカル型の推論 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5325a-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="5325a-103">Visual Basic コンパイラを使用して*型推論*なしで宣言されたローカル変数のデータの種類を決定する、`As`句。</span><span class="sxs-lookup"><span data-stu-id="5325a-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="5325a-104">コンパイラでは、初期化式の型から変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="5325a-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="5325a-105">これにより、次の例に示すように、型を明示的に指定せず変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="5325a-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="5325a-106">宣言では、結果として両方`num1`と`num2`整数として厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="5325a-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  <span data-ttu-id="5325a-107">たくない場合`num2`として型指定するのには、前の例で、`Integer`のような宣言を使用して別の型を指定することができます`Dim num3 As Object = 3`または`Dim num4 As Double = 3`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5325a-108">型の推論は、非静的ローカル変数に対してのみ使用できます。これは、クラスのフィールド、プロパティ、または関数の種類の決定に使用できません。</span><span class="sxs-lookup"><span data-stu-id="5325a-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="5325a-109">ローカル型推論は、プロシージャ レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="5325a-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="5325a-110">(クラス、構造体、モジュール、またはインターフェイス内では、プロシージャまたはブロック内ではなく)、モジュール レベルで変数の宣言には使用できません。</span><span class="sxs-lookup"><span data-stu-id="5325a-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="5325a-111">場合`num2`前の例では、プロシージャでローカル変数の代わりに、クラスのフィールドは、宣言でエラーが発生すると`Option Strict`、および分類は`num2`として、`Object`で`Option Strict`オフします。</span><span class="sxs-lookup"><span data-stu-id="5325a-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="5325a-112">同様に、ローカル型推論に該当するプロシージャ レベルの変数として宣言されている`Static`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="5325a-113">型の推論と遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="5325a-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="5325a-114">コードでは、推論をタイプには、遅延バインディングに依存するコードに似ています。</span><span class="sxs-lookup"><span data-stu-id="5325a-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="5325a-115">ただし、型の推論型を厳密としてそのままではなく変数`Object`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="5325a-116">コンパイラでは、変数の初期化子を使用して、事前バインディングされたコードを生成するために、コンパイル時に、変数の型を調べます。</span><span class="sxs-lookup"><span data-stu-id="5325a-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="5325a-117">前の例では、`num2`と同様に、 `num1`、として型指定された、`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="5325a-118">事前バインディングされた変数の動作は、遅延バインディングされた変数は、対象の実行時にのみ、型が不明の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5325a-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="5325a-119">種類を事前に知ることにより、実行する前に問題を特定、正確には、メモリの割り当てし、その他の最適化を実行するコンパイラ。</span><span class="sxs-lookup"><span data-stu-id="5325a-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="5325a-120">事前バインディングは、Visual Basic の統合開発環境 (IDE) のオブジェクトのメンバーについて IntelliSense のヘルプを提供するようにできます。</span><span class="sxs-lookup"><span data-stu-id="5325a-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="5325a-121">事前バインディングは、パフォーマンスの推奨もあります。</span><span class="sxs-lookup"><span data-stu-id="5325a-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="5325a-122">これは、遅延バインディングされた変数に格納されているすべてのデータを型としてラップする必要があるため`Object`、低速のプログラムは、実行時に、型のメンバーにアクセスするとします。</span><span class="sxs-lookup"><span data-stu-id="5325a-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5325a-123">使用例</span><span class="sxs-lookup"><span data-stu-id="5325a-123">Examples</span></span>  
 <span data-ttu-id="5325a-124">型の推定が発生せず、ローカル変数が宣言されている場合、`As`句と初期化します。</span><span class="sxs-lookup"><span data-stu-id="5325a-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="5325a-125">コンパイラは、変数の型として割り当てられた初期値の型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5325a-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="5325a-126">たとえば、型の変数を宣言次のコード行の各`String`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 <span data-ttu-id="5325a-127">次のコードでは、整数の配列を作成する 2 つの同等の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5325a-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 <span data-ttu-id="5325a-128">ループ コントロール変数の種類を決定する型の推定を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="5325a-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="5325a-129">次のコードでコンパイラが推論される`number`は、`Integer`ため`someNumbers2`前の例は、整数の配列。</span><span class="sxs-lookup"><span data-stu-id="5325a-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 <span data-ttu-id="5325a-130">ローカル型推論を使用できる`Using`ステートメントを次の例に示すように、リソースの名前の型を確立します。</span><span class="sxs-lookup"><span data-stu-id="5325a-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 <span data-ttu-id="5325a-131">次の例に示すように、変数の型を関数の戻り値から推論もできます。</span><span class="sxs-lookup"><span data-stu-id="5325a-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="5325a-132">両方`pList1`と`pList2`プロセスの配列であるため、`Process.GetProcesses`プロセスの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="5325a-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a><span data-ttu-id="5325a-133">Option Infer します。</span><span class="sxs-lookup"><span data-stu-id="5325a-133">Option Infer</span></span>  
 <span data-ttu-id="5325a-134">`Option Infer` ローカル型推論が、特定のファイルで許可されているかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5325a-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="5325a-135">有効または、オプションをブロックするファイルの先頭に次のステートメントのいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="5325a-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="5325a-136">値を指定しない場合`Option Infer`コンパイラの既定値は、コードで、`Option Infer On`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="5325a-137">アップグレードされたプロジェクトの[!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)]コンパイラの既定値は、前に、または`Option Infer Off`します。</span><span class="sxs-lookup"><span data-stu-id="5325a-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="5325a-138">ファイルの `Option Infer` に設定した値が IDE またはコマンド ラインに設定した値と競合した場合は、ファイルの値が優先されます。</span><span class="sxs-lookup"><span data-stu-id="5325a-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="5325a-139">詳細については、次を参照してください。 [Option Infer ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)と[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)します。</span><span class="sxs-lookup"><span data-stu-id="5325a-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5325a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="5325a-140">See also</span></span>

- [<span data-ttu-id="5325a-141">匿名型</span><span class="sxs-lookup"><span data-stu-id="5325a-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="5325a-142">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="5325a-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="5325a-143">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="5325a-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5325a-144">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="5325a-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5325a-145">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="5325a-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="5325a-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="5325a-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="5325a-147">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5325a-147">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
