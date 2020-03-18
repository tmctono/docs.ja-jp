---
title: Blazor アプリのプロジェクト構造
description: Web フォームと Blazor プロジェクトのプロジェクト構造ASP.NET比較する方法について説明します。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401743"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="c6c93-103">Blazor アプリのプロジェクト構造</span><span class="sxs-lookup"><span data-stu-id="c6c93-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c6c93-104">プロジェクト構造の違いは大きいにもかかわらず、ASP.NET Web フォームと Blazor は多くの類似概念を共有しています。</span><span class="sxs-lookup"><span data-stu-id="c6c93-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="c6c93-105">ここでは、Blazor プロジェクトの構造を見て、それを ASP.NET Web フォーム プロジェクトと比較します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="c6c93-106">最初の Blazor アプリを作成するには[、Blazor の開始手順](/aspnet/core/blazor/get-started)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c6c93-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="c6c93-107">指示に従って、Blazor Server アプリまたは ASP.NET Core でホストされている Blazor WebAssembly アプリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="c6c93-108">ホスト モデル固有のロジックを除き、両方のプロジェクトのコードの大部分は同じです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="c6c93-109">プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="c6c93-109">Project file</span></span>

<span data-ttu-id="c6c93-110">Blazor サーバー アプリは .NET Core プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="c6c93-111">Blazor Server アプリのプロジェクト ファイルは、次のように簡単です。</span><span class="sxs-lookup"><span data-stu-id="c6c93-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="c6c93-112">Blazor WebAssembly アプリのプロジェクト ファイルは、少し複雑に見えます (正確なバージョン番号は異なる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="c6c93-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="c6c93-113">Blazor WebAssembly プロジェクトは、WebAssembly ベースの .NET ランタイムでブラウザーで実行されるため、.NET Core ではなく .NET 標準を対象とします。</span><span class="sxs-lookup"><span data-stu-id="c6c93-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="c6c93-114">サーバーや開発者のコンピューターのように、.NET を Web ブラウザーにインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="c6c93-115">したがって、プロジェクトは個々のパッケージ参照を使用して Blazor フレームワークを参照します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="c6c93-116">これに対し、Web フォーム プロジェクトASP.NET既定のファイルには *、.csproj*ファイルに約 300 行の XML が含まれており、そのほとんどはプロジェクトのさまざまなコードファイルとコンテンツ ファイルを明示的にリストしています。</span><span class="sxs-lookup"><span data-stu-id="c6c93-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="c6c93-117">NET Core ベースおよび .NET Standard ベースのプロジェクトの簡略化の多くは、SDK を参照してインポートされる既定の`Microsoft.NET.Sdk.Web`ターゲットとプロパティから取得されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="c6c93-118">Web SDK には、ワイルドカードなどの便利な機能が用意されており、プロジェクトにコードファイルやコンテンツファイルを簡単に含めることができ、その機能が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="c6c93-119">ファイルを明示的に一覧表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="c6c93-120">NET Core を対象とする場合、Web SDK は 、.NET Core と ASP.NET コアの両方の共有フレームワークにフレームワーク参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="c6c93-121">フレームワークは、[**ソリューション エクスプローラー** ] ウィンドウの **[依存関係** > **フレームワーク**] ノードから表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="c6c93-122">共有フレームワークは、.NET Core をインストールするときにコンピューターにインストールされたアセンブリのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="c6c93-123">これらのアセンブリはサポートされていますが、個々のアセンブリ参照は .NET Core プロジェクトではあまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="c6c93-124">ほとんどのプロジェクトの依存関係は、NuGet パッケージ参照として処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="c6c93-125">最上位レベルのパッケージの依存関係を参照する必要があるのは、.NET Core プロジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="c6c93-126">推移的な依存関係は自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="c6c93-127">パッケージを参照する web フォーム プロジェクトASP.NET一般的に見られる*packages.config*ファイルを使用する代わりに、パッケージ`<PackageReference>`参照は要素を使用してプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="c6c93-128">エントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="c6c93-128">Entry point</span></span>

