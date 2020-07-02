---
title: 匿名型と組型の選択
description: 匿名型とタプル型のどちらかを選択するのが適切な場合について説明します。
ms.date: 06/29/2020
ms.technology: dotnet-standard
ms.openlocfilehash: bc17695830a42a6eed9d60c0e097ee9d02a7957e
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803769"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="a433d-103">匿名型と組型の選択</span><span class="sxs-lookup"><span data-stu-id="a433d-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="a433d-104">適切な種類を選択するには、他の種類と比較して使いやすさ、パフォーマンス、およびトレードオフを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a433d-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="a433d-105">匿名型は、C# 3.0 以降で使用できますが、ジェネリック <xref:System.Tuple%602?displayProperty=nameWithType> 型は .NET Framework 4.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a433d-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="a433d-106">その後、言語レベルのサポートで新しいオプションが導入されました。たとえば、名前が示すように、 <xref:System.ValueTuple%602?displayProperty=nameWithType> 匿名型の柔軟性を持つ値型を提供します。</span><span class="sxs-lookup"><span data-stu-id="a433d-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="a433d-107">この記事では、もう一方の型を選択するのが適切な場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="a433d-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="a433d-108">使いやすさと機能</span><span class="sxs-lookup"><span data-stu-id="a433d-108">Usability and functionality</span></span>

<span data-ttu-id="a433d-109">匿名型は、C# 3.0 で統合言語クエリ (LINQ) 式を使用して導入されました。</span><span class="sxs-lookup"><span data-stu-id="a433d-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="a433d-110">LINQ では、開発者は多くの場合、クエリの結果を、使用しているオブジェクトからいくつかの select プロパティを保持する匿名型に射影します。</span><span class="sxs-lookup"><span data-stu-id="a433d-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="a433d-111">次の例では、オブジェクトの配列をインスタンス化 <xref:System.DateTime> し、2つのプロパティを持つ匿名型に射影されたオブジェクトを反復処理しています。</span><span class="sxs-lookup"><span data-stu-id="a433d-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

<span data-ttu-id="a433d-112">匿名型は演算子を使用してインスタンス化され、 [`new`](../../csharp/language-reference/operators/new-operator.md) プロパティの名前と型は宣言から推論されます。</span><span class="sxs-lookup"><span data-stu-id="a433d-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="a433d-113">同じアセンブリ内の複数の匿名オブジェクト初期化子が、同じ順序で同じ名前と型を持つプロパティのシーケンスを指定した場合、コンパイラはそれらのオブジェクトを同じ型のインスタンスとして扱います。</span><span class="sxs-lookup"><span data-stu-id="a433d-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="a433d-114">これらのオブジェクトは、コンパイラで生成された同一の型情報を共有します。</span><span class="sxs-lookup"><span data-stu-id="a433d-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="a433d-115">前の C# スニペットでは、次のコンパイラで生成された C# クラスと同様に、2つのプロパティを持つ匿名型を射影しています。</span><span class="sxs-lookup"><span data-stu-id="a433d-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

