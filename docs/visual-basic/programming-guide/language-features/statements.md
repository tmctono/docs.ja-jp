---
title: ステートメント
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401467"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="a549d-102">Visual Basic におけるステートメント</span><span class="sxs-lookup"><span data-stu-id="a549d-102">Statements in Visual Basic</span></span>

<span data-ttu-id="a549d-103">Visual Basic のステートメントは、完全な命令です。</span><span class="sxs-lookup"><span data-stu-id="a549d-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="a549d-104">キーワード、演算子、変数、定数、および式を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="a549d-105">各ステートメントは、次のカテゴリのいずれかに属します。</span><span class="sxs-lookup"><span data-stu-id="a549d-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="a549d-106">**宣言ステートメント**変数、定数、またはプロシージャの名前を指定し、データ型を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="a549d-107">**実行可能ステートメント**: アクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a549d-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="a549d-108">これらのステートメントは、メソッドまたは関数を呼び出し、コードブロックをループまたは分岐できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="a549d-109">実行可能ステートメントには、変数または定数に値または式を代入する**代入ステートメント**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a549d-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="a549d-110">このトピックでは、各カテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a549d-110">This topic describes each category.</span></span> <span data-ttu-id="a549d-111">また、このトピックでは、複数のステートメントを 1 行に結合する方法と、複数行にわたってステートメントを継続する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a549d-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="a549d-112">宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="a549d-112">Declaration statements</span></span>

<span data-ttu-id="a549d-113">宣言ステートメントを使用して、プロシージャ、変数、プロパティ、配列、および定数に名前を付け、定義します。</span><span class="sxs-lookup"><span data-stu-id="a549d-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="a549d-114">プログラミング要素を宣言する場合は、そのデータ型、アクセス レベル、およびスコープを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="a549d-115">詳細については、「[宣言された要素の特性](./declared-elements/declared-element-characteristics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="a549d-116">次の例には、3 つの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a549d-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="a549d-117">最初の宣言はステートメント`Sub`です。</span><span class="sxs-lookup"><span data-stu-id="a549d-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="a549d-118">一致する`End Sub`ステートメントと共に、 という名前`applyFormat`のプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a549d-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="a549d-119">また、これを`Public`参照`applyFormat`できるコードは、それを呼び出すことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a549d-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="a549d-120">2 番目の`Const`宣言は、`limit``Integer`定数 を宣言するステートメントで、データ型と値 33 を指定します。</span><span class="sxs-lookup"><span data-stu-id="a549d-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="a549d-121">3 番目の`Dim`宣言は、変数`thisWidget`を宣言するステートメントです。</span><span class="sxs-lookup"><span data-stu-id="a549d-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="a549d-122">データ型は特定のオブジェクト、つまりクラスから作成されたオブジェクトです`Widget`。</span><span class="sxs-lookup"><span data-stu-id="a549d-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="a549d-123">変数は、任意の基本データ型、または使用しているアプリケーションで公開される任意のオブジェクト型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="a549d-124">初期値</span><span class="sxs-lookup"><span data-stu-id="a549d-124">Initial Values</span></span>

<span data-ttu-id="a549d-125">宣言ステートメントを含むコードを実行すると、宣言された要素に必要なメモリが確保されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="a549d-126">要素に値が格納されている場合、Visual Basic では、その値がデータ型の既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="a549d-127">詳細については[、Dim ステートメント](../../language-reference/statements/dim-statement.md)の「動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="a549d-128">次の例に示すように、初期値を宣言の一部として変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="a549d-129">変数がオブジェクト変数の場合、次の例に示すように[、New Operator](../../../visual-basic/language-reference/operators/new-operator.md)キーワードを使用して宣言するときに、そのクラスのインスタンスを明示的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="a549d-130">宣言ステートメントで指定した初期値は、実行がその宣言ステートメントに達するまで変数に割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="a549d-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="a549d-131">その時点まで、変数にはデータ型の既定値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a549d-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="a549d-132">実行可能ステートメント</span><span class="sxs-lookup"><span data-stu-id="a549d-132">Executable statements</span></span>

