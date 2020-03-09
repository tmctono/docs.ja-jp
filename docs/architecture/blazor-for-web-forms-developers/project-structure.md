---
title: Blazor アプリのプロジェクト構造
description: ASP.NET Web フォームと Blazor プロジェクトのプロジェクト構造を比較する方法について説明します。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675003"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="d67a2-103">Blazor アプリのプロジェクト構造</span><span class="sxs-lookup"><span data-stu-id="d67a2-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d67a2-104">ASP.NET Web Forms と Blazor は、プロジェクト構造の大きな違いにもかかわらず、多くの同様の概念を共有しています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="d67a2-105">ここでは、Blazor プロジェクトの構造を確認し、ASP.NET Web フォームプロジェクトと比較します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="d67a2-106">最初の Blazor アプリを作成するには、「 [Blazor の概要](/aspnet/core/blazor/get-started)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="d67a2-107">指示に従って、ASP.NET Core でホストされている Blazor Server アプリまたは Blazor Webas アプリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="d67a2-108">ホスティングモデル固有のロジックを除き、両方のプロジェクトのコードのほとんどは同じです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="d67a2-109">プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="d67a2-109">Project file</span></span>

<span data-ttu-id="d67a2-110">Blazor サーバーアプリは .NET Core プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="d67a2-111">Blazor Server アプリのプロジェクトファイルは、次のように簡単に入手できます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d67a2-112">Blazor WebAssembly のプロジェクトファイルは少し複雑に見えます (正確なバージョン番号は異なる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="d67a2-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="d67a2-113">Blazor webassembly の .NET Standard プロジェクトは、.NET Core ではなく、ブラウザーで実行されます。これは、ブラウザーでは、web ベースの .NET ランタイム上で実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="d67a2-114">サーバーや開発者のコンピューターで使用できるように、web ブラウザーに .NET をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="d67a2-115">その結果、プロジェクトは個別のパッケージ参照を使用して Blazor フレームワークを参照します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="d67a2-116">これに対し、既定の ASP.NET Web フォームプロジェクトでは、 *.csproj*ファイルに約300行の XML が含まれています。そのほとんどは、プロジェクト内のさまざまなコードおよびコンテンツファイルを明示的に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="d67a2-117">.NET Core および .NET Standard ベースのプロジェクトの単純化の多くは、`Microsoft.NET.Sdk.Web` SDK を参照することによってインポートされる既定のターゲットとプロパティから取得されます。これは、多くの場合、単に単に Web SDK と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="d67a2-118">Web SDK には、プロジェクトにコードとコンテンツファイルを簡単に含めることができるワイルドカードやその他の便利なが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="d67a2-119">ファイルを明示的に一覧表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="d67a2-120">.NET Core を対象とする場合、Web SDK は .NET Core と ASP.NET Core の両方の共有フレームワークへのフレームワーク参照も追加します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="d67a2-121">フレームワークは、 **[ソリューションエクスプローラー]** ウィンドウの [**依存関係** > **フレームワーク**] ノードから表示できます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="d67a2-122">共有フレームワークは、.NET Core をインストールするときにコンピューターにインストールされたアセンブリのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="d67a2-123">これらはサポートされていますが、.NET Core プロジェクトでは、個々のアセンブリ参照はあまり一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="d67a2-124">ほとんどのプロジェクトの依存関係は、NuGet パッケージ参照として処理されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="d67a2-125">.NET Core プロジェクトでは、最上位レベルのパッケージの依存関係を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="d67a2-126">推移的な依存関係は自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="d67a2-127">ASP.NET Web フォームプロジェクトで一般的に見られる*パッケージの .config*ファイルを使用してパッケージを参照するのではなく、`<PackageReference>` 要素を使用してパッケージ参照をプロジェクトファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="d67a2-128">エントリポイント</span><span class="sxs-lookup"><span data-stu-id="d67a2-128">Entry point</span></span>

<span data-ttu-id="d67a2-129">Blazor Server アプリのエントリポイントは、コンソールアプリで見られるように、 *Program.cs*ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="d67a2-130">アプリを実行すると、web アプリ固有の既定値を使用して web ホストインスタンスが作成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="d67a2-131">Web ホストは、Blazor サーバーアプリのライフサイクルを管理し、ホストレベルのサービスを設定します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="d67a2-132">このようなサービスの例としては、構成、ログ記録、依存関係の注入、HTTP サーバーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="d67a2-133">このコードはほとんどが定型であり、変更されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="d67a2-134">Blazor WebAssembly では、 *Program.cs*にエントリポイントも定義されています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="d67a2-135">コードは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-135">The code looks slightly different.</span></span> <span data-ttu-id="d67a2-136">コードは、同じホストレベルのサービスをアプリに提供するようにアプリホストを設定するという点で似ています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="d67a2-137">ただし、ブラウザーで直接実行されるため、アプリケーションホストは HTTP サーバーを設定しません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="d67a2-138">Blazor アプリには、アプリのスタートアップロジックを定義するための、 *global.asax*ファイルではなく `Startup` クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="d67a2-139">`Startup` クラスは、アプリとアプリ固有のサービスを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="d67a2-140">Blazor Server アプリでは、クライアントブラウザーとサーバー間の Blazor によって使用されるリアルタイム接続のエンドポイントを設定するために `Startup` クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="d67a2-141">Blazor WebAssembly アプリでは、`Startup` クラスによって、アプリのルートコンポーネントとレンダリングされる場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="d67a2-142">`Startup` クラスの詳細については、「アプリの[スタートアップ](./app-startup.md)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="d67a2-143">静的ファイル</span><span class="sxs-lookup"><span data-stu-id="d67a2-143">Static files</span></span>

