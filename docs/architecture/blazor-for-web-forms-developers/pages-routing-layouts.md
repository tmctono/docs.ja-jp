---
title: ページ、ルーティング、レイアウト
description: でページを作成する方法 Blazor 、クライアント側のルーティングを使用する方法、およびページレイアウトを管理する方法について説明します。
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/19/2019
ms.openlocfilehash: fc1f6f9420c7149b6e67123f2f68bef75667aa0c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173108"
---
# <a name="pages-routing-and-layouts"></a><span data-ttu-id="dd80c-103">ページ、ルーティング、レイアウト</span><span class="sxs-lookup"><span data-stu-id="dd80c-103">Pages, routing, and layouts</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="dd80c-104">ASP.NET Web フォームアプリは、 *.aspx*ファイルで定義されたページで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-104">ASP.NET Web Forms apps are composed of pages defined in *.aspx* files.</span></span> <span data-ttu-id="dd80c-105">各ページのアドレスは、プロジェクトの物理ファイルパスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd80c-105">Each page's address is based on its physical file path in the project.</span></span> <span data-ttu-id="dd80c-106">ブラウザーがページに要求を行うと、ページの内容がサーバーに動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-106">When a browser makes a request to the page, the contents of the page are dynamically rendered on the server.</span></span> <span data-ttu-id="dd80c-107">ページの HTML マークアップとそのサーバーコントロールの両方に対する表示アカウント。</span><span class="sxs-lookup"><span data-stu-id="dd80c-107">The rendering accounts for both the page's HTML markup and its server controls.</span></span>

<span data-ttu-id="dd80c-108">で Blazor は、アプリの各ページは、通常、1つまたは複数の指定されたルートを使用して、razor ファイルで定義されているコンポーネントです *。*</span><span class="sxs-lookup"><span data-stu-id="dd80c-108">In Blazor, each page in the app is a component, typically defined in a *.razor* file, with one or more specified routes.</span></span> <span data-ttu-id="dd80c-109">ルーティングは、ほとんどの場合、特定のサーバー要求を介さずにクライアント側で行われます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-109">Routing mostly happens client-side without involving a specific server request.</span></span> <span data-ttu-id="dd80c-110">ブラウザーはまず、アプリのルートアドレスに要求を行います。</span><span class="sxs-lookup"><span data-stu-id="dd80c-110">The browser first makes a request to the root address of the app.</span></span> <span data-ttu-id="dd80c-111">`Router`その後、アプリ内のルートコンポーネントが、 Blazor 受信ナビゲーション要求を処理し、正しいコンポーネントに処理を行います。</span><span class="sxs-lookup"><span data-stu-id="dd80c-111">A root `Router` component in the Blazor app then handles intercepting navigation requests and them to the correct component.</span></span>

Blazor<span data-ttu-id="dd80c-112">*ディープリンク*もサポートします。</span><span class="sxs-lookup"><span data-stu-id="dd80c-112"> also supports *deep linking*.</span></span> <span data-ttu-id="dd80c-113">ディープリンクは、ブラウザーがアプリのルート以外の特定のルートに対して要求を行うときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-113">Deep linking occurs when the browser makes a request to a specific route other than the root of the app.</span></span> <span data-ttu-id="dd80c-114">サーバーに送信されるディープリンクの要求はアプリにルーティングされ Blazor 、その後、要求のクライアント側が正しいコンポーネントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-114">Requests for deep links sent to the server are routed to the Blazor app, which then routes the request client-side to the correct component.</span></span>

<span data-ttu-id="dd80c-115">ASP.NET Web フォームの単純なページには、次のマークアップが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-115">A simple page in ASP.NET Web Forms might contain the following markup:</span></span>

<span data-ttu-id="dd80c-116">*名前 .aspx*</span><span class="sxs-lookup"><span data-stu-id="dd80c-116">*Name.aspx*</span></span>

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

<span data-ttu-id="dd80c-117">*Name.aspx.cs*</span><span class="sxs-lookup"><span data-stu-id="dd80c-117">*Name.aspx.cs*</span></span>

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

