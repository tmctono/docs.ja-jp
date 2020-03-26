---
title: Blazor を使用して再利用可能な UI コンポーネントを構築する
description: Blazor を使用して再利用可能な UI コンポーネントを構築する方法と、それらのコンポーネントと Web フォーム コントロールの比較ASP.NETについて説明します。
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228622"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="8187a-103">Blazor を使用して再利用可能な UI コンポーネントを構築する</span><span class="sxs-lookup"><span data-stu-id="8187a-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8187a-104">web フォームASP.NET美しいことの 1 つは、再利用可能な UI コントロールに再利用可能なユーザー インターフェイス (UI) コードをカプセル化する方法です。</span><span class="sxs-lookup"><span data-stu-id="8187a-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="8187a-105">カスタム ユーザー コントロールは *、マークアップで定義できます.*</span><span class="sxs-lookup"><span data-stu-id="8187a-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="8187a-106">また、デザイナーの完全なサポートを使用して、コード内に精巧なサーバー コントロールを構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="8187a-107">Blazor は *、コンポーネント*を介した UI カプセル化もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8187a-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="8187a-108">コンポーネント:</span><span class="sxs-lookup"><span data-stu-id="8187a-108">A component:</span></span>

- <span data-ttu-id="8187a-109">UI の自己完結型のチャンクです。</span><span class="sxs-lookup"><span data-stu-id="8187a-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="8187a-110">独自の状態とレンダリング ロジックを維持します。</span><span class="sxs-lookup"><span data-stu-id="8187a-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="8187a-111">UI イベント ハンドラーの定義、入力データへのバインド、および独自のライフサイクルの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8187a-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="8187a-112">通常は、Razor 構文を使用して *.razor*ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="8187a-113">カミソリの紹介</span><span class="sxs-lookup"><span data-stu-id="8187a-113">An introduction to Razor</span></span>

<span data-ttu-id="8187a-114">Razor は、HTML と C# に基づく軽量マークアップテンプレート言語です。</span><span class="sxs-lookup"><span data-stu-id="8187a-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="8187a-115">Razor を使用すると、マークアップと C# コードの間でシームレスに遷移して、コンポーネントのレンダリング ロジックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="8187a-116">razor*ファイル*がコンパイルされると、レンダリング ロジックは構造化された方法で .NET クラスにキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="8187a-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="8187a-117">コンパイルされたクラスの名前は *、.razor*ファイル名から取得されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="8187a-118">名前空間は、プロジェクトの既定の名前空間とフォルダー パスから取得されるか、ディレクティブを使用して名前空間を`@namespace`明示的に指定できます (後述の Razor ディレクティブの詳細)。</span><span class="sxs-lookup"><span data-stu-id="8187a-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="8187a-119">コンポーネントのレンダリング ロジックは、C# を使用して追加された動的ロジックを使用して、通常の HTML マークアップを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="8187a-120">文字`@`は C# に遷移するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="8187a-121">Razor は、通常、HTML に切り替えたときに見つけ出す方法に関してスマートです。</span><span class="sxs-lookup"><span data-stu-id="8187a-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="8187a-122">たとえば、次のコンポーネントは現在の時間`<p>`を持つタグをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="8187a-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="8187a-123">C# 式の先頭と末尾を明示的に指定するには、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="8187a-124">Razor では、レンダリング ロジックで C# の制御フローを簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="8187a-125">たとえば、条件付きで次のような HTML をレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="8187a-126">または、次のように通常の C#`foreach`ループを使用して項目のリストを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="8187a-127">Razor ディレクティブは、ASP.NET Web フォームのディレクティブと同様に、Razor コンポーネントのコンパイル方法の多くの側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="8187a-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="8187a-128">たとえば、コンポーネントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8187a-128">Examples include the component's:</span></span>