<span data-ttu-id="d67a2-144">ASP.NET Web フォームプロジェクトとは異なり、Blazor プロジェクト内のすべてのファイルを静的ファイルとして要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="d67a2-145">*Wwwroot*フォルダー内のファイルのみが web アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="d67a2-146">このフォルダーは、アプリの "web ルート" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="d67a2-147">アプリの web ルート以外のものは、web アドレスを指定でき*ません*。</span><span class="sxs-lookup"><span data-stu-id="d67a2-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="d67a2-148">このセットアップでは、web 経由でプロジェクトファイルが誤って公開されないようにするための追加のセキュリティレベルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="d67a2-149">構成</span><span class="sxs-lookup"><span data-stu-id="d67a2-149">Configuration</span></span>

<span data-ttu-id="d67a2-150">ASP.NET Web フォームアプリの構成は、通常、1つまたは複数の web.config ファイルを使用して処理さ*れます。*</span><span class="sxs-lookup"><span data-stu-id="d67a2-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="d67a2-151">Blazor アプリには、通常、 *web.config ファイルが*ありません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="d67a2-152">ファイルがある場合は、IIS でホストされている場合にのみ、ファイルが IIS 固有の設定を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="d67a2-153">代わりに、Blazor サーバーアプリでは ASP.NET Core 構成の抽象化を使用します (Blazor アプリでは現在、同じ構成の抽象化はサポートされていませんが、今後追加される機能である可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="d67a2-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="d67a2-154">たとえば、既定の Blazor Server アプリでは、いくつかの設定が*appsettings. json*に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="d67a2-155">構成の詳細については、[構成](./config.md)セクションの ASP.NET Core プロジェクトに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="d67a2-156">Razor のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d67a2-156">Razor components</span></span>

<span data-ttu-id="d67a2-157">Blazor プロジェクトのほとんどのファイルは、 *razor*ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="d67a2-158">Razor は、HTML C#に基づくテンプレート言語であり、web UI を動的に生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="d67a2-159">この*razor*ファイルは、アプリの UI を構成するコンポーネントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="d67a2-160">ほとんどの場合、これらのコンポーネントは、Blazor サーバーと Blazor WebAssembly の両方で同じです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="d67a2-161">Blazor のコンポーネントは、ASP.NET Web フォームのユーザーコントロールに似ています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="d67a2-162">各 Razor コンポーネントファイルは、プロジェクトのビルド時に .NET クラスにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="d67a2-163">生成されたクラスは、コンポーネントの状態、レンダリングロジック、ライフサイクルメソッド、イベントハンドラー、およびその他のロジックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d67a2-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="d67a2-164">「 [Blazor を使用して再利用可能な UI コンポーネントを構築](./components.md)する」セクションの「コンポーネントの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="d67a2-165">*_Imports razor*ファイルは razor コンポーネントファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="d67a2-166">代わりに、同じフォルダーおよびそのサブフォルダー内の他の*razor*ファイルにインポートする razor ディレクティブのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="d67a2-167">たとえば、_Imports の*razor*ファイルは、一般的に使用される名前空間に対して `using` ステートメントを追加する従来の方法です。</span><span class="sxs-lookup"><span data-stu-id="d67a2-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="d67a2-168">ページ</span><span class="sxs-lookup"><span data-stu-id="d67a2-168">Pages</span></span>

<span data-ttu-id="d67a2-169">Blazor アプリのページはどこにありますか。</span><span class="sxs-lookup"><span data-stu-id="d67a2-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="d67a2-170">Blazor では、ASP.NET Web フォームアプリの *.aspx*ファイルのように、アドレス指定可能なページに対して個別のファイル拡張子を定義していません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="d67a2-171">代わりに、ページはコンポーネントにルートを割り当てることによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="d67a2-172">ルートは、通常、`@page` Razor ディレクティブを使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="d67a2-173">たとえば、 *Pages/Counter. razor*ファイルで作成された `Counter` コンポーネントは、次のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="d67a2-174">Blazor でのルーティングは、サーバー上ではなく、クライアント側で処理されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="d67a2-175">ユーザーがブラウザーで移動すると、Blazor はナビゲーションをインターセプトし、一致するルートを使用してコンポーネントをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="d67a2-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="d67a2-176">コンポーネントのルートは、現在、 *.aspx*ページのようなコンポーネントのファイルの場所によって推測されていません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="d67a2-177">この機能は今後追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-177">This feature may be added in the future.</span></span> <span data-ttu-id="d67a2-178">各ルートは、コンポーネントに対して明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="d67a2-179">ルーティング可能なコンポーネントを*Pages*フォルダーに格納することは、特別な意味を持たず、純粋に規則です。</span><span class="sxs-lookup"><span data-stu-id="d67a2-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="d67a2-180">詳細については、「routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="d67a2-181">[レイアウト]</span><span class="sxs-lookup"><span data-stu-id="d67a2-181">Layout</span></span>