<span data-ttu-id="a549d-133">実行可能ステートメントは、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a549d-133">An executable statement performs an action.</span></span> <span data-ttu-id="a549d-134">プロシージャを呼び出したり、コード内の別の場所に分岐したり、複数のステートメントをループ処理したり、式を評価したりできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="a549d-135">代入ステートメントは、実行可能ステートメントの特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="a549d-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="a549d-136">次の例では、`If...Then...Else`制御構造を使用して、変数の値に基づいてさまざまなコード ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="a549d-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="a549d-137">各コード ブロック内では、`For...Next`ループは指定された回数だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="a549d-138">前`If`の例のステートメントは、パラメーター`clockwise`の値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="a549d-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="a549d-139">値が の`True`場合は、`spinClockwise`のメソッド`aWidget`を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a549d-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="a549d-140">値が の`False`場合は、`spinCounterClockwise`のメソッド`aWidget`を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a549d-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="a549d-141">制御`If...Then...Else`構造の最後は`End If`で終わります。</span><span class="sxs-lookup"><span data-stu-id="a549d-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="a549d-142">各`For...Next`ブロック内のループは、パラメータの値と同じ回数だけ適切なメソッドを`revolutions`呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a549d-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="a549d-143">割り当てステートメント</span><span class="sxs-lookup"><span data-stu-id="a549d-143">Assignment statements</span></span>

<span data-ttu-id="a549d-144">代入ステートメントは代入演算子を実行しますが、これは代入演算子 (`=`) の右側の値を取得し、それを左の要素に格納します。</span><span class="sxs-lookup"><span data-stu-id="a549d-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="a549d-145">前の例では、代入ステートメントはリテラル値 42 を変数`v`に格納します。</span><span class="sxs-lookup"><span data-stu-id="a549d-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="a549d-146">適格なプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="a549d-146">Eligible programming elements</span></span>

<span data-ttu-id="a549d-147">代入演算子の左側にあるプログラミング要素は、値を受け入れて格納できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="a549d-148">つまり、変数またはプロパティは[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)ではないか、配列要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="a549d-149">代入ステートメントのコンテキストでは、このような要素は"left *value" の左辺値*と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="a549d-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="a549d-150">代入演算子の右側の値は、リテラル、定数、変数、プロパティ、配列要素、その他の式、または関数呼び出しの任意の組み合わせで構成される式によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="a549d-151">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="a549d-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="a549d-152">前の例では、変数に保持されている値`y`を変数`z`に保持されている値に追加し、関数`findResult`の呼び出しによって返される値を加算します。</span><span class="sxs-lookup"><span data-stu-id="a549d-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="a549d-153">この式の合計値は、 variable`x`に格納されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="a549d-154">代入ステートメントのデータ型</span><span class="sxs-lookup"><span data-stu-id="a549d-154">Data types in assignment statements</span></span>

<span data-ttu-id="a549d-155">次の例に示すように、代入演算子は数値に`String`加えて値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="a549d-156">次の例に`Boolean`示すように、リテラルまたは`Boolean`式を`Boolean`使用して値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="a549d-157">同様に、 、`Char``Date`または`Object`データ型のプログラミング要素に適切な値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="a549d-158">また、オブジェクトインスタンスを、そのインスタンスの作成元クラスとして宣言された要素に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="a549d-159">複合割当ステートメント</span><span class="sxs-lookup"><span data-stu-id="a549d-159">Compound assignment statements</span></span>

