---
title: => 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: a7fea9810cb02269278638ec71cd106463b029e9
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025016"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b1dad-102">=> 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b1dad-102">=> operator (C# reference)</span></span>

<span data-ttu-id="b1dad-103">`=>` トークンは、ラムダ演算子、および式本体の定義におけるメンバー名とメンバー実装の区切り記号という 2 つの形式でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="b1dad-104">ラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="b1dad-104">Lambda operator</span></span>

<span data-ttu-id="b1dad-105">[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)では、ラムダ演算子 `=>` により、左側の入力変数と右側のラムダ本体とが分けられます。</span><span class="sxs-lookup"><span data-stu-id="b1dad-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="b1dad-106">次の例は、メソッド構文で [LINQ](../../programming-guide/concepts/linq/index.md) 機能を使用して、ラムダ式の使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="b1dad-107">ラムダ式の入力変数は、コンパイル時に厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="b1dad-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="b1dad-108">前の例のように、コンパイラが入力変数の型を推論できる場合は、省型宣言を略できます。</span><span class="sxs-lookup"><span data-stu-id="b1dad-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="b1dad-109">入力変数の型を指定する必要がある場合は、次の例に示すように、変数ごとに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1dad-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="b1dad-110">次の例は、入力変数を含まないラムダ式を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="b1dad-111">詳細については、「[ラムダ式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1dad-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="b1dad-112">式本体の定義</span><span class="sxs-lookup"><span data-stu-id="b1dad-112">Expression body definition</span></span>

<span data-ttu-id="b1dad-113">式本体の定義には、次の一般的な構文があります。</span><span class="sxs-lookup"><span data-stu-id="b1dad-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="b1dad-114">この *expression* には有効な式を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1dad-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="b1dad-115">メンバーの戻り値の型が `void` の場合か、メンバーがコンストラクター、ファイナライザー、またはプロパティ `set` アクセサーの場合にのみ、*式*は*ステートメント式*になります。</span><span class="sxs-lookup"><span data-stu-id="b1dad-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="b1dad-116">次の例は、`Person.ToString` メソッドの式本体の定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="b1dad-117">これは、次のメソッド定義の短縮形バージョンです。</span><span class="sxs-lookup"><span data-stu-id="b1dad-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="b1dad-118">メソッドおよび読み取り専用プロパティの式本体の定義は、C# 6 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="b1dad-119">コンストラクター、ファイナライザー、プロパティ アクセサー、およびインデクサーの式本体の定義は、C# 7.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b1dad-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="b1dad-120">詳細については、「[式形式のメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1dad-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b1dad-121">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="b1dad-121">Operator overloadability</span></span>

<span data-ttu-id="b1dad-122">`=>` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="b1dad-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b1dad-123">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b1dad-123">C# language specification</span></span>

<span data-ttu-id="b1dad-124">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1dad-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1dad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1dad-125">See also</span></span>

- [<span data-ttu-id="b1dad-126">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b1dad-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b1dad-127">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="b1dad-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="b1dad-128">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="b1dad-128">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="b1dad-129">式形式のメンバー</span><span class="sxs-lookup"><span data-stu-id="b1dad-129">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)
