---
title: C# 8.0 の新機能 - C# ガイド
description: C# 8.0 で使用できる新しい機能の概要を説明します。 この記事は、プレビュー 5 での最新のものです。
ms.date: 02/12/2019
ms.openlocfilehash: 14c86fe4b1ecd1c89ebbbb082c5c9956bc51e03e
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105511"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="fa5c1-104">C# 8.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="fa5c1-104">What's new in C# 8.0</span></span>

<span data-ttu-id="fa5c1-105">C# 言語では、既に試すことができる多くの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-105">There are many enhancements to the C# language that you can try out already.</span></span> 

- [<span data-ttu-id="fa5c1-106">読み取り専用メンバー</span><span class="sxs-lookup"><span data-stu-id="fa5c1-106">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="fa5c1-107">既定のインターフェイス メンバー</span><span class="sxs-lookup"><span data-stu-id="fa5c1-107">Default interface members</span></span>](#default-interface-members)
- <span data-ttu-id="fa5c1-108">[パターン マッチングの拡張機能](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="fa5c1-108">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="fa5c1-109">switch 式</span><span class="sxs-lookup"><span data-stu-id="fa5c1-109">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="fa5c1-110">プロパティのパターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-110">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="fa5c1-111">タプル パターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-111">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="fa5c1-112">位置指定パターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-112">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="fa5c1-113">using 宣言</span><span class="sxs-lookup"><span data-stu-id="fa5c1-113">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="fa5c1-114">静的ローカル関数</span><span class="sxs-lookup"><span data-stu-id="fa5c1-114">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="fa5c1-115">破棄可能な ref 構造体</span><span class="sxs-lookup"><span data-stu-id="fa5c1-115">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="fa5c1-116">Null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="fa5c1-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="fa5c1-117">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="fa5c1-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="fa5c1-118">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="fa5c1-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="fa5c1-119">この記事の最後の更新は、C# 8.0 プレビュー 5 に関するものです。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-119">This article was last updated for C# 8.0 preview 5.</span></span>

<span data-ttu-id="fa5c1-120">この記事の以降では、これらの機能について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="fa5c1-121">詳細な記事がある場合は、それらのチュートリアルと概要へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="fa5c1-122">`dotnet try` グローバル ツールを使って、これらの機能をご自身の環境で調べることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-122">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="fa5c1-123">[dotnet try](https://github.com/dotnet/try/blob/master/README.md#setup) グローバル ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-123">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="fa5c1-124">[dotnet/try-samples](https://github.com/dotnet/try-samples) リポジトリを複製します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-124">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="fa5c1-125">現在のディレクトリを、*try-samples* リポジトリの *csharp8* サブディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-125">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="fa5c1-126">`dotnet try` を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-126">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="fa5c1-127">読み取り専用メンバー</span><span class="sxs-lookup"><span data-stu-id="fa5c1-127">Readonly members</span></span>

<span data-ttu-id="fa5c1-128">構造体の任意のメンバーに `readonly` 修飾子を適用できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-128">You can apply the `readonly` modifier to any member of a struct.</span></span> <span data-ttu-id="fa5c1-129">これは、メンバーによって状態が変更されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-129">It indicates that the member does not modify state.</span></span> <span data-ttu-id="fa5c1-130">`readonly` 修飾子を `struct` 宣言に適用するよりも詳細になります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-130">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="fa5c1-131">次の変更可能な構造体を検討します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-131">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="fa5c1-132">ほとんどの構造体と同様に、`ToString()` メソッドでは、状態を変更しません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-132">Like most structs, the `ToString()` method does not modify state.</span></span> <span data-ttu-id="fa5c1-133">それを示すには、`ToString()` の宣言に修飾子 `readonly` を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-133">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="fa5c1-134">上記の変更により、`ToString` が `readonly` とマークされていない `Distance` プロパティにアクセスするため、コンパイラの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-134">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which is not marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="fa5c1-135">コンパイラからは、防御用のコピーを作成する必要があるときに警告されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-135">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="fa5c1-136">`Distance` プロパティでは状態を変更しないため、宣言に `readonly` 修飾子を追加することで、この警告を修正できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-136">The `Distance` property does not change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="fa5c1-137">`readonly` 修飾子は読み取り専用プロパティに必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-137">Notice that the `readonly` modifier is necessary on a read only property.</span></span> <span data-ttu-id="fa5c1-138">コンパイラでは、`get` アクセサーが状態を変更しないことを想定していないため、`readonly` を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-138">The compiler doesn't assume `get` accessors do not modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="fa5c1-139">コンパイラによって、`readonly` メンバーによって状態が変更されないというルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-139">The compiler does enforce the rule that `readonly` members do not modify state.</span></span> <span data-ttu-id="fa5c1-140">次のメソッドは、`readonly` 修飾子を削除しない限りコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-140">The following method will not compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="fa5c1-141">この機能により、設計の意図を指定し、コンパイラによってそれが適用され、その意図に基づいて最適化が行われるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-141">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

## <a name="default-interface-members"></a><span data-ttu-id="fa5c1-142">既定のインターフェイス メンバー</span><span class="sxs-lookup"><span data-stu-id="fa5c1-142">Default interface members</span></span>

<span data-ttu-id="fa5c1-143">ここでインターフェイスにメンバーを追加し、それらのメンバーの実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-143">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="fa5c1-144">この言語機能を使用することで、API 作成者は、インターフェイスの既存の実装とのソースやバイナリの互換性を損なうことなく、新しいバージョンのそのインターフェイスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-144">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="fa5c1-145">既存の実装では既定の実装が*継承*されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-145">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="fa5c1-146">さらに、この機能により、同様の機能をサポートする Android や Swift を対象とする API を、C# と連携させることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-146">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="fa5c1-147">既定のインターフェイス メンバーでは、"traits" 言語機能のようなシナリオも可能になります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-147">Default interface members also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="fa5c1-148">多くのシナリオと言語要素が、既定のインターフェイス メンバーによって影響されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-148">Default interface members affects many scenarios and language elements.</span></span> <span data-ttu-id="fa5c1-149">最初のチュートリアルでは、[既定の実装でのインターフェイスの更新](../tutorials/default-interface-members-versions.md)について取り上げています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-149">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-members-versions.md).</span></span> <span data-ttu-id="fa5c1-150">その他のチュートリアルとリファレンスの更新は、一般公開に間に合うように提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-150">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="fa5c1-151">より多くの場所でより多くのパターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-151">More patterns in more places</span></span>

<span data-ttu-id="fa5c1-152">**パターン マッチング**では、関連はあっても種類が異なるデータをまたがってシェイプに依存する機能を提供するツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-152">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="fa5c1-153">C# 7.0 では、[`is`](../language-reference/keywords/is.md) 式と [`switch`](../language-reference/keywords/switch.md) ステートメントを使用することで、型パターンと定数パターンの構文が導入されました。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-153">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="fa5c1-154">これらの機能では、データと機能が分かれて存在するプログラミング パラダイムのサポートに向けた最初の試験的なステップが示されました。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-154">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="fa5c1-155">業界はマイクロサービスと他のクラウド ベース アーキテクチャに向けて移動しており、他の言語ツールが必要になっています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-155">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="fa5c1-156">C# 8.0 では、このボキャブラリが展開されて、コードのより多くの場所で、より多くのパターン式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-156">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="fa5c1-157">データと機能が分かれているときは、これらの機能を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-157">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="fa5c1-158">アルゴリズムがオブジェクトのランタイム型以外の事実に依存している場合は、パターン マッチングを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-158">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="fa5c1-159">これらの手法では、設計を表現する別の方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-159">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="fa5c1-160">新しい場所での新しいパターンだけでなく、C# 8.0 では**再帰パターン**が追加されています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-160">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="fa5c1-161">パターン式の結果は式です。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-161">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="fa5c1-162">再帰パターンは、単に、別のパターン式の出力に適用されるパターン式です。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-162">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="fa5c1-163">switch 式</span><span class="sxs-lookup"><span data-stu-id="fa5c1-163">switch expressions</span></span>

<span data-ttu-id="fa5c1-164">多くの場合、[`switch`](../language-reference/keywords/switch.md) ステートメントでは、その各 `case` ブロックで値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-164">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="fa5c1-165">**switch 式**を使用すると、より簡潔な式の構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-165">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="fa5c1-166">反復的な `case` や `break` キーワード、および中かっこの数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-166">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="fa5c1-167">たとえば、虹の色を示す次のような列挙型について考えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-167">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="fa5c1-168">アプリケーションで `R`、`G`、および `B` コンポーネントから構成される `RGBColor` 型が定義されている場合は、switch 式を含む次のメソッドを使用して、`Rainbow` の値をその RGB 値に変換できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-168">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="fa5c1-169">この構文ではいくつかの点が改良されています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-169">There are several syntax improvements here:</span></span>

- <span data-ttu-id="fa5c1-170">変数は `switch` キーワードの前にあります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-170">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="fa5c1-171">順序を変えることで、switch ステートメントからの switch 式の視覚的な区別が容易になります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-171">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="fa5c1-172">`case` 要素と `:` 要素は、`=>` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-172">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="fa5c1-173">より簡潔でわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-173">It's more concise and intuitive.</span></span>
- <span data-ttu-id="fa5c1-174">`default` ケースは、`_` 破棄に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-174">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="fa5c1-175">本体は式であり、ステートメントではありません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-175">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="fa5c1-176">従来の `switch` ステートメントを使用した同等のコードと比較してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-176">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="fa5c1-177">プロパティ パターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-177">Property patterns</span></span>

<span data-ttu-id="fa5c1-178">**プロパティ パターン**を使用すると、調査対象のオブジェクトのプロパティと照合することができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-178">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="fa5c1-179">購入者の住所に基づいて消費税を計算する必要がある eコマース サイトについて考えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-179">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="fa5c1-180">そのような計算は、`Address` クラスの核心的な役割ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-180">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="fa5c1-181">時間とともに、おそらくは住所の形式の変更より頻繁に、変更されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-181">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="fa5c1-182">消費税の金額は、住所の `State` プロパティに依存します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-182">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="fa5c1-183">次のメソッドでは、プロパティ パターンを使用して、住所と価格から消費税を計算しています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-183">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="fa5c1-184">パターン マッチングにより、このアルゴリズムを表現するための簡潔な構文が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-184">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="fa5c1-185">タプル パターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-185">Tuple patterns</span></span>

<span data-ttu-id="fa5c1-186">いくつかのアルゴリズムは複数の入力に依存しています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-186">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="fa5c1-187">**タプル パターン**を使うと、[タプル](../tuples.md)として表現された複数の値に基づいて切り替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-187">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="fa5c1-188">"*rock、paper、scissors (じゃんけん)* " ゲーム用の switch 式を示すコードを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-188">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="fa5c1-189">メッセージは勝者を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-189">The messages indicate the winner.</span></span> <span data-ttu-id="fa5c1-190">破棄のケースは、引き分けとなる 3 つの組み合わせ、またはその他のテキスト入力を表します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-190">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="fa5c1-191">位置指定パターン</span><span class="sxs-lookup"><span data-stu-id="fa5c1-191">Positional patterns</span></span>

<span data-ttu-id="fa5c1-192">一部の型には、そのプロパティを個別の変数に分解する `Deconstruct` メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-192">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="fa5c1-193">`Deconstruct` メソッドにアクセスできる場合、**位置指定パターン**を使ってオブジェクトのプロパティを検査し、パターン用にそれらのプロパティを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-193">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="fa5c1-194">`X` と `Y` の個別の変数を作成する `Deconstruct` メソッドを含む `Point` クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-194">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="fa5c1-195">さらに、クアドラントのさまざまな位置を表す次の列挙を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-195">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="fa5c1-196">次のメソッドでは、**位置指定パターン**を使用して、`x` と `y` の値を抽出しています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-196">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="fa5c1-197">その後、`when` 句を使用して、点の `Quadrant` を決定します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-197">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="fa5c1-198">前の switch での破棄パターンは、`x` または `y` のどちらか一方が 0 のときに一致しますが、両方とも 0 のときには一致しません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-198">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="fa5c1-199">switch 式は、値を生成するか、または例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-199">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="fa5c1-200">どのケースとも一致しない場合、switch 式は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-200">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="fa5c1-201">可能性のあるすべてのケースが switch 式でカバーされていない場合、コンパイラで警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-201">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="fa5c1-202">この[パターン マッチングの高度なチュートリアル](../tutorials/pattern-matching.md)で、パターン マッチング手法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-202">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="fa5c1-203">using 宣言</span><span class="sxs-lookup"><span data-stu-id="fa5c1-203">using declarations</span></span>

<span data-ttu-id="fa5c1-204">**using 宣言**は、`using` キーワードが前に付いている変数宣言です。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-204">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="fa5c1-205">宣言されている変数を外側のスコープの最後に破棄する必要があることを、コンパイラに伝えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-205">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="fa5c1-206">たとえば、テキスト ファイルを書き込む次のようなコードについて考えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-206">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="fa5c1-207">上の例では、メソッドの右中かっこに達した時点で、ファイルは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-207">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="fa5c1-208">そこは、`file` が宣言されているスコープの末端です。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-208">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="fa5c1-209">上記のコードは、従来の [using ステートメント](../language-reference/keywords/using-statement.md)を使用する次のコードと同等です。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-209">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="fa5c1-210">上の例では、`using` ステートメントに関連付けられている右中かっこに達すると、ファイルは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-210">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="fa5c1-211">どちらの場合も、コンパイラでは `Dispose()` の呼び出しが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-211">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="fa5c1-212">`using` ステートメント内の式を破棄できない場合、コンパイラによってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-212">The compiler generates an error if the expression in the `using` statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="fa5c1-213">静的ローカル関数</span><span class="sxs-lookup"><span data-stu-id="fa5c1-213">Static local functions</span></span>

<span data-ttu-id="fa5c1-214">`static` 修飾子をローカル関数に追加することにより、ローカル関数で外側のスコープの変数がキャプチャ (参照) されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-214">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="fa5c1-215">それを行うと、`CS8421` "静的ローカル関数は \<variable> への参照を含むことができない" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-215">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="fa5c1-216">次のコードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-216">Consider the following code.</span></span> <span data-ttu-id="fa5c1-217">ローカル関数 `LocalFunction` は、外側のスコープ (`M` メソッド) で宣言されている変数 `y` にアクセスしています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-217">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="fa5c1-218">そのため、`LocalFunction` では `static` 修飾子を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-218">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="fa5c1-219">次のコードには、静的ローカル関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-219">The following code contains a static local function.</span></span> <span data-ttu-id="fa5c1-220">外側のスコープ内のどの変数にもアクセスしていないため、静的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-220">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="fa5c1-221">破棄可能な ref 構造体</span><span class="sxs-lookup"><span data-stu-id="fa5c1-221">Disposable ref structs</span></span>

<span data-ttu-id="fa5c1-222">`ref` 修飾子付きで宣言されている `struct` ではインターフェイスを実装できないので、<xref:System.IDisposable> を実装できません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-222">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="fa5c1-223">したがって、`ref struct` を破棄できるようにするには、アクセス可能な `void Dispose()` メソッドを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-223">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="fa5c1-224">これは、`readonly ref struct` 宣言にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-224">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="fa5c1-225">null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="fa5c1-225">Nullable reference types</span></span>

<span data-ttu-id="fa5c1-226">null 許容注釈コンテキスト内では、参照型のすべての変数は、**null 非許容参照型**と見なされます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-226">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="fa5c1-227">変数が null 許容であることを示したい場合は、型名に `?` を追加し、**null 許容参照型**として変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-227">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="fa5c1-228">null 非許容参照型の場合は、コンパイラでフロー分析を使用して、ローカル変数が宣言時に null 以外の値に初期化されることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-228">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="fa5c1-229">フィールドは、構築時に初期化される必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-229">Fields must be initialized during construction.</span></span> <span data-ttu-id="fa5c1-230">変数が使用可能ないずれかのコンストラクターの呼び出しまたは初期化子によって設定されていない場合、コンパイラで警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-230">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="fa5c1-231">さらに、null 非許容参照型に、null になる可能性がある値を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-231">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="fa5c1-232">null 許容参照型の場合は、null に割り当てられたり初期化されたりしないことは確認されません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-232">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="fa5c1-233">ただし、null 許容参照型の変数が null 非許容参照型にアクセスしたり割り当てられたりするときは、その前に、コンパイラでフロー分析を使用して、null 値のチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-233">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="fa5c1-234">詳しくは、「[null 許容参照型](../nullable-references.md)」の概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-234">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="fa5c1-235">この [null 許容参照型チュートリアル](../tutorials/nullable-reference-types.md)の新しいアプリケーションを使って、自分で試してみてください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-235">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="fa5c1-236">既存のコードベースを null 許容参照型を使用するように移行する手順について詳しくは、[null 許容参照型を使用するようにアプリケーションを移行する方法についてのチュートリアル](../tutorials/upgrade-to-nullable-references.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-236">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="fa5c1-237">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="fa5c1-237">Asynchronous streams</span></span>

<span data-ttu-id="fa5c1-238">C# 8.0 以降では、ストリームを非同期的に作成して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-238">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="fa5c1-239">非同期ストリームを返すメソッドには、次の 3 つの特徴があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-239">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="fa5c1-240">`async` 修飾子を使用して宣言されています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-240">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="fa5c1-241"><xref:System.Collections.Generic.IAsyncEnumerable%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-241">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="fa5c1-242">メソッドに、連続する要素を非同期ストリームで返すための `yield return` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-242">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="fa5c1-243">非同期ストリームを使用するには、ストリームの要素を列挙するときに、`foreach` キーワードの前に `await` キーワードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-243">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="fa5c1-244">`await` キーワードを追加するには、非同期ストリームを列挙するメソッドが、`async` 修飾子を使用して宣言されていて、`async` メソッドに対して許可される型を返すようになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-244">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="fa5c1-245">通常は、<xref:System.Threading.Tasks.Task> または <xref:System.Threading.Tasks.Task%601> を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-245">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fa5c1-246"><xref:System.Threading.Tasks.ValueTask> または <xref:System.Threading.Tasks.ValueTask%601> にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-246">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="fa5c1-247">同じメソッドで非同期ストリームの使用と生成の両方を行うことができます。これは、そのメソッドが <xref:System.Collections.Generic.IAsyncEnumerable%601> を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-247">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="fa5c1-248">次のコードでは、0 から 19 の値のシーケンスが生成され、各値の間に 100 ミリ秒の待機が設けられています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-248">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="fa5c1-249">シーケンスの列挙は、`await foreach` ステートメントを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-249">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="fa5c1-250">[非同期ストリームの作成と使用](../tutorials/generate-consume-asynchronous-stream.md)に関するチュートリアルを使用して、自分で非同期ストリームを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-250">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="fa5c1-251">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="fa5c1-251">Indices and ranges</span></span>

<span data-ttu-id="fa5c1-252">範囲とインデックスでは、配列、<xref:System.Span%601>、または <xref:System.ReadOnlySpan%601> 内の部分範囲を指定するための簡潔な構文が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-252">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="fa5c1-253">この言語のサポートでは、2 つの新しい型と 2 つの新しい演算子を使用しています。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-253">This language support relies on two new types, and two new operators.</span></span>
- <span data-ttu-id="fa5c1-254"><xref:System.Index?displayProperty=nameWithType> はシーケンスとしてインデックスを表します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-254"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="fa5c1-255">`^` 演算子。シーケンスの末尾から相対的なインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-255">The `^` operator, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="fa5c1-256"><xref:System.Range?displayProperty=nameWithType> はシーケンスのサブ範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-256"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="fa5c1-257">範囲演算子 (`..`)。範囲の先頭と末尾をそのオペランドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-257">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="fa5c1-258">インデックスのルールから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-258">Let's start with the rules for indexes.</span></span> <span data-ttu-id="fa5c1-259">配列 `sequence` を考えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-259">Consider an array `sequence`.</span></span> <span data-ttu-id="fa5c1-260">`0` インデックスは `sequence[0]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-260">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="fa5c1-261">`^0` インデックスは `sequence[sequence.Length]` と同じです。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-261">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="fa5c1-262">`sequence[sequence.Length]` と同様に、`sequence[^0]` は例外をスローすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-262">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="fa5c1-263">任意の数値 `n` の場合、インデックス `^n` は `sequence.Length - n` と同じです。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-263">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="fa5c1-264">範囲は、範囲の*先頭*と*末尾*を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-264">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="fa5c1-265">範囲の先頭は包含ですが、範囲の末尾は排他です。つまり、"*先頭*" は範囲に含まれますが、"*末尾*" は範囲に含まれません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-265">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* is not included in the range.</span></span> <span data-ttu-id="fa5c1-266">範囲 `[0..^0]` は、`[0..sequence.Length]` が範囲全体を表すのと同じように、範囲全体を表します。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-266">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="fa5c1-267">いくつか例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-267">Let's look at a few examples.</span></span> <span data-ttu-id="fa5c1-268">先頭および末尾からのインデックスの注釈が付けられた、次のような配列について考えます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-268">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="fa5c1-269">最後の単語は、`^1` というインデックスで取得することができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-269">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="fa5c1-270">次のコードでは、単語 "quick"、"brown"、"fox" から成る部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-270">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="fa5c1-271">それには、`words[1]` から `words[3]` までが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-271">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="fa5c1-272">要素 `words[4]` は範囲内ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-272">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="fa5c1-273">次のコードでは、"lazy" と "dog" の部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-273">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="fa5c1-274">それには、`words[^2]` と `words[^1]` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-274">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="fa5c1-275">末尾インデックス `words[^0]` は含まれません。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-275">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="fa5c1-276">次の例では、先頭と末尾の一方または両方が開いている範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-276">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="fa5c1-277">変数として範囲を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-277">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="fa5c1-278">その場合、範囲は文字 `[` と `]` の内側で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-278">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="fa5c1-279">チュートリアルでのインデックスと範囲について詳しくは、「[Indices and ranges (インデックスと範囲)](../tutorials/ranges-indexes.md)」で調べることができます。</span><span class="sxs-lookup"><span data-stu-id="fa5c1-279">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>