<span data-ttu-id="dd80c-118">アプリの同等のページは次の Blazor ようになります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-118">The equivalent page in a Blazor app would look like this:</span></span>

<span data-ttu-id="dd80c-119">*名前。 razor*</span><span class="sxs-lookup"><span data-stu-id="dd80c-119">*Name.razor*</span></span>

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a><span data-ttu-id="dd80c-120">ページの作成</span><span class="sxs-lookup"><span data-stu-id="dd80c-120">Create pages</span></span>

<span data-ttu-id="dd80c-121">でページを作成するには Blazor 、コンポーネントを作成し、Razor ディレクティブを追加して、 `@page` コンポーネントのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-121">To create a page in Blazor, create a component and add the `@page` Razor directive to specify the route for the component.</span></span> <span data-ttu-id="dd80c-122">ディレクティブは、 `@page` そのコンポーネントに追加するルートテンプレートである1つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-122">The `@page` directive takes a single parameter, which is the route template to add to that component.</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="dd80c-123">ルートテンプレートパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd80c-123">The route template parameter is required.</span></span> <span data-ttu-id="dd80c-124">ASP.NET Web フォームとは異なり、コンポーネントへのルートがファイルの場所から推論されることは Blazor あり*ません*(ただし、将来追加される機能である可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="dd80c-124">Unlike ASP.NET Web Forms, the route to a Blazor component *isn't* inferred from its file location (although that may be a feature added in the future).</span></span>

<span data-ttu-id="dd80c-125">ルートテンプレートの構文は、ASP.NET Web フォームでのルーティングに使用される基本構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="dd80c-125">The route template syntax is the same basic syntax used for routing in ASP.NET Web Forms.</span></span> <span data-ttu-id="dd80c-126">ルートパラメーターは、テンプレート内で中かっこを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-126">Route parameters are specified in the template using braces.</span></span> Blazor<span data-ttu-id="dd80c-127">ルート値を同じ名前のコンポーネントパラメーターにバインドします (大文字と小文字は区別されません)。</span><span class="sxs-lookup"><span data-stu-id="dd80c-127"> will bind route values to component parameters with the same name (case-insensitive).</span></span>

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

<span data-ttu-id="dd80c-128">Route パラメーターの値に対して制約を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-128">You can also specify constraints on the value of the route parameter.</span></span> <span data-ttu-id="dd80c-129">たとえば、製品 ID をに制限するには、次のようにし `int` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-129">For example, to constrain the product ID to be an `int`:</span></span>

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