- <span data-ttu-id="8187a-129">名前空間</span><span class="sxs-lookup"><span data-stu-id="8187a-129">Namespace</span></span>
- <span data-ttu-id="8187a-130">基底クラス</span><span class="sxs-lookup"><span data-stu-id="8187a-130">Base class</span></span>
- <span data-ttu-id="8187a-131">実装されたインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8187a-131">Implemented interfaces</span></span>
- <span data-ttu-id="8187a-132">ジェネリック パラメーター</span><span class="sxs-lookup"><span data-stu-id="8187a-132">Generic parameters</span></span>
- <span data-ttu-id="8187a-133">[インポートされた名前空間]</span><span class="sxs-lookup"><span data-stu-id="8187a-133">Imported namespaces</span></span>
- <span data-ttu-id="8187a-134">ルート</span><span class="sxs-lookup"><span data-stu-id="8187a-134">Routes</span></span>

<span data-ttu-id="8187a-135">Razor ディレクティブは`@`、文字で始まり、通常はファイルの先頭で新しい行の先頭で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="8187a-136">たとえば、ディレクティブは`@namespace`コンポーネントの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="8187a-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="8187a-137">次の表は、Blazor で使用される各種の Razor ディレクティブと、そのASP.NET Web フォームに相当するディレクティブ (存在する場合) を要約しています。</span><span class="sxs-lookup"><span data-stu-id="8187a-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="8187a-138">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="8187a-138">Directive</span></span>    |<span data-ttu-id="8187a-139">説明</span><span class="sxs-lookup"><span data-stu-id="8187a-139">Description</span></span>|<span data-ttu-id="8187a-140">例</span><span class="sxs-lookup"><span data-stu-id="8187a-140">Example</span></span>|<span data-ttu-id="8187a-141">Web フォームに相当するもの</span><span class="sxs-lookup"><span data-stu-id="8187a-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="8187a-142">コンポーネントにクラス レベルの属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="8187a-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="8187a-143">なし</span><span class="sxs-lookup"><span data-stu-id="8187a-143">None</span></span>|
|`@code`      |<span data-ttu-id="8187a-144">クラス メンバーをコンポーネントに追加します。</span><span class="sxs-lookup"><span data-stu-id="8187a-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="8187a-145">指定されたインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="8187a-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="8187a-146">コードビハインドを使用する</span><span class="sxs-lookup"><span data-stu-id="8187a-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="8187a-147">指定した基本クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="8187a-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="8187a-148">コンポーネントにサービスを挿入します。</span><span class="sxs-lookup"><span data-stu-id="8187a-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="8187a-149">なし</span><span class="sxs-lookup"><span data-stu-id="8187a-149">None</span></span>|
|`@layout`    |<span data-ttu-id="8187a-150">コンポーネントのレイアウト コンポーネントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="8187a-151">コンポーネントの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="8187a-152">なし</span><span class="sxs-lookup"><span data-stu-id="8187a-152">None</span></span>|
|`@page`      |<span data-ttu-id="8187a-153">コンポーネントのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="8187a-154">コンポーネントのジェネリック型パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="8187a-155">コードビハインドを使用する</span><span class="sxs-lookup"><span data-stu-id="8187a-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="8187a-156">スコープに取り込む名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="8187a-157">*web.config*に名前空間を追加する</span><span class="sxs-lookup"><span data-stu-id="8187a-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="8187a-158">Razor コンポーネントは、要素に対する*ディレクティブ属性*を広範囲に使用して、コンポーネントのコンパイル方法 (イベント処理、データ バインディング、コンポーネント&要素参照など) のさまざまな側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="8187a-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="8187a-159">ディレクティブ属性はすべて、括弧内の値がオプションである一般的なジェネリック構文に従います。</span><span class="sxs-lookup"><span data-stu-id="8187a-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="8187a-160">次の表は、Blazor で使用される Razor ディレクティブのさまざまな属性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8187a-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="8187a-161">属性</span><span class="sxs-lookup"><span data-stu-id="8187a-161">Attribute</span></span>    |<span data-ttu-id="8187a-162">説明</span><span class="sxs-lookup"><span data-stu-id="8187a-162">Description</span></span>|<span data-ttu-id="8187a-163">例</span><span class="sxs-lookup"><span data-stu-id="8187a-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="8187a-164">属性のディクショナリをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="8187a-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="8187a-165">双方向のデータ バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="8187a-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="8187a-166">指定したイベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8187a-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="8187a-167">コレクション内の要素を保持するために、拡散アルゴリズムで使用するキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="8187a-168">コンポーネントまたは HTML 要素への参照をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8187a-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="8187a-169">Blazor (`@onclick`、 、、、`@bind``@ref`など) で使用されるさまざまなディレクティブ属性については、以下の章と後の章で説明します。</span><span class="sxs-lookup"><span data-stu-id="8187a-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="8187a-170">*.aspx*ファイルと *.ascx*ファイルで使用される構文の多くは、Razor で並列構文を持っています。</span><span class="sxs-lookup"><span data-stu-id="8187a-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="8187a-171">以下は、web フォームとカミソリのASP.NETの構文の簡単な比較です。</span><span class="sxs-lookup"><span data-stu-id="8187a-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="8187a-172">機能</span><span class="sxs-lookup"><span data-stu-id="8187a-172">Feature</span></span>                      |<span data-ttu-id="8187a-173">Web フォーム</span><span class="sxs-lookup"><span data-stu-id="8187a-173">Web Forms</span></span>           |<span data-ttu-id="8187a-174">構文</span><span class="sxs-lookup"><span data-stu-id="8187a-174">Syntax</span></span>               |<span data-ttu-id="8187a-175">Razor</span><span class="sxs-lookup"><span data-stu-id="8187a-175">Razor</span></span>         |<span data-ttu-id="8187a-176">構文</span><span class="sxs-lookup"><span data-stu-id="8187a-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="8187a-177">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="8187a-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="8187a-178">コード ブロック</span><span class="sxs-lookup"><span data-stu-id="8187a-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="8187a-179">式</span><span class="sxs-lookup"><span data-stu-id="8187a-179">Expressions</span></span><br><span data-ttu-id="8187a-180">(HTML エンコード)</span><span class="sxs-lookup"><span data-stu-id="8187a-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="8187a-181">暗黙：`@`</span><span class="sxs-lookup"><span data-stu-id="8187a-181">Implicit: `@`</span></span><br><span data-ttu-id="8187a-182">明示的：`@()`</span><span class="sxs-lookup"><span data-stu-id="8187a-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="8187a-183">説明</span><span class="sxs-lookup"><span data-stu-id="8187a-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="8187a-184">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="8187a-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="8187a-185">Razor コンポーネント クラスにメンバーを追加するには、`@code`ディレクティブを使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="8187a-186">この方法は、web フォーム`<script runat="server">...</script>`のユーザー コントロールまたはページASP.NETブロックを使用する方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="8187a-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="8187a-187">Razor は C# に基づいているため、C# プロジェクト (*.csproj*) 内からコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="8187a-188">.razor ファイルは *.razor*、Visual Basic プロジェクト (*.vbproj*) からコンパイルできません。</span><span class="sxs-lookup"><span data-stu-id="8187a-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="8187a-189">ブラザプロジェクトから Visual Basic プロジェクトを参照することはできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="8187a-190">その逆も当てはまります。</span><span class="sxs-lookup"><span data-stu-id="8187a-190">The opposite is true too.</span></span>

