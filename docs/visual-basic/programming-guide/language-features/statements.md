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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352502"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="89f6f-102">Visual Basic におけるステートメント</span><span class="sxs-lookup"><span data-stu-id="89f6f-102">Statements in Visual Basic</span></span>

<span data-ttu-id="89f6f-103">Visual Basic のステートメントは完全な命令です。</span><span class="sxs-lookup"><span data-stu-id="89f6f-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="89f6f-104">キーワード、演算子、変数、定数、および式を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="89f6f-105">各ステートメントは、次のいずれかのカテゴリに属します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="89f6f-106">変数、定数、またはプロシージャの名前を**宣言する宣言ステートメント**。データ型を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="89f6f-107">**実行可能なステートメント**。アクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="89f6f-108">これらのステートメントは、メソッドまたは関数を呼び出すことができ、コードのブロックをループまたは分岐できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="89f6f-109">実行可能なステートメントには、変数または定数に値または式を割り当てる**代入ステートメント**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="89f6f-110">このトピックでは、各カテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-110">This topic describes each category.</span></span> <span data-ttu-id="89f6f-111">また、このトピックでは、複数のステートメントを1行に結合する方法と、ステートメントを複数の行にわたって継続する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="89f6f-112">宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="89f6f-112">Declaration statements</span></span>