<span data-ttu-id="c6c93-129">Blazor Server アプリのエントリ ポイントは、コンソール アプリケーションで確認されるように *、Program.cs*ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="c6c93-130">アプリが実行されると、Web アプリ固有の既定値を使用して Web ホスト インスタンスが作成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="c6c93-131">Web ホストは Blazor Server アプリケーションのライフサイクルを管理し、ホストレベルのサービスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="c6c93-132">このようなサービスの例としては、構成、ロギング、依存関係の注入、および HTTP サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="c6c93-133">このコードは、ほとんどが定型であり、多くの場合、変更されません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-133">This code is mostly boilerplate and is often left unchanged.</span></span>

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

<span data-ttu-id="c6c93-134">Blazor WebAssembly アプリでは *、Program.cs*のエントリ ポイントも定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="c6c93-135">コードの外観が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-135">The code looks slightly different.</span></span> <span data-ttu-id="c6c93-136">コードは、アプリに同じホスト レベルのサービスを提供するようにアプリ ホストを設定するという点で似ています。</span><span class="sxs-lookup"><span data-stu-id="c6c93-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="c6c93-137">ただし、WebAssembly アプリ ホストはブラウザで直接実行されるため、HTTP サーバーをセットアップしません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="c6c93-138">Blazor アプリには`Startup`*、Global.asax*ファイルではなく、アプリのスタートアップ ロジックを定義するクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="c6c93-139">この`Startup`クラスは、アプリとアプリ固有のサービスを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="c6c93-140">Blazor Server アプリケーションでは、`Startup`このクラスを使用して、クライアントブラウザーとサーバー間で Blazor が使用するリアルタイム接続用のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c6c93-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="c6c93-141">Blazor WebAssembly アプリでは、`Startup`クラスはアプリのルート コンポーネントと、レンダリングする場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="c6c93-142">`Startup` [「アプリのスタートアップ](./app-startup.md)」セクションのクラスを詳しく見ていきます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="c6c93-143">静的ファイル</span><span class="sxs-lookup"><span data-stu-id="c6c93-143">Static files</span></span>

<span data-ttu-id="c6c93-144">Web フォーム プロジェクトASP.NETとは異なり、Blazor プロジェクト内のすべてのファイルを静的ファイルとして要求できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="c6c93-145">*wwwroot*フォルダ内のファイルのみが Web アドレス指定可能です。</span><span class="sxs-lookup"><span data-stu-id="c6c93-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="c6c93-146">このフォルダーは、アプリの 「web ルート」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="c6c93-147">アプリの Web*ルート以外*のものは、Web アドレス指定できません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="c6c93-148">このセットアップでは、プロジェクト ファイルが Web 上で偶発的に公開されるのを防ぐセキュリティレベルが強化されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="c6c93-149">構成</span><span class="sxs-lookup"><span data-stu-id="c6c93-149">Configuration</span></span>

