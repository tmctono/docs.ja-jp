---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398029"
---
# <a name="dotnet-new"></a><span data-ttu-id="8791b-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8791b-103">dotnet new</span></span>

<span data-ttu-id="8791b-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8791b-105">name</span><span class="sxs-lookup"><span data-stu-id="8791b-105">Name</span></span>

<span data-ttu-id="8791b-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8791b-107">構文</span><span class="sxs-lookup"><span data-stu-id="8791b-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8791b-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="8791b-108">Description</span></span>

<span data-ttu-id="8791b-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="8791b-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="8791b-111">引数</span><span class="sxs-lookup"><span data-stu-id="8791b-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="8791b-112">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="8791b-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8791b-113">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8791b-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8791b-114">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8791b-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="8791b-115">`dotnet new --list` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="8791b-116">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="8791b-117">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="8791b-118">`dotnet new` の呼び出し時に、CLI によってテンプレートの一致が (部分的にも) 検出されない場合。</span><span class="sxs-lookup"><span data-stu-id="8791b-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="8791b-119">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="8791b-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="8791b-120">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="8791b-121">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8791b-121">The command contains a default list of templates.</span></span> <span data-ttu-id="8791b-122">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="8791b-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8791b-123">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8791b-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="8791b-124">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="8791b-125">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="8791b-126">テンプレート</span><span class="sxs-lookup"><span data-stu-id="8791b-126">Templates</span></span>                                    | <span data-ttu-id="8791b-127">短い名前</span><span class="sxs-lookup"><span data-stu-id="8791b-127">Short name</span></span>                      | <span data-ttu-id="8791b-128">言語</span><span class="sxs-lookup"><span data-stu-id="8791b-128">Language</span></span>     | <span data-ttu-id="8791b-129">Tags</span><span class="sxs-lookup"><span data-stu-id="8791b-129">Tags</span></span>                                  | <span data-ttu-id="8791b-130">導入時期</span><span class="sxs-lookup"><span data-stu-id="8791b-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="8791b-131">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8791b-131">Console Application</span></span>                          | [<span data-ttu-id="8791b-132">console</span><span class="sxs-lookup"><span data-stu-id="8791b-132">console</span></span>](#console)             | <span data-ttu-id="8791b-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-133">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-134">Common/Console</span><span class="sxs-lookup"><span data-stu-id="8791b-134">Common/Console</span></span>                        | <span data-ttu-id="8791b-135">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-135">1.0</span></span>        |
| <span data-ttu-id="8791b-136">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-136">Class library</span></span>                                | [<span data-ttu-id="8791b-137">classlib</span><span class="sxs-lookup"><span data-stu-id="8791b-137">classlib</span></span>](#classlib)           | <span data-ttu-id="8791b-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-138">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-139">Common/Library</span><span class="sxs-lookup"><span data-stu-id="8791b-139">Common/Library</span></span>                        | <span data-ttu-id="8791b-140">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-140">1.0</span></span>        |
| <span data-ttu-id="8791b-141">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8791b-141">WPF Application</span></span>                              | [<span data-ttu-id="8791b-142">wpf</span><span class="sxs-lookup"><span data-stu-id="8791b-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="8791b-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-143">[C#]</span></span>         | <span data-ttu-id="8791b-144">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8791b-144">Common/WPF</span></span>                            | <span data-ttu-id="8791b-145">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-145">3.0</span></span>        |
| <span data-ttu-id="8791b-146">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-146">WPF Class library</span></span>                            | [<span data-ttu-id="8791b-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="8791b-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="8791b-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-148">[C#]</span></span>         | <span data-ttu-id="8791b-149">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8791b-149">Common/WPF</span></span>                            | <span data-ttu-id="8791b-150">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-150">3.0</span></span>        |
| <span data-ttu-id="8791b-151">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="8791b-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="8791b-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="8791b-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-153">[C#]</span></span>         | <span data-ttu-id="8791b-154">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8791b-154">Common/WPF</span></span>                            | <span data-ttu-id="8791b-155">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-155">3.0</span></span>        |
| <span data-ttu-id="8791b-156">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="8791b-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8791b-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="8791b-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-158">[C#]</span></span>         | <span data-ttu-id="8791b-159">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8791b-159">Common/WPF</span></span>                            | <span data-ttu-id="8791b-160">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-160">3.0</span></span>        |
| <span data-ttu-id="8791b-161">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8791b-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="8791b-162">winforms</span><span class="sxs-lookup"><span data-stu-id="8791b-162">winforms</span></span>](#winforms)           | <span data-ttu-id="8791b-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-163">[C#]</span></span>         | <span data-ttu-id="8791b-164">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="8791b-164">Common/WinForms</span></span>                       | <span data-ttu-id="8791b-165">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-165">3.0</span></span>        |
| <span data-ttu-id="8791b-166">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="8791b-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="8791b-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="8791b-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-168">[C#]</span></span>         | <span data-ttu-id="8791b-169">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="8791b-169">Common/WinForms</span></span>                       | <span data-ttu-id="8791b-170">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-170">3.0</span></span>        |
| <span data-ttu-id="8791b-171">Worker Service</span><span class="sxs-lookup"><span data-stu-id="8791b-171">Worker Service</span></span>                               | [<span data-ttu-id="8791b-172">worker</span><span class="sxs-lookup"><span data-stu-id="8791b-172">worker</span></span>](#web-others)           | <span data-ttu-id="8791b-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-173">[C#]</span></span>         | <span data-ttu-id="8791b-174">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="8791b-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="8791b-175">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-175">3.0</span></span>        |
| <span data-ttu-id="8791b-176">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8791b-176">Unit Test Project</span></span>                            | [<span data-ttu-id="8791b-177">mstest</span><span class="sxs-lookup"><span data-stu-id="8791b-177">mstest</span></span>](#test)                 | <span data-ttu-id="8791b-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-178">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8791b-179">Test/MSTest</span></span>                           | <span data-ttu-id="8791b-180">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-180">1.0</span></span>        |
| <span data-ttu-id="8791b-181">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8791b-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="8791b-182">nunit</span><span class="sxs-lookup"><span data-stu-id="8791b-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="8791b-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-183">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8791b-184">Test/NUnit</span></span>                            | <span data-ttu-id="8791b-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="8791b-185">2.1.400</span></span>    |
| <span data-ttu-id="8791b-186">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="8791b-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="8791b-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-187">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8791b-188">Test/NUnit</span></span>                            | <span data-ttu-id="8791b-189">2.2</span><span class="sxs-lookup"><span data-stu-id="8791b-189">2.2</span></span>        |
| <span data-ttu-id="8791b-190">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8791b-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="8791b-191">xunit</span><span class="sxs-lookup"><span data-stu-id="8791b-191">xunit</span></span>](#test)                  | <span data-ttu-id="8791b-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8791b-192">[C#], F#, VB</span></span> | <span data-ttu-id="8791b-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8791b-193">Test/xUnit</span></span>                            | <span data-ttu-id="8791b-194">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-194">1.0</span></span>        |
| <span data-ttu-id="8791b-195">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8791b-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="8791b-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-196">[C#]</span></span>         | <span data-ttu-id="8791b-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8791b-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="8791b-198">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-198">3.0</span></span>        |
| <span data-ttu-id="8791b-199">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="8791b-199">Razor Page</span></span>                                   | [<span data-ttu-id="8791b-200">page</span><span class="sxs-lookup"><span data-stu-id="8791b-200">page</span></span>](#page)                   | <span data-ttu-id="8791b-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-201">[C#]</span></span>         | <span data-ttu-id="8791b-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8791b-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="8791b-203">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-203">2.0</span></span>        |
| <span data-ttu-id="8791b-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8791b-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="8791b-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="8791b-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="8791b-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-206">[C#]</span></span>         | <span data-ttu-id="8791b-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8791b-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="8791b-208">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-208">2.0</span></span>        |
| <span data-ttu-id="8791b-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8791b-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="8791b-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-210">[C#]</span></span>         | <span data-ttu-id="8791b-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8791b-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="8791b-212">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-212">2.0</span></span>        |
| <span data-ttu-id="8791b-213">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="8791b-213">Blazor Server App</span></span>                            | [<span data-ttu-id="8791b-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8791b-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="8791b-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-215">[C#]</span></span>         | <span data-ttu-id="8791b-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="8791b-216">Web/Blazor</span></span>                            | <span data-ttu-id="8791b-217">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-217">3.0</span></span>        |
| <span data-ttu-id="8791b-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="8791b-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="8791b-219">web</span><span class="sxs-lookup"><span data-stu-id="8791b-219">web</span></span>](#web)                     | <span data-ttu-id="8791b-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8791b-220">[C#], F#</span></span>     | <span data-ttu-id="8791b-221">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8791b-221">Web/Empty</span></span>                             | <span data-ttu-id="8791b-222">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-222">1.0</span></span>        |
| <span data-ttu-id="8791b-223">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="8791b-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="8791b-224">mvc</span><span class="sxs-lookup"><span data-stu-id="8791b-224">mvc</span></span>](#web-options)             | <span data-ttu-id="8791b-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8791b-225">[C#], F#</span></span>     | <span data-ttu-id="8791b-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8791b-226">Web/MVC</span></span>                               | <span data-ttu-id="8791b-227">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-227">1.0</span></span>        |
| <span data-ttu-id="8791b-228">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="8791b-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="8791b-229">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="8791b-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="8791b-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-230">[C#]</span></span>         | <span data-ttu-id="8791b-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8791b-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="8791b-232">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="8791b-233">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8791b-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="8791b-234">angular</span><span class="sxs-lookup"><span data-stu-id="8791b-234">angular</span></span>](#spa)                 | <span data-ttu-id="8791b-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-235">[C#]</span></span>         | <span data-ttu-id="8791b-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8791b-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8791b-237">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-237">2.0</span></span>        |
| <span data-ttu-id="8791b-238">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8791b-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="8791b-239">react</span><span class="sxs-lookup"><span data-stu-id="8791b-239">react</span></span>](#spa)                   | <span data-ttu-id="8791b-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-240">[C#]</span></span>         | <span data-ttu-id="8791b-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8791b-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8791b-242">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-242">2.0</span></span>        |
| <span data-ttu-id="8791b-243">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8791b-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="8791b-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="8791b-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="8791b-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-245">[C#]</span></span>         | <span data-ttu-id="8791b-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8791b-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8791b-247">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-247">2.0</span></span>        |
| <span data-ttu-id="8791b-248">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8791b-248">Razor Class Library</span></span>                          | [<span data-ttu-id="8791b-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8791b-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="8791b-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-250">[C#]</span></span>         | <span data-ttu-id="8791b-251">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="8791b-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="8791b-252">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-252">2.1</span></span>        |
| <span data-ttu-id="8791b-253">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="8791b-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="8791b-254">webapi</span><span class="sxs-lookup"><span data-stu-id="8791b-254">webapi</span></span>](#webapi)               | <span data-ttu-id="8791b-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8791b-255">[C#], F#</span></span>     | <span data-ttu-id="8791b-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8791b-256">Web/WebAPI</span></span>                            | <span data-ttu-id="8791b-257">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-257">1.0</span></span>        |
| <span data-ttu-id="8791b-258">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="8791b-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="8791b-259">grpc</span><span class="sxs-lookup"><span data-stu-id="8791b-259">grpc</span></span>](#web-others)             | <span data-ttu-id="8791b-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="8791b-260">[C#]</span></span>         | <span data-ttu-id="8791b-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="8791b-261">Web/gRPC</span></span>                              | <span data-ttu-id="8791b-262">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-262">3.0</span></span>        |
| <span data-ttu-id="8791b-263">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="8791b-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="8791b-264">proto</span><span class="sxs-lookup"><span data-stu-id="8791b-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="8791b-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="8791b-265">Web/gRPC</span></span>                              | <span data-ttu-id="8791b-266">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-266">3.0</span></span>        |
| <span data-ttu-id="8791b-267">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="8791b-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="8791b-268">Config</span><span class="sxs-lookup"><span data-stu-id="8791b-268">Config</span></span>                                | <span data-ttu-id="8791b-269">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-269">3.0</span></span>        |
| <span data-ttu-id="8791b-270">global.json file</span><span class="sxs-lookup"><span data-stu-id="8791b-270">global.json file</span></span>                             | [<span data-ttu-id="8791b-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="8791b-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="8791b-272">Config</span><span class="sxs-lookup"><span data-stu-id="8791b-272">Config</span></span>                                | <span data-ttu-id="8791b-273">2.0</span><span class="sxs-lookup"><span data-stu-id="8791b-273">2.0</span></span>        |
| <span data-ttu-id="8791b-274">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="8791b-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="8791b-275">Config</span><span class="sxs-lookup"><span data-stu-id="8791b-275">Config</span></span>                                | <span data-ttu-id="8791b-276">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-276">1.0</span></span>        |
| <span data-ttu-id="8791b-277">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="8791b-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="8791b-278">Config</span><span class="sxs-lookup"><span data-stu-id="8791b-278">Config</span></span>                                | <span data-ttu-id="8791b-279">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-279">3.0</span></span>        |
| <span data-ttu-id="8791b-280">Web 構成</span><span class="sxs-lookup"><span data-stu-id="8791b-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="8791b-281">Config</span><span class="sxs-lookup"><span data-stu-id="8791b-281">Config</span></span>                                | <span data-ttu-id="8791b-282">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-282">1.0</span></span>        |
| <span data-ttu-id="8791b-283">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="8791b-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="8791b-284">解決策:</span><span class="sxs-lookup"><span data-stu-id="8791b-284">Solution</span></span>                              | <span data-ttu-id="8791b-285">1.0</span><span class="sxs-lookup"><span data-stu-id="8791b-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="8791b-286">オプション</span><span class="sxs-lookup"><span data-stu-id="8791b-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="8791b-287">指定されたコマンドが実行された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="8791b-288">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="8791b-289">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8791b-290">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="8791b-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8791b-291">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="8791b-291">Prints out help for the command.</span></span> <span data-ttu-id="8791b-292">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8791b-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="8791b-293">たとえば、「 `dotnet new mvc --help` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8791b-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="8791b-294">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8791b-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8791b-295">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8791b-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8791b-296">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="8791b-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="8791b-297">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8791b-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="8791b-298">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="8791b-299">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8791b-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="8791b-300">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="8791b-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="8791b-301">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="8791b-302">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="8791b-302">The language of the template to create.</span></span> <span data-ttu-id="8791b-303">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8791b-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8791b-304">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="8791b-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8791b-305">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="8791b-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8791b-306">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8791b-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="8791b-307">たとえば、「 `dotnet new console -lang "F#"` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8791b-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="8791b-308">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="8791b-308">The name for the created output.</span></span> <span data-ttu-id="8791b-309">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="8791b-310">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="8791b-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="8791b-311">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8791b-312">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="8791b-312">Location to place the generated output.</span></span> <span data-ttu-id="8791b-313">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="8791b-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="8791b-314">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8791b-314">Filters templates based on available types.</span></span> <span data-ttu-id="8791b-315">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="8791b-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="8791b-316">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8791b-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8791b-317">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="8791b-318">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="8791b-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="8791b-319">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8791b-320">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8791b-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8791b-321">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8791b-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="8791b-322">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="8791b-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="8791b-323">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8791b-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="8791b-324">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="8791b-325">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="8791b-326">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="8791b-327">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="8791b-327">Template options</span></span>

<span data-ttu-id="8791b-328">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8791b-328">Each project template may have additional options available.</span></span> <span data-ttu-id="8791b-329">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="8791b-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="8791b-330">console</span><span class="sxs-lookup"><span data-stu-id="8791b-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-331">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-332">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8791b-333">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-334">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-334">SDK version</span></span> | <span data-ttu-id="8791b-335">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-336">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-337">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8791b-338">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8791b-339">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8791b-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8791b-340">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8791b-340">Not supported for F#.</span></span> <span data-ttu-id="8791b-341">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-342">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8791b-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-343">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="8791b-344">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="8791b-345">classlib</span><span class="sxs-lookup"><span data-stu-id="8791b-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-346">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-347">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8791b-348">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8791b-349">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8791b-350">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8791b-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8791b-351">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8791b-351">Not supported for F#.</span></span> <span data-ttu-id="8791b-352">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-353">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8791b-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-354">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="8791b-355">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8791b-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-356">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-357">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8791b-358">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8791b-359">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8791b-360">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8791b-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8791b-361">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8791b-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-362">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="8791b-363">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="8791b-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8791b-364">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8791b-365">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8791b-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8791b-366">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8791b-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-367">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="8791b-368">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="8791b-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-369">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-370">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8791b-371">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-372">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-373">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="8791b-374">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="8791b-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-375">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-376">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="8791b-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8791b-377">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-378">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-378">SDK version</span></span> | <span data-ttu-id="8791b-379">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-380">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-381">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8791b-382">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-383">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="8791b-384">nunit</span><span class="sxs-lookup"><span data-stu-id="8791b-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-385">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="8791b-386">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-387">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-387">SDK version</span></span> | <span data-ttu-id="8791b-388">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-389">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-390">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8791b-391">2.2</span><span class="sxs-lookup"><span data-stu-id="8791b-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="8791b-392">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8791b-393">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-394">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="8791b-395">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="8791b-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8791b-396">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="8791b-396">Namespace for the generated code.</span></span> <span data-ttu-id="8791b-397">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="8791b-398">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="8791b-399">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="8791b-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8791b-400">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="8791b-400">Namespace for the generated code.</span></span> <span data-ttu-id="8791b-401">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="8791b-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8791b-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8791b-403">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8791b-403">The type of authentication to use.</span></span> <span data-ttu-id="8791b-404">指定できる値は、</span><span class="sxs-lookup"><span data-stu-id="8791b-404">The possible values are:</span></span>

  - <span data-ttu-id="8791b-405">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8791b-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8791b-406">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8791b-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8791b-407">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8791b-408">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8791b-409">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="8791b-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8791b-410">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8791b-411">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8791b-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8791b-412">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-413">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8791b-414">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8791b-415">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8791b-416">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="8791b-417">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8791b-418">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8791b-419">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8791b-420">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8791b-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8791b-421">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8791b-422">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8791b-423">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-423">The Client ID for this project.</span></span> <span data-ttu-id="8791b-424">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8791b-425">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8791b-426">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8791b-426">The domain for the directory tenant.</span></span> <span data-ttu-id="8791b-427">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-428">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8791b-429">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8791b-430">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-431">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8791b-432">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="8791b-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8791b-433">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-434">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8791b-435">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8791b-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8791b-436">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-437">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-438">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-438">Turns off HTTPS.</span></span> <span data-ttu-id="8791b-439">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8791b-440">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8791b-441">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-442">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="8791b-443">Web</span><span class="sxs-lookup"><span data-stu-id="8791b-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-444">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-445">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-446">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8791b-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-447">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-448">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-448">SDK version</span></span> | <span data-ttu-id="8791b-449">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-450">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-451">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8791b-452">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8791b-453">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-454">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="8791b-455">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="8791b-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8791b-456">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8791b-456">The type of authentication to use.</span></span> <span data-ttu-id="8791b-457">指定できる値は、</span><span class="sxs-lookup"><span data-stu-id="8791b-457">The possible values are:</span></span>

  - <span data-ttu-id="8791b-458">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8791b-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8791b-459">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8791b-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8791b-460">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8791b-461">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8791b-462">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="8791b-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8791b-463">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8791b-464">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8791b-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8791b-465">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-466">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8791b-467">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8791b-468">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8791b-469">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="8791b-470">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8791b-471">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8791b-472">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8791b-473">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8791b-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8791b-474">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8791b-475">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8791b-476">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-476">The Client ID for this project.</span></span> <span data-ttu-id="8791b-477">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8791b-478">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8791b-479">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8791b-479">The domain for the directory tenant.</span></span> <span data-ttu-id="8791b-480">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-481">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8791b-482">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8791b-483">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-484">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8791b-485">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="8791b-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8791b-486">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-487">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8791b-488">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8791b-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8791b-489">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-490">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-491">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-491">Turns off HTTPS.</span></span> <span data-ttu-id="8791b-492">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8791b-493">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8791b-494">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-495">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-496">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="8791b-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8791b-497">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-498">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-498">SDK version</span></span> | <span data-ttu-id="8791b-499">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-500">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-501">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="8791b-502">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="8791b-503">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="8791b-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="8791b-504">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8791b-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="8791b-505">angular、react</span><span class="sxs-lookup"><span data-stu-id="8791b-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8791b-506">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8791b-506">The type of authentication to use.</span></span> <span data-ttu-id="8791b-507">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="8791b-508">指定できる値は、</span><span class="sxs-lookup"><span data-stu-id="8791b-508">The possible values are:</span></span>

  - <span data-ttu-id="8791b-509">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8791b-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8791b-510">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8791b-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-511">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-512">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-513">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-513">Turns off HTTPS.</span></span> <span data-ttu-id="8791b-514">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8791b-515">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8791b-516">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-517">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-518">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-519">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8791b-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-520">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-521">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-521">SDK version</span></span> | <span data-ttu-id="8791b-522">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-523">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-524">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8791b-525">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="8791b-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="8791b-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-527">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-528">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-529">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8791b-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-530">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-531">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-531">SDK version</span></span> | <span data-ttu-id="8791b-532">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-533">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-534">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8791b-535">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="8791b-536">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-537">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="8791b-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8791b-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="8791b-539">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="8791b-540">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8791b-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="8791b-541">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8791b-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="8791b-542">webapi</span><span class="sxs-lookup"><span data-stu-id="8791b-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8791b-543">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8791b-543">The type of authentication to use.</span></span> <span data-ttu-id="8791b-544">指定できる値は、</span><span class="sxs-lookup"><span data-stu-id="8791b-544">The possible values are:</span></span>

  - <span data-ttu-id="8791b-545">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8791b-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8791b-546">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8791b-547">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8791b-548">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8791b-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8791b-549">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8791b-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8791b-550">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8791b-551">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8791b-552">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8791b-553">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8791b-554">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8791b-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8791b-555">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-556">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8791b-557">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-557">The Client ID for this project.</span></span> <span data-ttu-id="8791b-558">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-559">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8791b-560">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8791b-560">The domain for the directory tenant.</span></span> <span data-ttu-id="8791b-561">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-562">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8791b-563">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8791b-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8791b-564">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8791b-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8791b-565">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8791b-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8791b-566">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8791b-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8791b-567">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8791b-568">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8791b-569">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8791b-569">Turns off HTTPS.</span></span> <span data-ttu-id="8791b-570">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8791b-571">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8791b-572">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8791b-573">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8791b-574">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8791b-575">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8791b-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8791b-576">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8791b-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8791b-577">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8791b-577">SDK version</span></span> | <span data-ttu-id="8791b-578">既定値</span><span class="sxs-lookup"><span data-stu-id="8791b-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8791b-579">3.1</span><span class="sxs-lookup"><span data-stu-id="8791b-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8791b-580">3.0</span><span class="sxs-lookup"><span data-stu-id="8791b-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8791b-581">2.1</span><span class="sxs-lookup"><span data-stu-id="8791b-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8791b-582">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8791b-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="8791b-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="8791b-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="8791b-584">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="8791b-585">例</span><span class="sxs-lookup"><span data-stu-id="8791b-585">Examples</span></span>

- <span data-ttu-id="8791b-586">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="8791b-587">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="8791b-588">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="8791b-589">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="8791b-590">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8791b-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="8791b-591">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8791b-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="8791b-592">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8791b-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="8791b-593">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="8791b-594">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="8791b-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="8791b-595">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8791b-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="8791b-596">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8791b-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="8791b-597">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8791b-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="8791b-598">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8791b-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="8791b-599">参照</span><span class="sxs-lookup"><span data-stu-id="8791b-599">See also</span></span>

- [<span data-ttu-id="8791b-600">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="8791b-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="8791b-601">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="8791b-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="8791b-602">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="8791b-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="8791b-603">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="8791b-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