<span data-ttu-id="8187a-191">完全な Razor 構文のリファレンスについては、「 [ASP.NET コアの Razor 構文のリファレンス](/aspnet/core/mvc/views/razor)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8187a-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="8187a-192">コンポーネントを使う</span><span class="sxs-lookup"><span data-stu-id="8187a-192">Use components</span></span>

<span data-ttu-id="8187a-193">通常の HTML 以外にも、コンポーネントはレンダリング ロジックの一部として他のコンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="8187a-194">Razor でコンポーネントを使用するための構文は、ASP.NET Web フォーム アプリでユーザー コントロールを使用するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="8187a-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="8187a-195">コンポーネントは、コンポーネントの型名と一致する要素タグを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="8187a-196">たとえば、次のようなコンポーネントを`Counter`追加できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="8187a-197">ASP.NET Web フォームとは異なり、Blazor のコンポーネント:</span><span class="sxs-lookup"><span data-stu-id="8187a-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="8187a-198">要素のプレフィックス (たとえば)`asp:`を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8187a-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="8187a-199">ページまたは*web.config*での登録は不要です。</span><span class="sxs-lookup"><span data-stu-id="8187a-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="8187a-200">.NET 型と同じように Razor コンポーネントを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="8187a-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="8187a-201">コンポーネントを含むアセンブリが参照されている場合、そのコンポーネントは使用可能です。</span><span class="sxs-lookup"><span data-stu-id="8187a-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="8187a-202">コンポーネントの名前空間をスコープにするには、ディレクティブを適用します`@using`。</span><span class="sxs-lookup"><span data-stu-id="8187a-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="8187a-203">既定の Blazor プロジェクトで見られるように、ディレクティブを`@using`*_Imports.razor*ファイルに配置して、同じディレクトリ内および子ディレクトリ内のすべての *.razor*ファイルにインポートされるようにするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="8187a-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="8187a-204">コンポーネントの名前空間がスコープ内にない場合は、C# のように、完全な型名を使用してコンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="8187a-205">コンポーネントのパラメーター</span><span class="sxs-lookup"><span data-stu-id="8187a-205">Component parameters</span></span>

