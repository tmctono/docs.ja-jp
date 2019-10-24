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
ms.openlocfilehash: 2b239e17ba7fa0b6a6b08d52f4394541eaa08b28
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775719"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="292a3-102">ローカル型の推論 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="292a3-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="292a3-103">Visual Basic コンパイラは、*型の推定*を使用して、`As` 句を使用せずに宣言されたローカル変数のデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="292a3-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="292a3-104">コンパイラは、初期化式の型から変数の型を推測します。</span><span class="sxs-lookup"><span data-stu-id="292a3-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="292a3-105">これにより、次の例に示すように、明示的に型を指定せずに変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="292a3-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="292a3-106">宣言の結果として、`num1` と `num2` の両方が整数として厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="292a3-107">前の例の `num2` を `Integer` として入力したくない場合は、`Dim num3 As Object = 3` や `Dim num4 As Double = 3` などの宣言を使用して別の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="292a3-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="292a3-108">型の推定は、非静的ローカル変数に対してのみ使用できます。クラスフィールド、プロパティ、または関数の型を判断するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="292a3-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="292a3-109">ローカル型の推論はプロシージャレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="292a3-110">モジュールレベルで変数を宣言するために使用することはできません (クラス、構造体、モジュール、またはインターフェイス内で、プロシージャまたはブロック内には含まれません)。</span><span class="sxs-lookup"><span data-stu-id="292a3-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="292a3-111">前の例の `num2` がプロシージャ内のローカル変数ではなくクラスのフィールドであった場合、宣言によって `Option Strict` でエラーが発生し、`num2` が `Option Strict` off の `Object` として分類されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="292a3-112">同様に、ローカル型の推定は、`Static` として宣言されたプロシージャレベルの変数には適用されません。</span><span class="sxs-lookup"><span data-stu-id="292a3-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="292a3-113">型推論と遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="292a3-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="292a3-114">型の推定を使用するコードは、遅延バインディングに依存するコードに似ています。</span><span class="sxs-lookup"><span data-stu-id="292a3-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="292a3-115">ただし、型の推定では、変数が `Object` として保持されるのではなく、厳密に型になります。</span><span class="sxs-lookup"><span data-stu-id="292a3-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="292a3-116">コンパイラは、コンパイル時に変数の初期化子を使用して、事前バインディングされたコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="292a3-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="292a3-117">前の例では、`num1` のように `num2` が `Integer` として型指定されています。</span><span class="sxs-lookup"><span data-stu-id="292a3-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="292a3-118">事前バインディングされた変数の動作は、遅延バインディングされた変数の動作とは異なり、型は実行時にのみ認識されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="292a3-119">型を早期に把握すると、コンパイラは実行前に問題を特定し、メモリを正確に割り当て、その他の最適化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="292a3-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="292a3-120">また、事前バインディングを使用すると、Visual Basic 統合開発環境 (IDE) で、オブジェクトのメンバーに関する IntelliSense のヘルプを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="292a3-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="292a3-121">事前バインディングは、パフォーマンスのためにも推奨されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="292a3-122">これは、遅延バインディング変数に格納されているすべてのデータが `Object` 型としてラップされる必要があり、実行時にその型のメンバーにアクセスするとプログラムの速度が低下するためです。</span><span class="sxs-lookup"><span data-stu-id="292a3-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="292a3-123">使用例</span><span class="sxs-lookup"><span data-stu-id="292a3-123">Examples</span></span>

<span data-ttu-id="292a3-124">型の推定は、ローカル変数が `As` 句なしで宣言されて初期化される場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="292a3-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="292a3-125">コンパイラは、割り当てられた初期値の型を変数の型として使用します。</span><span class="sxs-lookup"><span data-stu-id="292a3-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="292a3-126">たとえば、次のコード行では、`String` 型の変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="292a3-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="292a3-127">次のコードは、整数の配列を作成する2つの同等の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="292a3-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="292a3-128">型の推定を使用して、ループコントロール変数の型を決定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="292a3-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="292a3-129">次のコードでは、前の例の `someNumbers2` が整数の配列であるため、コンパイラは `number` が `Integer` であると推論します。</span><span class="sxs-lookup"><span data-stu-id="292a3-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="292a3-130">次の例に示すように、`Using` ステートメントでローカル型の推論を使用して、リソース名の型を設定できます。</span><span class="sxs-lookup"><span data-stu-id="292a3-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="292a3-131">変数の型は、次の例に示すように、関数の戻り値から推論することもできます。</span><span class="sxs-lookup"><span data-stu-id="292a3-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="292a3-132">@No__t_2 はプロセスの配列を返すため、`pList1` と `pList2` はどちらもプロセスの配列です。</span><span class="sxs-lookup"><span data-stu-id="292a3-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="292a3-133">オプションの推論</span><span class="sxs-lookup"><span data-stu-id="292a3-133">Option Infer</span></span>

<span data-ttu-id="292a3-134">`Option Infer` を使用すると、特定のファイルでローカル型の推論が許可されるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="292a3-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="292a3-135">オプションを有効または禁止するには、ファイルの先頭に次のいずれかのステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="292a3-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="292a3-136">コードで `Option Infer` の値を指定しない場合、コンパイラの既定値は `Option Infer On` になります。</span><span class="sxs-lookup"><span data-stu-id="292a3-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="292a3-137">ファイルの `Option Infer` に設定した値が IDE またはコマンド ラインに設定した値と競合した場合は、ファイルの値が優先されます。</span><span class="sxs-lookup"><span data-stu-id="292a3-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="292a3-138">詳細については、[[オプションの推論ステートメント]](../../../../visual-basic/language-reference/statements/option-infer-statement.md)と [[コンパイル] ページ (プロジェクトデザイナー) (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="292a3-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="292a3-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="292a3-139">See also</span></span>

- [<span data-ttu-id="292a3-140">匿名型</span><span class="sxs-lookup"><span data-stu-id="292a3-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="292a3-141">事前バインディングと遅延バインディング</span><span class="sxs-lookup"><span data-stu-id="292a3-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="292a3-142">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="292a3-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="292a3-143">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="292a3-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="292a3-144">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="292a3-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="292a3-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="292a3-145">-optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="292a3-146">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="292a3-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
