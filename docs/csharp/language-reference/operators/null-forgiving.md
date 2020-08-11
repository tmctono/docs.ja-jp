---
title: '! (null 免除) 演算子 - C# リファレンス'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 5d8dcba5eb794d4d64f58e23a3ad952ef8055aeb
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916750"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="ba01b-103">!</span><span class="sxs-lookup"><span data-stu-id="ba01b-103">!</span></span> <span data-ttu-id="ba01b-104">(null 免除) 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ba01b-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="ba01b-105">C# 8.0 以降では、単項の接尾辞 `!` 演算子は null 免除演算子です。</span><span class="sxs-lookup"><span data-stu-id="ba01b-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="ba01b-106">有効な [null 許容注釈コンテキスト](../../nullable-references.md#nullable-annotation-context)では、null 免除演算子を使用して、参照型の式 `x` が `null`: `x!` ではないことを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ba01b-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="ba01b-107">単項の接頭辞 `!` 演算子は、[論理否定演算子](boolean-logical-operators.md#logical-negation-operator-)です。</span><span class="sxs-lookup"><span data-stu-id="ba01b-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="ba01b-108">null 免除演算子は実行時には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="ba01b-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="ba01b-109">式の null 状態を変更することによって、コンパイラの静的フロー分析にのみ影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="ba01b-110">実行時に、式 `x!` は基になる式 `x` の結果に評価されます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="ba01b-111">C# 8 では、null を許容しない演算子は、前の [null 条件](member-access-operators.md#null-conditional-operators--and-)操作のリストを終了します。</span><span class="sxs-lookup"><span data-stu-id="ba01b-111">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="ba01b-112">たとえば、式 `x?.y!.z` は `(x?.y)!.z` として解析されます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-112">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="ba01b-113">この解釈のため、`x` が `null` の場合でも `z` が評価されるため、<xref:System.NullReferenceException> が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba01b-113">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="ba01b-114">null 許容参照型の機能の詳細については、「[null 許容参照型](../builtin-types/nullable-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba01b-114">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="ba01b-115">使用例</span><span class="sxs-lookup"><span data-stu-id="ba01b-115">Examples</span></span>

<span data-ttu-id="ba01b-116">null 免除演算子のユース ケースの 1 つは、引数検証ロジックをテストすることです。</span><span class="sxs-lookup"><span data-stu-id="ba01b-116">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="ba01b-117">たとえば、次のクラスを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-117">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="ba01b-118">[MSTest テスト フレームワーク](../../../core/testing/unit-testing-with-mstest.md) を使用して、コンストラクターの検証ロジックに対して次のテストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-118">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="ba01b-119">null 免除演算子を使用しない場合は、コンパイラによって上のコードに対して次の警告が生成されます: `Warning CS8625: Cannot convert null literal to non-nullable reference type`。</span><span class="sxs-lookup"><span data-stu-id="ba01b-119">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="ba01b-120">null 免除演算子を使用すると、`null` を渡すことが予測されており、警告を生成しないことがコンパイラに通知されます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-120">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="ba01b-121">また、式を `null` にできないことが明確にわかっているが、コンパイラでそのことを認識できない場合にも、null 免除演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-121">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="ba01b-122">次の例では、`IsValid` メソッドによって `true` が返された場合、その引数は `null` ではなく、安全に逆参照できます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-122">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="ba01b-123">null 免除演算子を使用しない場合は、コンパイラによって `p.Name` コードに対して次の警告が生成されます: `Warning CS8602: Dereference of a possibly null reference`。</span><span class="sxs-lookup"><span data-stu-id="ba01b-123">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="ba01b-124">`IsValid` メソッドを変更できる場合は、[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) 属性を使用して、メソッドによって `true` が返されたときに `IsValid` メソッドの引数を `null` にできないことをコンパイラに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="ba01b-124">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="ba01b-125">前の例では、null 免除演算子を使用する必要はありません。これは、`if` ステートメント内で `p` を `null` にできないことを把握するのに十分な情報がコンパイラに含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="ba01b-125">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="ba01b-126">変数の null 状態に関する追加情報を提供するための属性の詳細については、[null 予測を定義する属性を使用した API のアップグレード](../attributes/nullable-analysis.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba01b-126">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ba01b-127">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ba01b-127">C# language specification</span></span>

<span data-ttu-id="ba01b-128">詳細については、[null 許容参照型仕様の下書き](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)の「[null 免除演算子](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba01b-128">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba01b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba01b-129">See also</span></span>

- [<span data-ttu-id="ba01b-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ba01b-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ba01b-131">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="ba01b-131">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="ba01b-132">チュートリアル: null 許容参照型を使用して設計する</span><span class="sxs-lookup"><span data-stu-id="ba01b-132">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