<span data-ttu-id="8187a-206">web フォームASP.NETでは、パブリック プロパティを使用して、パラメーターとデータをコントロールにフローできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="8187a-207">これらのプロパティは、属性を使用してマークアップで設定することも、コードで直接設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="8187a-208">Blazor コンポーネントは同様の方法で動作しますが、コンポーネントのプロパティにもコンポーネントパラメータ`[Parameter]`と見なされる属性を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="8187a-209">次`Counter`のコンポーネントは、ボタンがクリック`IncrementAmount`されるたびにインクリメントする必要がある量を`Counter`指定するために使用できるコンポーネント パラメータを定義します。</span><span class="sxs-lookup"><span data-stu-id="8187a-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="8187a-210">Blazor でコンポーネントパラメータを指定するには、Web フォームで使用するASP.NETと同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="8187a-211">イベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="8187a-211">Event handlers</span></span>

<span data-ttu-id="8187a-212">web フォームと Blazor ASP.NETは、UI イベントを処理するためのイベント ベースのプログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="8187a-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="8187a-213">このようなイベントの例としては、ボタンのクリックやテキスト入力などがあります。</span><span class="sxs-lookup"><span data-stu-id="8187a-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="8187a-214">ASP.NET Web フォームでは、HTML サーバー コントロールを使用して DOM によって公開される UI イベントを処理したり、Web サーバー コントロールによって公開されるイベントを処理したりできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="8187a-215">イベントは、フォームのポストバック要求を通じてサーバー上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="8187a-216">次の Web フォーム ボタンのクリック例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="8187a-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="8187a-217">*カウンター.ascx*</span><span class="sxs-lookup"><span data-stu-id="8187a-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="8187a-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="8187a-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="8187a-219">Blazor では、FORM`@on{event}`のディレクティブ属性を使用して DOM UI イベントのハンドラを直接登録できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="8187a-220">プレースホルダ`{event}`は、イベントの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="8187a-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="8187a-221">たとえば、次のようなボタンのクリックをリッスンできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="8187a-222">イベント ハンドラーは、イベントに関する詳細情報を提供するために、オプションのイベント固有の引数を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="8187a-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="8187a-223">たとえば、マウス イベントは引数を`MouseEventArgs`取ることができますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="8187a-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="8187a-224">イベント ハンドラーのメソッド グループを参照する代わりに、ラムダ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="8187a-225">ラムダ式を使用すると、スコープ内の他の値を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="8187a-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="8187a-226">イベント ハンドラは、同期的または非同期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="8187a-227">たとえば、次`OnClick`のイベント ハンドラーは非同期で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="8187a-228">イベントが処理されると、コンポーネントの状態が変更された場合に対応するようにコンポーネントがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8187a-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="8187a-229">非同期イベント ハンドラーを使用すると、コンポーネントはハンドラーの実行が完了した直後にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8187a-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="8187a-230">コンポーネントは、非同期`Task`の完了後に*再び*レンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8187a-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="8187a-231">この非同期実行モードは、非同期`Task`がまだ進行中の状態で、適切な UI を表示する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="8187a-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="8187a-232">コンポーネントは、 type`EventCallback<TValue>`のコンポーネント パラメータを定義することによって、独自のイベントを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="8187a-233">イベント コールバックは、オプションの引数、同期または非同期、メソッド グループ、ラムダ式など、DOM UI イベント ハンドラーのすべてのバリエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8187a-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="8187a-234">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="8187a-234">Data binding</span></span>

