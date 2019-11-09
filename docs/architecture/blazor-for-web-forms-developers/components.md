---
title: Blazor を使用して再利用可能な UI コンポーネントを構築する
description: Blazor を使用して再利用可能な UI コンポーネントを構築する方法と、それらを ASP.NET Web フォームコントロールと比較する方法について説明します。
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 79919b183a4eb759f0b27c97500ee71c9378770b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841961"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="9bd44-103">Blazor を使用して再利用可能な UI コンポーネントを構築する</span><span class="sxs-lookup"><span data-stu-id="9bd44-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9bd44-104">ASP.NET Web フォームに関するすばらしい点の1つは、再利用可能なユーザーインターフェイス (UI) コードを再利用可能な UI コントロールにカプセル化できるようにする方法です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="9bd44-105">カスタムユーザーコントロールは、 *.ascx*ファイルを使用してマークアップで定義できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="9bd44-106">デザイナーを完全にサポートするコードで、複雑なサーバーコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="9bd44-107">Blazor は、*コンポーネント*による UI カプセル化もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="9bd44-108">コンポーネント:</span><span class="sxs-lookup"><span data-stu-id="9bd44-108">A component:</span></span>

- <span data-ttu-id="9bd44-109">は、UI の自己完結型のチャンクです。</span><span class="sxs-lookup"><span data-stu-id="9bd44-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="9bd44-110">は、独自の状態およびレンダリングロジックを保持します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="9bd44-111">UI イベントハンドラーを定義し、入力データにバインドして、独自のライフサイクルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="9bd44-112">は、通常、Razor 構文を使用する*razor*ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="9bd44-113">Razor の概要</span><span class="sxs-lookup"><span data-stu-id="9bd44-113">An introduction to Razor</span></span>

