---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157220"
---
# <a name="dotnet-new"></a><span data-ttu-id="b68ab-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b68ab-103">dotnet new</span></span>

<span data-ttu-id="b68ab-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b68ab-105">名前</span><span class="sxs-lookup"><span data-stu-id="b68ab-105">Name</span></span>

<span data-ttu-id="b68ab-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b68ab-107">構文</span><span class="sxs-lookup"><span data-stu-id="b68ab-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="b68ab-108">説明</span><span class="sxs-lookup"><span data-stu-id="b68ab-108">Description</span></span>

<span data-ttu-id="b68ab-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="b68ab-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="b68ab-111">引数</span><span class="sxs-lookup"><span data-stu-id="b68ab-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="b68ab-112">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="b68ab-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b68ab-113">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b68ab-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b68ab-114">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="b68ab-115">`dotnet new --list` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="b68ab-116">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="b68ab-117">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="b68ab-118">`dotnet new` の呼び出し時に、CLI によってテンプレートの一致が (部分的にも) 検出されない場合。</span><span class="sxs-lookup"><span data-stu-id="b68ab-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="b68ab-119">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="b68ab-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="b68ab-120">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="b68ab-121">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-121">The command contains a default list of templates.</span></span> <span data-ttu-id="b68ab-122">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="b68ab-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b68ab-123">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="b68ab-124">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="b68ab-125">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="b68ab-126">テンプレート</span><span class="sxs-lookup"><span data-stu-id="b68ab-126">Templates</span></span>                                    | <span data-ttu-id="b68ab-127">短い名前</span><span class="sxs-lookup"><span data-stu-id="b68ab-127">Short name</span></span>                      | <span data-ttu-id="b68ab-128">言語</span><span class="sxs-lookup"><span data-stu-id="b68ab-128">Language</span></span>     | <span data-ttu-id="b68ab-129">Tags</span><span class="sxs-lookup"><span data-stu-id="b68ab-129">Tags</span></span>                                  | <span data-ttu-id="b68ab-130">導入時期</span><span class="sxs-lookup"><span data-stu-id="b68ab-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="b68ab-131">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b68ab-131">Console Application</span></span>                          | [<span data-ttu-id="b68ab-132">console</span><span class="sxs-lookup"><span data-stu-id="b68ab-132">console</span></span>](#console)             | <span data-ttu-id="b68ab-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-133">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-134">Common/Console</span><span class="sxs-lookup"><span data-stu-id="b68ab-134">Common/Console</span></span>                        | <span data-ttu-id="b68ab-135">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-135">1.0</span></span>        |
| <span data-ttu-id="b68ab-136">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-136">Class library</span></span>                                | [<span data-ttu-id="b68ab-137">classlib</span><span class="sxs-lookup"><span data-stu-id="b68ab-137">classlib</span></span>](#classlib)           | <span data-ttu-id="b68ab-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-138">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-139">Common/Library</span><span class="sxs-lookup"><span data-stu-id="b68ab-139">Common/Library</span></span>                        | <span data-ttu-id="b68ab-140">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-140">1.0</span></span>        |
| <span data-ttu-id="b68ab-141">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b68ab-141">WPF Application</span></span>                              | [<span data-ttu-id="b68ab-142">wpf</span><span class="sxs-lookup"><span data-stu-id="b68ab-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="b68ab-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-143">[C#]</span></span>         | <span data-ttu-id="b68ab-144">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="b68ab-144">Common/WPF</span></span>                            | <span data-ttu-id="b68ab-145">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-145">3.0</span></span>        |
| <span data-ttu-id="b68ab-146">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-146">WPF Class library</span></span>                            | [<span data-ttu-id="b68ab-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="b68ab-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="b68ab-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-148">[C#]</span></span>         | <span data-ttu-id="b68ab-149">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="b68ab-149">Common/WPF</span></span>                            | <span data-ttu-id="b68ab-150">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-150">3.0</span></span>        |
| <span data-ttu-id="b68ab-151">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="b68ab-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="b68ab-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="b68ab-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-153">[C#]</span></span>         | <span data-ttu-id="b68ab-154">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="b68ab-154">Common/WPF</span></span>                            | <span data-ttu-id="b68ab-155">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-155">3.0</span></span>        |
| <span data-ttu-id="b68ab-156">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="b68ab-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="b68ab-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="b68ab-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-158">[C#]</span></span>         | <span data-ttu-id="b68ab-159">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="b68ab-159">Common/WPF</span></span>                            | <span data-ttu-id="b68ab-160">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-160">3.0</span></span>        |
| <span data-ttu-id="b68ab-161">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b68ab-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="b68ab-162">winforms</span><span class="sxs-lookup"><span data-stu-id="b68ab-162">winforms</span></span>](#winforms)           | <span data-ttu-id="b68ab-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-163">[C#]</span></span>         | <span data-ttu-id="b68ab-164">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="b68ab-164">Common/WinForms</span></span>                       | <span data-ttu-id="b68ab-165">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-165">3.0</span></span>        |
| <span data-ttu-id="b68ab-166">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="b68ab-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="b68ab-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="b68ab-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-168">[C#]</span></span>         | <span data-ttu-id="b68ab-169">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="b68ab-169">Common/WinForms</span></span>                       | <span data-ttu-id="b68ab-170">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-170">3.0</span></span>        |
| <span data-ttu-id="b68ab-171">Worker Service</span><span class="sxs-lookup"><span data-stu-id="b68ab-171">Worker Service</span></span>                               | [<span data-ttu-id="b68ab-172">worker</span><span class="sxs-lookup"><span data-stu-id="b68ab-172">worker</span></span>](#web-others)           | <span data-ttu-id="b68ab-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-173">[C#]</span></span>         | <span data-ttu-id="b68ab-174">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="b68ab-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="b68ab-175">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-175">3.0</span></span>        |
| <span data-ttu-id="b68ab-176">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b68ab-176">Unit Test Project</span></span>                            | [<span data-ttu-id="b68ab-177">mstest</span><span class="sxs-lookup"><span data-stu-id="b68ab-177">mstest</span></span>](#test)                 | <span data-ttu-id="b68ab-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-178">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="b68ab-179">Test/MSTest</span></span>                           | <span data-ttu-id="b68ab-180">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-180">1.0</span></span>        |
| <span data-ttu-id="b68ab-181">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b68ab-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="b68ab-182">nunit</span><span class="sxs-lookup"><span data-stu-id="b68ab-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="b68ab-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-183">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="b68ab-184">Test/NUnit</span></span>                            | <span data-ttu-id="b68ab-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="b68ab-185">2.1.400</span></span>    |
| <span data-ttu-id="b68ab-186">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="b68ab-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="b68ab-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-187">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="b68ab-188">Test/NUnit</span></span>                            | <span data-ttu-id="b68ab-189">2.2</span><span class="sxs-lookup"><span data-stu-id="b68ab-189">2.2</span></span>        |
| <span data-ttu-id="b68ab-190">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b68ab-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="b68ab-191">xunit</span><span class="sxs-lookup"><span data-stu-id="b68ab-191">xunit</span></span>](#test)                  | <span data-ttu-id="b68ab-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b68ab-192">[C#], F#, VB</span></span> | <span data-ttu-id="b68ab-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="b68ab-193">Test/xUnit</span></span>                            | <span data-ttu-id="b68ab-194">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-194">1.0</span></span>        |
| <span data-ttu-id="b68ab-195">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b68ab-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="b68ab-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-196">[C#]</span></span>         | <span data-ttu-id="b68ab-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b68ab-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="b68ab-198">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-198">3.0</span></span>        |
| <span data-ttu-id="b68ab-199">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="b68ab-199">Razor Page</span></span>                                   | [<span data-ttu-id="b68ab-200">page</span><span class="sxs-lookup"><span data-stu-id="b68ab-200">page</span></span>](#page)                   | <span data-ttu-id="b68ab-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-201">[C#]</span></span>         | <span data-ttu-id="b68ab-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b68ab-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="b68ab-203">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-203">2.0</span></span>        |
| <span data-ttu-id="b68ab-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b68ab-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="b68ab-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="b68ab-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="b68ab-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-206">[C#]</span></span>         | <span data-ttu-id="b68ab-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b68ab-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="b68ab-208">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-208">2.0</span></span>        |
| <span data-ttu-id="b68ab-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b68ab-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="b68ab-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-210">[C#]</span></span>         | <span data-ttu-id="b68ab-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b68ab-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="b68ab-212">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-212">2.0</span></span>        |
| <span data-ttu-id="b68ab-213">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-213">Blazor Server App</span></span>                            | [<span data-ttu-id="b68ab-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="b68ab-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="b68ab-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-215">[C#]</span></span>         | <span data-ttu-id="b68ab-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="b68ab-216">Web/Blazor</span></span>                            | <span data-ttu-id="b68ab-217">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-217">3.0</span></span>        |
| <span data-ttu-id="b68ab-218">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="b68ab-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="b68ab-219">web</span><span class="sxs-lookup"><span data-stu-id="b68ab-219">web</span></span>](#web)                     | <span data-ttu-id="b68ab-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b68ab-220">[C#], F#</span></span>     | <span data-ttu-id="b68ab-221">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="b68ab-221">Web/Empty</span></span>                             | <span data-ttu-id="b68ab-222">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-222">1.0</span></span>        |
| <span data-ttu-id="b68ab-223">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="b68ab-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="b68ab-224">mvc</span><span class="sxs-lookup"><span data-stu-id="b68ab-224">mvc</span></span>](#web-options)             | <span data-ttu-id="b68ab-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b68ab-225">[C#], F#</span></span>     | <span data-ttu-id="b68ab-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="b68ab-226">Web/MVC</span></span>                               | <span data-ttu-id="b68ab-227">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-227">1.0</span></span>        |
| <span data-ttu-id="b68ab-228">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="b68ab-229">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="b68ab-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="b68ab-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-230">[C#]</span></span>         | <span data-ttu-id="b68ab-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="b68ab-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="b68ab-232">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="b68ab-233">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b68ab-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="b68ab-234">angular</span><span class="sxs-lookup"><span data-stu-id="b68ab-234">angular</span></span>](#spa)                 | <span data-ttu-id="b68ab-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-235">[C#]</span></span>         | <span data-ttu-id="b68ab-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b68ab-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b68ab-237">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-237">2.0</span></span>        |
| <span data-ttu-id="b68ab-238">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b68ab-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="b68ab-239">react</span><span class="sxs-lookup"><span data-stu-id="b68ab-239">react</span></span>](#spa)                   | <span data-ttu-id="b68ab-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-240">[C#]</span></span>         | <span data-ttu-id="b68ab-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b68ab-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b68ab-242">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-242">2.0</span></span>        |
| <span data-ttu-id="b68ab-243">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b68ab-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="b68ab-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="b68ab-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="b68ab-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-245">[C#]</span></span>         | <span data-ttu-id="b68ab-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b68ab-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b68ab-247">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-247">2.0</span></span>        |
| <span data-ttu-id="b68ab-248">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-248">Razor Class Library</span></span>                          | [<span data-ttu-id="b68ab-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="b68ab-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="b68ab-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-250">[C#]</span></span>         | <span data-ttu-id="b68ab-251">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="b68ab-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="b68ab-252">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-252">2.1</span></span>        |
| <span data-ttu-id="b68ab-253">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="b68ab-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="b68ab-254">webapi</span><span class="sxs-lookup"><span data-stu-id="b68ab-254">webapi</span></span>](#webapi)               | <span data-ttu-id="b68ab-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b68ab-255">[C#], F#</span></span>     | <span data-ttu-id="b68ab-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="b68ab-256">Web/WebAPI</span></span>                            | <span data-ttu-id="b68ab-257">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-257">1.0</span></span>        |
| <span data-ttu-id="b68ab-258">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="b68ab-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="b68ab-259">grpc</span><span class="sxs-lookup"><span data-stu-id="b68ab-259">grpc</span></span>](#web-others)             | <span data-ttu-id="b68ab-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="b68ab-260">[C#]</span></span>         | <span data-ttu-id="b68ab-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="b68ab-261">Web/gRPC</span></span>                              | <span data-ttu-id="b68ab-262">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-262">3.0</span></span>        |
| <span data-ttu-id="b68ab-263">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="b68ab-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="b68ab-264">proto</span><span class="sxs-lookup"><span data-stu-id="b68ab-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="b68ab-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="b68ab-265">Web/gRPC</span></span>                              | <span data-ttu-id="b68ab-266">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-266">3.0</span></span>        |
| <span data-ttu-id="b68ab-267">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="b68ab-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="b68ab-268">構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-268">Config</span></span>                                | <span data-ttu-id="b68ab-269">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-269">3.0</span></span>        |
| <span data-ttu-id="b68ab-270">global.json file</span><span class="sxs-lookup"><span data-stu-id="b68ab-270">global.json file</span></span>                             | [<span data-ttu-id="b68ab-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="b68ab-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="b68ab-272">構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-272">Config</span></span>                                | <span data-ttu-id="b68ab-273">2.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-273">2.0</span></span>        |
| <span data-ttu-id="b68ab-274">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="b68ab-275">構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-275">Config</span></span>                                | <span data-ttu-id="b68ab-276">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-276">1.0</span></span>        |
| <span data-ttu-id="b68ab-277">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="b68ab-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="b68ab-278">構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-278">Config</span></span>                                | <span data-ttu-id="b68ab-279">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-279">3.0</span></span>        |
| <span data-ttu-id="b68ab-280">Web 構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="b68ab-281">構成</span><span class="sxs-lookup"><span data-stu-id="b68ab-281">Config</span></span>                                | <span data-ttu-id="b68ab-282">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-282">1.0</span></span>        |
| <span data-ttu-id="b68ab-283">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="b68ab-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="b68ab-284">ソリューション</span><span class="sxs-lookup"><span data-stu-id="b68ab-284">Solution</span></span>                              | <span data-ttu-id="b68ab-285">1</span><span class="sxs-lookup"><span data-stu-id="b68ab-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="b68ab-286">オプション</span><span class="sxs-lookup"><span data-stu-id="b68ab-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="b68ab-287">指定されたコマンドが実行された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="b68ab-288">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="b68ab-289">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b68ab-290">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b68ab-291">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-291">Prints out help for the command.</span></span> <span data-ttu-id="b68ab-292">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="b68ab-293">たとえば、`dotnet new mvc --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="b68ab-294">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b68ab-295">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b68ab-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b68ab-296">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="b68ab-297">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="b68ab-298">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="b68ab-299">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="b68ab-300">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="b68ab-301">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="b68ab-302">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="b68ab-302">The language of the template to create.</span></span> <span data-ttu-id="b68ab-303">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b68ab-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b68ab-304">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b68ab-305">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b68ab-306">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="b68ab-307">たとえば、`dotnet new console -lang "F#"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="b68ab-308">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-308">The name for the created output.</span></span> <span data-ttu-id="b68ab-309">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="b68ab-310">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="b68ab-311">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="b68ab-312">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="b68ab-312">Location to place the generated output.</span></span> <span data-ttu-id="b68ab-313">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="b68ab-314">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-314">Filters templates based on available types.</span></span> <span data-ttu-id="b68ab-315">定義済みの値は、"project"、"item"、または "other" です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="b68ab-316">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b68ab-317">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="b68ab-318">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="b68ab-319">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b68ab-320">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b68ab-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b68ab-321">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="b68ab-322">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="b68ab-323">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="b68ab-324">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="b68ab-325">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="b68ab-326">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="b68ab-327">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="b68ab-327">Template options</span></span>

<span data-ttu-id="b68ab-328">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b68ab-328">Each project template may have additional options available.</span></span> <span data-ttu-id="b68ab-329">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="b68ab-330">コンソール</span><span class="sxs-lookup"><span data-stu-id="b68ab-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-331">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-332">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b68ab-333">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-334">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-334">SDK version</span></span> | <span data-ttu-id="b68ab-335">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-336">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-337">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b68ab-338">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b68ab-339">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="b68ab-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b68ab-340">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-340">Not supported for F#.</span></span> <span data-ttu-id="b68ab-341">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-342">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-343">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="b68ab-344">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="b68ab-345">classlib</span><span class="sxs-lookup"><span data-stu-id="b68ab-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-346">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-347">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b68ab-348">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b68ab-349">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b68ab-350">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="b68ab-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b68ab-351">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-351">Not supported for F#.</span></span> <span data-ttu-id="b68ab-352">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-353">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-354">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="b68ab-355">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="b68ab-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-356">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-357">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="b68ab-358">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b68ab-359">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b68ab-360">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="b68ab-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="b68ab-361">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-362">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="b68ab-363">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="b68ab-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b68ab-364">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b68ab-365">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="b68ab-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="b68ab-366">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b68ab-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-367">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="b68ab-368">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="b68ab-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-369">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-370">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="b68ab-371">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-372">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-373">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="b68ab-374">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="b68ab-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-375">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-376">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b68ab-377">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-378">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-378">SDK version</span></span> | <span data-ttu-id="b68ab-379">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-380">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-381">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="b68ab-382">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-383">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="b68ab-384">nunit</span><span class="sxs-lookup"><span data-stu-id="b68ab-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-385">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="b68ab-386">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-387">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-387">SDK version</span></span> | <span data-ttu-id="b68ab-388">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-389">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-390">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b68ab-391">2.2</span><span class="sxs-lookup"><span data-stu-id="b68ab-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="b68ab-392">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="b68ab-393">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-394">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="b68ab-395">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="b68ab-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="b68ab-396">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-396">Namespace for the generated code.</span></span> <span data-ttu-id="b68ab-397">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="b68ab-398">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="b68ab-399">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="b68ab-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="b68ab-400">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-400">Namespace for the generated code.</span></span> <span data-ttu-id="b68ab-401">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="b68ab-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="b68ab-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b68ab-403">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="b68ab-403">The type of authentication to use.</span></span> <span data-ttu-id="b68ab-404">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-404">The possible values are:</span></span>

  - <span data-ttu-id="b68ab-405">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="b68ab-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b68ab-406">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="b68ab-407">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b68ab-408">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b68ab-409">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="b68ab-410">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-411">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="b68ab-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b68ab-412">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-413">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b68ab-414">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b68ab-415">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="b68ab-416">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="b68ab-417">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="b68ab-418">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="b68ab-419">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-420">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b68ab-421">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b68ab-422">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b68ab-423">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-423">The Client ID for this project.</span></span> <span data-ttu-id="b68ab-424">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b68ab-425">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b68ab-426">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-426">The domain for the directory tenant.</span></span> <span data-ttu-id="b68ab-427">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-428">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b68ab-429">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b68ab-430">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-431">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="b68ab-432">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b68ab-433">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-434">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b68ab-435">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b68ab-436">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-437">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-438">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-438">Turns off HTTPS.</span></span> <span data-ttu-id="b68ab-439">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b68ab-440">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b68ab-441">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-442">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="b68ab-443">Web</span><span class="sxs-lookup"><span data-stu-id="b68ab-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-444">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-445">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-446">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-447">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-448">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-448">SDK version</span></span> | <span data-ttu-id="b68ab-449">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-450">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-451">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b68ab-452">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="b68ab-453">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-454">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="b68ab-455">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="b68ab-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b68ab-456">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="b68ab-456">The type of authentication to use.</span></span> <span data-ttu-id="b68ab-457">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-457">The possible values are:</span></span>

  - <span data-ttu-id="b68ab-458">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="b68ab-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b68ab-459">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="b68ab-460">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b68ab-461">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b68ab-462">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="b68ab-463">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-464">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="b68ab-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b68ab-465">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-466">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b68ab-467">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b68ab-468">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="b68ab-469">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="b68ab-470">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="b68ab-471">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="b68ab-472">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-473">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b68ab-474">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b68ab-475">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b68ab-476">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-476">The Client ID for this project.</span></span> <span data-ttu-id="b68ab-477">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b68ab-478">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b68ab-479">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-479">The domain for the directory tenant.</span></span> <span data-ttu-id="b68ab-480">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-481">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b68ab-482">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b68ab-483">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-484">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="b68ab-485">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b68ab-486">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-487">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b68ab-488">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b68ab-489">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-490">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-491">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-491">Turns off HTTPS.</span></span> <span data-ttu-id="b68ab-492">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b68ab-493">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b68ab-494">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-495">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-496">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b68ab-497">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-498">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-498">SDK version</span></span> | <span data-ttu-id="b68ab-499">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-500">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-501">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="b68ab-502">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="b68ab-503">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="b68ab-504">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="b68ab-505">angular、react</span><span class="sxs-lookup"><span data-stu-id="b68ab-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b68ab-506">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="b68ab-506">The type of authentication to use.</span></span> <span data-ttu-id="b68ab-507">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="b68ab-508">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-508">The possible values are:</span></span>

  - <span data-ttu-id="b68ab-509">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="b68ab-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b68ab-510">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-511">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-512">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-513">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-513">Turns off HTTPS.</span></span> <span data-ttu-id="b68ab-514">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b68ab-515">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b68ab-516">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-517">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-518">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-519">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-520">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-521">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-521">SDK version</span></span> | <span data-ttu-id="b68ab-522">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-523">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-524">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b68ab-525">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="b68ab-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="b68ab-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-527">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-528">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-529">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-530">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-531">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-531">SDK version</span></span> | <span data-ttu-id="b68ab-532">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-533">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-534">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b68ab-535">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="b68ab-536">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-537">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="b68ab-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="b68ab-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="b68ab-539">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="b68ab-540">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="b68ab-541">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="b68ab-542">webapi</span><span class="sxs-lookup"><span data-stu-id="b68ab-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b68ab-543">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="b68ab-543">The type of authentication to use.</span></span> <span data-ttu-id="b68ab-544">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-544">The possible values are:</span></span>

  - <span data-ttu-id="b68ab-545">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="b68ab-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b68ab-546">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b68ab-547">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b68ab-548">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="b68ab-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-549">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="b68ab-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b68ab-550">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b68ab-551">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b68ab-552">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b68ab-553">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b68ab-554">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b68ab-555">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-556">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b68ab-557">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-557">The Client ID for this project.</span></span> <span data-ttu-id="b68ab-558">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-559">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b68ab-560">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="b68ab-560">The domain for the directory tenant.</span></span> <span data-ttu-id="b68ab-561">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-562">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b68ab-563">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b68ab-564">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b68ab-565">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="b68ab-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b68ab-566">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b68ab-567">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b68ab-568">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b68ab-569">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b68ab-569">Turns off HTTPS.</span></span> <span data-ttu-id="b68ab-570">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b68ab-571">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b68ab-572">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b68ab-573">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b68ab-574">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b68ab-575">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b68ab-576">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="b68ab-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b68ab-577">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="b68ab-577">SDK version</span></span> | <span data-ttu-id="b68ab-578">既定値</span><span class="sxs-lookup"><span data-stu-id="b68ab-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b68ab-579">3.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b68ab-580">3.0</span><span class="sxs-lookup"><span data-stu-id="b68ab-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b68ab-581">2.1</span><span class="sxs-lookup"><span data-stu-id="b68ab-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="b68ab-582">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="b68ab-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="b68ab-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="b68ab-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="b68ab-584">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="b68ab-585">使用例</span><span class="sxs-lookup"><span data-stu-id="b68ab-585">Examples</span></span>

- <span data-ttu-id="b68ab-586">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="b68ab-587">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="b68ab-588">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="b68ab-589">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="b68ab-590">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="b68ab-591">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="b68ab-592">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="b68ab-593">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="b68ab-594">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="b68ab-595">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="b68ab-596">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="b68ab-597">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b68ab-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="b68ab-598">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b68ab-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="b68ab-599">関連項目</span><span class="sxs-lookup"><span data-stu-id="b68ab-599">See also</span></span>

- [<span data-ttu-id="b68ab-600">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="b68ab-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="b68ab-601">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b68ab-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="b68ab-602">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="b68ab-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="b68ab-603">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="b68ab-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