<span data-ttu-id="8187a-235">Blazor は、UI コンポーネントからコンポーネントの状態にデータをバインドする簡単なメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="8187a-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="8187a-236">この方法は、データ ソースから UI コントロールにデータをバインドする場合の、ASP.NET Web フォームの機能とは異なります。</span><span class="sxs-lookup"><span data-stu-id="8187a-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="8187a-237">「データの取り扱い」セクションで、さまざまなデータ ソースからの[データの処理について](data.md)説明します。</span><span class="sxs-lookup"><span data-stu-id="8187a-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="8187a-238">UI コンポーネントからコンポーネントの状態への双方向データ バインディングを作成するには、ディレクティブ属性を使用します`@bind`。</span><span class="sxs-lookup"><span data-stu-id="8187a-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="8187a-239">次の例では、チェック ボックスの値がフィールドに`isChecked`バインドされています。</span><span class="sxs-lookup"><span data-stu-id="8187a-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="8187a-240">コンポーネントがレンダリングされると、チェックボックスの値はフィールドの値に設定されます`isChecked`。</span><span class="sxs-lookup"><span data-stu-id="8187a-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="8187a-241">ユーザーがチェックボックスを切り替えた場合`onchange`、イベントが発生し`isChecked`、フィールドが新しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="8187a-242">この`@bind`場合の構文は、次のマークアップと同じです。</span><span class="sxs-lookup"><span data-stu-id="8187a-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="8187a-243">バインドに使用するイベントを変更するには、 属性`@bind:event`を使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="8187a-244">コンポーネントは、パラメーターへのデータ バインディングもサポートできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="8187a-245">データ バインドするには、バインド可能なパラメーターと同じ名前のイベント コールバック パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="8187a-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="8187a-246">名前に"変更済み" サフィックスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="8187a-247">*パスワードボックス.カミソリ*</span><span class="sxs-lookup"><span data-stu-id="8187a-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="8187a-248">基になる UI 要素にデータ バインディングを連結するには、値を設定し、属性を使用する代わりに UI`@bind`要素で直接イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="8187a-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="8187a-249">コンポーネント・パラメーターにバインドするには、属性を`@bind-{Parameter}`使用して、バインドするパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8187a-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="8187a-250">状態の変化</span><span class="sxs-lookup"><span data-stu-id="8187a-250">State changes</span></span>

<span data-ttu-id="8187a-251">コンポーネントの状態が通常の UI イベントまたはイベント コールバックの外部で変更された場合、コンポーネントは再描画が必要であることを手動で通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="8187a-252">コンポーネントの状態が変化したことを通知するには、コンポーネントの`StateHasChanged`メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8187a-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="8187a-253">次の例では、コンポーネントは、アプリの`AppState`他の部分で更新できるサービスからのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="8187a-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="8187a-254">コンポーネントは`StateHasChanged`、メッセージが更新されるたびにコンポーネント`AppState.OnChange`がレンダリングされるように、そのメソッドをイベントに登録します。</span><span class="sxs-lookup"><span data-stu-id="8187a-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="8187a-255">コンポーネントのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="8187a-255">Component lifecycle</span></span>