<span data-ttu-id="d67a2-182">ASP.NET Web フォームアプリでは、共通ページレイアウトはマスターページ ( *.master*) を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="d67a2-183">Blazor apps では、ページレイアウトはレイアウトコンポーネント (*Shared/mainlayout. razor*) を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="d67a2-184">レイアウトコンポーネントの詳細につい[ては、「ページ、ルーティング、レイアウト](./pages-routing-layouts.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="d67a2-185">ブートストラップ Blazor</span><span class="sxs-lookup"><span data-stu-id="d67a2-185">Bootstrap Blazor</span></span>

<span data-ttu-id="d67a2-186">Blazor をブートストラップするには、アプリで次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d67a2-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="d67a2-187">ページ上のルートコンポーネント (*app.xaml*) を表示する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="d67a2-188">対応する Blazor framework スクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="d67a2-189">Blazor Server アプリでは、ルートコンポーネントのホストページは *_Host*ファイルに定義されています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="d67a2-190">このファイルは、コンポーネントではなく Razor ページを定義します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="d67a2-191">Razor 構文 Razor Pages 使用して、サーバーアドレス指定可能なページを定義し*ます。* これは .aspx ページとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="d67a2-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="d67a2-192">`Html.RenderComponentAsync<TComponent>(RenderMode)` メソッドは、ルートレベルのコンポーネントを表示する場所を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="d67a2-193">`RenderMode` オプションは、コンポーネントを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="d67a2-194">次の表に、サポートされている `RenderMode` オプションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="d67a2-195">オプション</span><span class="sxs-lookup"><span data-stu-id="d67a2-195">Option</span></span>                        |<span data-ttu-id="d67a2-196">説明</span><span class="sxs-lookup"><span data-stu-id="d67a2-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="d67a2-197">ブラウザーとの接続が確立されると、対話形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="d67a2-198">最初の prerendered してから対話形式で表示する</span><span class="sxs-lookup"><span data-stu-id="d67a2-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="d67a2-199">静的コンテンツとしてレンダリング</span><span class="sxs-lookup"><span data-stu-id="d67a2-199">Rendered as static content</span></span>|

<span data-ttu-id="d67a2-200">*_Framework/blazor.server.js*へのスクリプト参照は、サーバーとのリアルタイム接続を確立し、すべてのユーザー操作と UI 更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="d67a2-201">Blazor WebAssembly では、ホストページは*wwwroot/index.html*の下の単純な静的 HTML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d67a2-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="d67a2-202">`<app>` 要素は、ルートコンポーネントを表示する場所を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="d67a2-203">レンダリングする特定のコンポーネントは、アプリの `Startup.Configure` メソッドで、コンポーネントのレンダリング先を示す対応する CSS セレクターを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="d67a2-204">ビルド出力</span><span class="sxs-lookup"><span data-stu-id="d67a2-204">Build output</span></span>

<span data-ttu-id="d67a2-205">Blazor プロジェクトをビルドすると、すべての Razor コンポーネントとコードファイルが1つのアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="d67a2-206">ASP.NET Web フォームプロジェクトとは異なり、Blazor は UI ロジックのランタイムコンパイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="d67a2-207">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="d67a2-207">Run the app</span></span>

<span data-ttu-id="d67a2-208">Blazor Server アプリを実行するには、Visual Studio で `F5` を押します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="d67a2-209">Blazor アプリはランタイムコンパイルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="d67a2-210">コードとコンポーネントのマークアップの変更結果を表示するには、デバッガーがアタッチされた状態でアプリをリビルドして再起動します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="d67a2-211">デバッガーがアタッチされていない状態でを実行した場合 (`Ctrl+F5`)、Visual Studio はファイルの変更を監視し、変更が加えられるとアプリを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="d67a2-212">変更が行われると、ブラウザーが手動で更新されます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="d67a2-213">Blazor WebAssembly を実行するには、次のいずれかの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="d67a2-214">開発サーバーを使用して、クライアントプロジェクトを直接実行します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="d67a2-215">ASP.NET Core を使用してアプリをホストするときに、サーバープロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="d67a2-216">Blazor WebAssembly は、Visual Studio を使用したデバッグをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d67a2-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="d67a2-217">アプリを実行するには、`F5`ではなく `Ctrl+F5` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d67a2-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="d67a2-218">代わりに、Blazor WebAssembly を直接ブラウザーでデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="d67a2-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="d67a2-219">詳細については、「 [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d67a2-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d67a2-220">[前へ](hosting-models.md)
>[次へ](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="d67a2-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
