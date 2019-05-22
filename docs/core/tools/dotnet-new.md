---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 05/06/2019
ms.openlocfilehash: f8bc8cb59ae6e421f4e9bd05925376399939056d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878315"
---
# <a name="dotnet-new"></a><span data-ttu-id="04cf3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="04cf3-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="04cf3-104">name</span><span class="sxs-lookup"><span data-stu-id="04cf3-104">Name</span></span>

<span data-ttu-id="04cf3-105">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="04cf3-106">構文</span><span class="sxs-lookup"><span data-stu-id="04cf3-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="04cf3-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="04cf3-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04cf3-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04cf3-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04cf3-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04cf3-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04cf3-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04cf3-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="04cf3-111">説明</span><span class="sxs-lookup"><span data-stu-id="04cf3-111">Description</span></span>

<span data-ttu-id="04cf3-112">`dotnet new` コマンドは、有効な .NET Core プロジェクトを初期化する便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="04cf3-113">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="04cf3-114">引数</span><span class="sxs-lookup"><span data-stu-id="04cf3-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="04cf3-115">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="04cf3-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="04cf3-116">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="04cf3-117">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="04cf3-118">`TEMPLATE` の値が「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="04cf3-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="04cf3-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="04cf3-120">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04cf3-120">The command contains a default list of templates.</span></span> <span data-ttu-id="04cf3-121">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="04cf3-122">次の表は、.NET Core SDK 2.2.100 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="04cf3-123">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="04cf3-124">テンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-124">Templates</span></span>                                    | <span data-ttu-id="04cf3-125">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="04cf3-125">Short Name</span></span>        | <span data-ttu-id="04cf3-126">言語</span><span class="sxs-lookup"><span data-stu-id="04cf3-126">Language</span></span>     | <span data-ttu-id="04cf3-127">Tags</span><span class="sxs-lookup"><span data-stu-id="04cf3-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="04cf3-128">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="04cf3-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="04cf3-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-129">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-130">Common/Console</span><span class="sxs-lookup"><span data-stu-id="04cf3-130">Common/Console</span></span>                        |
| <span data-ttu-id="04cf3-131">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="04cf3-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-132">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-133">Common/Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-133">Common/Library</span></span>                        |
| <span data-ttu-id="04cf3-134">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="04cf3-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-135">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="04cf3-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="04cf3-137">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="04cf3-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-138">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="04cf3-140">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="04cf3-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="04cf3-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-141">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="04cf3-143">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="04cf3-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-144">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="04cf3-146">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="04cf3-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="04cf3-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-147">[C#]</span></span>         | <span data-ttu-id="04cf3-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="04cf3-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="04cf3-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-150">[C#]</span></span>         | <span data-ttu-id="04cf3-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="04cf3-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="04cf3-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-153">[C#]</span></span>         | <span data-ttu-id="04cf3-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-155">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="04cf3-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="04cf3-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-156">[C#], F#</span></span>     | <span data-ttu-id="04cf3-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="04cf3-157">Web/Empty</span></span>                             |
| <span data-ttu-id="04cf3-158">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="04cf3-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="04cf3-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-159">[C#], F#</span></span>     | <span data-ttu-id="04cf3-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="04cf3-160">Web/MVC</span></span>                               |
| <span data-ttu-id="04cf3-161">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="04cf3-162">`webapp`、 `razor`</span><span class="sxs-lookup"><span data-stu-id="04cf3-162">`webapp`, `razor`</span></span> | <span data-ttu-id="04cf3-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-163">[C#]</span></span>         | <span data-ttu-id="04cf3-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="04cf3-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="04cf3-165">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="04cf3-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-166">[C#]</span></span>         | <span data-ttu-id="04cf3-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="04cf3-168">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="04cf3-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-169">[C#]</span></span>         | <span data-ttu-id="04cf3-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="04cf3-171">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="04cf3-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-172">[C#]</span></span>         | <span data-ttu-id="04cf3-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="04cf3-174">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="04cf3-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-175">[C#]</span></span>         | <span data-ttu-id="04cf3-176">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="04cf3-177">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="04cf3-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="04cf3-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-178">[C#], F#</span></span>     | <span data-ttu-id="04cf3-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="04cf3-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="04cf3-180">global.json file</span><span class="sxs-lookup"><span data-stu-id="04cf3-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="04cf3-181">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-181">Config</span></span>                                |
| <span data-ttu-id="04cf3-182">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="04cf3-183">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-183">Config</span></span>                                |
| <span data-ttu-id="04cf3-184">Web 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="04cf3-185">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-185">Config</span></span>                                |
| <span data-ttu-id="04cf3-186">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="04cf3-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="04cf3-187">ソリューション</span><span class="sxs-lookup"><span data-stu-id="04cf3-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04cf3-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04cf3-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="04cf3-189">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04cf3-189">The command contains a default list of templates.</span></span> <span data-ttu-id="04cf3-190">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="04cf3-191">次の表は、.NET Core SDK 2.1.300 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="04cf3-192">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="04cf3-193">テンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-193">Templates</span></span>                                    | <span data-ttu-id="04cf3-194">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="04cf3-194">Short Name</span></span>      | <span data-ttu-id="04cf3-195">言語</span><span class="sxs-lookup"><span data-stu-id="04cf3-195">Language</span></span>     | <span data-ttu-id="04cf3-196">Tags</span><span class="sxs-lookup"><span data-stu-id="04cf3-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="04cf3-197">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="04cf3-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="04cf3-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-198">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-199">Common/Console</span><span class="sxs-lookup"><span data-stu-id="04cf3-199">Common/Console</span></span>                        |
| <span data-ttu-id="04cf3-200">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="04cf3-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-201">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-202">Common/Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-202">Common/Library</span></span>                        |
| <span data-ttu-id="04cf3-203">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="04cf3-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-204">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="04cf3-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="04cf3-206">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="04cf3-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-207">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="04cf3-209">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="04cf3-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="04cf3-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-210">[C#]</span></span>         | <span data-ttu-id="04cf3-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="04cf3-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="04cf3-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-213">[C#]</span></span>         | <span data-ttu-id="04cf3-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="04cf3-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="04cf3-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-216">[C#]</span></span>         | <span data-ttu-id="04cf3-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="04cf3-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="04cf3-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="04cf3-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-219">[C#], F#</span></span>     | <span data-ttu-id="04cf3-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="04cf3-220">Web/Empty</span></span>                             |
| <span data-ttu-id="04cf3-221">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="04cf3-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="04cf3-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-222">[C#], F#</span></span>     | <span data-ttu-id="04cf3-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="04cf3-223">Web/MVC</span></span>                               |
| <span data-ttu-id="04cf3-224">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="04cf3-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-225">[C#]</span></span>         | <span data-ttu-id="04cf3-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="04cf3-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="04cf3-227">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="04cf3-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-228">[C#]</span></span>         | <span data-ttu-id="04cf3-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="04cf3-230">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="04cf3-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-231">[C#]</span></span>         | <span data-ttu-id="04cf3-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="04cf3-233">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="04cf3-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-234">[C#]</span></span>         | <span data-ttu-id="04cf3-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="04cf3-236">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="04cf3-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-237">[C#]</span></span>         | <span data-ttu-id="04cf3-238">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="04cf3-239">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="04cf3-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="04cf3-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-240">[C#], F#</span></span>     | <span data-ttu-id="04cf3-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="04cf3-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="04cf3-242">global.json file</span><span class="sxs-lookup"><span data-stu-id="04cf3-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="04cf3-243">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-243">Config</span></span>                                |
| <span data-ttu-id="04cf3-244">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="04cf3-245">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-245">Config</span></span>                                |
| <span data-ttu-id="04cf3-246">Web 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="04cf3-247">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-247">Config</span></span>                                |
| <span data-ttu-id="04cf3-248">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="04cf3-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="04cf3-249">ソリューション</span><span class="sxs-lookup"><span data-stu-id="04cf3-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04cf3-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04cf3-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="04cf3-251">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04cf3-251">The command contains a default list of templates.</span></span> <span data-ttu-id="04cf3-252">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="04cf3-253">次の表は、.NET Core SDK 2.0.0 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="04cf3-254">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="04cf3-255">テンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-255">Templates</span></span>                                    | <span data-ttu-id="04cf3-256">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="04cf3-256">Short Name</span></span>    | <span data-ttu-id="04cf3-257">言語</span><span class="sxs-lookup"><span data-stu-id="04cf3-257">Language</span></span>     | <span data-ttu-id="04cf3-258">Tags</span><span class="sxs-lookup"><span data-stu-id="04cf3-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="04cf3-259">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="04cf3-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="04cf3-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-260">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-261">Common/Console</span><span class="sxs-lookup"><span data-stu-id="04cf3-261">Common/Console</span></span>      |
| <span data-ttu-id="04cf3-262">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="04cf3-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-263">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-264">Common/Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-264">Common/Library</span></span>      |
| <span data-ttu-id="04cf3-265">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="04cf3-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-266">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="04cf3-267">Test/MSTest</span></span>         |
| <span data-ttu-id="04cf3-268">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="04cf3-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04cf3-269">[C#], F#, VB</span></span> | <span data-ttu-id="04cf3-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-270">Test/xUnit</span></span>          |
| <span data-ttu-id="04cf3-271">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="04cf3-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="04cf3-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-272">[C#], F#</span></span>     | <span data-ttu-id="04cf3-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="04cf3-273">Web/Empty</span></span>           |
| <span data-ttu-id="04cf3-274">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="04cf3-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="04cf3-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-275">[C#], F#</span></span>     | <span data-ttu-id="04cf3-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="04cf3-276">Web/MVC</span></span>             |
| <span data-ttu-id="04cf3-277">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="04cf3-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-278">[C#]</span></span>         | <span data-ttu-id="04cf3-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="04cf3-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="04cf3-280">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="04cf3-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-281">[C#]</span></span>         | <span data-ttu-id="04cf3-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="04cf3-283">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="04cf3-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-284">[C#]</span></span>         | <span data-ttu-id="04cf3-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="04cf3-286">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04cf3-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="04cf3-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-287">[C#]</span></span>         | <span data-ttu-id="04cf3-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="04cf3-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="04cf3-289">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="04cf3-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="04cf3-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-290">[C#], F#</span></span>     | <span data-ttu-id="04cf3-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="04cf3-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="04cf3-292">global.json file</span><span class="sxs-lookup"><span data-stu-id="04cf3-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="04cf3-293">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-293">Config</span></span>              |
| <span data-ttu-id="04cf3-294">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="04cf3-295">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-295">Config</span></span>              |
| <span data-ttu-id="04cf3-296">Web 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="04cf3-297">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-297">Config</span></span>              |
| <span data-ttu-id="04cf3-298">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="04cf3-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="04cf3-299">ソリューション</span><span class="sxs-lookup"><span data-stu-id="04cf3-299">Solution</span></span>            |
| <span data-ttu-id="04cf3-300">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="04cf3-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="04cf3-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="04cf3-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="04cf3-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="04cf3-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="04cf3-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="04cf3-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="04cf3-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04cf3-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04cf3-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04cf3-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="04cf3-307">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04cf3-307">The command contains a default list of templates.</span></span> <span data-ttu-id="04cf3-308">使用可能なテンプレートの一覧を取得するには、`dotnet new -all` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="04cf3-309">次の表は、.NET Core SDK 1.0.1 にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="04cf3-310">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="04cf3-311">テンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-311">Templates</span></span>            | <span data-ttu-id="04cf3-312">短い形式の名前</span><span class="sxs-lookup"><span data-stu-id="04cf3-312">Short Name</span></span>    | <span data-ttu-id="04cf3-313">言語</span><span class="sxs-lookup"><span data-stu-id="04cf3-313">Language</span></span> | <span data-ttu-id="04cf3-314">Tags</span><span class="sxs-lookup"><span data-stu-id="04cf3-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="04cf3-315">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="04cf3-315">Console Application</span></span>  | `console`     | <span data-ttu-id="04cf3-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-316">[C#], F#</span></span> | <span data-ttu-id="04cf3-317">Common/Console</span><span class="sxs-lookup"><span data-stu-id="04cf3-317">Common/Console</span></span> |
| <span data-ttu-id="04cf3-318">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="04cf3-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-319">[C#], F#</span></span> | <span data-ttu-id="04cf3-320">Common/Library</span><span class="sxs-lookup"><span data-stu-id="04cf3-320">Common/Library</span></span> |
| <span data-ttu-id="04cf3-321">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="04cf3-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-322">[C#], F#</span></span> | <span data-ttu-id="04cf3-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="04cf3-323">Test/MSTest</span></span>    |
| <span data-ttu-id="04cf3-324">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="04cf3-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="04cf3-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-325">[C#], F#</span></span> | <span data-ttu-id="04cf3-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="04cf3-326">Test/xUnit</span></span>     |
| <span data-ttu-id="04cf3-327">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="04cf3-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="04cf3-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-328">[C#]</span></span>     | <span data-ttu-id="04cf3-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="04cf3-329">Web/Empty</span></span>      |
| <span data-ttu-id="04cf3-330">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="04cf3-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04cf3-331">[C#], F#</span></span> | <span data-ttu-id="04cf3-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="04cf3-332">Web/MVC</span></span>        |
| <span data-ttu-id="04cf3-333">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="04cf3-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="04cf3-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="04cf3-334">[C#]</span></span>     | <span data-ttu-id="04cf3-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="04cf3-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="04cf3-336">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="04cf3-337">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-337">Config</span></span>         |
| <span data-ttu-id="04cf3-338">Web 構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="04cf3-339">構成</span><span class="sxs-lookup"><span data-stu-id="04cf3-339">Config</span></span>         |
| <span data-ttu-id="04cf3-340">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="04cf3-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="04cf3-341">ソリューション</span><span class="sxs-lookup"><span data-stu-id="04cf3-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="04cf3-342">オプション</span><span class="sxs-lookup"><span data-stu-id="04cf3-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="04cf3-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="04cf3-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="04cf3-344">指定されたコマンドが実行されてテンプレートが作成された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="04cf3-345">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="04cf3-346">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04cf3-347">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-347">Prints out help for the command.</span></span> <span data-ttu-id="04cf3-348">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-349">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="04cf3-350">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="04cf3-351">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="04cf3-352">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="04cf3-353">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="04cf3-354">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="04cf3-355">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04cf3-356">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="04cf3-357">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="04cf3-357">The language of the template to create.</span></span> <span data-ttu-id="04cf3-358">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04cf3-359">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-360">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="04cf3-361">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04cf3-362">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-362">The name for the created output.</span></span> <span data-ttu-id="04cf3-363">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="04cf3-364">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04cf3-365">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="04cf3-365">Location to place the generated output.</span></span> <span data-ttu-id="04cf3-366">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="04cf3-367">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-367">Filters templates based on available types.</span></span> <span data-ttu-id="04cf3-368">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-369">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="04cf3-370">`<PATH|NUGET_ID>` 値を除外すると、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-371">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="04cf3-372">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、*./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="04cf3-373">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04cf3-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04cf3-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="04cf3-375">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="04cf3-376">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04cf3-377">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-377">Prints out help for the command.</span></span> <span data-ttu-id="04cf3-378">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-379">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="04cf3-380">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="04cf3-381">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="04cf3-382">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="04cf3-383">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="04cf3-384">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="04cf3-385">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04cf3-386">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="04cf3-387">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="04cf3-387">The language of the template to create.</span></span> <span data-ttu-id="04cf3-388">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04cf3-389">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-390">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="04cf3-391">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04cf3-392">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-392">The name for the created output.</span></span> <span data-ttu-id="04cf3-393">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="04cf3-394">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04cf3-395">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="04cf3-395">Location to place the generated output.</span></span> <span data-ttu-id="04cf3-396">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="04cf3-397">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-397">Filters templates based on available types.</span></span> <span data-ttu-id="04cf3-398">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-399">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-400">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="04cf3-401">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、*./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="04cf3-402">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04cf3-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04cf3-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="04cf3-404">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="04cf3-405">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04cf3-406">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-406">Prints out help for the command.</span></span> <span data-ttu-id="04cf3-407">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-408">指定された `PATH` または `NUGET_ID` からソース パックまたはテンプレート パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="04cf3-409">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="04cf3-410">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="04cf3-411">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="04cf3-412">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="04cf3-413">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="04cf3-414">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04cf3-415">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="04cf3-416">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="04cf3-416">The language of the template to create.</span></span> <span data-ttu-id="04cf3-417">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04cf3-418">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-419">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="04cf3-420">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04cf3-421">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-421">The name for the created output.</span></span> <span data-ttu-id="04cf3-422">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04cf3-423">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="04cf3-423">Location to place the generated output.</span></span> <span data-ttu-id="04cf3-424">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="04cf3-425">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-425">Filters templates based on available types.</span></span> <span data-ttu-id="04cf3-426">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="04cf3-427">指定された `PATH` または `NUGET_ID` で、ソース パックまたはテンプレート パックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-428">ソース `PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="04cf3-429">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、*./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="04cf3-430">また、テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="04cf3-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="04cf3-431">テンプレートのアンインストールに必要な `PATH` または `NUGET_ID` 引数を決定できない場合、引数なしで `dotnet new --uninstall` を実行するとインストールされているすべてのテンプレートと、それをアンインストールするために必要な引数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04cf3-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04cf3-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="04cf3-433">`dotnet new` コマンドのコンテキストでのみ実行すると、特定の種類のプロジェクトに対するすべてのテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="04cf3-434">`dotnet new web -all` など、特定のテンプレートのコンテキストで実行すると、`-all` は強制作成フラグとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="04cf3-435">これは、出力ディレクトリに既にプロジェクトが含まれている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04cf3-436">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-436">Prints out help for the command.</span></span> <span data-ttu-id="04cf3-437">`dotnet new` コマンド自体、または `dotnet new mvc --help` などの任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="04cf3-438">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="04cf3-439">`dotnet new` コマンドに対して呼び出すと、指定されたディレクトリで使用できるテンプレートが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04cf3-440">たとえば、ディレクトリに既にプロジェクトが含まれている場合、すべてのプロジェクト テンプレートは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="04cf3-441">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="04cf3-441">The language of the template to create.</span></span> <span data-ttu-id="04cf3-442">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04cf3-443">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf3-444">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="04cf3-445">そのような場合は、`dotnet new console -lang "F#"` などの言語パラメーター値を囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04cf3-446">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-446">The name for the created output.</span></span> <span data-ttu-id="04cf3-447">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04cf3-448">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="04cf3-448">Location to place the generated output.</span></span> <span data-ttu-id="04cf3-449">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="04cf3-450">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="04cf3-450">Template options</span></span>

<span data-ttu-id="04cf3-451">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="04cf3-451">Each project template may have additional options available.</span></span> <span data-ttu-id="04cf3-452">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="04cf3-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="04cf3-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="04cf3-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="04cf3-454">**console**</span><span class="sxs-lookup"><span data-stu-id="04cf3-454">**console**</span></span>

<span data-ttu-id="04cf3-455">`--langVersion <VERSION_NUMBER>` - 作成されたプロジェクト ファイルの `LangVersion` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="04cf3-456">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="04cf3-457">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-457">Not supported for F#.</span></span>

<span data-ttu-id="04cf3-458">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-459">**angular、react、reactredux**</span><span class="sxs-lookup"><span data-stu-id="04cf3-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="04cf3-460">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-461">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-462">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-463">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="04cf3-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-464">**razorclasslib**</span></span>

<span data-ttu-id="04cf3-465">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-466">**classlib**</span></span>

<span data-ttu-id="04cf3-467">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-468">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.2`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="04cf3-469">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="04cf3-470">`--langVersion <VERSION_NUMBER>` - 作成されたプロジェクト ファイルの `LangVersion` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="04cf3-471">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="04cf3-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="04cf3-472">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-472">Not supported for F#.</span></span>

<span data-ttu-id="04cf3-473">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="04cf3-474">**mstest, xunit**</span></span>

<span data-ttu-id="04cf3-475">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="04cf3-476">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="04cf3-477">**nunit**</span></span>

<span data-ttu-id="04cf3-478">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-479">既定値は `netcoreapp2.1` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="04cf3-480">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="04cf3-481">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-482">**page**</span><span class="sxs-lookup"><span data-stu-id="04cf3-482">**page**</span></span>

<span data-ttu-id="04cf3-483">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-484">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="04cf3-485">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="04cf3-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="04cf3-486">**viewimports**</span></span>

<span data-ttu-id="04cf3-487">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-488">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="04cf3-489">**web**</span><span class="sxs-lookup"><span data-stu-id="04cf3-489">**web**</span></span>

<span data-ttu-id="04cf3-490">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-491">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-492">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-493">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="04cf3-494">**mvc、webapp**</span><span class="sxs-lookup"><span data-stu-id="04cf3-494">**mvc, webapp**</span></span>

<span data-ttu-id="04cf3-495">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-496">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-496">The possible values are:</span></span>

- <span data-ttu-id="04cf3-497">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-498">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="04cf3-499">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-500">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-501">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="04cf3-502">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-503">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-504">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-505">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-506">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-507">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-508">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="04cf3-509">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-510">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="04cf3-511">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-512">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-513">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-514">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-515">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-516">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-517">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-518">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-519">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-520">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-521">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-522">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-523">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-524">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="04cf3-525">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-526">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="04cf3-527">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-528">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-529">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-530">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-531">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="04cf3-532">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="04cf3-533">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-534">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-535">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="04cf3-536">**webapi**</span></span>

<span data-ttu-id="04cf3-537">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-538">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-538">The possible values are:</span></span>

- <span data-ttu-id="04cf3-539">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-540">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-541">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-542">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-543">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-544">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-545">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-546">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-547">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-548">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-549">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-550">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-551">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-552">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-553">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-554">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-555">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-556">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-557">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-558">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-559">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-560">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-561">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-562">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-563">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-564">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="04cf3-565">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="04cf3-566">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-567">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-568">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="04cf3-569">**globaljson**</span></span>

<span data-ttu-id="04cf3-570">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="04cf3-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="04cf3-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="04cf3-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="04cf3-573">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-574">**classlib**</span></span>

<span data-ttu-id="04cf3-575">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-576">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.1`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="04cf3-577">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="04cf3-578">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="04cf3-579">**mstest, xunit**</span></span>

<span data-ttu-id="04cf3-580">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="04cf3-581">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="04cf3-582">**globaljson**</span></span>

<span data-ttu-id="04cf3-583">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="04cf3-584">**web**</span><span class="sxs-lookup"><span data-stu-id="04cf3-584">**web**</span></span>

<span data-ttu-id="04cf3-585">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-586">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-587">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-588">このオプションは、`IndividualAuth` または `OrganizationalAuth` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="04cf3-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="04cf3-589">**webapi**</span></span>

<span data-ttu-id="04cf3-590">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-591">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-591">The possible values are:</span></span>

- <span data-ttu-id="04cf3-592">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-593">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-594">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-595">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-596">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-597">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-598">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-599">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-600">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-601">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-602">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-603">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-604">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-605">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-606">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-607">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-608">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-609">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-610">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-611">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-612">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-613">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-614">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-615">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-616">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-617">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-618">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-619">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-620">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="04cf3-621">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="04cf3-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="04cf3-622">**mvc, razor**</span></span>

<span data-ttu-id="04cf3-623">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-624">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-624">The possible values are:</span></span>

- <span data-ttu-id="04cf3-625">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-626">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="04cf3-627">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-628">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-629">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="04cf3-630">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-631">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-632">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-633">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-634">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-635">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-636">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="04cf3-637">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-638">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="04cf3-639">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-640">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-641">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-642">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-643">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-644">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-645">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-646">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-647">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-648">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-649">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-650">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-651">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-652">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="04cf3-653">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-654">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="04cf3-655">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-656">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-657">`--exclude-launch-settings` - 生成されたテンプレートから *launchSettings.json* を除外します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="04cf3-658">`--use-browserlink` - プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="04cf3-659">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-660">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-661">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-662">`--no-https` - プロジェクトは HTTPS を必要としません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="04cf3-663">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="04cf3-664">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="04cf3-665">**page**</span><span class="sxs-lookup"><span data-stu-id="04cf3-665">**page**</span></span>

<span data-ttu-id="04cf3-666">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-667">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="04cf3-668">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="04cf3-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="04cf3-669">**viewimports**</span></span>

<span data-ttu-id="04cf3-670">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-671">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="04cf3-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="04cf3-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="04cf3-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="04cf3-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="04cf3-674">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-675">**classlib**</span></span>

<span data-ttu-id="04cf3-676">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-677">値: .NET Core クラス ライブラリを作成するには `netcoreapp2.0`、.NET 標準クラス ライブラリを作成するには `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="04cf3-678">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="04cf3-679">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="04cf3-680">**mstest, xunit**</span></span>

<span data-ttu-id="04cf3-681">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="04cf3-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="04cf3-682">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="04cf3-683">**globaljson**</span></span>

<span data-ttu-id="04cf3-684">`--sdk-version <VERSION_NUMBER>` - *global.json* ファイル内で使用する .NET Core SDK のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="04cf3-685">**web**</span><span class="sxs-lookup"><span data-stu-id="04cf3-685">**web**</span></span>

<span data-ttu-id="04cf3-686">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04cf3-687">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="04cf3-688">**webapi**</span></span>

<span data-ttu-id="04cf3-689">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-690">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-690">The possible values are:</span></span>

- <span data-ttu-id="04cf3-691">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-692">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-693">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-694">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-695">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-696">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-697">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-698">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-699">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-700">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-701">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-702">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-703">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-704">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-705">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-706">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-707">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-708">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-709">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-710">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-711">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-712">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-713">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-714">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04cf3-715">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-716">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-717">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="04cf3-718">**mvc, razor**</span></span>

<span data-ttu-id="04cf3-719">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-720">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-720">The possible values are:</span></span>

- <span data-ttu-id="04cf3-721">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04cf3-722">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="04cf3-723">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04cf3-724">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04cf3-725">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="04cf3-726">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="04cf3-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04cf3-727">`--aad-b2c-instance <INSTANCE>` - 接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="04cf3-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04cf3-728">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-729">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04cf3-730">`-ssp|--susi-policy-id <ID>` - このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04cf3-731">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-732">`-rp|--reset-password-policy-id <ID>` - このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="04cf3-733">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-734">`-ep|--edit-profile-policy-id <ID>` - このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="04cf3-735">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-736">`--aad-instance <INSTANCE>` - 接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04cf3-737">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-738">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04cf3-739">`--client-id <ID>` - このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04cf3-740">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="04cf3-741">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04cf3-742">`--domain <DOMAIN>` - ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04cf3-743">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-744">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04cf3-745">`--tenant-id <ID>` - 接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04cf3-746">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04cf3-747">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04cf3-748">`--callback-path <PATH>` - リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="04cf3-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="04cf3-749">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04cf3-750">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="04cf3-751">`-r|--org-read-access` - このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04cf3-752">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04cf3-753">`--use-launch-settings` - 生成されたテンプレート出力に *launchSettings.json* を含めます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04cf3-754">`--use-browserlink` - プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="04cf3-755">`-uld|--use-local-db` - SQLite ではなく LocalDB が使用されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04cf3-756">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04cf3-757">`--no-restore` - プロジェクトの作成中には暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="04cf3-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="04cf3-758">**page**</span><span class="sxs-lookup"><span data-stu-id="04cf3-758">**page**</span></span>

<span data-ttu-id="04cf3-759">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-760">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="04cf3-761">`-np|--no-pagemodel` - PageModel なしでページを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="04cf3-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="04cf3-762">**viewimports**</span></span>

<span data-ttu-id="04cf3-763">`-na|--namespace <NAMESPACE_NAME>` - 生成するコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="04cf3-764">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04cf3-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04cf3-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="04cf3-766">**console、xunit、mstest、web、webapi**</span><span class="sxs-lookup"><span data-stu-id="04cf3-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="04cf3-767">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-768">値: `netcoreapp1.0` または `netcoreapp1.1` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="04cf3-769">既定値は `netcoreapp1.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="04cf3-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04cf3-770">**classlib**</span></span>

<span data-ttu-id="04cf3-771">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-772">値: `netcoreapp1.0`、`netcoreapp1.1`、または `netstandard1.0` から `netstandard1.6` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="04cf3-773">既定値は `netstandard1.4` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="04cf3-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="04cf3-774">**mvc**</span></span>

<span data-ttu-id="04cf3-775">`-f|--framework <FRAMEWORK>` - ターゲットにする[フレームワーク](../../standard/frameworks.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04cf3-776">値: `netcoreapp1.0` または `netcoreapp1.1` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="04cf3-777">既定値は `netcoreapp1.0` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="04cf3-778">`-au|--auth <AUTHENTICATION_TYPE>` - 使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="04cf3-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04cf3-779">値: `None` または `Individual` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="04cf3-780">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-780">The default value is `None`.</span></span>

<span data-ttu-id="04cf3-781">`-uld|--use-local-db` - SQLite の代わりに LocalDB を使うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="04cf3-782">値: `true` または `false` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-782">Values: `true` or `false`.</span></span> <span data-ttu-id="04cf3-783">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="04cf3-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="04cf3-784">使用例</span><span class="sxs-lookup"><span data-stu-id="04cf3-784">Examples</span></span>

<span data-ttu-id="04cf3-785">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="04cf3-786">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="04cf3-787">指定したディレクトリ内に .NET 標準クラス ライブラリ プロジェクトを作成します (.NET Core SDK 2.0 またはそれ以降のバージョンでのみ使用可能)。</span><span class="sxs-lookup"><span data-stu-id="04cf3-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="04cf3-788">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="04cf3-789">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="04cf3-790">MVC に利用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="04cf3-791">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="04cf3-792">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="04cf3-793">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="04cf3-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="04cf3-794">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="04cf3-795">ASP.NET Core のシングル ページ アプリケーション テンプレートのバージョン 2.0 をインストールします (コマンド オプションは .NET Core SDK 1.1 以降のバージョンでのみ使用できます):</span><span class="sxs-lookup"><span data-stu-id="04cf3-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="04cf3-796">SDK バージョン 2.0.0 (.NET Core SDK 2.0 以降のバージョンでのみ使用できます) を設定している現在のディレクトリ内に *global.json* を作成します。</span><span class="sxs-lookup"><span data-stu-id="04cf3-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="04cf3-797">関連項目</span><span class="sxs-lookup"><span data-stu-id="04cf3-797">See also</span></span>

- [<span data-ttu-id="04cf3-798">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="04cf3-799">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="04cf3-799">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="04cf3-800">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="04cf3-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="04cf3-801">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="04cf3-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