<span data-ttu-id="8187a-256">web フォーム フレームワークASP.NETには、モジュール、ページ、およびコントロールのライフサイクル メソッドが明確に定義されています。</span><span class="sxs-lookup"><span data-stu-id="8187a-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="8187a-257">たとえば、次のコントロールは、 、`Init``Load`およびライフサイクル イベントのイベント`UnLoad`ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="8187a-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="8187a-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="8187a-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="8187a-259">Blazor コンポーネントには、明確に定義されたライフサイクルもあります。</span><span class="sxs-lookup"><span data-stu-id="8187a-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="8187a-260">コンポーネントのライフサイクルを使用して、コンポーネントの状態を初期化し、コンポーネントの高度な動作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="8187a-261">Blazor のコンポーネントライフサイクルメソッドはすべて、同期バージョンと非同期バージョンの両方を備えています。</span><span class="sxs-lookup"><span data-stu-id="8187a-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="8187a-262">コンポーネントのレンダリングは同期的です。</span><span class="sxs-lookup"><span data-stu-id="8187a-262">Component rendering is synchronous.</span></span> <span data-ttu-id="8187a-263">コンポーネントのレンダリングの一部として非同期ロジックを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="8187a-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="8187a-264">すべての非同期ロジックは、ライフサイクル メソッドの`async`一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="8187a-265">初期化中</span><span class="sxs-lookup"><span data-stu-id="8187a-265">OnInitialized</span></span>

<span data-ttu-id="8187a-266">`OnInitialized`メソッドと`OnInitializedAsync`メソッドは、コンポーネントの初期化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="8187a-267">コンポーネントは通常、最初にレンダリングされた後に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="8187a-268">コンポーネントが初期化された後、最終的に破棄される前に複数回レンダリングされることがあります。</span><span class="sxs-lookup"><span data-stu-id="8187a-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="8187a-269">この`OnInitialized`メソッドは、Web`Page_Load`フォーム ページおよびコントロールASP.NETでのイベントに似ています。</span><span class="sxs-lookup"><span data-stu-id="8187a-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="8187a-270">パラメーターセット</span><span class="sxs-lookup"><span data-stu-id="8187a-270">OnParametersSet</span></span>

<span data-ttu-id="8187a-271">`OnParametersSet`コンポーネントが`OnParametersSetAsync`親からパラメータを受け取り、値がプロパティに割り当てられると、 と メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="8187a-272">これらのメソッドは、コンポーネントの初期化後、および*コンポーネントがレンダリングされるたびに実行されます*。</span><span class="sxs-lookup"><span data-stu-id="8187a-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="8187a-273">アフターレンダー</span><span class="sxs-lookup"><span data-stu-id="8187a-273">OnAfterRender</span></span>

<span data-ttu-id="8187a-274">`OnAfterRender`と`OnAfterRenderAsync`メソッドは、コンポーネントのレンダリングが終了した後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="8187a-275">要素参照とコンポーネント参照は、この時点で設定されます (詳細は、以下の概念)。</span><span class="sxs-lookup"><span data-stu-id="8187a-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="8187a-276">この時点で、ブラウザとの対話機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8187a-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="8187a-277">DOM および JavaScript の実行との対話は安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8187a-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="8187a-278">`OnAfterRender``OnAfterRenderAsync`*サーバーでのプレレンダリング時に呼び出されません*。</span><span class="sxs-lookup"><span data-stu-id="8187a-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="8187a-279">この`firstRender`パラメーターは`true`、コンポーネントが最初にレンダリングされる時間です。それ以外の場合、`false`その値は です。</span><span class="sxs-lookup"><span data-stu-id="8187a-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="8187a-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="8187a-280">IDisposable</span></span>

