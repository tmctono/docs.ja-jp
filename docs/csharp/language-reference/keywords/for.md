---
title: for ステートメント - C# リファレンス
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: fc6a23cabd93323cacc33dfc4388116881c1fc84
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552261"
---
# <a name="for-c-reference"></a><span data-ttu-id="731b3-102">for (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="731b3-102">for (C# reference)</span></span>

<span data-ttu-id="731b3-103">`for` ステートメントでは、指定されたブール式が `true` と評価される間に、ステートメントまたはステートメント ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="731b3-103">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="731b3-104">`for` ステートメント ブロック内の任意の位置で、[break](break.md) ステートメントを使ってループから抜けることができます。または、[continue](continue.md) ステートメントを使って、ループ内の次の繰り返しにスキップできます。</span><span class="sxs-lookup"><span data-stu-id="731b3-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="731b3-105">また、[goto](goto.md)、[return](return.md)、[throw](throw.md) ステートメントのいずれかを使って `for` ループを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="731b3-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="731b3-106">`for` ステートメントの構造</span><span class="sxs-lookup"><span data-stu-id="731b3-106">Structure of the `for` statement</span></span>

<span data-ttu-id="731b3-107">`for` ステートメントには、*initializer*、*condition*、*iterator* のセクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="731b3-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="731b3-108">3 つのセクションはすべて省略可能です。</span><span class="sxs-lookup"><span data-stu-id="731b3-108">All three sections are optional.</span></span> <span data-ttu-id="731b3-109">ループの本体は、ステートメントまたはステートメントのブロックのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="731b3-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="731b3-110">次の例では、`for` ステートメントと定義されているすべてのセクションが示されています。</span><span class="sxs-lookup"><span data-stu-id="731b3-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="731b3-111">*initializer* セクション</span><span class="sxs-lookup"><span data-stu-id="731b3-111">The *initializer* section</span></span>

<span data-ttu-id="731b3-112">*initializer* セクション内のステートメントは、ループに入る前に 1 回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="731b3-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="731b3-113">*initializer* セクションは、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="731b3-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="731b3-114">ローカル ループ変数の宣言と初期化。ループの外からアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="731b3-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="731b3-115">次に列挙した 0 個以上のステートメント式 (コンマ区切り)。</span><span class="sxs-lookup"><span data-stu-id="731b3-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="731b3-116">[代入](../operators/assignment-operator.md)ステートメント</span><span class="sxs-lookup"><span data-stu-id="731b3-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="731b3-117">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="731b3-117">invocation of a method</span></span>

  - <span data-ttu-id="731b3-118">前置または後置の[インクリメント](../operators/arithmetic-operators.md#increment-operator-)式 (`++i`、`i++` など)</span><span class="sxs-lookup"><span data-stu-id="731b3-118">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="731b3-119">前置または後置の[デクリメント](../operators/arithmetic-operators.md#decrement-operator---)式 (`--i`、`i--` など)</span><span class="sxs-lookup"><span data-stu-id="731b3-119">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="731b3-120">[new](../operators/new-operator.md) 演算子を使用したオブジェクト作成</span><span class="sxs-lookup"><span data-stu-id="731b3-120">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="731b3-121">[await](../operators/await.md) 式</span><span class="sxs-lookup"><span data-stu-id="731b3-121">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="731b3-122">上記の例の *initializer* セクションは、ローカル ループ変数 `i` を宣言して初期化します。</span><span class="sxs-lookup"><span data-stu-id="731b3-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="731b3-123">*condition* セクション</span><span class="sxs-lookup"><span data-stu-id="731b3-123">The *condition* section</span></span>

<span data-ttu-id="731b3-124">*condition* セクション (ある場合) は、ブール式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="731b3-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="731b3-125">その式はループの反復の前に毎回評価されます。</span><span class="sxs-lookup"><span data-stu-id="731b3-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="731b3-126">*condition* セクションが存在しないか、ブール式が `true` に評価される場合、次のループの反復が実行されます。そうでない場合は、ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="731b3-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="731b3-127">上記の例の*condition* セクションでは、ローカル ループ変数の値に基づいて、ループが終了するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="731b3-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="731b3-128">*iterator* セクション</span><span class="sxs-lookup"><span data-stu-id="731b3-128">The *iterator* section</span></span>

<span data-ttu-id="731b3-129">ループ本体の反復処理が終わるたびに実行される処理を *iterator* セクションで定義します。</span><span class="sxs-lookup"><span data-stu-id="731b3-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="731b3-130">*iterator* セクションには、次のステートメント式を 0 個以上、コンマで区切って記述します。</span><span class="sxs-lookup"><span data-stu-id="731b3-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="731b3-131">[代入](../operators/assignment-operator.md)ステートメント</span><span class="sxs-lookup"><span data-stu-id="731b3-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="731b3-132">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="731b3-132">invocation of a method</span></span>

- <span data-ttu-id="731b3-133">前置または後置の[インクリメント](../operators/arithmetic-operators.md#increment-operator-)式 (`++i`、`i++` など)</span><span class="sxs-lookup"><span data-stu-id="731b3-133">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="731b3-134">前置または後置の[デクリメント](../operators/arithmetic-operators.md#decrement-operator---)式 (`--i`、`i--` など)</span><span class="sxs-lookup"><span data-stu-id="731b3-134">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="731b3-135">[new](../operators/new-operator.md) 演算子を使用したオブジェクト作成</span><span class="sxs-lookup"><span data-stu-id="731b3-135">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="731b3-136">[await](../operators/await.md) 式</span><span class="sxs-lookup"><span data-stu-id="731b3-136">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="731b3-137">上記の例の *iterator* セクションでは、ローカルのループ変数をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="731b3-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="731b3-138">使用例</span><span class="sxs-lookup"><span data-stu-id="731b3-138">Examples</span></span>

<span data-ttu-id="731b3-139">次の例は、`for` ステートメント セクションのやや特殊な使用例です。*initializer* セクションで外部ループ変数に値を代入し、*initializer* セクションと *iterator* セクションの両方でメソッドを呼び出しています。さらに、*iterator* セクションで 2 つの変数の値を変更しています。</span><span class="sxs-lookup"><span data-stu-id="731b3-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="731b3-140">**[実行]** を選択して、コード例を実行します。</span><span class="sxs-lookup"><span data-stu-id="731b3-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="731b3-141">その後に、コードを変更し、もう一度実行することができます。</span><span class="sxs-lookup"><span data-stu-id="731b3-141">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="731b3-142">次の例では、無限 `for` ループが定義されます。</span><span class="sxs-lookup"><span data-stu-id="731b3-142">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="731b3-143">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="731b3-143">C# language specification</span></span>

<span data-ttu-id="731b3-144">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の [for ステートメント](~/_csharplang/spec/statements.md#the-for-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="731b3-144">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="731b3-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="731b3-145">See also</span></span>

- [<span data-ttu-id="731b3-146">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="731b3-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="731b3-147">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="731b3-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="731b3-148">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="731b3-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="731b3-149">foreach、in</span><span class="sxs-lookup"><span data-stu-id="731b3-149">foreach, in</span></span>](foreach-in.md)