<span data-ttu-id="9bd44-114">Razor は、HTML およびC#に基づく軽量のマークアップテンプレート言語です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="9bd44-115">Razor を使用すると、マークアップとC#コードをシームレスに切り替えて、コンポーネントのレンダリングロジックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="9bd44-116">*Razor*ファイルがコンパイルされると、レンダリングロジックは .net クラスで構造化された方法でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="9bd44-117">コンパイル済みクラスの名前は、 *razor*ファイル名から取得されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="9bd44-118">名前空間は、プロジェクトの既定の名前空間およびフォルダーパスから取得します。また、`@namespace` ディレクティブを使用して名前空間を明示的に指定することもできます (以下の Razor ディレクティブについてはこちらを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="9bd44-119">コンポーネントのレンダリングロジックは、を使用してC#動的なロジックを追加した通常の HTML マークアップを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="9bd44-120">`@` 文字は、にC#移行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="9bd44-121">Razor は、通常、HTML に切り替えたときに理解することが賢明です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="9bd44-122">たとえば、次のコンポーネントは、現在の時刻で `<p>` タグをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="9bd44-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="9bd44-123">C#式の開始と終了を明示的に指定するには、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="9bd44-124">Razor では、レンダリングロジックでC#制御フローを簡単に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="9bd44-125">たとえば、次のような HTML を条件付きでレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="9bd44-126">または、次のように通常C#の `foreach` ループを使用して項目の一覧を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>item.Text</li>
}
</ul>
```

<span data-ttu-id="9bd44-127">Razor ディレクティブは、ASP.NET Web フォームのディレクティブと同様に、Razor コンポーネントのコンパイル方法の多くの側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="9bd44-128">コンポーネントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-128">Examples include the component's:</span></span>

- <span data-ttu-id="9bd44-129">Namespace</span><span class="sxs-lookup"><span data-stu-id="9bd44-129">Namespace</span></span>
- <span data-ttu-id="9bd44-130">基底クラス</span><span class="sxs-lookup"><span data-stu-id="9bd44-130">Base class</span></span>
- <span data-ttu-id="9bd44-131">実装されたインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bd44-131">Implemented interfaces</span></span>
- <span data-ttu-id="9bd44-132">ジェネリックパラメーター</span><span class="sxs-lookup"><span data-stu-id="9bd44-132">Generic parameters</span></span>
- <span data-ttu-id="9bd44-133">インポートされた名前空間</span><span class="sxs-lookup"><span data-stu-id="9bd44-133">Imported namespaces</span></span>
- <span data-ttu-id="9bd44-134">ルート</span><span class="sxs-lookup"><span data-stu-id="9bd44-134">Routes</span></span>

<span data-ttu-id="9bd44-135">Razor ディレクティブは `@` 文字で始まり、通常、ファイルの先頭にある新しい行の先頭で使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="9bd44-136">たとえば、`@namespace` ディレクティブは、コンポーネントの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="9bd44-137">次の表は、Blazor で使用されるさまざまな Razor ディレクティブとそれらの ASP.NET Web フォームに相当するものをまとめたものです (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="9bd44-138">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9bd44-138">Directive</span></span>    |<span data-ttu-id="9bd44-139">説明</span><span class="sxs-lookup"><span data-stu-id="9bd44-139">Description</span></span>|<span data-ttu-id="9bd44-140">例</span><span class="sxs-lookup"><span data-stu-id="9bd44-140">Example</span></span>|<span data-ttu-id="9bd44-141">同等の Web フォーム</span><span class="sxs-lookup"><span data-stu-id="9bd44-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="9bd44-142">コンポーネントにクラスレベルの属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="9bd44-143">None</span><span class="sxs-lookup"><span data-stu-id="9bd44-143">None</span></span>|
|`@code`      |<span data-ttu-id="9bd44-144">コンポーネントにクラスメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="9bd44-145">指定したインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="9bd44-146">分離コードを使用する</span><span class="sxs-lookup"><span data-stu-id="9bd44-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="9bd44-147">指定した基底クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="9bd44-148">コンポーネントにサービスを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="9bd44-149">None</span><span class="sxs-lookup"><span data-stu-id="9bd44-149">None</span></span>|
|`@layout`    |<span data-ttu-id="9bd44-150">コンポーネントのレイアウトコンポーネントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="9bd44-151">コンポーネントの名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="9bd44-152">None</span><span class="sxs-lookup"><span data-stu-id="9bd44-152">None</span></span>|
|`@page`      |<span data-ttu-id="9bd44-153">コンポーネントのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="9bd44-154">コンポーネントのジェネリック型パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="9bd44-155">分離コードを使用する</span><span class="sxs-lookup"><span data-stu-id="9bd44-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="9bd44-156">スコープに取り込む名前空間を指定します</span><span class="sxs-lookup"><span data-stu-id="9bd44-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="9bd44-157">*Web.config に名前*空間を追加する</span><span class="sxs-lookup"><span data-stu-id="9bd44-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="9bd44-158">また、Razor コンポーネントでは、要素に対して*ディレクティブ属性*を広範に使用して、コンポーネントのコンパイル (イベント処理、データバインディング、コンポーネント & 要素参照など) のさまざまな側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="9bd44-159">ディレクティブ属性は、かっこ内の値が省略可能である一般的なジェネリック構文に従います。</span><span class="sxs-lookup"><span data-stu-id="9bd44-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="9bd44-160">次の表は、Blazor で使用される Razor ディレクティブのさまざまな属性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="9bd44-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="9bd44-161">属性</span><span class="sxs-lookup"><span data-stu-id="9bd44-161">Attribute</span></span>    |<span data-ttu-id="9bd44-162">説明</span><span class="sxs-lookup"><span data-stu-id="9bd44-162">Description</span></span>|<span data-ttu-id="9bd44-163">例</span><span class="sxs-lookup"><span data-stu-id="9bd44-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="9bd44-164">属性のディクショナリをレンダリングします</span><span class="sxs-lookup"><span data-stu-id="9bd44-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="9bd44-165">双方向のデータバインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="9bd44-166">指定したイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="9bd44-167">コレクション内の要素を保持するために比較アルゴリズムによって使用されるキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="9bd44-168">コンポーネントまたは HTML 要素への参照をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="9bd44-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="9bd44-169">Blazor (`@onclick`、`@bind`、`@ref`など) で使用されるさまざまなディレクティブ属性については、以降の章で説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="9bd44-170">*.Aspx*および *.ascx*ファイルで使用される構文の多くには、Razor の並列構文があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="9bd44-171">次に、ASP.NET Web フォームと Razor の構文を簡単に比較します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="9bd44-172">特性</span><span class="sxs-lookup"><span data-stu-id="9bd44-172">Feature</span></span>                      |<span data-ttu-id="9bd44-173">Web フォーム</span><span class="sxs-lookup"><span data-stu-id="9bd44-173">Web Forms</span></span>           |<span data-ttu-id="9bd44-174">構文</span><span class="sxs-lookup"><span data-stu-id="9bd44-174">Syntax</span></span>               |<span data-ttu-id="9bd44-175">Razor</span><span class="sxs-lookup"><span data-stu-id="9bd44-175">Razor</span></span>         |<span data-ttu-id="9bd44-176">構文</span><span class="sxs-lookup"><span data-stu-id="9bd44-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="9bd44-177">ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9bd44-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="9bd44-178">コードブロック</span><span class="sxs-lookup"><span data-stu-id="9bd44-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="9bd44-179">式</span><span class="sxs-lookup"><span data-stu-id="9bd44-179">Expressions</span></span><br><span data-ttu-id="9bd44-180">(HTML エンコード)</span><span class="sxs-lookup"><span data-stu-id="9bd44-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="9bd44-181">暗黙的: `@`</span><span class="sxs-lookup"><span data-stu-id="9bd44-181">Implicit: `@`</span></span><br><span data-ttu-id="9bd44-182">Explicit: `@()`</span><span class="sxs-lookup"><span data-stu-id="9bd44-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="9bd44-183">コメント</span><span class="sxs-lookup"><span data-stu-id="9bd44-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="9bd44-184">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="9bd44-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="9bd44-185">Razor コンポーネントクラスにメンバーを追加するには、`@code` ディレクティブを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="9bd44-186">この手法は、ASP.NET Web フォームのユーザーコントロールまたはページで `<script runat="server">...</script>` ブロックを使用するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="9bd44-187">Razor はにC#基づいているため、 C#プロジェクト ( *.csproj*) 内からコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="9bd44-188">VB プロジェクト ( *.vbproj*) から*razor*ファイルをコンパイルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-188">You can't compile *.razor* files from a VB project (*.vbproj*).</span></span> <span data-ttu-id="9bd44-189">Blazor プロジェクトから VB プロジェクトを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-189">You can still reference VB projects from your Blazor project.</span></span> <span data-ttu-id="9bd44-190">逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-190">The opposite is true too.</span></span>

<span data-ttu-id="9bd44-191">完全 Razor 構文リファレンスについては、「 [ASP.NET Core の Razor 構文リファレンス](/aspnet/core/mvc/views/razor)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd44-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="9bd44-192">コンポーネントを使う</span><span class="sxs-lookup"><span data-stu-id="9bd44-192">Use components</span></span>

<span data-ttu-id="9bd44-193">通常の HTML とは別に、コンポーネントはレンダリングロジックの一部として他のコンポーネントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="9bd44-194">Razor でコンポーネントを使用するための構文は、ASP.NET Web フォームアプリでユーザーコントロールを使用する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="9bd44-195">コンポーネントは、コンポーネントの型名と一致する要素タグを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="9bd44-196">たとえば、次のような `Counter` コンポーネントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="9bd44-197">ASP.NET Web フォームとは異なり、Blazor のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9bd44-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="9bd44-198">要素のプレフィックスは使用しないでください (たとえば、`asp:`)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="9bd44-199">ページまた*は web.config で*の登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="9bd44-200">.NET 型のような Razor コンポーネントについて考えてみましょう。これはまさにそのようなものです。</span><span class="sxs-lookup"><span data-stu-id="9bd44-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="9bd44-201">コンポーネントを含むアセンブリが参照されている場合は、コンポーネントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="9bd44-202">コンポーネントの名前空間をスコープに入れるには、`@using` ディレクティブを適用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="9bd44-203">既定の Blazor プロジェクトに示されているように、`@using` ディレクティブは、同じディレクトリおよび子ディレクトリ内のすべての*razor*ファイルにインポートされるように *_Imports razor*ファイルに配置するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="9bd44-204">コンポーネントの名前空間がスコープ内にない場合は、次のようにC#、完全な型名を使用してコンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="9bd44-205">コンポーネントのパラメーター</span><span class="sxs-lookup"><span data-stu-id="9bd44-205">Component parameters</span></span>

<span data-ttu-id="9bd44-206">ASP.NET Web フォームでは、パブリックプロパティを使用して、パラメーターとデータをコントロールにフローできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="9bd44-207">これらのプロパティは、属性を使用してマークアップで設定することも、コードで直接設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="9bd44-208">Blazor コンポーネントは同様の方法で動作しますが、コンポーネントのプロパティは、コンポーネントのパラメーターと見なされるように、`[Parameter]` 属性でマークする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="9bd44-209">次の `Counter` コンポーネントでは、ボタンがクリックされるたびに `Counter` をインクリメントする量を指定するために使用できる `IncrementAmount` と呼ばれるコンポーネントパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="9bd44-210">Blazor でコンポーネントパラメーターを指定するには、ASP.NET Web フォームの場合と同様に属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="9bd44-211">イベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="9bd44-211">Event handlers</span></span>

<span data-ttu-id="9bd44-212">ASP.NET Web Forms と Blazor はどちらも、UI イベントを処理するためのイベントベースのプログラミングモデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="9bd44-213">このようなイベントの例としては、ボタンのクリックやテキスト入力などがあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="9bd44-214">ASP.NET Web フォームでは、HTML サーバーコントロールを使用して、DOM によって公開される UI イベントを処理したり、web サーバーコントロールによって公開されるイベントを処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="9bd44-215">イベントは、ポストバック要求のフォームを使用してサーバー上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="9bd44-216">次の Web フォームのボタンをクリックする例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="9bd44-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="9bd44-217">*カウンタ .ascx*</span><span class="sxs-lookup"><span data-stu-id="9bd44-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="9bd44-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="9bd44-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="9bd44-219">Blazor では、`@on{event}`フォームのディレクティブ属性を使用して、DOM UI イベントのハンドラーを直接登録できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="9bd44-220">`{event}` プレースホルダーは、イベントの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="9bd44-221">たとえば、次のようなボタンのクリックをリッスンできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="9bd44-222">イベントハンドラーは、イベントに関する詳細情報を提供するために、省略可能なイベント固有の引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="9bd44-223">たとえば、マウスイベントは `MouseEventArgs` 引数を受け取ることができますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="9bd44-224">イベントハンドラーのメソッドグループを参照する代わりに、ラムダ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="9bd44-225">ラムダ式を使用すると、他のスコープ内の値を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="9bd44-226">イベントハンドラーは、同期または非同期で実行できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="9bd44-227">たとえば、次の `OnClick` イベントハンドラーは非同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="9bd44-228">イベントが処理されると、コンポーネントは、コンポーネントの状態の変更を考慮してレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="9bd44-229">非同期イベントハンドラーを使用すると、ハンドラーの実行が完了した直後にコンポーネントがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="9bd44-230">非同期 `Task` が完了すると、コンポーネントが*再び*表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="9bd44-231">この非同期実行モードでは、非同期 `Task` がまだ進行中であるときに、適切な UI を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="Get message">Get message</button>

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

<span data-ttu-id="9bd44-232">コンポーネントでは、`EventCallback<TValue>`型のコンポーネントパラメーターを定義することで、独自のイベントを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="9bd44-233">イベントコールバックは、省略可能な引数、同期または非同期、メソッドグループ、ラムダ式など、DOM UI イベントハンドラーのすべてのバリエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9bd44-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="9bd44-234">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="9bd44-234">Data binding</span></span>

<span data-ttu-id="9bd44-235">Blazor には、UI コンポーネントからコンポーネントの状態にデータをバインドするための単純なメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="9bd44-236">この方法は、データソースから UI コントロールにデータをバインドするための ASP.NET Web フォームの機能とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="9bd44-237">データの処理に[関する](data.md)セクションでは、さまざまなデータソースからのデータの処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="9bd44-238">UI コンポーネントからコンポーネントの状態への双方向のデータバインディングを作成するには、`@bind` ディレクティブ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="9bd44-239">次の例では、チェックボックスの値が `isChecked` フィールドにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="9bd44-240">コンポーネントがレンダリングされると、チェックボックスの値が [`isChecked`] フィールドの値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="9bd44-241">ユーザーがチェックボックスをオンにすると、`onchange` イベントが発生し、`isChecked` フィールドに新しい値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="9bd44-242">この場合の `@bind` 構文は、次のマークアップに相当します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="9bd44-243">バインドに使用するイベントを変更するには、`@bind:event` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="9bd44-244">コンポーネントは、パラメーターへのデータバインディングをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="9bd44-245">データバインドには、バインド可能なパラメーターと同じ名前のイベントコールバックパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="9bd44-246">"Changed" サフィックスが名前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="9bd44-247">*PasswordBox。 razor*</span><span class="sxs-lookup"><span data-stu-id="9bd44-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="9bd44-248">データバインディングを基になる UI 要素に連結するには、値を設定し、`@bind` 属性を使用するのではなく、UI 要素で直接イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="9bd44-249">コンポーネントパラメーターにバインドするには、`@bind-{Parameter}` 属性を使用して、バインド先のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="9bd44-250">状態変更</span><span class="sxs-lookup"><span data-stu-id="9bd44-250">State changes</span></span>

<span data-ttu-id="9bd44-251">コンポーネントの状態が通常の UI イベントまたはイベントコールバックの外部で変更された場合、コンポーネントは、再レンダリングが必要であることを手動で通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="9bd44-252">コンポーネントの状態が変更されたことを通知するには、コンポーネントの `StateHasChanged` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="9bd44-253">次の例では、アプリケーションの他の部分で更新できる `AppState` サービスからのメッセージがコンポーネントによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="9bd44-254">コンポーネントは、`StateHasChanged` メソッドを `AppState.OnChange` イベントに登録して、メッセージが更新されるたびにコンポーネントがレンダリングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="9bd44-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

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

## <a name="component-lifecycle"></a><span data-ttu-id="9bd44-255">コンポーネントのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="9bd44-255">Component lifecycle</span></span>

<span data-ttu-id="9bd44-256">ASP.NET Web Forms framework には、モジュール、ページ、およびコントロールに対して明確に定義されたライフサイクルメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="9bd44-257">たとえば、次のコントロールは、`Init`、`Load`、および `UnLoad` ライフサイクルイベントのイベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="9bd44-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="9bd44-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="9bd44-259">Blazor コンポーネントにも、明確に定義されたライフサイクルがあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="9bd44-260">コンポーネントのライフサイクルは、コンポーネントの状態を初期化し、高度なコンポーネントの動作を実装するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="9bd44-261">すべての Blazor のコンポーネントライフサイクルメソッドには、同期バージョンと非同期バージョンの両方があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="9bd44-262">コンポーネントのレンダリングは同期です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-262">Component rendering is synchronous.</span></span> <span data-ttu-id="9bd44-263">コンポーネントレンダリングの一部として非同期ロジックを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="9bd44-264">すべての非同期ロジックは、`async` ライフサイクルメソッドの一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="9bd44-265">OnInitialized 化</span><span class="sxs-lookup"><span data-stu-id="9bd44-265">OnInitialized</span></span>

<span data-ttu-id="9bd44-266">コンポーネントを初期化するには、`OnInitialized` メソッドと `OnInitializedAsync` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="9bd44-267">コンポーネントは通常、最初のレンダリング後に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="9bd44-268">コンポーネントが初期化されると、最終的に破棄される前に複数回レンダリングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="9bd44-269">`OnInitialized` メソッドは、ASP.NET Web フォームのページおよびコントロールの `Page_Load` イベントに似ています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="9bd44-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="9bd44-270">OnParametersSet</span></span>

<span data-ttu-id="9bd44-271">コンポーネントが親からパラメーターを受け取り、値がプロパティに割り当てられると、`OnParametersSet` メソッドと `OnParametersSetAsync` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="9bd44-272">これらのメソッドは、コンポーネントの初期化の後、および*コンポーネントがレンダリング*されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="9bd44-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="9bd44-273">OnAfterRender</span></span>

<span data-ttu-id="9bd44-274">`OnAfterRender` メソッドと `OnAfterRenderAsync` メソッドは、コンポーネントのレンダリングが完了した後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="9bd44-275">この時点で、要素参照とコンポーネント参照が設定されます (以下の概念を参照)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="9bd44-276">この時点では、ブラウザーとの対話機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9bd44-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="9bd44-277">DOM および JavaScript の実行とのやり取りは、安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="9bd44-278">`OnAfterRender` と `OnAfterRenderAsync`*は、サーバーでのプリレンダリング時に呼び出されません*。</span><span class="sxs-lookup"><span data-stu-id="9bd44-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="9bd44-279">`firstRender` パラメーターは、コンポーネントが初めてレンダリングされるときに `true` ます。それ以外の場合、その値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="9bd44-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="9bd44-280">IDisposable</span></span>

<span data-ttu-id="9bd44-281">Blazor コンポーネントは、UI からコンポーネントが削除されたときに、リソースを破棄する `IDisposable` を実装できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="9bd44-282">Razor コンポーネントは、`@implements` ディレクティブを使用して `IDispose` を実装できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="9bd44-283">コンポーネント参照のキャプチャ</span><span class="sxs-lookup"><span data-stu-id="9bd44-283">Capture component references</span></span>

<span data-ttu-id="9bd44-284">ASP.NET Web フォームでは、ID を参照することによって、コントロールインスタンスをコード内で直接操作するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="9bd44-285">Blazor では、コンポーネントへの参照をキャプチャして操作することもできますが、これはあまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="9bd44-286">Blazor でコンポーネント参照をキャプチャするには、`@ref` ディレクティブ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="9bd44-287">属性の値は、参照されるコンポーネントと同じ型の設定可能フィールドの名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="9bd44-288">親コンポーネントがレンダリングされると、そのフィールドに子コンポーネントインスタンスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="9bd44-289">その後、コンポーネントインスタンスのメソッドを呼び出したり、それ以外の操作を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="9bd44-290">コンポーネント参照を使用してコンポーネントの状態を直接操作することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="9bd44-291">これにより、コンポーネントが適切な時刻に自動的にレンダリングされるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="9bd44-292">要素参照のキャプチャ</span><span class="sxs-lookup"><span data-stu-id="9bd44-292">Capture element references</span></span>

<span data-ttu-id="9bd44-293">Blazor コンポーネントは、要素への参照をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="9bd44-294">ASP.NET Web フォームの HTML サーバーコントロールとは異なり、Blazor の要素参照を使用して DOM を直接操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="9bd44-295">Blazor は DOM 比較アルゴリズムを使用して、ほとんどの DOM 対話を処理します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="9bd44-296">Blazor でキャプチャされた要素参照は不透明です。</span><span class="sxs-lookup"><span data-stu-id="9bd44-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="9bd44-297">ただし、JavaScript の相互運用呼び出しで特定の要素参照を渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="9bd44-298">JavaScript の相互運用機能の詳細については、「 [ASP.NET Core Blazor javascript interop](/aspnet/core/blazor/javascript-interop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd44-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="9bd44-299">テンプレートコンポーネント</span><span class="sxs-lookup"><span data-stu-id="9bd44-299">Templated components</span></span>

<span data-ttu-id="9bd44-300">ASP.NET Web フォームでは、テンプレート化された*コントロール*を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="9bd44-301">開発者は、テンプレート化されたコントロールを使用して、コンテナーコントロールの表示に使用する HTML の一部を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="9bd44-302">テンプレート化されたサーバーコントロールを構築するメカニズムは複雑ですが、ユーザーがカスタマイズ可能な方法でデータを表示するための強力なシナリオを実現します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="9bd44-303">テンプレート化されたコントロールの例としては、`Repeater` や `DataList`などがあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="9bd44-304">Blazor コンポーネントは、`RenderFragment` または `RenderFragment<T>`型のコンポーネントパラメーターを定義することで、テンプレートを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="9bd44-305">`RenderFragment` は、コンポーネントによってレンダリングできる Razor マークアップのチャンクを表します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="9bd44-306">`RenderFragment<T>` は、レンダリングフラグメントのレンダリング時に指定できるパラメーターを受け取る Razor マークアップのチャンクです。</span><span class="sxs-lookup"><span data-stu-id="9bd44-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="9bd44-307">子コンテンツ</span><span class="sxs-lookup"><span data-stu-id="9bd44-307">Child content</span></span>

<span data-ttu-id="9bd44-308">Blazor コンポーネントは、子コンテンツを `RenderFragment` としてキャプチャし、コンポーネントレンダリングの一部としてそのコンテンツをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="9bd44-309">子コンテンツをキャプチャするには、`RenderFragment` 型のコンポーネントパラメーターを定義し、`ChildContent`という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="9bd44-310">*ChildContentComponent。 razor*</span><span class="sxs-lookup"><span data-stu-id="9bd44-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="9bd44-311">親コンポーネントは、通常の Razor 構文を使用して子コンテンツを提供できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="9bd44-312">テンプレート パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bd44-312">Template parameters</span></span>

<span data-ttu-id="9bd44-313">テンプレート化 Blazor コンポーネントでは、`RenderFragment` または `RenderFragment<T>`型の複数のコンポーネントパラメーターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="9bd44-314">`RenderFragment<T>` のパラメーターは、呼び出されたときに指定できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="9bd44-315">コンポーネントのジェネリック型パラメーターを指定するには、`@typeparam` Razor ディレクティブを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="9bd44-316">*SimpleListView。 razor*</span><span class="sxs-lookup"><span data-stu-id="9bd44-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="9bd44-317">テンプレート化されたコンポーネントを使用する場合、テンプレートパラメーターは、パラメーターの名前と一致する子要素を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="9bd44-318">要素として渡さ `RenderFragment<T>` 型のコンポーネント引数には、`context`という名前の暗黙的なパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="9bd44-319">この実装パラメーターの名前を変更するには、子要素の `Context` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="9bd44-320">ジェネリック型パラメーターは、型パラメーターの名前と一致する属性を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="9bd44-321">可能な場合は、型パラメーターが推論されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-321">The type parameter will be inferred if possible:</span></span>

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

<span data-ttu-id="9bd44-322">このコンポーネントの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="9bd44-323">分離コード</span><span class="sxs-lookup"><span data-stu-id="9bd44-323">Code-behind</span></span>

<span data-ttu-id="9bd44-324">Blazor コンポーネントは、通常、単一の*razor*ファイルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="9bd44-325">ただし、分離コードファイルを使用して、コードとマークアップを分離することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bd44-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="9bd44-326">コンポーネントファイルを使用するには、 C#コンポーネントファイルのファイル名と一致するファイルを追加*します。* ただし、.cs 拡張子が追加されます (*Counter.razor.cs*)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="9bd44-327">コンポーネントのC#基本クラスを定義するには、ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="9bd44-328">基底クラスには任意の名前を指定できますが、クラスにはコンポーネントクラスと同じ名前を付けますが、`Base` の拡張機能が追加されます (`CounterBase`)。</span><span class="sxs-lookup"><span data-stu-id="9bd44-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="9bd44-329">コンポーネントベースのクラスも `ComponentBase`から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="9bd44-330">次に、Razor コンポーネントファイルで、`@inherits` ディレクティブを追加して、コンポーネント (`@inherits CounterBase`) の基本クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd44-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="9bd44-331">*カウンタ。 razor*</span><span class="sxs-lookup"><span data-stu-id="9bd44-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="9bd44-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="9bd44-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="9bd44-333">基底クラスのコンポーネントのメンバーの可視性は、コンポーネントクラスに表示される `protected` または `public` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd44-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bd44-334">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="9bd44-334">Additional resources</span></span>

<span data-ttu-id="9bd44-335">前のは、Blazor コンポーネントのすべての側面を網羅するものではありません。</span><span class="sxs-lookup"><span data-stu-id="9bd44-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="9bd44-336">[ASP.NET Core Razor コンポーネントを作成して使用](/aspnet/core/blazor/components)する方法の詳細については、Blazor のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd44-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9bd44-337">[前へ](app-startup.md)
>[次へ](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="9bd44-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