<span data-ttu-id="8187a-281">Blazor コンポーネントは`IDisposable`、コンポーネントが UI から削除されたときにリソースを破棄するために実装できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="8187a-282">Razor コンポーネントは、`IDispose`ディレクティブを`@implements`使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="8187a-283">コンポーネント参照のキャプチャ</span><span class="sxs-lookup"><span data-stu-id="8187a-283">Capture component references</span></span>

<span data-ttu-id="8187a-284">ASP.NET Web フォームでは、コントロールの ID を参照して、コード内でコントロール インスタンスを直接操作するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="8187a-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="8187a-285">Blazor では、コンポーネントへの参照をキャプチャして操作することも可能ですが、あまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="8187a-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="8187a-286">Blazor でコンポーネント参照をキャプチャするには、ディレクティブ`@ref`属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="8187a-287">属性の値は、参照されるコンポーネントと同じ型の設定可能なフィールドの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="8187a-288">親コンポーネントがレンダリングされると、フィールドに子コンポーネントインスタンスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="8187a-289">その後、コンポーネント インスタンスに対してメソッドを呼び出したり、操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="8187a-290">コンポーネント参照を使用してコンポーネントの状態を直接操作することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="8187a-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="8187a-291">これにより、コンポーネントが正しい時刻に自動的にレンダリングされなくなります。</span><span class="sxs-lookup"><span data-stu-id="8187a-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="8187a-292">要素参照のキャプチャ</span><span class="sxs-lookup"><span data-stu-id="8187a-292">Capture element references</span></span>

<span data-ttu-id="8187a-293">Blazor コンポーネントは、要素への参照をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="8187a-294">web フォーム ASP.NETの HTML サーバー コントロールとは異なり、Blazor の要素参照を使用して DOM を直接操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="8187a-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="8187a-295">Blazor は DOM ディファリング アルゴリズムを使用して、ほとんどの DOM インタラクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="8187a-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="8187a-296">Blazor でキャプチャされた要素参照は不透明です。</span><span class="sxs-lookup"><span data-stu-id="8187a-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="8187a-297">ただし、JavaScript 相互運用呼び出しで特定の要素参照を渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="8187a-298">JavaScript 相互運用機能の詳細については、「[コア Blazor JavaScript の相互運用機能ASP.NET」](/aspnet/core/blazor/javascript-interop)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8187a-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="8187a-299">テンプレート コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8187a-299">Templated components</span></span>

<span data-ttu-id="8187a-300">ASP.NET Web フォームでは、 テンプレート*コントロール*を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="8187a-301">テンプレート コントロールを使用すると、開発者はコンテナ コントロールのレンダリングに使用する HTML の一部を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="8187a-302">テンプレート化されたサーバー コントロールを構築するしくみは複雑ですが、ユーザーがカスタマイズ可能な方法でデータをレンダリングする強力なシナリオを実現します。</span><span class="sxs-lookup"><span data-stu-id="8187a-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="8187a-303">テンプレート コントロールの例として`Repeater`は`DataList`、 および が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8187a-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="8187a-304">Blazor コンポーネントは、型`RenderFragment`または`RenderFragment<T>`のコンポーネント パラメータを定義することによってテンプレート化することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="8187a-305">A`RenderFragment`は、コンポーネントによってレンダリングできる Razor マークアップのチャンクを表します。</span><span class="sxs-lookup"><span data-stu-id="8187a-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="8187a-306">A`RenderFragment<T>`は、レンダリング フラグメントがレンダリングされるときに指定できるパラメーターを受け取る Razor マークアップのチャンクです。</span><span class="sxs-lookup"><span data-stu-id="8187a-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="8187a-307">子コンテンツ</span><span class="sxs-lookup"><span data-stu-id="8187a-307">Child content</span></span>

