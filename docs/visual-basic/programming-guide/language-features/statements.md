---
title: Visual Basic におけるステートメント
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
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946459"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="545e8-102">Visual Basic におけるステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-102">Statements in Visual Basic</span></span>

<span data-ttu-id="545e8-103">Visual Basic でのステートメントは、完全な命令です。</span><span class="sxs-lookup"><span data-stu-id="545e8-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="545e8-104">これは、キーワード、演算子、変数、定数、および式に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="545e8-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="545e8-105">各ステートメントは、次のカテゴリのいずれかに属します。</span><span class="sxs-lookup"><span data-stu-id="545e8-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="545e8-106">**宣言ステートメント**変数、定数、またはプロシージャの名前し、データ型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="545e8-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="545e8-107">**実行可能なステートメント**操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="545e8-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="545e8-108">メソッドまたは関数の場合、これらのステートメントを呼び出すことができ、ループや分岐のコード ブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="545e8-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="545e8-109">実行可能ステートメントを含む**代入ステートメント**、変数または定数に値または式に代入します。</span><span class="sxs-lookup"><span data-stu-id="545e8-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="545e8-110">このトピックでは、各カテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="545e8-110">This topic describes each category.</span></span> <span data-ttu-id="545e8-111">また、このトピックでは、1 行に複数のステートメントを結合する方法と複数行ステートメントを続行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="545e8-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="545e8-112">宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-112">Declaration statements</span></span>