<span data-ttu-id="dd80c-130">でサポートされているルート制約の完全な一覧につい Blazor ては、「[ルート制約](/aspnet/core/blazor/routing#route-constraints)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd80c-130">For a full list of the route constraints supported by Blazor, see [Route constraints](/aspnet/core/blazor/routing#route-constraints).</span></span>

## <a name="router-component"></a><span data-ttu-id="dd80c-131">ルーターコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dd80c-131">Router component</span></span>

<span data-ttu-id="dd80c-132">でのルーティング Blazor は、コンポーネントによって処理され `Router` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-132">Routing in Blazor is handled by the `Router` component.</span></span> <span data-ttu-id="dd80c-133">コンポーネントは、 `Router` 通常、アプリのルートコンポーネント (*app.xaml*) で使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-133">The `Router` component is typically used in the app's root component (*App.razor*).</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

<span data-ttu-id="dd80c-134">コンポーネントは、指定されたでルーティング可能なコンポーネントを検出し、 `Router` 必要に `AppAssembly` 応じて指定 `AdditionalAssemblies` します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-134">The `Router` component discovers the routable components in the specified `AppAssembly` and in the optionally specified `AdditionalAssemblies`.</span></span> <span data-ttu-id="dd80c-135">ブラウザーが移動すると、はナビゲーションをインターセプトし、ルートがアドレスと一致する場合は抽出されたを `Router` 使用してパラメーターの内容をレンダリングし `Found` `RouteData` ます。それ以外の場合は、 `Router` パラメーターをレンダリングし `NotFound` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-135">When the browser navigates, the `Router` intercepts the navigation and renders the contents of its `Found` parameter with the extracted `RouteData` if a route matches the address, otherwise the `Router` renders its `NotFound` parameter.</span></span>

<span data-ttu-id="dd80c-136">`RouteView`コンポーネントは、によって指定された一致するコンポーネントを `RouteData` レイアウトと共に表示します (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="dd80c-136">The `RouteView` component handles rendering the matched component specified by the `RouteData` with its layout if it has one.</span></span> <span data-ttu-id="dd80c-137">一致したコンポーネントにレイアウトがない場合は、必要に応じて指定したが `DefaultLayout` 使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-137">If the matched component doesn't have a layout, then the optionally specified `DefaultLayout` is used.</span></span>

<span data-ttu-id="dd80c-138">コンポーネントは、 `LayoutView` 指定されたレイアウト内で子コンテンツをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="dd80c-138">The `LayoutView` component renders its child content within the specified layout.</span></span> <span data-ttu-id="dd80c-139">レイアウトについては、この章で後ほど詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-139">We'll look at layouts more in detail later in this chapter.</span></span>

## <a name="navigation"></a><span data-ttu-id="dd80c-140">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="dd80c-140">Navigation</span></span>

<span data-ttu-id="dd80c-141">ASP.NET Web フォームでは、ブラウザーにリダイレクト応答を返すことによって、別のページへのナビゲーションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="dd80c-141">In ASP.NET Web Forms, you trigger navigation to a different page by returning a redirect response to the browser.</span></span> <span data-ttu-id="dd80c-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-142">For example:</span></span>

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

<span data-ttu-id="dd80c-143">では、通常、リダイレクト応答を返すことはできません Blazor 。</span><span class="sxs-lookup"><span data-stu-id="dd80c-143">Returning a redirect response isn't typically possible in Blazor.</span></span> Blazor<span data-ttu-id="dd80c-144">では、要求/応答モデルは使用されません。</span><span class="sxs-lookup"><span data-stu-id="dd80c-144"> doesn't use a request-reply model.</span></span> <span data-ttu-id="dd80c-145">ただし、JavaScript の場合と同様に、ブラウザーのナビゲーションを直接トリガーできます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-145">You can, however, trigger browser navigations directly, as you can with JavaScript.</span></span>

Blazor<span data-ttu-id="dd80c-146">には、 `NavigationManager` 次のために使用できるサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd80c-146"> provides a `NavigationManager` service that can be used to:</span></span>

- <span data-ttu-id="dd80c-147">現在のブラウザーアドレスを取得します</span><span class="sxs-lookup"><span data-stu-id="dd80c-147">Get the current browser address</span></span>
- <span data-ttu-id="dd80c-148">ベースアドレスを取得する</span><span class="sxs-lookup"><span data-stu-id="dd80c-148">Get the base address</span></span>
- <span data-ttu-id="dd80c-149">ナビゲーションのトリガー</span><span class="sxs-lookup"><span data-stu-id="dd80c-149">Trigger navigations</span></span>
- <span data-ttu-id="dd80c-150">アドレスが変更されたときに通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="dd80c-150">Get notified when the address changes</span></span>

<span data-ttu-id="dd80c-151">別のアドレスに移動するには、メソッドを使用し `NavigateTo` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-151">To navigate to a different address, use the `NavigateTo` method:</span></span>

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

<span data-ttu-id="dd80c-152">すべてのメンバーの説明につい `NavigationManager` ては、「 [URI およびナビゲーション状態ヘルパー](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd80c-152">For a description of all `NavigationManager` members, see [URI and navigation state helpers](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span></span>

## <a name="base-urls"></a><span data-ttu-id="dd80c-153">ベース URL</span><span class="sxs-lookup"><span data-stu-id="dd80c-153">Base URLs</span></span>

<span data-ttu-id="dd80c-154">Blazorアプリが基本パスの下にデプロイされている場合は、[作業にルーティング] プロパティを使用して、ページメタデータにベース URL を指定する必要があり `<base>` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-154">If your Blazor app is deployed under a base path, then you need to specify the base URL in the page metadata using the `<base>` tag for routing to work property.</span></span> <span data-ttu-id="dd80c-155">アプリケーションのホストページが Razor を使用してサーバーでレンダリングされる場合は、構文を使用して `~/` アプリのベースアドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-155">If the host page for the app is server-rendered using Razor, then you can use the `~/` syntax to specify the app's base address.</span></span> <span data-ttu-id="dd80c-156">ホストページが静的な HTML の場合は、ベース URL を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-156">If the host page is static HTML, then you need to specify the base URL explicitly.</span></span>

```html
<base href="~/" />
```

## <a name="page-layout"></a><span data-ttu-id="dd80c-157">ページのレイアウト</span><span class="sxs-lookup"><span data-stu-id="dd80c-157">Page layout</span></span>

<span data-ttu-id="dd80c-158">ASP.NET Web フォームのページレイアウトは、マスターページによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-158">Page layout in ASP.NET Web Forms is handled by Master Pages.</span></span> <span data-ttu-id="dd80c-159">マスターページは、1つまたは複数のコンテンツのプレースホルダーを持つテンプレートを定義します。このプレースホルダーは、個々のページで提供できます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-159">Master Pages define a template with one or more content placeholders that can then be supplied by individual pages.</span></span> <span data-ttu-id="dd80c-160">マスターページは、 *.master*ファイルで定義され、ディレクティブで始まります `<%@ Master %>` 。</span><span class="sxs-lookup"><span data-stu-id="dd80c-160">Master Pages are defined in *.master* files and start with the `<%@ Master %>` directive.</span></span> <span data-ttu-id="dd80c-161">*.Master*ファイルの内容は *.aspx*ページと同じようにコード化されますが、 `<asp:ContentPlaceHolder>` ページがコンテンツを提供できる場所をマークするためのコントロールが追加されています。</span><span class="sxs-lookup"><span data-stu-id="dd80c-161">The content of the *.master* files is coded as you would an *.aspx* page, but with the addition of `<asp:ContentPlaceHolder>` controls to mark where pages can supply content.</span></span>

<span data-ttu-id="dd80c-162">*Site.master*</span><span class="sxs-lookup"><span data-stu-id="dd80c-162">*Site.master*</span></span>

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

<span data-ttu-id="dd80c-163">で Blazor は、レイアウトコンポーネントを使用してページレイアウトを処理します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-163">In Blazor, you handle page layout using layout components.</span></span> <span data-ttu-id="dd80c-164">レイアウトコンポーネントはを継承 `LayoutComponentBase` します。これは、 `Body` `RenderFragment` ページの内容を表示するために使用できる型の単一のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-164">Layout components inherit from `LayoutComponentBase`, which defines a single `Body` property of type `RenderFragment`, which can be used to render the contents of the page.</span></span>

<span data-ttu-id="dd80c-165">*MainLayout。 razor*</span><span class="sxs-lookup"><span data-stu-id="dd80c-165">*MainLayout.razor*</span></span>

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

<span data-ttu-id="dd80c-166">レイアウトが指定されたページが表示されると、レイアウトがプロパティをレンダリングする場所で、指定されたレイアウトの内容内にページがレンダリングされ `Body` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-166">When the page with a layout is rendered, the page is rendered within the contents of the specified layout at the location where the layout renders its `Body` property.</span></span>

<span data-ttu-id="dd80c-167">ページにレイアウトを適用するには、ディレクティブを使用し `@layout` ます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-167">To apply a layout to a page, use the `@layout` directive:</span></span>

```razor
@layout MainLayout
```

<span data-ttu-id="dd80c-168">*_Imports の razor*ファイルを使用して、フォルダーおよびサブフォルダー内のすべてのコンポーネントのレイアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-168">You can specify the layout for all components in a folder and subfolders using an *_Imports.razor* file.</span></span> <span data-ttu-id="dd80c-169">[ルーターコンポーネント](#router-component)を使用して、すべてのページの既定のレイアウトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-169">You can also specify a default layout for all your pages using the [Router component](#router-component).</span></span>

<span data-ttu-id="dd80c-170">マスターページでは複数のコンテンツプレースホルダーを定義できますが、のレイアウトには Blazor 1 つのプロパティしかありません `Body` 。</span><span class="sxs-lookup"><span data-stu-id="dd80c-170">Master Pages can define multiple content placeholders, but layouts in Blazor only have a single `Body` property.</span></span> <span data-ttu-id="dd80c-171">レイアウトコンポーネントのこの制限 Blazor は、今後のリリースで対処される予定です。</span><span class="sxs-lookup"><span data-stu-id="dd80c-171">This limitation of Blazor layout components will hopefully be addressed in a future release.</span></span>

<span data-ttu-id="dd80c-172">ASP.NET Web フォームのマスターページは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-172">Master Pages in ASP.NET Web Forms can be nested.</span></span> <span data-ttu-id="dd80c-173">つまり、マスターページでマスターページを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-173">That is, a Master Page may also use a Master Page.</span></span> <span data-ttu-id="dd80c-174">のレイアウトコンポーネント Blazor も入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-174">Layout components in Blazor may be nested too.</span></span> <span data-ttu-id="dd80c-175">レイアウトコンポーネントをレイアウトコンポーネントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-175">You can apply a layout component to a layout component.</span></span> <span data-ttu-id="dd80c-176">内部レイアウトの内容は、外側のレイアウト内にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-176">The contents of the inner layout will be rendered within the outer layout.</span></span>

<span data-ttu-id="dd80c-177">*ChildLayout。 razor*</span><span class="sxs-lookup"><span data-stu-id="dd80c-177">*ChildLayout.razor*</span></span>

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

<span data-ttu-id="dd80c-178">*インデックス。 razor*</span><span class="sxs-lookup"><span data-stu-id="dd80c-178">*Index.razor*</span></span>

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

<span data-ttu-id="dd80c-179">ページのレンダリングされた出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-179">The rendered output for the page would then be:</span></span>

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

<span data-ttu-id="dd80c-180">のレイアウトで Blazor は、通常、ページ (、、 `<html>` `<body>` など) のルート `<head>` HTML 要素は定義されません。</span><span class="sxs-lookup"><span data-stu-id="dd80c-180">Layouts in Blazor don't typically define the root HTML elements for a page (`<html>`, `<body>`, `<head>`, and so on).</span></span> <span data-ttu-id="dd80c-181">ルート HTML 要素は Blazor アプリのホストページで定義され、アプリの初期 html コンテンツを表示するために使用されます ( [「 Blazor ブートストラップ](project-structure.md#bootstrap-blazor)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="dd80c-181">The root HTML elements are instead defined in a Blazor app's host page, which is used to render the initial HTML content for the app (see [Bootstrap Blazor](project-structure.md#bootstrap-blazor)).</span></span> <span data-ttu-id="dd80c-182">ホストページでは、周囲のマークアップを含むアプリの複数のルートコンポーネントをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="dd80c-182">The host page can render multiple root components for the app with surrounding markup.</span></span>

<span data-ttu-id="dd80c-183">ページを Blazor 含め、のコンポーネントはタグをレンダリングできません `<script>` 。</span><span class="sxs-lookup"><span data-stu-id="dd80c-183">Components in Blazor, including pages, can't render `<script>` tags.</span></span> <span data-ttu-id="dd80c-184">`<script>`タグが一度読み込まれてから変更できないため、この表示制限が存在します。</span><span class="sxs-lookup"><span data-stu-id="dd80c-184">This rendering restriction exists because `<script>` tags get loaded once and then can't be changed.</span></span> <span data-ttu-id="dd80c-185">Razor 構文を使用してタグを動的に表示しようとすると、予期しない動作が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-185">Unexpected behavior may occur if you try to render the tags dynamically using Razor syntax.</span></span> <span data-ttu-id="dd80c-186">代わりに、すべての `<script>` タグをアプリのホストページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd80c-186">Instead, all `<script>` tags should be added to the app's host page.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dd80c-187">[前へ](components.md)
>[次へ](state-management.md)</span><span class="sxs-lookup"><span data-stu-id="dd80c-187">[Previous](components.md)
[Next](state-management.md)</span></span>