<span data-ttu-id="8187a-308">Blazor コンポーネントは、子コンテンツを`RenderFragment`a としてキャプチャし、そのコンテンツをコンポーネントレンダリングの一部としてレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="8187a-309">子コンテンツをキャプチャするには、型`RenderFragment`のコンポーネント パラメータを定義し`ChildContent`、 という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="8187a-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="8187a-310">*かみそり*</span><span class="sxs-lookup"><span data-stu-id="8187a-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="8187a-311">親コンポーネントは、通常の Razor 構文を使用して子コンテンツを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="8187a-312">Template parameters</span><span class="sxs-lookup"><span data-stu-id="8187a-312">Template parameters</span></span>

<span data-ttu-id="8187a-313">テンプレート化された Blazor コンポーネントは、型`RenderFragment`または`RenderFragment<T>`の複数のコンポーネントパラメータを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="8187a-314">のパラメーターは、`RenderFragment<T>`呼び出されたときに指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="8187a-315">コンポーネントのジェネリック型パラメーターを指定するには、Razor ディレクティブ`@typeparam`を使用します。</span><span class="sxs-lookup"><span data-stu-id="8187a-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="8187a-316">*カミソリ*</span><span class="sxs-lookup"><span data-stu-id="8187a-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="8187a-317">テンプレート コンポーネントを使用する場合、テンプレート パラメーターは、パラメーターの名前に一致する子要素を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="8187a-318">要素として渡される`RenderFragment<T>`型のコンポーネント引数には、 という`context`名前の暗黙のパラメータがあります。</span><span class="sxs-lookup"><span data-stu-id="8187a-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="8187a-319">この実装パラメーターの名前は、子要素の属性`Context`を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="8187a-320">型パラメーターの名前と一致する属性を使用して、任意のジェネリック型パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8187a-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="8187a-321">可能であれば、型パラメーターは推論されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="8187a-322">このコンポーネントの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8187a-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="8187a-323">コードビハインド</span><span class="sxs-lookup"><span data-stu-id="8187a-323">Code-behind</span></span>

<span data-ttu-id="8187a-324">通常、Blazor コンポーネントは、1 つの *.razor*ファイルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="8187a-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="8187a-325">ただし、分離コード ファイルを使用してコードとマークアップを分離することもできます。</span><span class="sxs-lookup"><span data-stu-id="8187a-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="8187a-326">コンポーネント ファイルを使用するには、コンポーネント ファイルのファイル名と一致する C# ファイルを *.cs*追加します*Counter.razor.cs。*</span><span class="sxs-lookup"><span data-stu-id="8187a-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="8187a-327">C# ファイルを使用して、コンポーネントの基本クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8187a-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="8187a-328">基本クラスには、必要な名前を付けることができますが、クラスの名前はコンポーネント クラスと同じですが、`Base`拡張子が追加されています (`CounterBase`)。</span><span class="sxs-lookup"><span data-stu-id="8187a-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="8187a-329">コンポーネント ベースのクラスも`ComponentBase`から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="8187a-330">次に、Razor コンポーネント ファイルで、`@inherits`コンポーネントの基本クラスを指定するディレクティブを追加`@inherits CounterBase`します ( ) 。</span><span class="sxs-lookup"><span data-stu-id="8187a-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="8187a-331">*カウンターカミソリ*</span><span class="sxs-lookup"><span data-stu-id="8187a-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="8187a-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="8187a-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="8187a-333">基本クラス内のコンポーネントのメンバーの可視性は、コンポーネント クラス`protected`に`public`対して可視であるか、またはコンポーネント クラスから参照可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8187a-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8187a-334">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="8187a-334">Additional resources</span></span>

<span data-ttu-id="8187a-335">上記は、Blazor コンポーネントのすべての側面を網羅的に扱うものではありません。</span><span class="sxs-lookup"><span data-stu-id="8187a-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="8187a-336">[作成し、コア Razor コンポーネントを使用する](/aspnet/core/blazor/components)方法の詳細については、ASP.NETのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8187a-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8187a-337">[前次](app-startup.md)
>[Next](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="8187a-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
