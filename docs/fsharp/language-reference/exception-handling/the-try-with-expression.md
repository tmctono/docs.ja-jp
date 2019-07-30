---
title: 例外:try...with 式
description: 例外処理の F# の 'try...with' 式を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630252"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="5d479-103">例外:try...with 式</span><span class="sxs-lookup"><span data-stu-id="5d479-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="5d479-104">このトピックで説明します、`try...with`式、F# 言語での例外処理に使用される式。</span><span class="sxs-lookup"><span data-stu-id="5d479-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d479-105">構文</span><span class="sxs-lookup"><span data-stu-id="5d479-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="5d479-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d479-106">Remarks</span></span>

<span data-ttu-id="5d479-107">式`try...with`は、でF#例外を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d479-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="5d479-108">これは、の`try...catch` C#ステートメントに似ています。</span><span class="sxs-lookup"><span data-stu-id="5d479-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="5d479-109">前の構文では、 *expression1*のコードが例外を生成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d479-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="5d479-110">式`try...with`は値を返します。</span><span class="sxs-lookup"><span data-stu-id="5d479-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="5d479-111">例外がスローされない場合、式全体が*expression1*の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5d479-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="5d479-112">例外がスローされた場合は、各*パターン*が例外で比較され、最初に一致するパターンについて、その分岐の*例外ハンドラー*と呼ばれる対応する*式*が実行され、全体の式が実行されます。この例外ハンドラーの式の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5d479-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="5d479-113">一致するパターンがない場合、例外は、一致するハンドラーが見つかるまで呼び出し履歴を上位に伝達します。</span><span class="sxs-lookup"><span data-stu-id="5d479-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="5d479-114">例外ハンドラー内の各式から返される値の型は、 `try`ブロック内の式から返される型と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d479-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="5d479-115">多くの場合、エラーが発生したという事実は、各例外ハンドラーの式から返される有効な値がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5d479-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="5d479-116">よく使用されるパターンは、式の型がオプション型であることです。</span><span class="sxs-lookup"><span data-stu-id="5d479-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="5d479-117">次のコード例は、このパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d479-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="5d479-118">例外は、.NET 例外か F# の例外になることができます。</span><span class="sxs-lookup"><span data-stu-id="5d479-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="5d479-119">`exception`キーワードを使用F#して例外を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5d479-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="5d479-120">さまざまなパターンを使用して、例外の種類やその他の条件をフィルター処理できます。次の表に、オプションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5d479-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="5d479-121">パターン</span><span class="sxs-lookup"><span data-stu-id="5d479-121">Pattern</span></span>|<span data-ttu-id="5d479-122">説明</span><span class="sxs-lookup"><span data-stu-id="5d479-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="5d479-123">:?</span><span class="sxs-lookup"><span data-stu-id="5d479-123">:?</span></span> <span data-ttu-id="5d479-124">*exception-type*</span><span class="sxs-lookup"><span data-stu-id="5d479-124">*exception-type*</span></span>|<span data-ttu-id="5d479-125">指定された .NET 例外の種類と一致します。</span><span class="sxs-lookup"><span data-stu-id="5d479-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="5d479-126">:?</span><span class="sxs-lookup"><span data-stu-id="5d479-126">:?</span></span> <span data-ttu-id="5d479-127">*例外-* *識別子*としての型</span><span class="sxs-lookup"><span data-stu-id="5d479-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="5d479-128">指定された .NET 例外の種類と一致しますが、例外には名前付きの値が与えられます。</span><span class="sxs-lookup"><span data-stu-id="5d479-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="5d479-129">*例外-名前*(*引数*)</span><span class="sxs-lookup"><span data-stu-id="5d479-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="5d479-130">は、 F#例外の種類と一致し、引数をバインドします。</span><span class="sxs-lookup"><span data-stu-id="5d479-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="5d479-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="5d479-131">*identifier*</span></span>|<span data-ttu-id="5d479-132">任意の例外を一致させ、その名前を例外オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="5d479-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="5d479-133">**これはと等価です。System.exception_識別子_とし**ての例外</span><span class="sxs-lookup"><span data-stu-id="5d479-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="5d479-134">*条件*の場合の*識別子*</span><span class="sxs-lookup"><span data-stu-id="5d479-134">*identifier* when *condition*</span></span>|<span data-ttu-id="5d479-135">条件が true の場合、すべての例外に一致します。</span><span class="sxs-lookup"><span data-stu-id="5d479-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="5d479-136">使用例</span><span class="sxs-lookup"><span data-stu-id="5d479-136">Examples</span></span>

<span data-ttu-id="5d479-137">次のコード例は、さまざまな例外ハンドラーパターンの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d479-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="5d479-138">コンストラクトは、式と`try...finally`は別の式です。 `try...with`</span><span class="sxs-lookup"><span data-stu-id="5d479-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="5d479-139">したがって、コードに`with`ブロック`finally`とブロックの両方が必要な場合は、2つの式を入れ子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d479-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="5d479-140">は、非同期`try...with`ワークフローやその他の計算式で使用できます。その場合、 `try...with`式のカスタマイズされたバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d479-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="5d479-141">詳細については、「[非同期ワークフロー](../asynchronous-workflows.md)」と「[コンピュテーション式](../computation-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d479-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d479-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d479-142">See also</span></span>

- [<span data-ttu-id="5d479-143">例外処理</span><span class="sxs-lookup"><span data-stu-id="5d479-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="5d479-144">例外の種類</span><span class="sxs-lookup"><span data-stu-id="5d479-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="5d479-145">例外: `try...finally`式</span><span class="sxs-lookup"><span data-stu-id="5d479-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
