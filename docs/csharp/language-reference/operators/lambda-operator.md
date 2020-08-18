---
title: => 演算子 - C# リファレンス
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 30e1a3546f83a0a1ba5b1363238878868e94ab93
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063134"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4163b-102">=> 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4163b-102">=> operator (C# reference)</span></span>

<span data-ttu-id="4163b-103">`=>` トークンは、[ラムダ演算子](#lambda-operator)、および[式本体の定義](#expression-body-definition)におけるメンバー名とメンバー実装の区切り記号という 2 つの形式でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4163b-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="4163b-104">ラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="4163b-104">Lambda operator</span></span>

<span data-ttu-id="4163b-105">[ラムダ式](lambda-expressions.md)では、ラムダ演算子 `=>` により、左側の入力パラメーターと右側のラムダ本体とが分けられます。</span><span class="sxs-lookup"><span data-stu-id="4163b-105">In [lambda expressions](lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="4163b-106">次の例は、メソッド構文で [LINQ](../../programming-guide/concepts/linq/index.md) 機能を使用して、ラムダ式の使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4163b-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="4163b-107">ラムダ式の入力パラメーターは、コンパイル時に厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="4163b-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="4163b-108">前の例のように、コンパイラが入力パラメーターの型を推論できる場合は、型宣言を省略できます。</span><span class="sxs-lookup"><span data-stu-id="4163b-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="4163b-109">入力パラメーターの型を指定する必要がある場合は、次の例に示すように、パラメーターごとに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4163b-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="4163b-110">次の例は、入力パラメーターを含まないラムダ式を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4163b-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="4163b-111">詳細については、「[ラムダ式](lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4163b-111">For more information, see [Lambda expressions](lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="4163b-112">式本体の定義</span><span class="sxs-lookup"><span data-stu-id="4163b-112">Expression body definition</span></span>

<span data-ttu-id="4163b-113">式本体の定義には、次の一般的な構文があります。</span><span class="sxs-lookup"><span data-stu-id="4163b-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="4163b-114">ここで、`expression` には有効な式を指定します。</span><span class="sxs-lookup"><span data-stu-id="4163b-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="4163b-115">`expression` の戻り値の型は、メンバーの戻り値の型に暗黙的に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4163b-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="4163b-116">メンバーの戻り値の型が `void` の場合や、メンバーがコンストラクター、ファイナライザー、プロパティまたはインデクサー `set` のアクセサーの場合、`expression` は "[*ステートメント式*](~/_csharplang/spec/statements.md#expression-statements)" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4163b-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="4163b-117">式の結果が破棄されるため、その式の戻り値の型は任意の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4163b-117">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="4163b-118">次の例は、`Person.ToString` メソッドの式本体の定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="4163b-118">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="4163b-119">これは、次のメソッド定義の短縮形バージョンです。</span><span class="sxs-lookup"><span data-stu-id="4163b-119">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="4163b-120">メソッド、演算子、および読み取り専用プロパティの式本体の定義は、C# 6 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4163b-120">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="4163b-121">コンストラクター、ファイナライザー、プロパティ アクセサー、およびインデクサー アクセサーの式本体の定義は、C# 7.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4163b-121">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="4163b-122">詳細については、「[式形式のメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4163b-122">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4163b-123">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="4163b-123">Operator overloadability</span></span>

<span data-ttu-id="4163b-124">`=>` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="4163b-124">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4163b-125">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4163b-125">C# language specification</span></span>

<span data-ttu-id="4163b-126">ラムダ演算子の詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[匿名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4163b-126">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4163b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4163b-127">See also</span></span>

- [<span data-ttu-id="4163b-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="4163b-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4163b-129">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="4163b-129">C# operators and expressions</span></span>](index.md)