<span data-ttu-id="a433d-116">詳細については、「[匿名型](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a433d-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="a433d-117">LINQ クエリへの射影では、組と同じ機能が存在します。組にプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a433d-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="a433d-118">これらの組は、匿名型の場合と同様に、クエリを通過します。</span><span class="sxs-lookup"><span data-stu-id="a433d-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="a433d-119">ここで、を使用して、次の例を考えてみ `System.Tuple<string, long>` ます。</span><span class="sxs-lookup"><span data-stu-id="a433d-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

<span data-ttu-id="a433d-120">を使用すると、 <xref:System.Tuple%602?displayProperty=nameWithType> インスタンスは、、などの番号付きの項目プロパティを公開し `Item1` `Item2` ます。</span><span class="sxs-lookup"><span data-stu-id="a433d-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="a433d-121">プロパティ名は序数のみを提供するため、これらのプロパティ名を使用すると、プロパティ値の意図を理解するのが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="a433d-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="a433d-122">さらに、 `System.Tuple` 型は参照 `class` 型です。</span><span class="sxs-lookup"><span data-stu-id="a433d-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="a433d-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>ただし、は値 `struct` 型です。</span><span class="sxs-lookup"><span data-stu-id="a433d-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="a433d-124">次の C# スニペットでは、を使用してを `ValueTuple<string, long>` に射影しています。</span><span class="sxs-lookup"><span data-stu-id="a433d-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="a433d-125">この場合、リテラル構文を使用してが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a433d-125">In doing so, it assigns using a literal syntax.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

<span data-ttu-id="a433d-126">C# では、型を持つタプルの言語サポートと、次のセマンティクスが用意されてい <xref:System.ValueTuple> ます。</span><span class="sxs-lookup"><span data-stu-id="a433d-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="a433d-127">組の代入</span><span class="sxs-lookup"><span data-stu-id="a433d-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="a433d-128">[タプル分解](../../csharp/deconstruct.md)(タプルに限定されません)</span><span class="sxs-lookup"><span data-stu-id="a433d-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="a433d-129">タプルの等価性のチェック</span><span class="sxs-lookup"><span data-stu-id="a433d-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="a433d-130">タプル プロジェクション初期化子</span><span class="sxs-lookup"><span data-stu-id="a433d-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="a433d-131">ただし、上記の例はすべて機能的に同等です。使いやすさとその基盤となる実装にはわずかな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="a433d-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="a433d-132">トレードオフ</span><span class="sxs-lookup"><span data-stu-id="a433d-132">Tradeoffs</span></span>

<span data-ttu-id="a433d-133">常に over、匿名型を使用することもでき <xref:System.ValueTuple> <xref:System.Tuple> ますが、考慮すべきトレードオフがあります。</span><span class="sxs-lookup"><span data-stu-id="a433d-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="a433d-134">型は変更 <xref:System.ValueTuple> <xref:System.Tuple> 可能ですが、は読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a433d-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="a433d-135">式ツリーでは匿名型を使用できますが、タプルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a433d-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="a433d-136">次の表に、主な相違点の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a433d-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="a433d-137">主要な相違点</span><span class="sxs-lookup"><span data-stu-id="a433d-137">Key differences</span></span>

| <span data-ttu-id="a433d-138">名前</span><span class="sxs-lookup"><span data-stu-id="a433d-138">Name</span></span>                     | <span data-ttu-id="a433d-139">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="a433d-139">Access modifier</span></span> | <span data-ttu-id="a433d-140">Type</span><span class="sxs-lookup"><span data-stu-id="a433d-140">Type</span></span>     | <span data-ttu-id="a433d-141">カスタムプロパティ名</span><span class="sxs-lookup"><span data-stu-id="a433d-141">Custom property name</span></span> | <span data-ttu-id="a433d-142">分解のサポート</span><span class="sxs-lookup"><span data-stu-id="a433d-142">Deconstruction support</span></span> | <span data-ttu-id="a433d-143">式ツリーのサポート</span><span class="sxs-lookup"><span data-stu-id="a433d-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="a433d-144">匿名型</span><span class="sxs-lookup"><span data-stu-id="a433d-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="a433d-145">✔️</span><span class="sxs-lookup"><span data-stu-id="a433d-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="a433d-146">✔️</span><span class="sxs-lookup"><span data-stu-id="a433d-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="a433d-147">✔️</span><span class="sxs-lookup"><span data-stu-id="a433d-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="a433d-148">✔️</span><span class="sxs-lookup"><span data-stu-id="a433d-148">✔️</span></span>                   | <span data-ttu-id="a433d-149">✔️</span><span class="sxs-lookup"><span data-stu-id="a433d-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="a433d-150">シリアル化</span><span class="sxs-lookup"><span data-stu-id="a433d-150">Serialization</span></span>

<span data-ttu-id="a433d-151">型を選択する際の重要な考慮事項の1つは、シリアル化する必要があるかどうかです。</span><span class="sxs-lookup"><span data-stu-id="a433d-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="a433d-152">シリアル化とは、オブジェクトの状態を永続化または転送できる形式に変換するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="a433d-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="a433d-153">詳細については、「[シリアル化](../../csharp/programming-guide/concepts/serialization/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a433d-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="a433d-154">シリアル化が重要な場合は、 `class` 匿名型または組型よりもまたはを作成することを `struct` お勧めします。</span><span class="sxs-lookup"><span data-stu-id="a433d-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="a433d-155">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="a433d-155">Performance</span></span>

<span data-ttu-id="a433d-156">これらの種類の間のパフォーマンスは、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a433d-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="a433d-157">主な影響は、割り当てとコピーの間のトレードオフです。</span><span class="sxs-lookup"><span data-stu-id="a433d-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="a433d-158">ほとんどの場合、影響は小さくなります。</span><span class="sxs-lookup"><span data-stu-id="a433d-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="a433d-159">大きな影響が生じる可能性がある場合は、決定を通知するために測定値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a433d-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="a433d-160">まとめ</span><span class="sxs-lookup"><span data-stu-id="a433d-160">Conclusion</span></span>

<span data-ttu-id="a433d-161">組と匿名型のどちらかを選択する開発者として、考慮すべきいくつかの要素があります。</span><span class="sxs-lookup"><span data-stu-id="a433d-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="a433d-162">一般に、[式ツリー](../../csharp/expression-trees.md)を使用していないときに、タプル構文に慣れている場合は、 <xref:System.ValueTuple> プロパティに柔軟に値型を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a433d-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="a433d-163">式ツリーを使用していて、プロパティに名前を付けたい場合は、[匿名型] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a433d-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="a433d-164">それ以外の場合は、 <xref:System.Tuple>を指定します。</span><span class="sxs-lookup"><span data-stu-id="a433d-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a433d-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="a433d-165">See also</span></span>

- [<span data-ttu-id="a433d-166">匿名型</span><span class="sxs-lookup"><span data-stu-id="a433d-166">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="a433d-167">式ツリー</span><span class="sxs-lookup"><span data-stu-id="a433d-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="a433d-168">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a433d-168">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="a433d-169">タプル型</span><span class="sxs-lookup"><span data-stu-id="a433d-169">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="a433d-170">型のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a433d-170">Type design guidelines</span></span>](type.md)
