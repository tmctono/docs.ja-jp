---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174265"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="736b6-101">Blazor: コンパイル時にコンポーネントからトリミングされる無意味な空白文字</span><span class="sxs-lookup"><span data-stu-id="736b6-101">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="736b6-102">ASP.NET Core 5.0 Preview 7 より、Razor コンパイラでは、コンパイル時に Blazor コンポーネント ( *.razor* ファイル) の無意味な空白文字が除外されます。</span><span class="sxs-lookup"><span data-stu-id="736b6-102">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="736b6-103">ディスカッションについては、イシュー [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="736b6-103">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="736b6-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="736b6-104">Version introduced</span></span>

<span data-ttu-id="736b6-105">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="736b6-105">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="736b6-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="736b6-106">Old behavior</span></span>

<span data-ttu-id="736b6-107">Blazor Server と Blazor WebAssembly の 3.x バージョンでは、コンポーネントのソース コードで空白文字が許可されます。</span><span class="sxs-lookup"><span data-stu-id="736b6-107">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="736b6-108">空白文字のみのテキスト ノードは、視覚効果がないときでも、ブラウザーのドキュメント オブジェクト モデル (DOM) にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="736b6-108">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="736b6-109">次の Blazor コンポーネント コードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="736b6-109">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="736b6-110">前の例では、次の場所で 2 つの空白文字ノードがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="736b6-110">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="736b6-111">`@foreach` コード ブロックの外側。</span><span class="sxs-lookup"><span data-stu-id="736b6-111">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="736b6-112">`<li>` 要素の前後。</span><span class="sxs-lookup"><span data-stu-id="736b6-112">Around the `<li>` element.</span></span>
* <span data-ttu-id="736b6-113">`@item.Text` 出力の前後。</span><span class="sxs-lookup"><span data-stu-id="736b6-113">Around the `@item.Text` output.</span></span>

<span data-ttu-id="736b6-114">100 項目が含まれるリストの場合、402 の空白文字ノードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="736b6-114">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="736b6-115">これは、レンダリングされる出力に視覚的に影響を与える空白文字ノードがない場合でも、レンダリングされる全ノードの半分以上です。</span><span class="sxs-lookup"><span data-stu-id="736b6-115">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="736b6-116">コンポーネントの静的 HTML をレンダリングする場合、タグ内の空白文字は保持されませんでした。</span><span class="sxs-lookup"><span data-stu-id="736b6-116">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="736b6-117">たとえば、次のコンポーネントのソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="736b6-117">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="736b6-118">空白文字が保持されていません。</span><span class="sxs-lookup"><span data-stu-id="736b6-118">Whitespace isn't preserved.</span></span> <span data-ttu-id="736b6-119">プレレンダリングされた出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="736b6-119">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a><span data-ttu-id="736b6-120">新しい動作</span><span class="sxs-lookup"><span data-stu-id="736b6-120">New behavior</span></span>

<span data-ttu-id="736b6-121">`@preservewhitespace` ディレクティブが値 `true` と共に使用されない限り、空白文字ノードは次の場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="736b6-121">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="736b6-122">要素内で先頭または末尾にある。</span><span class="sxs-lookup"><span data-stu-id="736b6-122">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="736b6-123">`RenderFragment` パラメーター内の先頭または末尾にある。</span><span class="sxs-lookup"><span data-stu-id="736b6-123">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="736b6-124">たとえば、別のコンポーネントに渡される子コンテンツです。</span><span class="sxs-lookup"><span data-stu-id="736b6-124">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="736b6-125">`@if` や `@foreach` のような、C# コード ブロックの前か後にある。</span><span class="sxs-lookup"><span data-stu-id="736b6-125">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="736b6-126">変更理由</span><span class="sxs-lookup"><span data-stu-id="736b6-126">Reason for change</span></span>

<span data-ttu-id="736b6-127">ASP.NET Core 5.0 の Blazor の目標は、レンダリングと比較のパフォーマンスを改善することです。</span><span class="sxs-lookup"><span data-stu-id="736b6-127">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="736b6-128">無意味な空白文字ツリー ノードによって、ベンチマークでは、レンダリング時間の最大 40% が消費されていました。</span><span class="sxs-lookup"><span data-stu-id="736b6-128">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="736b6-129">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="736b6-129">Recommended action</span></span>

<span data-ttu-id="736b6-130">ほとんどの場合、レンダリングされたコンポーネントのビジュアル レイアウトは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="736b6-130">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="736b6-131">ただし、空白文字の削除は、`white-space: pre` などの CSS ルールを使用するときに、レンダリングされた出力に影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="736b6-131">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="736b6-132">このパフォーマンスの最適化を無効にして、空白を保持するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="736b6-132">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="736b6-133">特定のコンポーネントに設定を適用するには、 *.razor* ファイルの先頭に `@preservewhitespace true` ディレクティブを追加する。</span><span class="sxs-lookup"><span data-stu-id="736b6-133">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="736b6-134">サブディレクトリ全体またはプロジェクト全体に設定を適用するには、 *_Imports.razor* ファイル内に `@preservewhitespace true` ディレクティブを追加する。</span><span class="sxs-lookup"><span data-stu-id="736b6-134">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="736b6-135">ほとんどの場合、アプリケーションでは一般的に通常の動作が続行されるため (ただし、速くなります)、何の措置も必要ありません。</span><span class="sxs-lookup"><span data-stu-id="736b6-135">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="736b6-136">空白文字の削除で特定のコンポーネントに問題が発生する場合、そのコンポーネントで `@preservewhitespace true` を使用し、この最適化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="736b6-136">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

#### <a name="category"></a><span data-ttu-id="736b6-137">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="736b6-137">Category</span></span>

<span data-ttu-id="736b6-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="736b6-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="736b6-139">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="736b6-139">Affected APIs</span></span>

<span data-ttu-id="736b6-140">None</span><span class="sxs-lookup"><span data-stu-id="736b6-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
