---
description: => 演算子 - C# リファレンス
title: => 演算子 - C# リファレンス
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6a4df3a4bd358b87f98ff1bd5a3f624b1029a73b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128362"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c4267-103">=> 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c4267-103">=> operator (C# reference)</span></span>

<span data-ttu-id="c4267-104">`=>` トークンは、[ラムダ演算子](#lambda-operator)、および[式本体の定義](#expression-body-definition)におけるメンバー名とメンバー実装の区切り記号という 2 つの形式でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4267-104">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="c4267-105">ラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="c4267-105">Lambda operator</span></span>

<span data-ttu-id="c4267-106">[ラムダ式](lambda-expressions.md)では、ラムダ演算子 `=>` により、左側の入力パラメーターと右側のラムダ本体とが分けられます。</span><span class="sxs-lookup"><span data-stu-id="c4267-106">In [lambda expressions](lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="c4267-107">次の例は、メソッド構文で [LINQ](../../programming-guide/concepts/linq/index.md) 機能を使用して、ラムダ式の使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4267-107">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="c4267-108">ラムダ式の入力パラメーターは、コンパイル時に厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="c4267-108">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="c4267-109">前の例のように、コンパイラが入力パラメーターの型を推論できる場合は、型宣言を省略できます。</span><span class="sxs-lookup"><span data-stu-id="c4267-109">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="c4267-110">入力パラメーターの型を指定する必要がある場合は、次の例に示すように、パラメーターごとに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4267-110">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="c4267-111">次の例は、入力パラメーターを含まないラムダ式を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4267-111">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="c4267-112">詳細については、「[ラムダ式](lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4267-112">For more information, see [Lambda expressions](lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="c4267-113">式本体の定義</span><span class="sxs-lookup"><span data-stu-id="c4267-113">Expression body definition</span></span>

<span data-ttu-id="c4267-114">式本体の定義には、次の一般的な構文があります。</span><span class="sxs-lookup"><span data-stu-id="c4267-114">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="c4267-115">ここで、`expression` には有効な式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4267-115">where `expression` is a valid expression.</span></span> <span data-ttu-id="c4267-116">`expression` の戻り値の型は、メンバーの戻り値の型に暗黙的に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4267-116">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="c4267-117">メンバーの戻り値の型が `void` の場合や、メンバーがコンストラクター、ファイナライザー、プロパティまたはインデクサー `set` のアクセサーの場合、`expression` は "[*ステートメント式*](~/_csharplang/spec/statements.md#expression-statements)" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4267-117">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="c4267-118">式の結果が破棄されるため、その式の戻り値の型は任意の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4267-118">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="c4267-119">次の例は、`Person.ToString` メソッドの式本体の定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4267-119">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="c4267-120">これは、次のメソッド定義の短縮形バージョンです。</span><span class="sxs-lookup"><span data-stu-id="c4267-120">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="c4267-121">メソッド、演算子、および読み取り専用プロパティの式本体の定義は、C# 6 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4267-121">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="c4267-122">コンストラクター、ファイナライザー、プロパティ アクセサー、およびインデクサー アクセサーの式本体の定義は、C# 7.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4267-122">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="c4267-123">詳細については、「[式形式のメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4267-123">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c4267-124">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="c4267-124">Operator overloadability</span></span>

<span data-ttu-id="c4267-125">`=>` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="c4267-125">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c4267-126">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c4267-126">C# language specification</span></span>

<span data-ttu-id="c4267-127">ラムダ演算子の詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[匿名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4267-127">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4267-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4267-128">See also</span></span>

- [<span data-ttu-id="c4267-129">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c4267-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c4267-130">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="c4267-130">C# operators and expressions</span></span>](index.md)