<span data-ttu-id="a549d-160">*複合代入ステートメント*は、プログラミング要素に代入する前に、式に対して演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="a549d-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="a549d-161">次の例は、`+=`演算子の左側の変数の値を右側の式の値だけインクリメントする、これらの演算子の 1 つを示しています。</span><span class="sxs-lookup"><span data-stu-id="a549d-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="a549d-162">上の例では、 の値`n`に 1 を加算し、その新`n`しい値を に格納します。</span><span class="sxs-lookup"><span data-stu-id="a549d-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="a549d-163">これは、次のステートメントと同等の速記です。</span><span class="sxs-lookup"><span data-stu-id="a549d-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="a549d-164">このタイプの演算子を使用して、さまざまな複合代入演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="a549d-165">これらの演算子の一覧と、演算子の詳細については、「[代入演算子](../../../visual-basic/language-reference/operators/assignment-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="a549d-166">次の例に示すように、`&=`連結代入演算子 ( ) は、既存の文字列の末尾に文字列を追加する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a549d-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="a549d-167">代入ステートメントでの型変換</span><span class="sxs-lookup"><span data-stu-id="a549d-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="a549d-168">変数、プロパティ、または配列要素に代入する値は、その代入先要素に適したデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="a549d-169">一般に、変換先要素と同じデータ型の値を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="a549d-170">ただし、代入時に他の型に変換できる型もあります。</span><span class="sxs-lookup"><span data-stu-id="a549d-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="a549d-171">データ型間の変換については、「 [Visual Basic での型変換](./data-types/type-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="a549d-172">簡単に言うと、Visual Basic では、指定した型の値が、その値を拡大する他の任意の型に自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="a549d-173">*拡大変換*は、実行時に常に成功し、データを失わない変換です。</span><span class="sxs-lookup"><span data-stu-id="a549d-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="a549d-174">たとえば、Visual Basic では、`Integer`値が`Double`適切な`Integer`場合に変換`Double`されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="a549d-175">詳細については、「 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="a549d-176">*縮小変換*(拡大しない変換) は、実行時に失敗したり、データが失われるリスクを負ったりします。</span><span class="sxs-lookup"><span data-stu-id="a549d-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="a549d-177">型変換関数を使用して明示的に縮小変換を実行するか、または を設定してすべての変換を暗黙的に実行するようにコンパイラに指示`Option Strict Off`することができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="a549d-178">詳細については、「[暗黙的および明示的な変換](./data-types/implicit-and-explicit-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="a549d-179">複数のステートメントを 1 行に配置する</span><span class="sxs-lookup"><span data-stu-id="a549d-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="a549d-180">コロン (`:`) 文字で区切られた 1 行に複数のステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="a549d-181">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="a549d-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="a549d-182">この形式の構文は便利ですが、コードの読み取りや保守が困難になります。</span><span class="sxs-lookup"><span data-stu-id="a549d-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="a549d-183">したがって、1 つのステートメントを 1 行に保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a549d-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="a549d-184">複数行にわたるステートメントの継続</span><span class="sxs-lookup"><span data-stu-id="a549d-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="a549d-185">ステートメントは通常 1 行に収まりますが、長すぎる場合は、行`_`連結シーケンスを使用して次の行に続けることができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="a549d-186">次の例では、`MsgBox`実行可能ステートメントは 2 行にわたって続きます。</span><span class="sxs-lookup"><span data-stu-id="a549d-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="a549d-187">暗黙の行継続</span><span class="sxs-lookup"><span data-stu-id="a549d-187">Implicit line continuation</span></span>

<span data-ttu-id="a549d-188">多くの場合、アンダースコア文字 ( )`_`を使用せずに、次の連続する行でステートメントを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="a549d-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="a549d-189">次の構文要素は、次のコード行でステートメントを暗黙的に続行します。</span><span class="sxs-lookup"><span data-stu-id="a549d-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="a549d-190">コンマの後`,`( ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a549d-190">After a comma (`,`).</span></span> <span data-ttu-id="a549d-191">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="a549d-192">左括弧 (`(`) の後、 または閉`)`じかっこ ( ) の前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="a549d-193">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="a549d-194">中かっこ (`{`) の後、または右中かっこ (`}`) の前に表示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="a549d-195">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="a549d-196">詳細については、「[オブジェクト初期化子 : 名前付き型および匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)または[コレクション初期化子](./collection-initializers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="a549d-197">オープンな埋め込み`<%=`式 ( ) の後、または`%>`XML リテラル内の埋め込み式 ( ) の終了前。</span><span class="sxs-lookup"><span data-stu-id="a549d-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="a549d-198">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="a549d-199">詳細については[、「XML での埋め込み式](./xml/embedded-expressions-in-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="a549d-200">連結演算子 ( )`&`の後に</span><span class="sxs-lookup"><span data-stu-id="a549d-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="a549d-201">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="a549d-202">詳細については、「[機能別に表示される演算子](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="a549d-203">代入演算子 (`=` `&=`, `:=` `+=`, `-=` `*=`, `/=` `\=`, `^=` `<<=`, `>>=`, , , , , , , , , , , , , )。</span><span class="sxs-lookup"><span data-stu-id="a549d-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="a549d-204">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="a549d-205">詳細については、「[機能別に表示される演算子](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="a549d-206">式の中の`+`二`-`項`/`演算子`*` `Mod`( `<>` `<`, `>` `<=`, `>=` `^` `>>` `<<` `Like` `Xor`, , , , , , , , , , , , , , , , , , ) を実行します。 `And` `AndAlso` `Or` `OrElse`</span><span class="sxs-lookup"><span data-stu-id="a549d-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="a549d-207">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="a549d-208">詳細については、「[機能別に表示される演算子](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="a549d-209">演算子と`Is``IsNot`演算子の後。</span><span class="sxs-lookup"><span data-stu-id="a549d-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="a549d-210">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="a549d-211">詳細については、「[機能別に表示される演算子](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="a549d-212">メンバー修飾子文字 (`.`) の後、およびメンバー名の前。</span><span class="sxs-lookup"><span data-stu-id="a549d-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="a549d-213">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="a549d-214">ただし、`With`ステートメントを使用する場合、または型の`_`初期化リストに値を指定する場合は、メンバー修飾子文字の後に行連結文字 ( ) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="a549d-215">ステートメントまたはオブジェクト初期化リストを使用`=``With`している場合は、代入演算子 (例えば) の後の行を改行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="a549d-216">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="a549d-217">詳細については[、「.」を参照してください。ステートメント](../../../visual-basic/language-reference/statements/with-end-with-statement.md)または[オブジェクト初期化子で終わる: 名前付き型と匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a549d-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="a549d-218">XML 軸プロパティの修飾子`.`( `.@` `...`または ) の後に指定します。</span><span class="sxs-lookup"><span data-stu-id="a549d-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="a549d-219">ただし、キーワードを使用する場合は、メンバー修飾子`_`を指定する場合は、 行連結文字 ( `With` ) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="a549d-220">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="a549d-221">詳細については、「 [XML 軸のプロパティ 」](../../../visual-basic/language-reference/xml-axis/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="a549d-222">属性を指定した場合、非参照 (<) より小さい符号`>`の後、またはより大きい記号 ( ) の前。</span><span class="sxs-lookup"><span data-stu-id="a549d-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="a549d-223">属性を指定する場合も、より`>`大きな符号 ( ) の後に指定します。</span><span class="sxs-lookup"><span data-stu-id="a549d-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="a549d-224">ただし、アセンブリ レベルまたはモジュール レベルの属性`_`を指定する場合は、行連結文字 ( ) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="a549d-225">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="a549d-226">詳細については、「属性の[概要](../../../visual-basic/programming-guide/concepts/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="a549d-227">前後のクエリ演算子 (`Aggregate` `Distinct`, `From` `Group By`, `Group Join` `Join`, `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Descending`, , , , , , , , , , , , , , , , ) 。 `Where` `In` `Into` `On` `Ascending`</span><span class="sxs-lookup"><span data-stu-id="a549d-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="a549d-228">複数のキーワード`Order By`( 、 、、、、、、、、 `Group Join` `Take While`) で構成されるクエリ演算子の`Skip While`キーワードの間に線を引くことはできません。</span><span class="sxs-lookup"><span data-stu-id="a549d-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="a549d-229">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="a549d-230">詳細については、「[クエリ](../../../visual-basic/language-reference/queries/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="a549d-231">ステートメント内`In`のキーワードの`For Each`後。</span><span class="sxs-lookup"><span data-stu-id="a549d-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="a549d-232">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="a549d-233">詳細については、[For Each...Next ステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="a549d-234">コレクション初期化`From`子のキーワードの後。</span><span class="sxs-lookup"><span data-stu-id="a549d-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="a549d-235">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="a549d-236">詳細については、「[コレクション初期化子](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a549d-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="a549d-237">コメントの追加</span><span class="sxs-lookup"><span data-stu-id="a549d-237">Adding comments</span></span>

<span data-ttu-id="a549d-238">ソースコードは、それを書いたプログラマーにとっても、必ずしも自明ではありません。</span><span class="sxs-lookup"><span data-stu-id="a549d-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="a549d-239">そのため、コードを文書化するために、ほとんどのプログラマは埋め込みコメントを自由に使用しています。</span><span class="sxs-lookup"><span data-stu-id="a549d-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="a549d-240">コード内のコメントは、後で読んだり作業したりする人に対して、プロシージャや特定の命令を説明できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="a549d-241">Visual Basic では、コンパイル時にコメントは無視され、コンパイルされたコードには影響しません。</span><span class="sxs-lookup"><span data-stu-id="a549d-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="a549d-242">コメント行はアポストロフィ (`'`)`REM`で始まるか、またはスペースで始まります。</span><span class="sxs-lookup"><span data-stu-id="a549d-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="a549d-243">文字列内を除くコード内の任意の場所に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a549d-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="a549d-244">ステートメントにコメントを追加するには、アポストロフィまたは`REM`ステートメントの後ろにコメントを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a549d-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="a549d-245">コメントは、独自の行に行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="a549d-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="a549d-246">次の例では、これらの可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="a549d-247">コンパイル エラーの確認</span><span class="sxs-lookup"><span data-stu-id="a549d-247">Checking compilation errors</span></span>

<span data-ttu-id="a549d-248">コード行を入力した後、その行に青い波線が表示される場合 (エラー メッセージも表示される場合があります)、ステートメントに構文エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a549d-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="a549d-249">ステートメントの問題を調べるには(タスクリストを見るか、マウスポインタでエラーをポイントしてエラーメッセージを読む)、それを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a549d-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="a549d-250">コード内のすべての構文エラーを修正するまで、プログラムは正しくコンパイルできません。</span><span class="sxs-lookup"><span data-stu-id="a549d-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a549d-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="a549d-251">Related sections</span></span>

|<span data-ttu-id="a549d-252">期間</span><span class="sxs-lookup"><span data-stu-id="a549d-252">Term</span></span>|<span data-ttu-id="a549d-253">定義</span><span class="sxs-lookup"><span data-stu-id="a549d-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="a549d-254">代入演算子</span><span class="sxs-lookup"><span data-stu-id="a549d-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="a549d-255">などの代入演算子`=``*=`を含む言語リファレンス ページへのリンクを`&=`提供します。</span><span class="sxs-lookup"><span data-stu-id="a549d-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="a549d-256">演算子および式</span><span class="sxs-lookup"><span data-stu-id="a549d-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="a549d-257">要素と演算子を組み合わせて新しい値を生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="a549d-258">方法 : コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="a549d-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="a549d-259">1 つのステートメントを複数の行に分割する方法と、複数のステートメントを同じ行に配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="a549d-260">方法 : ステートメントへのラベル付け</span><span class="sxs-lookup"><span data-stu-id="a549d-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="a549d-261">コード行にラベルを付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a549d-261">Shows how to label a line of code.</span></span>|
