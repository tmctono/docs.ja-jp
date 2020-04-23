---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 04/10/2020
ms.openlocfilehash: 4ad0d7e54f93582237ed9457b562957018916d36
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463611"
---
# <a name="dotnet-new"></a><span data-ttu-id="38386-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="38386-103">dotnet new</span></span>

<span data-ttu-id="38386-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="38386-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="38386-105">名前</span><span class="sxs-lookup"><span data-stu-id="38386-105">Name</span></span>

<span data-ttu-id="38386-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="38386-107">構文</span><span class="sxs-lookup"><span data-stu-id="38386-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="38386-108">説明</span><span class="sxs-lookup"><span data-stu-id="38386-108">Description</span></span>

<span data-ttu-id="38386-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="38386-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="38386-111">引数</span><span class="sxs-lookup"><span data-stu-id="38386-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="38386-112">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="38386-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="38386-113">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="38386-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="38386-114">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38386-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="38386-115">`dotnet new --list` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="38386-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="38386-116">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="38386-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="38386-117">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="38386-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="38386-118">`dotnet new` の呼び出し時に、CLI でテンプレートの一致を (部分的にも) 検出できない場合。</span><span class="sxs-lookup"><span data-stu-id="38386-118">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="38386-119">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="38386-119">If there's a newer version of the template available.</span></span> <span data-ttu-id="38386-120">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="38386-121">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38386-121">The command contains a default list of templates.</span></span> <span data-ttu-id="38386-122">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="38386-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="38386-123">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="38386-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="38386-124">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="38386-125">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="38386-126">テンプレート</span><span class="sxs-lookup"><span data-stu-id="38386-126">Templates</span></span>                                    | <span data-ttu-id="38386-127">短い名前</span><span class="sxs-lookup"><span data-stu-id="38386-127">Short name</span></span>                      | <span data-ttu-id="38386-128">言語</span><span class="sxs-lookup"><span data-stu-id="38386-128">Language</span></span>     | <span data-ttu-id="38386-129">Tags</span><span class="sxs-lookup"><span data-stu-id="38386-129">Tags</span></span>                                  | <span data-ttu-id="38386-130">導入時期</span><span class="sxs-lookup"><span data-stu-id="38386-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="38386-131">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="38386-131">Console Application</span></span>                          | [<span data-ttu-id="38386-132">console</span><span class="sxs-lookup"><span data-stu-id="38386-132">console</span></span>](#console)             | <span data-ttu-id="38386-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-133">[C#], F#, VB</span></span> | <span data-ttu-id="38386-134">Common/Console</span><span class="sxs-lookup"><span data-stu-id="38386-134">Common/Console</span></span>                        | <span data-ttu-id="38386-135">1</span><span class="sxs-lookup"><span data-stu-id="38386-135">1.0</span></span>        |
| <span data-ttu-id="38386-136">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-136">Class library</span></span>                                | [<span data-ttu-id="38386-137">classlib</span><span class="sxs-lookup"><span data-stu-id="38386-137">classlib</span></span>](#classlib)           | <span data-ttu-id="38386-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-138">[C#], F#, VB</span></span> | <span data-ttu-id="38386-139">Common/Library</span><span class="sxs-lookup"><span data-stu-id="38386-139">Common/Library</span></span>                        | <span data-ttu-id="38386-140">1</span><span class="sxs-lookup"><span data-stu-id="38386-140">1.0</span></span>        |
| <span data-ttu-id="38386-141">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="38386-141">WPF Application</span></span>                              | [<span data-ttu-id="38386-142">wpf</span><span class="sxs-lookup"><span data-stu-id="38386-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="38386-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-143">[C#]</span></span>         | <span data-ttu-id="38386-144">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="38386-144">Common/WPF</span></span>                            | <span data-ttu-id="38386-145">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-145">3.0</span></span>        |
| <span data-ttu-id="38386-146">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-146">WPF Class library</span></span>                            | [<span data-ttu-id="38386-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="38386-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="38386-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-148">[C#]</span></span>         | <span data-ttu-id="38386-149">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="38386-149">Common/WPF</span></span>                            | <span data-ttu-id="38386-150">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-150">3.0</span></span>        |
| <span data-ttu-id="38386-151">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="38386-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="38386-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="38386-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-153">[C#]</span></span>         | <span data-ttu-id="38386-154">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="38386-154">Common/WPF</span></span>                            | <span data-ttu-id="38386-155">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-155">3.0</span></span>        |
| <span data-ttu-id="38386-156">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="38386-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="38386-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="38386-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-158">[C#]</span></span>         | <span data-ttu-id="38386-159">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="38386-159">Common/WPF</span></span>                            | <span data-ttu-id="38386-160">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-160">3.0</span></span>        |
| <span data-ttu-id="38386-161">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="38386-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="38386-162">winforms</span><span class="sxs-lookup"><span data-stu-id="38386-162">winforms</span></span>](#winforms)           | <span data-ttu-id="38386-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-163">[C#]</span></span>         | <span data-ttu-id="38386-164">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="38386-164">Common/WinForms</span></span>                       | <span data-ttu-id="38386-165">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-165">3.0</span></span>        |
| <span data-ttu-id="38386-166">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="38386-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="38386-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="38386-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-168">[C#]</span></span>         | <span data-ttu-id="38386-169">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="38386-169">Common/WinForms</span></span>                       | <span data-ttu-id="38386-170">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-170">3.0</span></span>        |
| <span data-ttu-id="38386-171">Worker Service</span><span class="sxs-lookup"><span data-stu-id="38386-171">Worker Service</span></span>                               | [<span data-ttu-id="38386-172">worker</span><span class="sxs-lookup"><span data-stu-id="38386-172">worker</span></span>](#web-others)           | <span data-ttu-id="38386-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-173">[C#]</span></span>         | <span data-ttu-id="38386-174">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="38386-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="38386-175">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-175">3.0</span></span>        |
| <span data-ttu-id="38386-176">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="38386-176">Unit Test Project</span></span>                            | [<span data-ttu-id="38386-177">mstest</span><span class="sxs-lookup"><span data-stu-id="38386-177">mstest</span></span>](#test)                 | <span data-ttu-id="38386-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-178">[C#], F#, VB</span></span> | <span data-ttu-id="38386-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="38386-179">Test/MSTest</span></span>                           | <span data-ttu-id="38386-180">1</span><span class="sxs-lookup"><span data-stu-id="38386-180">1.0</span></span>        |
| <span data-ttu-id="38386-181">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="38386-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="38386-182">nunit</span><span class="sxs-lookup"><span data-stu-id="38386-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="38386-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-183">[C#], F#, VB</span></span> | <span data-ttu-id="38386-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="38386-184">Test/NUnit</span></span>                            | <span data-ttu-id="38386-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="38386-185">2.1.400</span></span>    |
| <span data-ttu-id="38386-186">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="38386-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="38386-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-187">[C#], F#, VB</span></span> | <span data-ttu-id="38386-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="38386-188">Test/NUnit</span></span>                            | <span data-ttu-id="38386-189">2.2</span><span class="sxs-lookup"><span data-stu-id="38386-189">2.2</span></span>        |
| <span data-ttu-id="38386-190">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="38386-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="38386-191">xunit</span><span class="sxs-lookup"><span data-stu-id="38386-191">xunit</span></span>](#test)                  | <span data-ttu-id="38386-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="38386-192">[C#], F#, VB</span></span> | <span data-ttu-id="38386-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="38386-193">Test/xUnit</span></span>                            | <span data-ttu-id="38386-194">1</span><span class="sxs-lookup"><span data-stu-id="38386-194">1.0</span></span>        |
| <span data-ttu-id="38386-195">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="38386-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="38386-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-196">[C#]</span></span>         | <span data-ttu-id="38386-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="38386-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="38386-198">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-198">3.0</span></span>        |
| <span data-ttu-id="38386-199">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="38386-199">Razor Page</span></span>                                   | [<span data-ttu-id="38386-200">page</span><span class="sxs-lookup"><span data-stu-id="38386-200">page</span></span>](#page)                   | <span data-ttu-id="38386-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-201">[C#]</span></span>         | <span data-ttu-id="38386-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="38386-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="38386-203">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-203">2.0</span></span>        |
| <span data-ttu-id="38386-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="38386-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="38386-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="38386-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="38386-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-206">[C#]</span></span>         | <span data-ttu-id="38386-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="38386-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="38386-208">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-208">2.0</span></span>        |
| <span data-ttu-id="38386-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="38386-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="38386-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-210">[C#]</span></span>         | <span data-ttu-id="38386-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="38386-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="38386-212">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-212">2.0</span></span>        |
| <span data-ttu-id="38386-213">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="38386-213">Blazor Server App</span></span>                            | [<span data-ttu-id="38386-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="38386-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="38386-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-215">[C#]</span></span>         | <span data-ttu-id="38386-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="38386-216">Web/Blazor</span></span>                            | <span data-ttu-id="38386-217">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-217">3.0</span></span>        |
| <span data-ttu-id="38386-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="38386-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="38386-219">web</span><span class="sxs-lookup"><span data-stu-id="38386-219">web</span></span>](#web)                     | <span data-ttu-id="38386-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="38386-220">[C#], F#</span></span>     | <span data-ttu-id="38386-221">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="38386-221">Web/Empty</span></span>                             | <span data-ttu-id="38386-222">1</span><span class="sxs-lookup"><span data-stu-id="38386-222">1.0</span></span>        |
| <span data-ttu-id="38386-223">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="38386-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="38386-224">mvc</span><span class="sxs-lookup"><span data-stu-id="38386-224">mvc</span></span>](#web-options)             | <span data-ttu-id="38386-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="38386-225">[C#], F#</span></span>     | <span data-ttu-id="38386-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="38386-226">Web/MVC</span></span>                               | <span data-ttu-id="38386-227">1</span><span class="sxs-lookup"><span data-stu-id="38386-227">1.0</span></span>        |
| <span data-ttu-id="38386-228">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="38386-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="38386-229">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="38386-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="38386-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-230">[C#]</span></span>         | <span data-ttu-id="38386-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="38386-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="38386-232">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="38386-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="38386-233">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="38386-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="38386-234">angular</span><span class="sxs-lookup"><span data-stu-id="38386-234">angular</span></span>](#spa)                 | <span data-ttu-id="38386-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-235">[C#]</span></span>         | <span data-ttu-id="38386-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="38386-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="38386-237">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-237">2.0</span></span>        |
| <span data-ttu-id="38386-238">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="38386-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="38386-239">react</span><span class="sxs-lookup"><span data-stu-id="38386-239">react</span></span>](#spa)                   | <span data-ttu-id="38386-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-240">[C#]</span></span>         | <span data-ttu-id="38386-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="38386-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="38386-242">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-242">2.0</span></span>        |
| <span data-ttu-id="38386-243">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="38386-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="38386-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="38386-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="38386-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-245">[C#]</span></span>         | <span data-ttu-id="38386-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="38386-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="38386-247">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-247">2.0</span></span>        |
| <span data-ttu-id="38386-248">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="38386-248">Razor Class Library</span></span>                          | [<span data-ttu-id="38386-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="38386-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="38386-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-250">[C#]</span></span>         | <span data-ttu-id="38386-251">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="38386-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="38386-252">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-252">2.1</span></span>        |
| <span data-ttu-id="38386-253">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="38386-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="38386-254">webapi</span><span class="sxs-lookup"><span data-stu-id="38386-254">webapi</span></span>](#webapi)               | <span data-ttu-id="38386-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="38386-255">[C#], F#</span></span>     | <span data-ttu-id="38386-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="38386-256">Web/WebAPI</span></span>                            | <span data-ttu-id="38386-257">1</span><span class="sxs-lookup"><span data-stu-id="38386-257">1.0</span></span>        |
| <span data-ttu-id="38386-258">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="38386-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="38386-259">grpc</span><span class="sxs-lookup"><span data-stu-id="38386-259">grpc</span></span>](#web-others)             | <span data-ttu-id="38386-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="38386-260">[C#]</span></span>         | <span data-ttu-id="38386-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="38386-261">Web/gRPC</span></span>                              | <span data-ttu-id="38386-262">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-262">3.0</span></span>        |
| <span data-ttu-id="38386-263">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="38386-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="38386-264">proto</span><span class="sxs-lookup"><span data-stu-id="38386-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="38386-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="38386-265">Web/gRPC</span></span>                              | <span data-ttu-id="38386-266">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-266">3.0</span></span>        |
| <span data-ttu-id="38386-267">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="38386-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="38386-268">構成</span><span class="sxs-lookup"><span data-stu-id="38386-268">Config</span></span>                                | <span data-ttu-id="38386-269">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-269">3.0</span></span>        |
| <span data-ttu-id="38386-270">global.json file</span><span class="sxs-lookup"><span data-stu-id="38386-270">global.json file</span></span>                             | [<span data-ttu-id="38386-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="38386-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="38386-272">構成</span><span class="sxs-lookup"><span data-stu-id="38386-272">Config</span></span>                                | <span data-ttu-id="38386-273">2.0</span><span class="sxs-lookup"><span data-stu-id="38386-273">2.0</span></span>        |
| <span data-ttu-id="38386-274">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="38386-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="38386-275">構成</span><span class="sxs-lookup"><span data-stu-id="38386-275">Config</span></span>                                | <span data-ttu-id="38386-276">1</span><span class="sxs-lookup"><span data-stu-id="38386-276">1.0</span></span>        |
| <span data-ttu-id="38386-277">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="38386-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="38386-278">構成</span><span class="sxs-lookup"><span data-stu-id="38386-278">Config</span></span>                                | <span data-ttu-id="38386-279">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-279">3.0</span></span>        |
| <span data-ttu-id="38386-280">Web 構成</span><span class="sxs-lookup"><span data-stu-id="38386-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="38386-281">構成</span><span class="sxs-lookup"><span data-stu-id="38386-281">Config</span></span>                                | <span data-ttu-id="38386-282">1</span><span class="sxs-lookup"><span data-stu-id="38386-282">1.0</span></span>        |
| <span data-ttu-id="38386-283">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="38386-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="38386-284">ソリューション</span><span class="sxs-lookup"><span data-stu-id="38386-284">Solution</span></span>                              | <span data-ttu-id="38386-285">1</span><span class="sxs-lookup"><span data-stu-id="38386-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="38386-286">オプション</span><span class="sxs-lookup"><span data-stu-id="38386-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="38386-287">指定されたコマンドが実行された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="38386-288">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="38386-289">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="38386-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="38386-290">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="38386-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="38386-291">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="38386-291">Prints out help for the command.</span></span> <span data-ttu-id="38386-292">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="38386-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="38386-293">たとえば、`dotnet new mvc --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="38386-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="38386-294">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38386-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="38386-295">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38386-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="38386-296">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="38386-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="38386-297">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38386-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="38386-298">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="38386-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="38386-299">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38386-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="38386-300">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="38386-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="38386-301">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="38386-302">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="38386-302">The language of the template to create.</span></span> <span data-ttu-id="38386-303">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="38386-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="38386-304">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="38386-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="38386-305">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="38386-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="38386-306">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="38386-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="38386-307">たとえば、`dotnet new console -lang "F#"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="38386-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="38386-308">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="38386-308">The name for the created output.</span></span> <span data-ttu-id="38386-309">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="38386-310">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="38386-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="38386-311">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="38386-312">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="38386-312">Location to place the generated output.</span></span> <span data-ttu-id="38386-313">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="38386-313">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="38386-314">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="38386-314">Filters templates based on available types.</span></span> <span data-ttu-id="38386-315">事前定義されている値は `project`、`item`、`other` です。</span><span class="sxs-lookup"><span data-stu-id="38386-315">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="38386-316">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38386-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="38386-317">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="38386-318">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="38386-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="38386-319">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38386-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="38386-320">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38386-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="38386-321">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="38386-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="38386-322">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="38386-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="38386-323">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38386-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="38386-324">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="38386-325">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="38386-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="38386-326">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="38386-327">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="38386-327">Template options</span></span>

<span data-ttu-id="38386-328">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="38386-328">Each project template may have additional options available.</span></span> <span data-ttu-id="38386-329">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="38386-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="38386-330">コンソール</span><span class="sxs-lookup"><span data-stu-id="38386-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-331">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-332">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="38386-333">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-334">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-334">SDK version</span></span> | <span data-ttu-id="38386-335">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-336">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-337">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="38386-338">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="38386-339">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="38386-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="38386-340">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="38386-340">Not supported for F#.</span></span> <span data-ttu-id="38386-341">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-342">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38386-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-343">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="38386-344">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="38386-345">classlib</span><span class="sxs-lookup"><span data-stu-id="38386-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-346">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-347">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="38386-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="38386-348">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="38386-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="38386-349">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="38386-350">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="38386-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="38386-351">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="38386-351">Not supported for F#.</span></span> <span data-ttu-id="38386-352">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-353">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38386-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-354">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="38386-355">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="38386-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-356">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-357">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="38386-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="38386-358">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="38386-359">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="38386-360">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="38386-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="38386-361">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38386-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-362">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="38386-363">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="38386-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="38386-364">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="38386-365">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="38386-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="38386-366">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38386-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-367">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="38386-368">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="38386-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-369">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-370">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="38386-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="38386-371">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-372">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-373">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="38386-374">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="38386-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-375">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-376">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="38386-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="38386-377">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-378">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-378">SDK version</span></span> | <span data-ttu-id="38386-379">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-380">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-381">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="38386-382">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="38386-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-383">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="38386-384">nunit</span><span class="sxs-lookup"><span data-stu-id="38386-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-385">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="38386-386">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-387">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-387">SDK version</span></span> | <span data-ttu-id="38386-388">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-389">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-390">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="38386-391">2.2</span><span class="sxs-lookup"><span data-stu-id="38386-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="38386-392">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="38386-393">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="38386-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-394">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="38386-395">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="38386-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="38386-396">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="38386-396">Namespace for the generated code.</span></span> <span data-ttu-id="38386-397">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="38386-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="38386-398">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="38386-398">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="38386-399">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="38386-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="38386-400">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="38386-400">Namespace for the generated code.</span></span> <span data-ttu-id="38386-401">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="38386-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="38386-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="38386-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="38386-403">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="38386-403">The type of authentication to use.</span></span> <span data-ttu-id="38386-404">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="38386-404">The possible values are:</span></span>

  - <span data-ttu-id="38386-405">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="38386-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="38386-406">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="38386-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="38386-407">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="38386-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="38386-408">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="38386-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="38386-409">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="38386-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="38386-410">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="38386-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="38386-411">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="38386-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="38386-412">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-413">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="38386-414">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="38386-415">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="38386-416">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="38386-417">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="38386-418">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="38386-419">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="38386-420">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="38386-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="38386-421">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="38386-422">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="38386-423">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-423">The Client ID for this project.</span></span> <span data-ttu-id="38386-424">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="38386-425">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="38386-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="38386-426">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="38386-426">The domain for the directory tenant.</span></span> <span data-ttu-id="38386-427">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-428">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="38386-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="38386-429">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="38386-430">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-431">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="38386-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="38386-432">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="38386-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="38386-433">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-434">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="38386-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="38386-435">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="38386-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="38386-436">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-437">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-438">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-438">Turns off HTTPS.</span></span> <span data-ttu-id="38386-439">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="38386-440">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="38386-441">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-442">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="38386-443">Web</span><span class="sxs-lookup"><span data-stu-id="38386-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-444">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-445">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-446">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="38386-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-447">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-448">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-448">SDK version</span></span> | <span data-ttu-id="38386-449">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-450">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-451">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="38386-452">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="38386-453">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-454">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-454">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="38386-455">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="38386-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="38386-456">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="38386-456">The type of authentication to use.</span></span> <span data-ttu-id="38386-457">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="38386-457">The possible values are:</span></span>

  - <span data-ttu-id="38386-458">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="38386-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="38386-459">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="38386-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="38386-460">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="38386-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="38386-461">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="38386-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="38386-462">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="38386-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="38386-463">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="38386-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="38386-464">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="38386-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="38386-465">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-466">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="38386-467">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="38386-468">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="38386-469">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="38386-470">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="38386-471">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="38386-472">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="38386-473">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="38386-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="38386-474">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="38386-475">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="38386-476">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-476">The Client ID for this project.</span></span> <span data-ttu-id="38386-477">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="38386-478">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="38386-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="38386-479">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="38386-479">The domain for the directory tenant.</span></span> <span data-ttu-id="38386-480">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-481">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="38386-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="38386-482">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="38386-483">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-484">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="38386-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="38386-485">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="38386-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="38386-486">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-487">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="38386-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="38386-488">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="38386-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="38386-489">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-490">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-491">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-491">Turns off HTTPS.</span></span> <span data-ttu-id="38386-492">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="38386-493">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="38386-494">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-495">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-496">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="38386-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="38386-497">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-498">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-498">SDK version</span></span> | <span data-ttu-id="38386-499">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-500">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-501">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="38386-502">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="38386-503">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="38386-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="38386-504">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="38386-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="38386-505">デバッグ ビルドで [Razor ランタイム コンパイル](/aspnet/core/mvc/views/view-compilation#runtime-compilation)を使用するようにプロジェクトが構成されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="38386-505">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="38386-506">.NET Core 3.1 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="38386-506">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="38386-507">angular、react</span><span class="sxs-lookup"><span data-stu-id="38386-507">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="38386-508">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="38386-508">The type of authentication to use.</span></span> <span data-ttu-id="38386-509">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-509">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="38386-510">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="38386-510">The possible values are:</span></span>

  - <span data-ttu-id="38386-511">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="38386-511">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="38386-512">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="38386-512">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-513">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-514">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-514">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-515">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-515">Turns off HTTPS.</span></span> <span data-ttu-id="38386-516">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-516">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="38386-517">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="38386-518">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-519">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-519">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-520">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-521">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="38386-521">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-522">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-523">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-523">SDK version</span></span> | <span data-ttu-id="38386-524">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-525">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-526">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-526">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="38386-527">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-527">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="38386-528">reactredux</span><span class="sxs-lookup"><span data-stu-id="38386-528">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-529">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-529">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-530">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-530">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-531">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="38386-531">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-532">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-532">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-533">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-533">SDK version</span></span> | <span data-ttu-id="38386-534">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-534">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-535">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-535">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-536">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-536">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="38386-537">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-537">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="38386-538">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-538">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-539">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-539">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="38386-540">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="38386-540">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="38386-541">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="38386-542">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="38386-542">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="38386-543">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="38386-543">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="38386-544">webapi</span><span class="sxs-lookup"><span data-stu-id="38386-544">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="38386-545">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="38386-545">The type of authentication to use.</span></span> <span data-ttu-id="38386-546">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="38386-546">The possible values are:</span></span>

  - <span data-ttu-id="38386-547">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="38386-547">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="38386-548">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="38386-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="38386-549">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="38386-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="38386-550">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="38386-550">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="38386-551">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="38386-551">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="38386-552">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-552">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="38386-553">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-553">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="38386-554">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-554">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="38386-555">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-555">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="38386-556">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="38386-556">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="38386-557">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-557">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-558">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="38386-558">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="38386-559">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-559">The Client ID for this project.</span></span> <span data-ttu-id="38386-560">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-560">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-561">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="38386-561">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="38386-562">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="38386-562">The domain for the directory tenant.</span></span> <span data-ttu-id="38386-563">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-564">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="38386-564">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="38386-565">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="38386-565">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="38386-566">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="38386-566">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="38386-567">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="38386-567">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="38386-568">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="38386-568">Allows this application read-access to the directory.</span></span> <span data-ttu-id="38386-569">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-569">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="38386-570">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="38386-570">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="38386-571">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="38386-571">Turns off HTTPS.</span></span> <span data-ttu-id="38386-572">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="38386-572">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="38386-573">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-573">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="38386-574">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-574">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="38386-575">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="38386-575">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="38386-576">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-576">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="38386-577">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="38386-577">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="38386-578">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="38386-578">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="38386-579">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="38386-579">SDK version</span></span> | <span data-ttu-id="38386-580">既定値</span><span class="sxs-lookup"><span data-stu-id="38386-580">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="38386-581">3.1</span><span class="sxs-lookup"><span data-stu-id="38386-581">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="38386-582">3.0</span><span class="sxs-lookup"><span data-stu-id="38386-582">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="38386-583">2.1</span><span class="sxs-lookup"><span data-stu-id="38386-583">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="38386-584">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="38386-584">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="38386-585">globaljson</span><span class="sxs-lookup"><span data-stu-id="38386-585">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="38386-586">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-586">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="38386-587">使用例</span><span class="sxs-lookup"><span data-stu-id="38386-587">Examples</span></span>

- <span data-ttu-id="38386-588">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-588">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="38386-589">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-589">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="38386-590">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="38386-590">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="38386-591">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-591">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="38386-592">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="38386-592">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="38386-593">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38386-593">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="38386-594">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="38386-594">List all templates matching the *we* substring.</span></span> <span data-ttu-id="38386-595">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="38386-595">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="38386-596">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="38386-596">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="38386-597">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="38386-597">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="38386-598">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38386-598">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="38386-599">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38386-599">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="38386-600">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="38386-600">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="38386-601">関連項目</span><span class="sxs-lookup"><span data-stu-id="38386-601">See also</span></span>

- [<span data-ttu-id="38386-602">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="38386-602">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="38386-603">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="38386-603">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="38386-604">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="38386-604">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="38386-605">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="38386-605">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
