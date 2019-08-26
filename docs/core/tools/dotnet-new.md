---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 05/06/2019
ms.openlocfilehash: c9e960bab0e28e88b0cc8d431dad3b9f3f00c9c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660539"
---
# <a name="dotnet-new"></a><span data-ttu-id="47688-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="47688-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="47688-104">name</span><span class="sxs-lookup"><span data-stu-id="47688-104">Name</span></span>

<span data-ttu-id="47688-105">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="47688-106">構文</span><span class="sxs-lookup"><span data-stu-id="47688-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="47688-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="47688-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="47688-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="47688-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="47688-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="47688-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="47688-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="47688-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="47688-111">説明</span><span class="sxs-lookup"><span data-stu-id="47688-111">Description</span></span>

<span data-ttu-id="47688-112">`dotnet new` コマンドは、有効な .NET Core プロジェクトを初期化する便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="47688-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="47688-113">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="47688-114">引数</span><span class="sxs-lookup"><span data-stu-id="47688-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="47688-115">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="47688-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="47688-116">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="47688-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="47688-117">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47688-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="47688-118">`TEMPLATE` の値が「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="47688-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="47688-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="47688-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="47688-120">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47688-120">The command contains a default list of templates.</span></span> <span data-ttu-id="47688-121">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="47688-122">次の表は、.NET Core SDK 2.2.100 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="47688-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="47688-123">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="47688-124">テンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-124">Templates</span></span>                                    | <span data-ttu-id="47688-125">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="47688-125">Short Name</span></span>        | <span data-ttu-id="47688-126">言語</span><span class="sxs-lookup"><span data-stu-id="47688-126">Language</span></span>     | <span data-ttu-id="47688-127">Tags</span><span class="sxs-lookup"><span data-stu-id="47688-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="47688-128">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47688-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="47688-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-129">[C#], F#, VB</span></span> | <span data-ttu-id="47688-130">Common/Console</span><span class="sxs-lookup"><span data-stu-id="47688-130">Common/Console</span></span>                        |
| <span data-ttu-id="47688-131">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="47688-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-132">[C#], F#, VB</span></span> | <span data-ttu-id="47688-133">Common/Library</span><span class="sxs-lookup"><span data-stu-id="47688-133">Common/Library</span></span>                        |
| <span data-ttu-id="47688-134">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="47688-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-135">[C#], F#, VB</span></span> | <span data-ttu-id="47688-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="47688-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="47688-137">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="47688-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-138">[C#], F#, VB</span></span> | <span data-ttu-id="47688-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="47688-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="47688-140">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="47688-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="47688-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-141">[C#], F#, VB</span></span> | <span data-ttu-id="47688-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="47688-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="47688-143">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="47688-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-144">[C#], F#, VB</span></span> | <span data-ttu-id="47688-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="47688-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="47688-146">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="47688-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="47688-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-147">[C#]</span></span>         | <span data-ttu-id="47688-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="47688-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="47688-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-150">[C#]</span></span>         | <span data-ttu-id="47688-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="47688-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="47688-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-153">[C#]</span></span>         | <span data-ttu-id="47688-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-155">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="47688-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="47688-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-156">[C#], F#</span></span>     | <span data-ttu-id="47688-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="47688-157">Web/Empty</span></span>                             |
| <span data-ttu-id="47688-158">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="47688-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="47688-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-159">[C#], F#</span></span>     | <span data-ttu-id="47688-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="47688-160">Web/MVC</span></span>                               |
| <span data-ttu-id="47688-161">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="47688-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="47688-162">`webapp`、 `razor`</span><span class="sxs-lookup"><span data-stu-id="47688-162">`webapp`, `razor`</span></span> | <span data-ttu-id="47688-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-163">[C#]</span></span>         | <span data-ttu-id="47688-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="47688-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="47688-165">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="47688-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-166">[C#]</span></span>         | <span data-ttu-id="47688-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="47688-168">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="47688-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-169">[C#]</span></span>         | <span data-ttu-id="47688-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="47688-171">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="47688-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-172">[C#]</span></span>         | <span data-ttu-id="47688-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="47688-174">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="47688-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-175">[C#]</span></span>         | <span data-ttu-id="47688-176">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="47688-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="47688-177">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="47688-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="47688-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-178">[C#], F#</span></span>     | <span data-ttu-id="47688-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="47688-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="47688-180">global.json file</span><span class="sxs-lookup"><span data-stu-id="47688-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="47688-181">構成</span><span class="sxs-lookup"><span data-stu-id="47688-181">Config</span></span>                                |
| <span data-ttu-id="47688-182">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="47688-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="47688-183">構成</span><span class="sxs-lookup"><span data-stu-id="47688-183">Config</span></span>                                |
| <span data-ttu-id="47688-184">Web 構成</span><span class="sxs-lookup"><span data-stu-id="47688-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="47688-185">構成</span><span class="sxs-lookup"><span data-stu-id="47688-185">Config</span></span>                                |
| <span data-ttu-id="47688-186">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="47688-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="47688-187">ソリューション</span><span class="sxs-lookup"><span data-stu-id="47688-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="47688-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="47688-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="47688-189">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47688-189">The command contains a default list of templates.</span></span> <span data-ttu-id="47688-190">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="47688-191">次の表は、.NET Core SDK 2.1.300 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="47688-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="47688-192">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="47688-193">テンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-193">Templates</span></span>                                    | <span data-ttu-id="47688-194">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="47688-194">Short Name</span></span>      | <span data-ttu-id="47688-195">言語</span><span class="sxs-lookup"><span data-stu-id="47688-195">Language</span></span>     | <span data-ttu-id="47688-196">Tags</span><span class="sxs-lookup"><span data-stu-id="47688-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="47688-197">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47688-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="47688-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-198">[C#], F#, VB</span></span> | <span data-ttu-id="47688-199">Common/Console</span><span class="sxs-lookup"><span data-stu-id="47688-199">Common/Console</span></span>                        |
| <span data-ttu-id="47688-200">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="47688-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-201">[C#], F#, VB</span></span> | <span data-ttu-id="47688-202">Common/Library</span><span class="sxs-lookup"><span data-stu-id="47688-202">Common/Library</span></span>                        |
| <span data-ttu-id="47688-203">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="47688-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-204">[C#], F#, VB</span></span> | <span data-ttu-id="47688-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="47688-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="47688-206">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="47688-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-207">[C#], F#, VB</span></span> | <span data-ttu-id="47688-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="47688-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="47688-209">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="47688-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="47688-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-210">[C#]</span></span>         | <span data-ttu-id="47688-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="47688-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="47688-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-213">[C#]</span></span>         | <span data-ttu-id="47688-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="47688-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="47688-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-216">[C#]</span></span>         | <span data-ttu-id="47688-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="47688-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="47688-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="47688-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-219">[C#], F#</span></span>     | <span data-ttu-id="47688-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="47688-220">Web/Empty</span></span>                             |
| <span data-ttu-id="47688-221">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="47688-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="47688-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-222">[C#], F#</span></span>     | <span data-ttu-id="47688-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="47688-223">Web/MVC</span></span>                               |
| <span data-ttu-id="47688-224">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="47688-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="47688-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-225">[C#]</span></span>         | <span data-ttu-id="47688-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="47688-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="47688-227">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="47688-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-228">[C#]</span></span>         | <span data-ttu-id="47688-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="47688-230">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="47688-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-231">[C#]</span></span>         | <span data-ttu-id="47688-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="47688-233">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="47688-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-234">[C#]</span></span>         | <span data-ttu-id="47688-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="47688-236">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="47688-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-237">[C#]</span></span>         | <span data-ttu-id="47688-238">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="47688-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="47688-239">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="47688-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="47688-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-240">[C#], F#</span></span>     | <span data-ttu-id="47688-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="47688-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="47688-242">global.json file</span><span class="sxs-lookup"><span data-stu-id="47688-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="47688-243">構成</span><span class="sxs-lookup"><span data-stu-id="47688-243">Config</span></span>                                |
| <span data-ttu-id="47688-244">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="47688-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="47688-245">構成</span><span class="sxs-lookup"><span data-stu-id="47688-245">Config</span></span>                                |
| <span data-ttu-id="47688-246">Web 構成</span><span class="sxs-lookup"><span data-stu-id="47688-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="47688-247">構成</span><span class="sxs-lookup"><span data-stu-id="47688-247">Config</span></span>                                |
| <span data-ttu-id="47688-248">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="47688-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="47688-249">ソリューション</span><span class="sxs-lookup"><span data-stu-id="47688-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="47688-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="47688-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="47688-251">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47688-251">The command contains a default list of templates.</span></span> <span data-ttu-id="47688-252">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="47688-253">次の表は、.NET Core SDK 2.0.0 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="47688-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="47688-254">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="47688-255">テンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-255">Templates</span></span>                                    | <span data-ttu-id="47688-256">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="47688-256">Short Name</span></span>    | <span data-ttu-id="47688-257">言語</span><span class="sxs-lookup"><span data-stu-id="47688-257">Language</span></span>     | <span data-ttu-id="47688-258">Tags</span><span class="sxs-lookup"><span data-stu-id="47688-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="47688-259">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47688-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="47688-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-260">[C#], F#, VB</span></span> | <span data-ttu-id="47688-261">Common/Console</span><span class="sxs-lookup"><span data-stu-id="47688-261">Common/Console</span></span>      |
| <span data-ttu-id="47688-262">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="47688-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-263">[C#], F#, VB</span></span> | <span data-ttu-id="47688-264">Common/Library</span><span class="sxs-lookup"><span data-stu-id="47688-264">Common/Library</span></span>      |
| <span data-ttu-id="47688-265">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="47688-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-266">[C#], F#, VB</span></span> | <span data-ttu-id="47688-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="47688-267">Test/MSTest</span></span>         |
| <span data-ttu-id="47688-268">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="47688-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="47688-269">[C#], F#, VB</span></span> | <span data-ttu-id="47688-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="47688-270">Test/xUnit</span></span>          |
| <span data-ttu-id="47688-271">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="47688-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="47688-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-272">[C#], F#</span></span>     | <span data-ttu-id="47688-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="47688-273">Web/Empty</span></span>           |
| <span data-ttu-id="47688-274">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="47688-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="47688-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-275">[C#], F#</span></span>     | <span data-ttu-id="47688-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="47688-276">Web/MVC</span></span>             |
| <span data-ttu-id="47688-277">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="47688-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="47688-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-278">[C#]</span></span>         | <span data-ttu-id="47688-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="47688-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="47688-280">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="47688-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-281">[C#]</span></span>         | <span data-ttu-id="47688-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="47688-283">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="47688-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-284">[C#]</span></span>         | <span data-ttu-id="47688-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="47688-286">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="47688-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="47688-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-287">[C#]</span></span>         | <span data-ttu-id="47688-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="47688-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="47688-289">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="47688-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="47688-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-290">[C#], F#</span></span>     | <span data-ttu-id="47688-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="47688-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="47688-292">global.json file</span><span class="sxs-lookup"><span data-stu-id="47688-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="47688-293">構成</span><span class="sxs-lookup"><span data-stu-id="47688-293">Config</span></span>              |
| <span data-ttu-id="47688-294">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="47688-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="47688-295">構成</span><span class="sxs-lookup"><span data-stu-id="47688-295">Config</span></span>              |
| <span data-ttu-id="47688-296">Web 構成</span><span class="sxs-lookup"><span data-stu-id="47688-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="47688-297">構成</span><span class="sxs-lookup"><span data-stu-id="47688-297">Config</span></span>              |
| <span data-ttu-id="47688-298">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="47688-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="47688-299">ソリューション</span><span class="sxs-lookup"><span data-stu-id="47688-299">Solution</span></span>            |
| <span data-ttu-id="47688-300">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="47688-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="47688-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="47688-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="47688-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="47688-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="47688-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="47688-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="47688-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="47688-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="47688-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="47688-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="47688-307">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="47688-307">The command contains a default list of templates.</span></span> <span data-ttu-id="47688-308">使用可能なテンプレートの一覧を取得するには、`dotnet new -all` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="47688-309">次の表は、.NET Core SDK 1.0.1 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="47688-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="47688-310">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="47688-311">テンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-311">Templates</span></span>            | <span data-ttu-id="47688-312">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="47688-312">Short Name</span></span>    | <span data-ttu-id="47688-313">言語</span><span class="sxs-lookup"><span data-stu-id="47688-313">Language</span></span> | <span data-ttu-id="47688-314">Tags</span><span class="sxs-lookup"><span data-stu-id="47688-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="47688-315">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47688-315">Console Application</span></span>  | `console`     | <span data-ttu-id="47688-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-316">[C#], F#</span></span> | <span data-ttu-id="47688-317">Common/Console</span><span class="sxs-lookup"><span data-stu-id="47688-317">Common/Console</span></span> |
| <span data-ttu-id="47688-318">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="47688-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="47688-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-319">[C#], F#</span></span> | <span data-ttu-id="47688-320">Common/Library</span><span class="sxs-lookup"><span data-stu-id="47688-320">Common/Library</span></span> |
| <span data-ttu-id="47688-321">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="47688-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-322">[C#], F#</span></span> | <span data-ttu-id="47688-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="47688-323">Test/MSTest</span></span>    |
| <span data-ttu-id="47688-324">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="47688-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="47688-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-325">[C#], F#</span></span> | <span data-ttu-id="47688-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="47688-326">Test/xUnit</span></span>     |
| <span data-ttu-id="47688-327">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="47688-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="47688-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-328">[C#]</span></span>     | <span data-ttu-id="47688-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="47688-329">Web/Empty</span></span>      |
| <span data-ttu-id="47688-330">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="47688-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="47688-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="47688-331">[C#], F#</span></span> | <span data-ttu-id="47688-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="47688-332">Web/MVC</span></span>        |
| <span data-ttu-id="47688-333">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="47688-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="47688-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="47688-334">[C#]</span></span>     | <span data-ttu-id="47688-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="47688-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="47688-336">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="47688-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="47688-337">構成</span><span class="sxs-lookup"><span data-stu-id="47688-337">Config</span></span>         |
| <span data-ttu-id="47688-338">Web 構成</span><span class="sxs-lookup"><span data-stu-id="47688-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="47688-339">構成</span><span class="sxs-lookup"><span data-stu-id="47688-339">Config</span></span>         |
| <span data-ttu-id="47688-340">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="47688-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="47688-341">ソリューション</span><span class="sxs-lookup"><span data-stu-id="47688-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="47688-342">オプション</span><span class="sxs-lookup"><span data-stu-id="47688-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="47688-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="47688-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="47688-344">指定されたコマンドが実行されてテンプレートが作成された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="47688-345">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="47688-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="47688-346">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="47688-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="47688-347">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="47688-347">Prints out help for the command.</span></span> <span data-ttu-id="47688-348">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="47688-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="47688-349">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="47688-350">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="47688-351">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="47688-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="47688-352">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47688-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="47688-353">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47688-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="47688-354">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="47688-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="47688-355">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="47688-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="47688-356">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="47688-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="47688-357">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="47688-357">The language of the template to create.</span></span> <span data-ttu-id="47688-358">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="47688-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="47688-359">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="47688-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-360">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="47688-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="47688-361">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="47688-362">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="47688-362">The name for the created output.</span></span> <span data-ttu-id="47688-363">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="47688-364">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="47688-365">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="47688-365">Location to place the generated output.</span></span> <span data-ttu-id="47688-366">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="47688-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="47688-367">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="47688-367">Filters templates based on available types.</span></span> <span data-ttu-id="47688-368">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="47688-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="47688-369">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="47688-370">`<PATH|NUGET_ID>` 値を除外すると、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-371">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="47688-372">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47688-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="47688-373">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="47688-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="47688-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="47688-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="47688-375">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="47688-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="47688-376">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="47688-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="47688-377">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="47688-377">Prints out help for the command.</span></span> <span data-ttu-id="47688-378">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="47688-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="47688-379">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="47688-380">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="47688-381">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="47688-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="47688-382">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47688-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="47688-383">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47688-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="47688-384">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="47688-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="47688-385">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="47688-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="47688-386">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="47688-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="47688-387">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="47688-387">The language of the template to create.</span></span> <span data-ttu-id="47688-388">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="47688-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="47688-389">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="47688-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-390">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="47688-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="47688-391">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="47688-392">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="47688-392">The name for the created output.</span></span> <span data-ttu-id="47688-393">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="47688-394">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="47688-395">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="47688-395">Location to place the generated output.</span></span> <span data-ttu-id="47688-396">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="47688-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="47688-397">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="47688-397">Filters templates based on available types.</span></span> <span data-ttu-id="47688-398">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="47688-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="47688-399">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-400">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="47688-401">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47688-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="47688-402">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="47688-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="47688-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="47688-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="47688-404">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="47688-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="47688-405">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="47688-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="47688-406">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="47688-406">Prints out help for the command.</span></span> <span data-ttu-id="47688-407">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="47688-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="47688-408">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="47688-409">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="47688-410">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="47688-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="47688-411">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47688-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="47688-412">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47688-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="47688-413">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="47688-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="47688-414">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="47688-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="47688-415">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="47688-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="47688-416">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="47688-416">The language of the template to create.</span></span> <span data-ttu-id="47688-417">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="47688-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="47688-418">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="47688-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-419">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="47688-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="47688-420">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="47688-421">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="47688-421">The name for the created output.</span></span> <span data-ttu-id="47688-422">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="47688-423">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="47688-423">Location to place the generated output.</span></span> <span data-ttu-id="47688-424">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="47688-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="47688-425">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="47688-425">Filters templates based on available types.</span></span> <span data-ttu-id="47688-426">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="47688-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="47688-427">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="47688-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-428">ソース `PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="47688-429">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47688-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="47688-430">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="47688-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="47688-431">テンプレートのアンインストールに必要な `PATH` または `NUGET_ID` 引数を決定できない場合、引数なしで `dotnet new --uninstall` を実行するとインストールされているすべてのテンプレートと、それをアンインストールするために必要な引数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="47688-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="47688-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="47688-433">`dotnet new` コマンドのコンテキストでのみ実行すると、特定の種類のプロジェクトに対するすべてのテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47688-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="47688-434">`dotnet new web -all` など、特定のテンプレートのコンテキストで実行すると、`-all` は強制作成フラグとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="47688-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="47688-435">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="47688-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="47688-436">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="47688-436">Prints out help for the command.</span></span> <span data-ttu-id="47688-437">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="47688-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="47688-438">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="47688-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="47688-439">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="47688-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="47688-440">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="47688-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="47688-441">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="47688-441">The language of the template to create.</span></span> <span data-ttu-id="47688-442">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="47688-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="47688-443">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="47688-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="47688-444">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="47688-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="47688-445">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="47688-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="47688-446">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="47688-446">The name for the created output.</span></span> <span data-ttu-id="47688-447">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="47688-448">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="47688-448">Location to place the generated output.</span></span> <span data-ttu-id="47688-449">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="47688-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="47688-450">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="47688-450">Template options</span></span>

<span data-ttu-id="47688-451">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="47688-451">Each project template may have additional options available.</span></span> <span data-ttu-id="47688-452">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="47688-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="47688-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="47688-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="47688-454">**console**</span><span class="sxs-lookup"><span data-stu-id="47688-454">**console**</span></span>

<span data-ttu-id="47688-455">`--langVersion <VERSION_NUMBER>` - 作成されたプロジェクト ファイルの `LangVersion` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="47688-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="47688-456">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="47688-457">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="47688-457">Not supported for F#.</span></span>

<span data-ttu-id="47688-458">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-459">**angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="47688-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="47688-460">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-461">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-462">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-463">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="47688-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="47688-464">**razorclasslib**</span></span>

<span data-ttu-id="47688-465">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="47688-466">**classlib**</span></span>

<span data-ttu-id="47688-467">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-468">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.2`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="47688-469">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="47688-470">`--langVersion <VERSION_NUMBER>` - 作成されたプロジェクト ファイルの `LangVersion` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="47688-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="47688-471">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="47688-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="47688-472">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="47688-472">Not supported for F#.</span></span>

<span data-ttu-id="47688-473">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="47688-474">**mstest, xunit**</span></span>

<span data-ttu-id="47688-475">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47688-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="47688-476">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="47688-477">**nunit**</span></span>

<span data-ttu-id="47688-478">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-479">既定値は `netcoreapp2.1` です。</span><span class="sxs-lookup"><span data-stu-id="47688-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="47688-480">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47688-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="47688-481">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-482">**page**</span><span class="sxs-lookup"><span data-stu-id="47688-482">**page**</span></span>

<span data-ttu-id="47688-483">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="47688-484">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="47688-485">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="47688-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="47688-486">**viewimports**</span></span>

<span data-ttu-id="47688-487">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="47688-488">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="47688-489">**web**</span><span class="sxs-lookup"><span data-stu-id="47688-489">**web**</span></span>

<span data-ttu-id="47688-490">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-491">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-492">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-493">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="47688-494">**mvc、webapp**</span><span class="sxs-lookup"><span data-stu-id="47688-494">**mvc, webapp**</span></span>

<span data-ttu-id="47688-495">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-496">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-496">The possible values are:</span></span>

- <span data-ttu-id="47688-497">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-498">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="47688-499">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-500">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-501">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="47688-502">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-503">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-504">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-505">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-506">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-507">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-508">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="47688-509">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-510">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="47688-511">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-512">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-513">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-514">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-515">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-516">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-517">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-518">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-519">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-520">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-521">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-522">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-523">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-524">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="47688-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="47688-525">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-526">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="47688-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="47688-527">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-528">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-529">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-530">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-531">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="47688-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="47688-532">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="47688-533">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-534">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-535">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="47688-536">**webapi**</span></span>

<span data-ttu-id="47688-537">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-538">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-538">The possible values are:</span></span>

- <span data-ttu-id="47688-539">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-540">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-541">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-542">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-543">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-544">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-545">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-546">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-547">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-548">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-549">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-550">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-551">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-552">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-553">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-554">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-555">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-556">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-557">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-558">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-559">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-560">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-561">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-562">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-563">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-564">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="47688-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="47688-565">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="47688-566">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-567">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-568">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="47688-569">**globaljson**</span></span>

<span data-ttu-id="47688-570">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="47688-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="47688-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="47688-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="47688-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="47688-573">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="47688-574">**classlib**</span></span>

<span data-ttu-id="47688-575">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-576">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.1`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="47688-577">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="47688-578">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="47688-579">**mstest, xunit**</span></span>

<span data-ttu-id="47688-580">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47688-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="47688-581">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="47688-582">**globaljson**</span></span>

<span data-ttu-id="47688-583">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="47688-584">**web**</span><span class="sxs-lookup"><span data-stu-id="47688-584">**web**</span></span>

<span data-ttu-id="47688-585">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-586">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-587">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-588">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="47688-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="47688-589">**webapi**</span></span>

<span data-ttu-id="47688-590">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-591">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-591">The possible values are:</span></span>

- <span data-ttu-id="47688-592">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-593">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-594">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-595">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-596">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-597">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-598">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-599">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-600">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-601">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-602">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-603">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-604">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-605">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-606">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-607">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-608">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-609">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-610">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-611">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-612">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-613">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-614">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-615">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-616">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-617">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-618">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-619">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-620">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="47688-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="47688-621">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="47688-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="47688-622">**mvc, razor**</span></span>

<span data-ttu-id="47688-623">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-624">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-624">The possible values are:</span></span>

- <span data-ttu-id="47688-625">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-626">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="47688-627">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-628">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-629">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="47688-630">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-631">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-632">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-633">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-634">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-635">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-636">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="47688-637">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-638">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="47688-639">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-640">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-641">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-642">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-643">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-644">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-645">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-646">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-647">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-648">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-649">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-650">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-651">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-652">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="47688-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="47688-653">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-654">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="47688-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="47688-655">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-656">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-657">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="47688-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="47688-658">`--use-browserlink` - プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="47688-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="47688-659">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-660">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-661">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-662">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="47688-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="47688-663">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="47688-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="47688-664">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="47688-665">**page**</span><span class="sxs-lookup"><span data-stu-id="47688-665">**page**</span></span>

<span data-ttu-id="47688-666">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="47688-667">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="47688-668">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="47688-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="47688-669">**viewimports**</span></span>

<span data-ttu-id="47688-670">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="47688-671">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="47688-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="47688-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="47688-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="47688-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="47688-674">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="47688-675">**classlib**</span></span>

<span data-ttu-id="47688-676">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-677">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.0`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="47688-678">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="47688-679">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="47688-680">**mstest, xunit**</span></span>

<span data-ttu-id="47688-681">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47688-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="47688-682">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="47688-683">**globaljson**</span></span>

<span data-ttu-id="47688-684">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="47688-685">**web**</span><span class="sxs-lookup"><span data-stu-id="47688-685">**web**</span></span>

<span data-ttu-id="47688-686">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="47688-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="47688-687">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="47688-688">**webapi**</span></span>

<span data-ttu-id="47688-689">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-690">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-690">The possible values are:</span></span>

- <span data-ttu-id="47688-691">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-692">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-693">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-694">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-695">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-696">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-697">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-698">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-699">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-700">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-701">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-702">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-703">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-704">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-705">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-706">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-707">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-708">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-709">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-710">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-711">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-712">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-713">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-714">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="47688-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="47688-715">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-716">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-717">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="47688-718">**mvc, razor**</span></span>

<span data-ttu-id="47688-719">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-720">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47688-720">The possible values are:</span></span>

- <span data-ttu-id="47688-721">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="47688-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="47688-722">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="47688-723">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="47688-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="47688-724">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="47688-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="47688-725">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="47688-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="47688-726">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="47688-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="47688-727">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="47688-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="47688-728">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-729">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="47688-730">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="47688-731">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-732">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="47688-733">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-734">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="47688-735">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-736">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="47688-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="47688-737">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-738">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="47688-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="47688-739">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="47688-740">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="47688-741">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="47688-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="47688-742">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="47688-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="47688-743">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-744">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="47688-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="47688-745">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="47688-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="47688-746">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="47688-747">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="47688-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="47688-748">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="47688-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="47688-749">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="47688-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="47688-750">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="47688-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="47688-751">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="47688-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="47688-752">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="47688-753">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="47688-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="47688-754">`--use-browserlink` - プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="47688-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="47688-755">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="47688-756">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="47688-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="47688-757">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="47688-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="47688-758">**page**</span><span class="sxs-lookup"><span data-stu-id="47688-758">**page**</span></span>

<span data-ttu-id="47688-759">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="47688-760">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="47688-761">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="47688-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="47688-762">**viewimports**</span></span>

<span data-ttu-id="47688-763">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="47688-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="47688-764">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="47688-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="47688-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="47688-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="47688-766">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="47688-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="47688-767">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-768">値: `netcoreapp1.0` または `netcoreapp1.1` です。</span><span class="sxs-lookup"><span data-stu-id="47688-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="47688-769">既定値は `netcoreapp1.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="47688-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="47688-770">**classlib**</span></span>

<span data-ttu-id="47688-771">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-772">値: `netcoreapp1.0`、`netcoreapp1.1`、または `netstandard1.0` から `netstandard1.6` です。</span><span class="sxs-lookup"><span data-stu-id="47688-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="47688-773">既定値は `netstandard1.4` です。</span><span class="sxs-lookup"><span data-stu-id="47688-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="47688-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="47688-774">**mvc**</span></span>

<span data-ttu-id="47688-775">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="47688-776">値: `netcoreapp1.0` または `netcoreapp1.1` です。</span><span class="sxs-lookup"><span data-stu-id="47688-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="47688-777">既定値は `netcoreapp1.0` です。</span><span class="sxs-lookup"><span data-stu-id="47688-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="47688-778">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="47688-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="47688-779">値: `None` または `Individual` です。</span><span class="sxs-lookup"><span data-stu-id="47688-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="47688-780">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="47688-780">The default value is `None`.</span></span>

<span data-ttu-id="47688-781">`-uld|--use-local-db` - SQLite の代わりに LocalDB を使うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="47688-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="47688-782">値: `true` または `false` です。</span><span class="sxs-lookup"><span data-stu-id="47688-782">Values: `true` or `false`.</span></span> <span data-ttu-id="47688-783">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="47688-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="47688-784">使用例</span><span class="sxs-lookup"><span data-stu-id="47688-784">Examples</span></span>

<span data-ttu-id="47688-785">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="47688-786">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="47688-787">指定したディレクトリ内に .NET 標準クラス ライブラリ プロジェクトを作成します (.NET Core SDK 2.0 またはそれ以降のバージョンでのみ使用可能)。</span><span class="sxs-lookup"><span data-stu-id="47688-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="47688-788">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="47688-789">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="47688-790">MVC に利用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="47688-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="47688-791">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="47688-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="47688-792">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="47688-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="47688-793">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="47688-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="47688-794">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="47688-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="47688-795">ASP.NET Core のシングル ページ アプリケーション テンプレートのバージョン 2.0 をインストールします (コマンド オプションは .NET Core SDK 1.1 以降のバージョンでのみ使用できます):</span><span class="sxs-lookup"><span data-stu-id="47688-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="47688-796">SDK バージョン 2.0.0 (.NET Core SDK 2.0 以降のバージョンでのみ使用できます) を設定している現在のディレクトリ内に *global.json* を作成します。</span><span class="sxs-lookup"><span data-stu-id="47688-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="47688-797">関連項目</span><span class="sxs-lookup"><span data-stu-id="47688-797">See also</span></span>

- [<span data-ttu-id="47688-798">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="47688-799">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="47688-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="47688-800">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="47688-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="47688-801">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="47688-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