<span data-ttu-id="89f6f-113">宣言ステートメントを使用して、プロシージャ、変数、プロパティ、配列、および定数に名前を指定し、定義します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="89f6f-114">プログラミング要素を宣言するときに、そのデータ型、アクセスレベル、およびスコープを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="89f6f-115">詳細については、「[宣言された要素の特性](./declared-elements/declared-element-characteristics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="89f6f-116">次の例には、3つの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89f6f-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="89f6f-117">最初の宣言は、`Sub` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="89f6f-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="89f6f-118">一致する `End Sub` ステートメントと共に、`applyFormat`という名前のプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="89f6f-119">また、`applyFormat` が `Public`であることを指定します。これは、それを参照できるすべてのコードがそれを呼び出すことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="89f6f-120">2番目の宣言は `Const` ステートメントであり、`Integer` データ型と33の値を指定して `limit`定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="89f6f-121">3番目の宣言は、変数 `thisWidget`を宣言する `Dim` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="89f6f-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="89f6f-122">データ型は、特定のオブジェクト、つまり `Widget` クラスから作成されたオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="89f6f-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="89f6f-123">任意の基本データ型または使用しているアプリケーションで公開されている任意のオブジェクト型の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="89f6f-124">初期値</span><span class="sxs-lookup"><span data-stu-id="89f6f-124">Initial Values</span></span>

<span data-ttu-id="89f6f-125">宣言ステートメントを含むコードを実行すると、Visual Basic は、宣言された要素に必要なメモリを予約します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="89f6f-126">要素が値を保持している場合は、Visual Basic そのデータ型の既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="89f6f-127">詳細については、「[Dim ステートメント](../../language-reference/statements/dim-statement.md)」の「動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="89f6f-128">次の例に示すように、変数に初期値を宣言の一部として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="89f6f-129">変数がオブジェクト変数の場合は、次の例に示すように、 [New 演算子](../../../visual-basic/language-reference/operators/new-operator.md)キーワードを使用して宣言するときに、そのクラスのインスタンスを明示的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="89f6f-130">宣言ステートメントで指定する初期値は、実行が宣言ステートメントに到達するまで変数に割り当てられないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="89f6f-131">この時間が経過するまで、変数にはそのデータ型の既定値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="89f6f-132">実行可能なステートメント</span><span class="sxs-lookup"><span data-stu-id="89f6f-132">Executable statements</span></span>

<span data-ttu-id="89f6f-133">実行可能なステートメントがアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-133">An executable statement performs an action.</span></span> <span data-ttu-id="89f6f-134">プロシージャを呼び出したり、コード内の別の場所に分岐したり、複数のステートメントをループ処理したり、式を評価したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="89f6f-135">代入ステートメントは、実行可能なステートメントの特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="89f6f-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="89f6f-136">次の例では、`If...Then...Else` コントロール構造体を使用して、変数の値に基づいてさまざまなコードブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="89f6f-137">各コードブロック内では、`For...Next` ループが指定された回数実行されます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="89f6f-138">前の例の `If` ステートメントでは、パラメーター `clockwise`の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="89f6f-139">値が `True`場合、`aWidget`の `spinClockwise` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="89f6f-140">値が `False`場合、`aWidget`の `spinCounterClockwise` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="89f6f-141">`If...Then...Else` コントロールの構造体は、`End If`で終了します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="89f6f-142">各ブロック内の `For...Next` ループは、`revolutions` パラメーターの値と等しい回数、適切なメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="89f6f-143">代入ステートメント</span><span class="sxs-lookup"><span data-stu-id="89f6f-143">Assignment statements</span></span>

<span data-ttu-id="89f6f-144">代入ステートメントは、代入演算子 (`=`) の右側にある値を取得し、次の例のように左側の要素に格納することで構成される代入演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="89f6f-145">前の例では、代入ステートメントによって、リテラル値42が変数 `v`に格納されています。</span><span class="sxs-lookup"><span data-stu-id="89f6f-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="89f6f-146">対象となるプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="89f6f-146">Eligible programming elements</span></span>

<span data-ttu-id="89f6f-147">代入演算子の左側のプログラミング要素は、値を受け入れて格納できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="89f6f-148">これは、[読み取り専用](../../../visual-basic/language-reference/modifiers/readonly.md)ではない変数またはプロパティであるか、配列要素である必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="89f6f-149">代入ステートメントのコンテキストでは、このような要素は "左辺値" として*左辺*値と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="89f6f-150">代入演算子の右側の値は、式によって生成されます。式は、リテラル、定数、変数、プロパティ、配列要素、他の式、または関数呼び出しの任意の組み合わせで構成されます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="89f6f-151">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="89f6f-152">前の例では、変数 `y` に保持されている値を変数 `z`に保持されている値に追加した後、関数 `findResult`への呼び出しによって返された値を追加します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="89f6f-153">この式の合計値は、変数 `x`に格納されます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="89f6f-154">代入ステートメントのデータ型</span><span class="sxs-lookup"><span data-stu-id="89f6f-154">Data types in assignment statements</span></span>

<span data-ttu-id="89f6f-155">次の例に示すように、代入演算子は数値に加えて `String` 値も割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="89f6f-156">次の例に示すように、`Boolean` リテラルまたは `Boolean` 式を使用して `Boolean` 値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="89f6f-157">同様に、`Char`、`Date`、または `Object` データ型のプログラミング要素に適切な値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="89f6f-158">また、インスタンスの作成元のクラスとして宣言された要素にオブジェクトインスタンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="89f6f-159">複合代入ステートメント</span><span class="sxs-lookup"><span data-stu-id="89f6f-159">Compound assignment statements</span></span>

<span data-ttu-id="89f6f-160">*複合代入ステートメント*は、最初に式に対して操作を実行してから、プログラミング要素に代入します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="89f6f-161">次の例では、演算子の左辺の変数の値を右側の式の値でインクリメントする、`+=`のいずれかの演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="89f6f-162">前の例では、`n`の値に1を加算し、その新しい値を `n`に格納しています。</span><span class="sxs-lookup"><span data-stu-id="89f6f-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="89f6f-163">これは、次のステートメントの省略形に相当します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="89f6f-164">この型の演算子を使用すると、さまざまな複合代入演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="89f6f-165">これらの演算子の一覧と詳細については、「[代入演算子](../../../visual-basic/language-reference/operators/assignment-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="89f6f-166">連結代入演算子 (`&=`) は、次の例に示すように、既存の文字列の末尾に文字列を追加する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="89f6f-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="89f6f-167">代入ステートメントでの型変換</span><span class="sxs-lookup"><span data-stu-id="89f6f-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="89f6f-168">変数、プロパティ、または配列要素に割り当てる値は、そのターゲット要素に適したデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="89f6f-169">一般に、destination 要素と同じデータ型の値を生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89f6f-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="89f6f-170">ただし、割り当て時に他の型に変換できる型もあります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="89f6f-171">データ型間の変換の詳細については、「[Visual Basic での型変換](./data-types/type-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="89f6f-172">簡単に言えば、Visual Basic は、指定された型の値を、拡大変換先の他の型に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="89f6f-173">*拡大変換*は、常に実行時に成功し、データを失うことのないの1つです。</span><span class="sxs-lookup"><span data-stu-id="89f6f-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="89f6f-174">たとえば、Visual Basic は、`Integer` が `Double`に拡大変換されるため、必要に応じて `Integer` 値を `Double` に変換します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="89f6f-175">詳細については、「[拡大変換と縮小変換](./data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="89f6f-176">*縮小変換*(拡大されていないもの) は、実行時またはデータ損失のリスクを発生させます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="89f6f-177">型変換関数を使用して縮小変換を明示的に実行することも、`Option Strict Off`を設定することによって暗黙的にすべての変換を実行するようにコンパイラに指示することもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="89f6f-178">詳細については、「[暗黙的な変換と明示的な変換](./data-types/implicit-and-explicit-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="89f6f-179">1行に複数のステートメントを配置する</span><span class="sxs-lookup"><span data-stu-id="89f6f-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="89f6f-180">1つの行に複数のステートメントを記述して、コロン (`:`) 文字で区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="89f6f-181">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="89f6f-182">この形式の構文を使用すると、コードの読み取りと保守が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="89f6f-183">したがって、1つのステートメントを1行に収めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89f6f-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="89f6f-184">複数行にわたってステートメントを続行する</span><span class="sxs-lookup"><span data-stu-id="89f6f-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="89f6f-185">ステートメントは通常1行に配置されますが、長すぎる場合は、行連結シーケンスを使用して次の行に進むことができます。これは、スペースの後にアンダースコア文字 (`_`) が続き、その後に復帰が続くもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="89f6f-186">次の例では、`MsgBox` の実行可能なステートメントは2つの行にわたって続きます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="89f6f-187">暗黙の行の連結</span><span class="sxs-lookup"><span data-stu-id="89f6f-187">Implicit line continuation</span></span>

<span data-ttu-id="89f6f-188">多くの場合、アンダースコア文字 (`_`) を使用せずに、次の連続する行でステートメントを続行できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="89f6f-189">次の構文要素は、ステートメントを次のコード行で暗黙的に続行します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="89f6f-190">コンマ (`,`) の後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-190">After a comma (`,`).</span></span> <span data-ttu-id="89f6f-191">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="89f6f-192">開いているかっこ (`(`) の後、または閉じかっこ (`)`) の前。</span><span class="sxs-lookup"><span data-stu-id="89f6f-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="89f6f-193">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="89f6f-194">左中かっこ (`{`) の後、または右中かっこ (`}`) の前。</span><span class="sxs-lookup"><span data-stu-id="89f6f-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="89f6f-195">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="89f6f-196">詳細については、「[オブジェクト初期化子: 名前付き、匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)、または[コレクション初期化子](./collection-initializers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="89f6f-197">開いている埋め込み式 (`<%=`) の後、または XML リテラル内の埋め込み式 (`%>`) の終了前。</span><span class="sxs-lookup"><span data-stu-id="89f6f-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="89f6f-198">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="89f6f-199">詳細については、「 [XML での埋め込み式](./xml/embedded-expressions-in-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="89f6f-200">連結演算子 (`&`) の後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="89f6f-201">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="89f6f-202">詳細については、「[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="89f6f-203">代入演算子 (`=`、`&=`、`:=`、`+=`、`-=`、`*=`、`/=`、`\=`、`^=`、`<<=`、`>>=`) 後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="89f6f-204">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="89f6f-205">詳細については、「[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="89f6f-206">二項演算子 (`+`、`-`、`/`、`*`、`Mod`、`<>`、`<`、`>`、`<=`、`>=`、`^`) の後に、式の中で、`>>`、`<<`、`And`)。`AndAlso``Or``OrElse``Like``Xor`</span><span class="sxs-lookup"><span data-stu-id="89f6f-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="89f6f-207">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="89f6f-208">詳細については、「[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="89f6f-209">`Is` 演算子と `IsNot` 演算子の後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="89f6f-210">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="89f6f-211">詳細については、「[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="89f6f-212">メンバー修飾子文字 (`.`) の後、およびメンバー名の前。</span><span class="sxs-lookup"><span data-stu-id="89f6f-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="89f6f-213">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="89f6f-214">ただし、`With` ステートメントを使用する場合、または型の初期化リストに値を指定する場合は、メンバー修飾子文字の後に行連結文字 (`_`) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="89f6f-215">`With` ステートメントまたはオブジェクトの初期化リストを使用している場合は、代入演算子 (`=`など) の後にある行を分割することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="89f6f-216">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="89f6f-217">詳細については、「」を参照してください。 [ステートメント](../../../visual-basic/language-reference/statements/with-end-with-statement.md)またはオブジェクト初期化子を使用した終了[: 名前付きの型と匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="89f6f-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="89f6f-218">XML 軸プロパティ修飾子 (`.` または `.@` または `...`) の後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="89f6f-219">ただし、`With` キーワードを使用する場合は、メンバー修飾子を指定するときに、行連結文字 (`_`) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="89f6f-220">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="89f6f-221">詳細については、「 [XML 軸のプロパティ](../../../visual-basic/language-reference/xml-axis/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="89f6f-222">属性を指定するときに、小なり記号 (<) またはそれより大きい記号 (`>`) の後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="89f6f-223">属性を指定する場合は、大なり記号 (`>`) の後にもなります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="89f6f-224">ただし、アセンブリレベルまたはモジュールレベルの属性を指定する場合は、行連結文字 (`_`) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="89f6f-225">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="89f6f-226">詳細については、「[属性の概要](../../../visual-basic/programming-guide/concepts/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="89f6f-227">クエリ演算子の前後 (`Aggregate`、`Distinct`、`From`、`Group By`、`Group Join`、`Join`、`Let`、`Order By`、`Select`、`Skip`、`Skip While`、`Take`、`Take While`、`Where`、および `In`) に対して実行されます。`Into``On``Ascending``Descending`</span><span class="sxs-lookup"><span data-stu-id="89f6f-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="89f6f-228">複数のキーワード (`Order By`、`Group Join`、`Take While`、および `Skip While`) で構成されているクエリ演算子のキーワード間で行を分割することはできません。</span><span class="sxs-lookup"><span data-stu-id="89f6f-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="89f6f-229">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="89f6f-230">詳細については、「[クエリ](../../../visual-basic/language-reference/queries/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="89f6f-231">`For Each` ステートメントの `In` キーワードの後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="89f6f-232">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="89f6f-233">詳細については、[For Each...Next ステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="89f6f-234">コレクション初期化子内の `From` キーワードの後。</span><span class="sxs-lookup"><span data-stu-id="89f6f-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="89f6f-235">例 :</span><span class="sxs-lookup"><span data-stu-id="89f6f-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="89f6f-236">詳細については、「[コレクション初期化子](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89f6f-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="89f6f-237">コメントの追加</span><span class="sxs-lookup"><span data-stu-id="89f6f-237">Adding comments</span></span>

<span data-ttu-id="89f6f-238">ソースコードは、それを記述したプログラマであっても、常に自明であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="89f6f-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="89f6f-239">コードを文書化するために、ほとんどのプログラマは、埋め込みコメントを自由に使用します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="89f6f-240">コード内のコメントは、後で読み取りや操作を行うためのプロシージャまたは特定の命令を説明することができます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="89f6f-241">Visual Basic は、コンパイル時にコメントを無視し、コンパイルされたコードには影響しません。</span><span class="sxs-lookup"><span data-stu-id="89f6f-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="89f6f-242">コメント行の先頭には、アポストロフィ (`'`) または `REM` の後にスペースが付きます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="89f6f-243">文字列内を除き、コード内の任意の場所に追加できます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="89f6f-244">ステートメントにコメントを追加するには、ステートメントの後にコメントを続けて、アポストロフィまたは `REM` を挿入します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="89f6f-245">コメントは、独自の行を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="89f6f-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="89f6f-246">次の例は、これらの可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="89f6f-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="89f6f-247">コンパイルエラーの確認</span><span class="sxs-lookup"><span data-stu-id="89f6f-247">Checking compilation errors</span></span>

<span data-ttu-id="89f6f-248">コード行を入力した後に、線が青い下線付きで表示されている場合 (エラーメッセージも表示される場合があります)、ステートメントに構文エラーがあります。</span><span class="sxs-lookup"><span data-stu-id="89f6f-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="89f6f-249">ステートメントに問題がないことを確認する必要があります (タスク一覧を検索するか、マウスポインターを使用してエラーをポイントし、エラーメッセージを読み取って)、修正します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="89f6f-250">コード内のすべての構文エラーを修正するまで、プログラムは正しくコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="89f6f-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="89f6f-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="89f6f-251">Related sections</span></span>

|<span data-ttu-id="89f6f-252">用語</span><span class="sxs-lookup"><span data-stu-id="89f6f-252">Term</span></span>|<span data-ttu-id="89f6f-253">Definition</span><span class="sxs-lookup"><span data-stu-id="89f6f-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="89f6f-254">代入演算子</span><span class="sxs-lookup"><span data-stu-id="89f6f-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="89f6f-255">`=`、`*=`、`&=`などの代入演算子を扱う言語リファレンスページへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="89f6f-256">演算子および式</span><span class="sxs-lookup"><span data-stu-id="89f6f-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="89f6f-257">要素を演算子と組み合わせて新しい値を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="89f6f-258">方法 : コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="89f6f-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="89f6f-259">1つのステートメントを複数の行に分割する方法と、複数のステートメントを同じ行に配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="89f6f-260">方法 : ステートメントへのラベル付け</span><span class="sxs-lookup"><span data-stu-id="89f6f-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="89f6f-261">コード行にラベルを付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89f6f-261">Shows how to label a line of code.</span></span>|