<span data-ttu-id="c6c93-150">通常、ASP.NET Web フォーム アプリの構成は、1 つ以上*の web.config*ファイルを使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="c6c93-151">Blazor アプリには通常 *、web.config*ファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="c6c93-152">その場合、ファイルは IIS でホストされている場合にのみ IIS 固有の設定を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="c6c93-153">代わりに、Blazor Server アプリはASP.NETコア構成の抽象化を使用します (Blazor WebAssembly アプリは現在、同じ構成抽象化をサポートしていませんが、これは将来追加される機能になる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c6c93-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="c6c93-154">たとえば、デフォルトの Blazor サーバー アプリケーションは、いくつかの設定を*appsettings.json*に格納します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

<span data-ttu-id="c6c93-155">「構成」セクションの「ASP.NETコア プロジェクト」の構成について詳しく[説明](./config.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="c6c93-156">Razor のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c6c93-156">Razor components</span></span>

<span data-ttu-id="c6c93-157">Blazor プロジェクトのほとんどのファイルは *.razor*ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="c6c93-158">Razor は HTML と C# に基づくテンプレート言語で、Web UI を動的に生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="c6c93-159">*Razor*ファイルは、アプリの UI を構成するコンポーネントを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="c6c93-160">ほとんどの場合、コンポーネントは、Blazor サーバーと Blazor WebAssembly アプリケーションの両方で同じです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="c6c93-161">Blazor のコンポーネントは、web フォームのユーザー コントロールASP.NET似ています。</span><span class="sxs-lookup"><span data-stu-id="c6c93-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="c6c93-162">各 Razor コンポーネント ファイルは、プロジェクトのビルド時に .NET クラスにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="c6c93-163">生成されたクラスは、コンポーネントの状態、レンダリング ロジック、ライフサイクル メソッド、イベント ハンドラー、およびその他のロジックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c6c93-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="c6c93-164">[「Blazor を使用して再利用可能な UI コンポーネントを構築](./components.md)する」セクションでコンポーネントの作成を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="c6c93-165">*_Imports.razor*ファイルは Razor コンポーネント ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="c6c93-166">代わりに、同じフォルダーとそのサブフォルダー内の他の *.razor*ファイルにインポートする Razor ディレクティブのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="c6c93-167">たとえば *、_Imports.razor*ファイルは、一般的に使用される`using`名前空間のステートメントを追加する従来の方法です。</span><span class="sxs-lookup"><span data-stu-id="c6c93-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a><span data-ttu-id="c6c93-168">ページ</span><span class="sxs-lookup"><span data-stu-id="c6c93-168">Pages</span></span>

<span data-ttu-id="c6c93-169">Blazor アプリのページはどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="c6c93-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="c6c93-170">Blazor では、アドレス指定可能なページ (ASP.NET Web フォーム アプリの *.aspx*ファイルなど) 用の別のファイル拡張子は定義されません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="c6c93-171">代わりに、ページは、コンポーネントにルートを割り当てることによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="c6c93-172">ルートは通常、Razor ディレクティブ`@page`を使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="c6c93-173">たとえば`Counter`*、Pages/Counter.razor*ファイルで作成されたコンポーネントは、次のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="c6c93-174">Blazor でのルーティングは、サーバーではなくクライアント側で処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="c6c93-175">ユーザーがブラウザ内を移動すると、Blazor はナビゲーションをインターセプトし、一致するルートを持つコンポーネントをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="c6c93-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="c6c93-176">コンポーネント ルートは、*現在、.aspx*ページと同様に、コンポーネントのファイルの場所によって推測されていません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="c6c93-177">この機能は、将来的に追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-177">This feature may be added in the future.</span></span> <span data-ttu-id="c6c93-178">各ルートは、コンポーネントで明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c93-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="c6c93-179">ルーティング可能なコンポーネントを*Pages*フォルダに格納することは、特別な意味を持たないため、純粋に規則です。</span><span class="sxs-lookup"><span data-stu-id="c6c93-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="c6c93-180">[「ページ、ルーティング、レイアウト](./pages-routing-layouts.md)」セクションの Blazor でのルーティングについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="c6c93-181">[レイアウト]</span><span class="sxs-lookup"><span data-stu-id="c6c93-181">Layout</span></span>

<span data-ttu-id="c6c93-182">Web フォーム アプリASP.NETでは、共通のページ レイアウトはマスター ページ (*Site.Master*) を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="c6c93-183">Blazor アプリでは、ページ レイアウトはレイアウト コンポーネント (*共有/MainLayout.razor)* を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="c6c93-184">レイアウト コンポーネントについては、「[ページ、ルーティング、レイアウト](./pages-routing-layouts.md)」セクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="c6c93-185">ブートストラップブラゾール</span><span class="sxs-lookup"><span data-stu-id="c6c93-185">Bootstrap Blazor</span></span>

<span data-ttu-id="c6c93-186">Blazor をブートストラップするには、アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6c93-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="c6c93-187">ページ上でルート コンポーネント (*App.Razor*) を表示する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="c6c93-188">対応する Blazor フレームワークスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="c6c93-189">Blazor Server アプリケーションでは、ルート コンポーネントのホスト ページは *_Host.cshtml*ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="c6c93-190">このファイルは、コンポーネントではなく、Razor ページを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="c6c93-191">Razor ページは *、.aspx*ページと非常に似た、サーバーアドレス指定可能なページを定義するのに Razor の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="c6c93-192">この`Html.RenderComponentAsync<TComponent>(RenderMode)`メソッドは、ルートレベルのコンポーネントをレンダリングする場所を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="c6c93-193">この`RenderMode`オプションは、コンポーネントのレンダリング方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="c6c93-194">次の表は、サポートされる`RenderMode`オプションの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6c93-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="c6c93-195">オプション</span><span class="sxs-lookup"><span data-stu-id="c6c93-195">Option</span></span>                        |<span data-ttu-id="c6c93-196">説明</span><span class="sxs-lookup"><span data-stu-id="c6c93-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="c6c93-197">ブラウザとの接続が確立されるとインタラクティブにレンダリング</span><span class="sxs-lookup"><span data-stu-id="c6c93-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="c6c93-198">最初に事前レンダリングしてからインタラクティブにレンダリング</span><span class="sxs-lookup"><span data-stu-id="c6c93-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="c6c93-199">静的コンテンツとしてレンダリング</span><span class="sxs-lookup"><span data-stu-id="c6c93-199">Rendered as static content</span></span>|

<span data-ttu-id="c6c93-200">*_framework/blazor.server.js*へのスクリプト参照は、サーバーとのリアルタイム接続を確立し、すべてのユーザー操作と UI の更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

<span data-ttu-id="c6c93-201">Blazor WebAssembly アプリでは、ホスト ページは*wwwroot/index.html*下の単純な静的 HTML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c6c93-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="c6c93-202">要素`<app>`は、ルート コンポーネントをレンダリングする場所を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

<span data-ttu-id="c6c93-203">レンダリングする特定のコンポーネントは、アプリケーションの`Startup.Configure`メソッドで、コンポーネントのレンダリング先を示す対応する CSS セレクターを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a><span data-ttu-id="c6c93-204">ビルド出力</span><span class="sxs-lookup"><span data-stu-id="c6c93-204">Build output</span></span>

<span data-ttu-id="c6c93-205">Blazor プロジェクトがビルドされると、すべての Razor コンポーネントとコード ファイルが 1 つのアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="c6c93-206">Web フォーム プロジェクトASP.NETとは異なり、Blazor は UI ロジックの実行時コンパイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="c6c93-207">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="c6c93-207">Run the app</span></span>

<span data-ttu-id="c6c93-208">Blazor サーバー アプリを実行するには`F5`、Visual Studio を押します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="c6c93-209">Blazor アプリは、ランタイム コンパイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="c6c93-210">コードとコンポーネントのマークアップの変更の結果を表示するには、デバッガーをアタッチしてアプリを再構築し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="c6c93-211">デバッガーをアタッチせずに実行する場合`Ctrl+F5`( )、Visual Studio はファイルの変更を監視し、変更が加えられた時点でアプリを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="c6c93-212">変更が加えられた場合は、ブラウザを手動で更新します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="c6c93-213">Blazor WebAssembly アプリを実行するには、次のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="c6c93-214">開発サーバーを使用してクライアント プロジェクトを直接実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="c6c93-215">ASP.NET Core でアプリをホストする場合は、サーバー プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="c6c93-216">Blazor WebAssembly アプリは、Visual Studio を使用したデバッグをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c6c93-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="c6c93-217">アプリを実行するには、`Ctrl+F5`の`F5`代わりに を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6c93-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="c6c93-218">代わりに、ブラウザで直接 Blazor WebAssembly アプリをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="c6c93-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="c6c93-219">詳細については[、「コア ブレイザASP.NETデバッグ](/aspnet/core/blazor/debug)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6c93-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c6c93-220">[前次](hosting-models.md)
>[Next](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="c6c93-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