<span data-ttu-id="545e8-113">宣言ステートメントを使用して名前を指定し、プロシージャ、変数、プロパティ、配列、および定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="545e8-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="545e8-114">プログラミング要素を宣言するときに、そのデータ型、アクセス レベル、およびスコープも定義できます。</span><span class="sxs-lookup"><span data-stu-id="545e8-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="545e8-115">詳細については、次を参照してください。[宣言された要素の特性](./declared-elements/declared-element-characteristics.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="545e8-116">次の例には、3 つの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="545e8-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="545e8-117">最初の宣言は、`Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="545e8-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="545e8-118">その照合と共に`End Sub`という名前のプロシージャ宣言ステートメントでは、`applyFormat`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="545e8-119">指定する`applyFormat`は`Public`、つまり、それを参照できる任意のコードで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="545e8-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="545e8-120">2 番目の宣言は、`Const`ステートメントでは、定数を宣言しますが、`limit`を指定して、`Integer`データ型と 33 の値。</span><span class="sxs-lookup"><span data-stu-id="545e8-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="545e8-121">3 番目の宣言は、`Dim`ステートメントでは、変数を宣言しますが、`thisWidget`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="545e8-122">データ型は、特定のオブジェクト、つまりからオブジェクトが作成された、`Widget`クラス。</span><span class="sxs-lookup"><span data-stu-id="545e8-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="545e8-123">任意の基本データ型、または使用するアプリケーションで公開されているオブジェクトの種類の変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="545e8-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="545e8-124">初期値</span><span class="sxs-lookup"><span data-stu-id="545e8-124">Initial Values</span></span>

<span data-ttu-id="545e8-125">宣言ステートメントを含むコードを実行すると、Visual Basic は、宣言された要素に必要なメモリを予約します。</span><span class="sxs-lookup"><span data-stu-id="545e8-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="545e8-126">要素には、値が含まれる、Visual Basic により、データ型の既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="545e8-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="545e8-127">詳細については、「動作」を参照してください[Dim ステートメント](../../language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="545e8-128">次の例に示すように、その宣言の一部として変数に初期値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="545e8-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="545e8-129">使用して宣言するときに、明示的にそのクラスのインスタンスを作成する変数がオブジェクト変数の場合は、 [New 演算子](../../../visual-basic/language-reference/operators/new-operator.md)キーワードでは、次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="545e8-130">宣言ステートメントに達するまで、宣言ステートメントで指定した初期値が変数に代入しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="545e8-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="545e8-131">それまでは、変数には、そのデータ型の既定値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="545e8-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="545e8-132">実行可能なステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-132">Executable statements</span></span>

<span data-ttu-id="545e8-133">実行可能なステートメントは、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="545e8-133">An executable statement performs an action.</span></span> <span data-ttu-id="545e8-134">式を評価するプロシージャのコードでいくつかのステートメントをループ処理する別の場所に分岐を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="545e8-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="545e8-135">代入ステートメントは、実行可能なステートメントの特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="545e8-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="545e8-136">次の例では、`If...Then...Else`変数の値に基づくコードの別のブロックを実行する構造を制御します。</span><span class="sxs-lookup"><span data-stu-id="545e8-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="545e8-137">各コード ブロック内で、`For...Next`ループの実行回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="545e8-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="545e8-138">`If`ステートメントは上記の例では、パラメーターの値を確認します。`clockwise`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="545e8-139">値が場合`True`、呼び出し、`spinClockwise`メソッドの`aWidget`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="545e8-140">値が場合`False`、呼び出し、`spinCounterClockwise`メソッドの`aWidget`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="545e8-141">`If...Then...Else`制御構造が終わる`End If`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="545e8-142">`For...Next`各ブロック内でループ メソッドを呼び出して適切な時間数の値と等しく、`revolutions`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="545e8-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="545e8-143">代入ステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-143">Assignment statements</span></span>

<span data-ttu-id="545e8-144">代入ステートメントは、代入演算子の右側にある値を取得するので構成されている、代入演算を実行 (`=`) 次の例のように、左の要素に格納することです。</span><span class="sxs-lookup"><span data-stu-id="545e8-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="545e8-145">前の例では、代入ステートメントは、変数のリテラル値 42 を格納`v`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="545e8-146">対象となるプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="545e8-146">Eligible programming elements</span></span>

<span data-ttu-id="545e8-147">代入演算子の左側にあるプログラミング要素は、そのまま使用し、値を格納できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="545e8-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="545e8-148">つまり、変数またはプロパティが必要があります[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)、または配列要素があります。</span><span class="sxs-lookup"><span data-stu-id="545e8-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="545e8-149">代入ステートメントのコンテキストでこのような要素とも呼ばれます、*左辺値*の「左辺値です」。</span><span class="sxs-lookup"><span data-stu-id="545e8-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="545e8-150">代入演算子の右側にある値は、リテラル、定数、変数、プロパティ、配列の要素、その他の式、または関数呼び出しの組み合わせで構成される、式によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="545e8-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="545e8-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="545e8-152">上記の例では、変数に保持された値を追加します。`y`変数に保持された値に`z`、し、関数の呼び出しによって返される値を追加`findResult`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="545e8-153">この式の合計値が変数に格納し、`x`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="545e8-154">代入ステートメントでのデータ型</span><span class="sxs-lookup"><span data-stu-id="545e8-154">Data types in assignment statements</span></span>

<span data-ttu-id="545e8-155">数値の値に加えて、代入演算子は割り当てることができますも`String`値は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="545e8-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="545e8-156">割り当てることもできます`Boolean`値のいずれかを使用して、`Boolean`リテラルまたは`Boolean`式として次の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="545e8-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="545e8-157">同様のプログラミング要素に適切な値を割り当てることができます、 `Char`、 `Date`、または`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="545e8-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="545e8-158">そのインスタンスの作成元のクラスを指定して宣言された要素をオブジェクトのインスタンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="545e8-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="545e8-159">複合代入ステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-159">Compound assignment statements</span></span>

<span data-ttu-id="545e8-160">*複合代入ステートメント*最初プログラミング要素に割り当てる前に、式に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="545e8-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="545e8-161">次の例は、これらの演算子のいずれかを示しています`+=`右側の式の値によって、演算子の左側にある変数の値をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="545e8-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="545e8-162">前の例の値に 1 を加算する`n`でその新しい値を格納して`n`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="545e8-163">短縮形は、次のステートメントのと同じです。</span><span class="sxs-lookup"><span data-stu-id="545e8-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="545e8-164">この種類の演算子を使用して、さまざまな複合代入演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="545e8-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="545e8-165">これらの演算子とその詳細情報の一覧は、次を参照してください。[代入演算子](../../../visual-basic/language-reference/operators/assignment-operators.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="545e8-166">連結代入演算子 (`&=`) の既存の末尾に文字列を追加する場合に便利ですが、次の例に示すように、文字列します。</span><span class="sxs-lookup"><span data-stu-id="545e8-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="545e8-167">代入ステートメントでの型変換</span><span class="sxs-lookup"><span data-stu-id="545e8-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="545e8-168">変換先の要素に適切なデータ型の変数、プロパティ、または配列要素に割り当てる値がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="545e8-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="545e8-169">一般に、目的の要素のと同じデータ型の値を生成しようとする必要があります。</span><span class="sxs-lookup"><span data-stu-id="545e8-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="545e8-170">ただし、一部の種類は、割り当ての際に他の型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="545e8-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="545e8-171">データ型の間で変換する方法については、次を参照してください。 [Visual Basic における型変換](./data-types/type-conversions.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="545e8-172">簡単に言うと Visual Basic は、他の型、拡大変換に指定された型の値を自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="545e8-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="545e8-173">A*拡大変換*は 1 つを常に実行時に成功すると、すべてのデータが失われない。</span><span class="sxs-lookup"><span data-stu-id="545e8-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="545e8-174">Visual Basic の変換など、`Integer`値を`Double`適切な場合、ため`Integer`に拡大変換されます`Double`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="545e8-175">詳細については、[拡大変換と縮小変換](./data-types/widening-and-narrowing-conversions.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="545e8-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="545e8-176">*縮小変換*(拡大変換がないもの) の実行時に、エラーまたはデータ損失のリスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="545e8-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="545e8-177">縮小変換を明示的に実行するには、型変換関数を使用して、または暗黙的に設定してすべての変換を実行するコンパイラに指示できます`Option Strict Off`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="545e8-178">詳細については、次を参照してください。[暗黙的および明示的な変換](./data-types/implicit-and-explicit-conversions.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="545e8-179">1 つの行に複数のステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="545e8-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="545e8-180">コロンで区切られた 1 行に複数のステートメントがあることができます (`:`) 文字。</span><span class="sxs-lookup"><span data-stu-id="545e8-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="545e8-181">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="545e8-182">場合によっては便利な場合の構文は、この形式により、コード読み取りおよびメンテナンスが困難です。</span><span class="sxs-lookup"><span data-stu-id="545e8-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="545e8-183">そのため、行に 1 つのステートメントを維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="545e8-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="545e8-184">複数の行にまたがるステートメント</span><span class="sxs-lookup"><span data-stu-id="545e8-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="545e8-185">ステートメントは、通常は 1 つの行に収まるが長すぎるときに、スペースとアンダー スコア文字で構成される行連結シーケンスを使用して次の行に続けることができます (`_`) 後にキャリッジ リターン。</span><span class="sxs-lookup"><span data-stu-id="545e8-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="545e8-186">次の例では、`MsgBox`に 2 行の実行可能ステートメントが続きます。</span><span class="sxs-lookup"><span data-stu-id="545e8-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="545e8-187">暗黙的な行継続</span><span class="sxs-lookup"><span data-stu-id="545e8-187">Implicit line continuation</span></span>

<span data-ttu-id="545e8-188">多くの場合、せずに続行できますステートメントを次の連続する行にアンダー スコア文字を使用して (`_`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="545e8-189">次の構文要素は、次のコード行で暗黙的に、ステートメントを続行します。</span><span class="sxs-lookup"><span data-stu-id="545e8-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="545e8-190">コンマの後に (`,`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-190">After a comma (`,`).</span></span> <span data-ttu-id="545e8-191">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="545e8-192">始めかっこの後 (`(`) または閉じかっこの前に、(`)`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="545e8-193">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="545e8-194">かっこの後 (`{`) または右中かっこの前に (`}`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="545e8-195">例:</span><span class="sxs-lookup"><span data-stu-id="545e8-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="545e8-196">詳細については、次を参照してください。[オブジェクト初期化子。名前付きの匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)または[コレクション初期化子](./collection-initializers/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="545e8-197">埋め込み式、開かれた後 (`<%=`) または埋め込み式の終了前に (`%>`) XML リテラル内で。</span><span class="sxs-lookup"><span data-stu-id="545e8-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="545e8-198">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="545e8-199">詳細については、次を参照してください。 [XML での埋め込み式](./xml/embedded-expressions-in-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="545e8-200">連結演算子の後に (`&`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="545e8-201">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="545e8-202">詳細については、次を参照してください。[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="545e8-203">代入演算子の後 (`=`、 `&=`、 `:=`、 `+=`、 `-=`、 `*=`、 `/=`、 `\=`、 `^=`、 `<<=`、 `>>=`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="545e8-204">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="545e8-205">詳細については、次を参照してください。[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="545e8-206">二項演算子の後 (`+`、 `-`、 `/`、 `*`、 `Mod`、 `<>`、 `<`、 `>`、 `<=`、 `>=`、 `^`、 `>>`、`<<`、 `And`、 `AndAlso`、 `Or`、 `OrElse`、 `Like`、 `Xor`) 式内で。</span><span class="sxs-lookup"><span data-stu-id="545e8-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="545e8-207">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="545e8-208">詳細については、次を参照してください。[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="545e8-209">後に、`Is`と`IsNot`演算子。</span><span class="sxs-lookup"><span data-stu-id="545e8-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="545e8-210">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="545e8-211">詳細については、次を参照してください。[機能別の演算子一覧](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="545e8-212">メンバー修飾子文字の後 (`.`) とメンバー名の前にします。</span><span class="sxs-lookup"><span data-stu-id="545e8-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="545e8-213">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="545e8-214">ただし、行連結文字を含める必要があります (`_`) を使用するメンバーの修飾子文字を以下に、`With`ステートメントまたは型の初期化リスト内の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="545e8-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="545e8-215">代入演算子の後で改行を検討してください (たとえば、 `=`) を使用する場合`With`ステートメントやオブジェクトの初期化リスト。</span><span class="sxs-lookup"><span data-stu-id="545e8-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="545e8-216">例:</span><span class="sxs-lookup"><span data-stu-id="545e8-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="545e8-217">詳細については、次を参照してください[としています... ステートメントで終了して](../../../visual-basic/language-reference/statements/with-end-with-statement.md)または[オブジェクト初期化子。名前付きの匿名型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="545e8-218">XML 軸プロパティ修飾子の後 (`.`または`.@`または`...`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="545e8-219">ただし、行連結文字を含める必要があります (`_`) を使用するときにメンバー修飾子を指定すると、`With`キーワード。</span><span class="sxs-lookup"><span data-stu-id="545e8-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="545e8-220">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="545e8-221">詳細については、次を参照してください。 [XML 軸プロパティ](../../../visual-basic/language-reference/xml-axis/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="545e8-222">小後-不等号 (<)、または前に、大きい-不等号 (`>`) 属性を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="545e8-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="545e8-223">大きい後も、不等号 (`>`) 属性を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="545e8-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="545e8-224">ただし、行連結文字を含める必要があります (`_`) アセンブリ レベルまたはモジュール レベルの属性を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="545e8-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="545e8-225">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="545e8-226">詳細については、次を参照してください。[属性の概要](../../../visual-basic/programming-guide/concepts/attributes/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="545e8-227">クエリ演算子の前後に (`Aggregate`、 `Distinct`、 `From`、 `Group By`、 `Group Join`、 `Join`、 `Let`、 `Order By`、 `Select`、 `Skip`、 `Skip While`、 `Take`、 `Take While`、 `Where`、 `In`、 `Into`、 `On`、 `Ascending`、および`Descending`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="545e8-228">複数のキーワードで構成されているクエリ演算子のキーワードの間に行を分割することはできません (`Order By`、 `Group Join`、 `Take While`、および`Skip While`)。</span><span class="sxs-lookup"><span data-stu-id="545e8-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="545e8-229">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="545e8-230">詳細については、次を参照してください。[クエリ](../../../visual-basic/language-reference/queries/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="545e8-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="545e8-231">後に、`In`キーワード、`For Each`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="545e8-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="545e8-232">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="545e8-233">詳細については、[For Each...Next ステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="545e8-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="545e8-234">後に、`From`コレクション初期化子内のキーワード。</span><span class="sxs-lookup"><span data-stu-id="545e8-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="545e8-235">例えば:</span><span class="sxs-lookup"><span data-stu-id="545e8-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="545e8-236">詳細については、「[コレクション初期化子](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="545e8-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="545e8-237">コメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="545e8-237">Adding comments</span></span>

<span data-ttu-id="545e8-238">ソース コードは自明ですが、それを記述したプログラマにも常にします。</span><span class="sxs-lookup"><span data-stu-id="545e8-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="545e8-239">そのコードを文書化するには、そのため、プログラマのほとんどに利用リベラル派埋め込まれたコメント。</span><span class="sxs-lookup"><span data-stu-id="545e8-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="545e8-240">コード内のコメントには、プロシージャ、またはすべてのユーザーの読み取りまたは後で使用する特定の命令を説明します。</span><span class="sxs-lookup"><span data-stu-id="545e8-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="545e8-241">Visual Basic は、コンパイル時に、コメントを無視し、コンパイル済みコードには影響しません。</span><span class="sxs-lookup"><span data-stu-id="545e8-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="545e8-242">コメント行はアポストロフィで始まります (`'`) または`REM`スペースします。</span><span class="sxs-lookup"><span data-stu-id="545e8-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="545e8-243">追加できる任意の場所コードでは、以外の文字列内で。</span><span class="sxs-lookup"><span data-stu-id="545e8-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="545e8-244">ステートメントにコメントを追加するには、アポストロフィを挿入または`REM`後、ステートメントの後に、コメント、します。</span><span class="sxs-lookup"><span data-stu-id="545e8-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="545e8-245">コメントは、独自の個別の行に移動できます。</span><span class="sxs-lookup"><span data-stu-id="545e8-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="545e8-246">次の例では、これらの可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="545e8-247">コンパイル エラーの確認</span><span class="sxs-lookup"><span data-stu-id="545e8-247">Checking compilation errors</span></span>

<span data-ttu-id="545e8-248">後のコード行を入力する場合は、(エラー メッセージが表示されることも) 青色の波下線付きの行が表示されます、ステートメントに構文エラーがあります。</span><span class="sxs-lookup"><span data-stu-id="545e8-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="545e8-249">(タスク一覧で検索またはポインターを合わせると、マウス ポインターをエラーとエラー メッセージを読み取って) で新機能については、ステートメントで間違ったと、修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="545e8-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="545e8-250">コードですべての構文エラーを修正するまで、プログラムは正常にコンパイルは失敗します。</span><span class="sxs-lookup"><span data-stu-id="545e8-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="545e8-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="545e8-251">Related sections</span></span>

|<span data-ttu-id="545e8-252">用語</span><span class="sxs-lookup"><span data-stu-id="545e8-252">Term</span></span>|<span data-ttu-id="545e8-253">定義</span><span class="sxs-lookup"><span data-stu-id="545e8-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="545e8-254">代入演算子</span><span class="sxs-lookup"><span data-stu-id="545e8-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="545e8-255">代入演算子をカバーするなどの言語リファレンスのページへのリンクを提供`=`、 `*=`、および`&=`します。</span><span class="sxs-lookup"><span data-stu-id="545e8-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="545e8-256">演算子および式</span><span class="sxs-lookup"><span data-stu-id="545e8-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="545e8-257">新しい値を取得する演算子を含む要素を結合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="545e8-258">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="545e8-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="545e8-259">1 つのステートメントを複数の行に分割する方法と同じ行に複数のステートメントを配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="545e8-260">方法: ステートメントへのラベル付け</span><span class="sxs-lookup"><span data-stu-id="545e8-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="545e8-261">コードの行にラベル付けする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="545e8-261">Shows how to label a line of code.</span></span>|
