---
title: decimal キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: 7ad01f9e4f5a8b1a153b1ef306e9d6168335eb3d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424303"
---
# <a name="decimal-c-reference"></a><span data-ttu-id="2a20b-102">decimal (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2a20b-102">decimal (C# Reference)</span></span>

<span data-ttu-id="2a20b-103">`decimal` キーワードは、128 ビットのデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="2a20b-104">`decimal` 型は、他の浮動小数点型よりも有効桁数が多く、範囲が狭いので、財務や金融の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="2a20b-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="2a20b-105">`decimal` 型の概算の範囲と有効桁数は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a20b-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>

|<span data-ttu-id="2a20b-106">型</span><span class="sxs-lookup"><span data-stu-id="2a20b-106">Type</span></span>|<span data-ttu-id="2a20b-107">おおよその範囲</span><span class="sxs-lookup"><span data-stu-id="2a20b-107">Approximate Range</span></span>|<span data-ttu-id="2a20b-108">有効桁数</span><span class="sxs-lookup"><span data-stu-id="2a20b-108">Precision</span></span>|<span data-ttu-id="2a20b-109">.NET 型</span><span class="sxs-lookup"><span data-stu-id="2a20b-109">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|<span data-ttu-id="2a20b-110">±1.0 x 10<sup>-28</sup> から ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="2a20b-110">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="2a20b-111">有効桁数 28 ～ 29</span><span class="sxs-lookup"><span data-stu-id="2a20b-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="2a20b-112">`decimal` の既定値は 0m です。</span><span class="sxs-lookup"><span data-stu-id="2a20b-112">The default value of a `decimal` is 0m.</span></span>

## <a name="literals"></a><span data-ttu-id="2a20b-113">リテラル</span><span class="sxs-lookup"><span data-stu-id="2a20b-113">Literals</span></span>

<span data-ttu-id="2a20b-114">実数値リテラルを `decimal` として扱うには、サフィックス m または M を使用します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>

```csharp
decimal myMoney = 300.5m;
```

<span data-ttu-id="2a20b-115">サフィックス m がない場合は [double](../../../csharp/language-reference/keywords/double.md) として扱われ、コンパイラ エラーになります。</span><span class="sxs-lookup"><span data-stu-id="2a20b-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>

## <a name="conversions"></a><span data-ttu-id="2a20b-116">変換</span><span class="sxs-lookup"><span data-stu-id="2a20b-116">Conversions</span></span>

<span data-ttu-id="2a20b-117">整数型は、暗黙的に `decimal` に変換され、結果は `decimal` になります。</span><span class="sxs-lookup"><span data-stu-id="2a20b-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="2a20b-118">したがって、サフィックスなしで整数リテラルを使用して 10 進変数を初期化できます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>

```csharp
decimal myMoney = 300;
```

<span data-ttu-id="2a20b-119">他の浮動小数点型と `decimal` 型の間に暗黙の型変換はありません。2 つの型の間で変換を実行するには、キャストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20b-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="2a20b-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-120">For example:</span></span>

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

<span data-ttu-id="2a20b-121">`decimal` 型と数値の整数型を同じ式に混在させることもできます。</span><span class="sxs-lookup"><span data-stu-id="2a20b-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="2a20b-122">ただし、`decimal` 型と他の浮動小数点型をキャストなしで混在させると、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="2a20b-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>

<span data-ttu-id="2a20b-123">暗黙的な数値変換の詳細については、「[暗黙的な数値変換の一覧表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20b-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="2a20b-124">明示的な数値変換の詳細については、「[明示的な数値変換の一覧表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20b-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="formatting-decimal-output"></a><span data-ttu-id="2a20b-125">10 進出力の書式指定</span><span class="sxs-lookup"><span data-stu-id="2a20b-125">Formatting decimal output</span></span>

<span data-ttu-id="2a20b-126">結果の書式を指定するには、`String.Format` メソッドを使用するか、<xref:System.Console.Write%2A?displayProperty=nameWithType> を呼び出す `String.Format()` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="2a20b-127">通貨書式を指定するには、この記事の 2 番目の例に示されているように、標準の通貨の書式指定文字列である "C" または "c" を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="2a20b-128">`String.Format` メソッドの詳細については、<xref:System.String.Format%2A?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20b-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="2a20b-129">例</span><span class="sxs-lookup"><span data-stu-id="2a20b-129">Example</span></span>

<span data-ttu-id="2a20b-130">次の例では、[double](../../../csharp/language-reference/keywords/double.md) の変数と `decimal` の変数を加算しようとして、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

<span data-ttu-id="2a20b-131">実行の結果、次のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a20b-131">The result is the following error:</span></span>

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

<span data-ttu-id="2a20b-132">この例では、同じ式に `decimal` と [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) が混在しています。</span><span class="sxs-lookup"><span data-stu-id="2a20b-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) are mixed in the same expression.</span></span> <span data-ttu-id="2a20b-133">結果は `decimal` 型になります。</span><span class="sxs-lookup"><span data-stu-id="2a20b-133">The result evaluates to the `decimal` type.</span></span>

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a><span data-ttu-id="2a20b-134">例</span><span class="sxs-lookup"><span data-stu-id="2a20b-134">Example</span></span>

<span data-ttu-id="2a20b-135">ここでは、通貨の書式指定文字列を使用して、出力の書式を指定する例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a20b-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="2a20b-136">小数点以下の桁数が $0.99 を超えるため、`x` を丸めている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a20b-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="2a20b-137">変数 `y` は最大固定桁数を表し、正しい書式で正確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a20b-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="2a20b-138">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2a20b-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2a20b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a20b-139">See also</span></span>

- <xref:System.Decimal>
- [<span data-ttu-id="2a20b-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2a20b-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2a20b-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2a20b-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2a20b-142">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="2a20b-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="2a20b-143">整数型</span><span class="sxs-lookup"><span data-stu-id="2a20b-143">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="2a20b-144">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="2a20b-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="2a20b-145">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="2a20b-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="2a20b-146">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="2a20b-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="2a20b-147">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="2a20b-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
