---
description: if-else - C# リファレンス
title: if-else - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: e2de84807a049bd47ea277db9fb010d0c2e4857d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118508"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="9b6c5-103">if-else (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="9b6c5-103">if-else (C# Reference)</span></span>

<span data-ttu-id="9b6c5-104">`if` ステートメントは、ブール式の値に基づいて実行するステートメントを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-104">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="9b6c5-105">次の例では、 `bool` 変数 `condition` を `true` に設定してから、 `if` ステートメントにチェックインします。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-105">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="9b6c5-106">出力は `The variable is set to true.`になります。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-106">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="9b6c5-107">このトピックの例を実行するには、コンソール アプリケーションの `Main` メソッドに例を挿入します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="9b6c5-108">C# の `if` ステートメントは、次の例に示すように 2 つの形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

<span data-ttu-id="9b6c5-109">`if-else` ステートメントで、 `condition` が true に評価されると、 `then-statement` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="9b6c5-110">`condition` が false の場合は、 `else-statement` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="9b6c5-111">`condition` が同時に true と false に評価されることはないため、 `then-statement` ステートメントの `else-statement` と `if-else` の両方が実行されることは決してありません。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="9b6c5-112">`then-statement` または `else-statement` が実行された後、制御は `if` ステートメントの後のステートメントに移ります。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="9b6c5-113">`else` ステートメントが含まれない `if` ステートメントで `condition` が true に評価された場合は、 `then-statement` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="9b6c5-114">`condition` が false の場合、制御は `if` ステートメントの後のステートメントに移ります。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="9b6c5-115">`then-statement` と `else-statement` はどちらも、中かっこ (`{}`) で囲まれた 1 つのステートメントまたは複数のステートメントで構成できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="9b6c5-116">ステートメントが 1 つの場合、中かっこは省略可能ですが、使用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-116">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="9b6c5-117">`then-statement` および `else-statement` では、任意の種類のステートメントを使用できます。元の `if` ステートメント内に別の `if` ステートメントを入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="9b6c5-118">入れ子になった `if` ステートメントでは、各 `else` 句が、対応する `if` がない最後の `else`に属します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="9b6c5-119">次の例では、 `Result1` と `m > 10` の両方が true に評価されると、 `n > 20` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="9b6c5-120">`m > 10` が true で `n > 20` が false の場合は、 `Result2` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="9b6c5-121">代わりに `Result2` が false の場合に `(m > 10)` を表示させるには、次の例に示すように、中かっこを使用して入れ子になった `if` の開始と終了を設定することで、その関連付けを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-121">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="9b6c5-122">条件 `(m > 10)` が false に評価されると、`Result2` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-122">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="9b6c5-123">例</span><span class="sxs-lookup"><span data-stu-id="9b6c5-123">Example</span></span>

<span data-ttu-id="9b6c5-124">次の例では、キーボードから文字を入力すると、プログラムが、入れ子になった `if` ステートメントを実行して、入力された文字が英字かどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-124">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="9b6c5-125">入力された文字が英字である場合、プログラムはその文字が小文字と大文字のどちらであるかを判別します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-125">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="9b6c5-126">いずれの場合も、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-126">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="9b6c5-127">例</span><span class="sxs-lookup"><span data-stu-id="9b6c5-127">Example</span></span>

<span data-ttu-id="9b6c5-128">以下の部分的なコードに示すように、`if` ステートメントを else ブロック内に入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-128">You can also nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="9b6c5-129">この例では、2 つの else ブロックと 1 つの then ブロックの中で `if` ステートメントを入れ子にしています。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-129">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="9b6c5-130">コメントに、各ブロックでどの条件が true または false であるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-130">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="9b6c5-131">例</span><span class="sxs-lookup"><span data-stu-id="9b6c5-131">Example</span></span>

<span data-ttu-id="9b6c5-132">この例では、入力された文字が小文字、大文字、または数値のいずれであるかを判別します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-132">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="9b6c5-133">3 つすべての条件が false の場合、文字は英数字ではありません。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-133">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="9b6c5-134">この例では、いずれの場合もメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-134">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="9b6c5-135">else ブロックまたは then ブロック内のステートメントを任意の有効なステートメントにできるように、条件には任意の有効なブール式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-135">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="9b6c5-136">`!`、`&&`、`||`、`&`、`|`、`^` などの[論理演算子](../operators/boolean-logical-operators.md)を使用して複合条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-136">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="9b6c5-137">次のコードに例を示します。</span><span class="sxs-lookup"><span data-stu-id="9b6c5-137">The following code shows examples.</span></span>

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a><span data-ttu-id="9b6c5-138">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="9b6c5-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9b6c5-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b6c5-139">See also</span></span>

- [<span data-ttu-id="9b6c5-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="9b6c5-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b6c5-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="9b6c5-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9b6c5-142">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="9b6c5-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9b6c5-143">?:演算子</span><span class="sxs-lookup"><span data-stu-id="9b6c5-143">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="9b6c5-144">if-else ステートメント (C++)</span><span class="sxs-lookup"><span data-stu-id="9b6c5-144">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="9b6c5-145">switch</span><span class="sxs-lookup"><span data-stu-id="9b6c5-145">switch</span></span>](switch.md)
