---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102828"
---
# <a name="dotnet-new"></a><span data-ttu-id="8f38f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8f38f-103">dotnet new</span></span>

<span data-ttu-id="8f38f-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8f38f-105">名前</span><span class="sxs-lookup"><span data-stu-id="8f38f-105">Name</span></span>

<span data-ttu-id="8f38f-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8f38f-107">構文</span><span class="sxs-lookup"><span data-stu-id="8f38f-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="8f38f-108">説明</span><span class="sxs-lookup"><span data-stu-id="8f38f-108">Description</span></span>

<span data-ttu-id="8f38f-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="8f38f-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="8f38f-111">暗黙的な復元</span><span class="sxs-lookup"><span data-stu-id="8f38f-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="8f38f-112">引数</span><span class="sxs-lookup"><span data-stu-id="8f38f-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="8f38f-113">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="8f38f-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8f38f-114">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f38f-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8f38f-115">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="8f38f-116">`dotnet new --list` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="8f38f-117">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="8f38f-118">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="8f38f-119">`dotnet new` の呼び出し時に、CLI でテンプレートの一致を (部分的にも) 検出できない場合。</span><span class="sxs-lookup"><span data-stu-id="8f38f-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="8f38f-120">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="8f38f-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="8f38f-121">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="8f38f-122">このコマンドには、テンプレートの既定の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-122">The command contains a default list of templates.</span></span> <span data-ttu-id="8f38f-123">使用可能なテンプレートの一覧を取得するには、`dotnet new -l` を使います。</span><span class="sxs-lookup"><span data-stu-id="8f38f-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8f38f-124">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="8f38f-125">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="8f38f-126">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="8f38f-127">テンプレート</span><span class="sxs-lookup"><span data-stu-id="8f38f-127">Templates</span></span>                                    | <span data-ttu-id="8f38f-128">短い名前</span><span class="sxs-lookup"><span data-stu-id="8f38f-128">Short name</span></span>                      | <span data-ttu-id="8f38f-129">言語</span><span class="sxs-lookup"><span data-stu-id="8f38f-129">Language</span></span>     | <span data-ttu-id="8f38f-130">Tags</span><span class="sxs-lookup"><span data-stu-id="8f38f-130">Tags</span></span>                                  | <span data-ttu-id="8f38f-131">導入時期</span><span class="sxs-lookup"><span data-stu-id="8f38f-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="8f38f-132">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8f38f-132">Console Application</span></span>                          | [<span data-ttu-id="8f38f-133">console</span><span class="sxs-lookup"><span data-stu-id="8f38f-133">console</span></span>](#console)             | <span data-ttu-id="8f38f-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-134">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-135">Common/Console</span><span class="sxs-lookup"><span data-stu-id="8f38f-135">Common/Console</span></span>                        | <span data-ttu-id="8f38f-136">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-136">1.0</span></span>        |
| <span data-ttu-id="8f38f-137">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-137">Class library</span></span>                                | [<span data-ttu-id="8f38f-138">classlib</span><span class="sxs-lookup"><span data-stu-id="8f38f-138">classlib</span></span>](#classlib)           | <span data-ttu-id="8f38f-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-139">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-140">Common/Library</span><span class="sxs-lookup"><span data-stu-id="8f38f-140">Common/Library</span></span>                        | <span data-ttu-id="8f38f-141">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-141">1.0</span></span>        |
| <span data-ttu-id="8f38f-142">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8f38f-142">WPF Application</span></span>                              | [<span data-ttu-id="8f38f-143">wpf</span><span class="sxs-lookup"><span data-stu-id="8f38f-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="8f38f-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-144">[C#]</span></span>         | <span data-ttu-id="8f38f-145">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8f38f-145">Common/WPF</span></span>                            | <span data-ttu-id="8f38f-146">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-146">3.0</span></span>        |
| <span data-ttu-id="8f38f-147">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-147">WPF Class library</span></span>                            | [<span data-ttu-id="8f38f-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="8f38f-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="8f38f-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-149">[C#]</span></span>         | <span data-ttu-id="8f38f-150">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8f38f-150">Common/WPF</span></span>                            | <span data-ttu-id="8f38f-151">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-151">3.0</span></span>        |
| <span data-ttu-id="8f38f-152">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="8f38f-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="8f38f-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="8f38f-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-154">[C#]</span></span>         | <span data-ttu-id="8f38f-155">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8f38f-155">Common/WPF</span></span>                            | <span data-ttu-id="8f38f-156">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-156">3.0</span></span>        |
| <span data-ttu-id="8f38f-157">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="8f38f-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8f38f-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="8f38f-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-159">[C#]</span></span>         | <span data-ttu-id="8f38f-160">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="8f38f-160">Common/WPF</span></span>                            | <span data-ttu-id="8f38f-161">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-161">3.0</span></span>        |
| <span data-ttu-id="8f38f-162">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8f38f-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="8f38f-163">winforms</span><span class="sxs-lookup"><span data-stu-id="8f38f-163">winforms</span></span>](#winforms)           | <span data-ttu-id="8f38f-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-164">[C#]</span></span>         | <span data-ttu-id="8f38f-165">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="8f38f-165">Common/WinForms</span></span>                       | <span data-ttu-id="8f38f-166">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-166">3.0</span></span>        |
| <span data-ttu-id="8f38f-167">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="8f38f-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="8f38f-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="8f38f-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-169">[C#]</span></span>         | <span data-ttu-id="8f38f-170">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="8f38f-170">Common/WinForms</span></span>                       | <span data-ttu-id="8f38f-171">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-171">3.0</span></span>        |
| <span data-ttu-id="8f38f-172">Worker Service</span><span class="sxs-lookup"><span data-stu-id="8f38f-172">Worker Service</span></span>                               | [<span data-ttu-id="8f38f-173">worker</span><span class="sxs-lookup"><span data-stu-id="8f38f-173">worker</span></span>](#web-others)           | <span data-ttu-id="8f38f-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-174">[C#]</span></span>         | <span data-ttu-id="8f38f-175">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="8f38f-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="8f38f-176">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-176">3.0</span></span>        |
| <span data-ttu-id="8f38f-177">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8f38f-177">Unit Test Project</span></span>                            | [<span data-ttu-id="8f38f-178">mstest</span><span class="sxs-lookup"><span data-stu-id="8f38f-178">mstest</span></span>](#test)                 | <span data-ttu-id="8f38f-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-179">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-180">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="8f38f-180">Test/MSTest</span></span>                           | <span data-ttu-id="8f38f-181">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-181">1.0</span></span>        |
| <span data-ttu-id="8f38f-182">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8f38f-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="8f38f-183">nunit</span><span class="sxs-lookup"><span data-stu-id="8f38f-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="8f38f-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-184">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-185">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8f38f-185">Test/NUnit</span></span>                            | <span data-ttu-id="8f38f-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="8f38f-186">2.1.400</span></span>    |
| <span data-ttu-id="8f38f-187">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="8f38f-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="8f38f-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-188">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-189">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="8f38f-189">Test/NUnit</span></span>                            | <span data-ttu-id="8f38f-190">2.2</span><span class="sxs-lookup"><span data-stu-id="8f38f-190">2.2</span></span>        |
| <span data-ttu-id="8f38f-191">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="8f38f-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="8f38f-192">xunit</span><span class="sxs-lookup"><span data-stu-id="8f38f-192">xunit</span></span>](#test)                  | <span data-ttu-id="8f38f-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8f38f-193">[C#], F#, VB</span></span> | <span data-ttu-id="8f38f-194">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="8f38f-194">Test/xUnit</span></span>                            | <span data-ttu-id="8f38f-195">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-195">1.0</span></span>        |
| <span data-ttu-id="8f38f-196">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8f38f-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="8f38f-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-197">[C#]</span></span>         | <span data-ttu-id="8f38f-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8f38f-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="8f38f-199">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-199">3.0</span></span>        |
| <span data-ttu-id="8f38f-200">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="8f38f-200">Razor Page</span></span>                                   | [<span data-ttu-id="8f38f-201">page</span><span class="sxs-lookup"><span data-stu-id="8f38f-201">page</span></span>](#page)                   | <span data-ttu-id="8f38f-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-202">[C#]</span></span>         | <span data-ttu-id="8f38f-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8f38f-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="8f38f-204">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-204">2.0</span></span>        |
| <span data-ttu-id="8f38f-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8f38f-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="8f38f-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="8f38f-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="8f38f-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-207">[C#]</span></span>         | <span data-ttu-id="8f38f-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8f38f-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="8f38f-209">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-209">2.0</span></span>        |
| <span data-ttu-id="8f38f-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8f38f-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="8f38f-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-211">[C#]</span></span>         | <span data-ttu-id="8f38f-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8f38f-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="8f38f-213">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-213">2.0</span></span>        |
| <span data-ttu-id="8f38f-214">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-214">Blazor Server App</span></span>                            | [<span data-ttu-id="8f38f-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8f38f-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="8f38f-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-216">[C#]</span></span>         | <span data-ttu-id="8f38f-217">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="8f38f-217">Web/Blazor</span></span>                            | <span data-ttu-id="8f38f-218">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-218">3.0</span></span>        |
| <span data-ttu-id="8f38f-219">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="8f38f-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="8f38f-220">web</span><span class="sxs-lookup"><span data-stu-id="8f38f-220">web</span></span>](#web)                     | <span data-ttu-id="8f38f-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8f38f-221">[C#], F#</span></span>     | <span data-ttu-id="8f38f-222">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="8f38f-222">Web/Empty</span></span>                             | <span data-ttu-id="8f38f-223">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-223">1.0</span></span>        |
| <span data-ttu-id="8f38f-224">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="8f38f-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="8f38f-225">mvc</span><span class="sxs-lookup"><span data-stu-id="8f38f-225">mvc</span></span>](#web-options)             | <span data-ttu-id="8f38f-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8f38f-226">[C#], F#</span></span>     | <span data-ttu-id="8f38f-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="8f38f-227">Web/MVC</span></span>                               | <span data-ttu-id="8f38f-228">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-228">1.0</span></span>        |
| <span data-ttu-id="8f38f-229">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="8f38f-230">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="8f38f-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="8f38f-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-231">[C#]</span></span>         | <span data-ttu-id="8f38f-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="8f38f-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="8f38f-233">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="8f38f-234">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8f38f-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="8f38f-235">angular</span><span class="sxs-lookup"><span data-stu-id="8f38f-235">angular</span></span>](#spa)                 | <span data-ttu-id="8f38f-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-236">[C#]</span></span>         | <span data-ttu-id="8f38f-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8f38f-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8f38f-238">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-238">2.0</span></span>        |
| <span data-ttu-id="8f38f-239">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8f38f-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="8f38f-240">react</span><span class="sxs-lookup"><span data-stu-id="8f38f-240">react</span></span>](#spa)                   | <span data-ttu-id="8f38f-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-241">[C#]</span></span>         | <span data-ttu-id="8f38f-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8f38f-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8f38f-243">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-243">2.0</span></span>        |
| <span data-ttu-id="8f38f-244">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8f38f-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="8f38f-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="8f38f-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="8f38f-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-246">[C#]</span></span>         | <span data-ttu-id="8f38f-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="8f38f-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="8f38f-248">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-248">2.0</span></span>        |
| <span data-ttu-id="8f38f-249">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-249">Razor Class Library</span></span>                          | [<span data-ttu-id="8f38f-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8f38f-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="8f38f-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-251">[C#]</span></span>         | <span data-ttu-id="8f38f-252">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="8f38f-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="8f38f-253">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-253">2.1</span></span>        |
| <span data-ttu-id="8f38f-254">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="8f38f-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="8f38f-255">webapi</span><span class="sxs-lookup"><span data-stu-id="8f38f-255">webapi</span></span>](#webapi)               | <span data-ttu-id="8f38f-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8f38f-256">[C#], F#</span></span>     | <span data-ttu-id="8f38f-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="8f38f-257">Web/WebAPI</span></span>                            | <span data-ttu-id="8f38f-258">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-258">1.0</span></span>        |
| <span data-ttu-id="8f38f-259">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="8f38f-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="8f38f-260">grpc</span><span class="sxs-lookup"><span data-stu-id="8f38f-260">grpc</span></span>](#web-others)             | <span data-ttu-id="8f38f-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="8f38f-261">[C#]</span></span>         | <span data-ttu-id="8f38f-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="8f38f-262">Web/gRPC</span></span>                              | <span data-ttu-id="8f38f-263">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-263">3.0</span></span>        |
| <span data-ttu-id="8f38f-264">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="8f38f-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="8f38f-265">proto</span><span class="sxs-lookup"><span data-stu-id="8f38f-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="8f38f-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="8f38f-266">Web/gRPC</span></span>                              | <span data-ttu-id="8f38f-267">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-267">3.0</span></span>        |
| <span data-ttu-id="8f38f-268">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="8f38f-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="8f38f-269">構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-269">Config</span></span>                                | <span data-ttu-id="8f38f-270">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-270">3.0</span></span>        |
| <span data-ttu-id="8f38f-271">global.json file</span><span class="sxs-lookup"><span data-stu-id="8f38f-271">global.json file</span></span>                             | [<span data-ttu-id="8f38f-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="8f38f-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="8f38f-273">構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-273">Config</span></span>                                | <span data-ttu-id="8f38f-274">2.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-274">2.0</span></span>        |
| <span data-ttu-id="8f38f-275">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="8f38f-276">構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-276">Config</span></span>                                | <span data-ttu-id="8f38f-277">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-277">1.0</span></span>        |
| <span data-ttu-id="8f38f-278">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="8f38f-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="8f38f-279">構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-279">Config</span></span>                                | <span data-ttu-id="8f38f-280">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-280">3.0</span></span>        |
| <span data-ttu-id="8f38f-281">Web 構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="8f38f-282">構成</span><span class="sxs-lookup"><span data-stu-id="8f38f-282">Config</span></span>                                | <span data-ttu-id="8f38f-283">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-283">1.0</span></span>        |
| <span data-ttu-id="8f38f-284">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="8f38f-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="8f38f-285">ソリューション</span><span class="sxs-lookup"><span data-stu-id="8f38f-285">Solution</span></span>                              | <span data-ttu-id="8f38f-286">1</span><span class="sxs-lookup"><span data-stu-id="8f38f-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="8f38f-287">オプション</span><span class="sxs-lookup"><span data-stu-id="8f38f-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="8f38f-288">指定されたコマンドが実行された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="8f38f-289">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="8f38f-290">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8f38f-291">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8f38f-292">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-292">Prints out help for the command.</span></span> <span data-ttu-id="8f38f-293">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="8f38f-294">たとえば、`dotnet new mvc --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="8f38f-295">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8f38f-296">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f38f-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8f38f-297">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="8f38f-298">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="8f38f-299">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="8f38f-300">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="8f38f-301">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="8f38f-302">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="8f38f-303">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="8f38f-303">The language of the template to create.</span></span> <span data-ttu-id="8f38f-304">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8f38f-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8f38f-305">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8f38f-306">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8f38f-307">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="8f38f-308">たとえば、`dotnet new console -lang "F#"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="8f38f-309">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-309">The name for the created output.</span></span> <span data-ttu-id="8f38f-310">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="8f38f-311">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="8f38f-312">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8f38f-313">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="8f38f-313">Location to place the generated output.</span></span> <span data-ttu-id="8f38f-314">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="8f38f-315">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-315">Filters templates based on available types.</span></span> <span data-ttu-id="8f38f-316">事前定義されている値は `project`、`item`、`other` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="8f38f-317">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8f38f-318">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="8f38f-319">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="8f38f-320">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8f38f-321">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f38f-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8f38f-322">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="8f38f-323">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="8f38f-324">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="8f38f-325">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="8f38f-326">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="8f38f-327">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="8f38f-328">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="8f38f-328">Template options</span></span>

<span data-ttu-id="8f38f-329">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f38f-329">Each project template may have additional options available.</span></span> <span data-ttu-id="8f38f-330">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="8f38f-331">コンソール</span><span class="sxs-lookup"><span data-stu-id="8f38f-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-332">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-333">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8f38f-334">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-335">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-335">SDK version</span></span> | <span data-ttu-id="8f38f-336">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-337">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-338">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8f38f-339">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8f38f-340">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8f38f-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8f38f-341">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-341">Not supported for F#.</span></span> <span data-ttu-id="8f38f-342">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-343">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-344">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="8f38f-345">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="8f38f-346">classlib</span><span class="sxs-lookup"><span data-stu-id="8f38f-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-347">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-348">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8f38f-349">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8f38f-350">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8f38f-351">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8f38f-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="8f38f-352">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-352">Not supported for F#.</span></span> <span data-ttu-id="8f38f-353">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-354">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-355">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="8f38f-356">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="8f38f-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-357">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-358">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8f38f-359">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8f38f-360">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8f38f-361">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8f38f-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8f38f-362">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-363">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="8f38f-364">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="8f38f-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="8f38f-365">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="8f38f-366">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="8f38f-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="8f38f-367">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f38f-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-368">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="8f38f-369">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="8f38f-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-370">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-371">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="8f38f-372">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-373">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-374">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="8f38f-375">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="8f38f-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-376">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-377">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8f38f-378">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-379">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-379">SDK version</span></span> | <span data-ttu-id="8f38f-380">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-381">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-382">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8f38f-383">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-384">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="8f38f-385">nunit</span><span class="sxs-lookup"><span data-stu-id="8f38f-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-386">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="8f38f-387">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-388">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-388">SDK version</span></span> | <span data-ttu-id="8f38f-389">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-390">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-391">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8f38f-392">2.2</span><span class="sxs-lookup"><span data-stu-id="8f38f-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="8f38f-393">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="8f38f-394">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-395">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="8f38f-396">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="8f38f-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8f38f-397">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-397">Namespace for the generated code.</span></span> <span data-ttu-id="8f38f-398">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="8f38f-399">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="8f38f-400">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="8f38f-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="8f38f-401">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-401">Namespace for the generated code.</span></span> <span data-ttu-id="8f38f-402">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="8f38f-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="8f38f-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8f38f-404">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8f38f-404">The type of authentication to use.</span></span> <span data-ttu-id="8f38f-405">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-405">The possible values are:</span></span>

  - <span data-ttu-id="8f38f-406">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8f38f-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8f38f-407">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8f38f-408">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8f38f-409">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8f38f-410">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8f38f-411">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-412">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8f38f-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8f38f-413">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-414">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8f38f-415">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8f38f-416">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8f38f-417">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="8f38f-418">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8f38f-419">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8f38f-420">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-421">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8f38f-422">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8f38f-423">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8f38f-424">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-424">The Client ID for this project.</span></span> <span data-ttu-id="8f38f-425">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8f38f-426">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8f38f-427">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-427">The domain for the directory tenant.</span></span> <span data-ttu-id="8f38f-428">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-429">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8f38f-430">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8f38f-431">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-432">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8f38f-433">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8f38f-434">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-435">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8f38f-436">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8f38f-437">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-438">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-439">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-439">Turns off HTTPS.</span></span> <span data-ttu-id="8f38f-440">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8f38f-441">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8f38f-442">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-443">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="8f38f-444">Web</span><span class="sxs-lookup"><span data-stu-id="8f38f-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-445">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-446">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-447">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-448">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-449">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-449">SDK version</span></span> | <span data-ttu-id="8f38f-450">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-451">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-452">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8f38f-453">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8f38f-454">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-455">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="8f38f-456">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="8f38f-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8f38f-457">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8f38f-457">The type of authentication to use.</span></span> <span data-ttu-id="8f38f-458">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-458">The possible values are:</span></span>

  - <span data-ttu-id="8f38f-459">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8f38f-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8f38f-460">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="8f38f-461">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8f38f-462">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8f38f-463">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="8f38f-464">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-465">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8f38f-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8f38f-466">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-467">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8f38f-468">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8f38f-469">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="8f38f-470">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="8f38f-471">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="8f38f-472">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="8f38f-473">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-474">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8f38f-475">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8f38f-476">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8f38f-477">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-477">The Client ID for this project.</span></span> <span data-ttu-id="8f38f-478">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8f38f-479">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8f38f-480">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-480">The domain for the directory tenant.</span></span> <span data-ttu-id="8f38f-481">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-482">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8f38f-483">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8f38f-484">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-485">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="8f38f-486">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8f38f-487">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-488">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8f38f-489">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8f38f-490">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-491">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-492">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-492">Turns off HTTPS.</span></span> <span data-ttu-id="8f38f-493">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8f38f-494">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8f38f-495">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-496">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-497">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8f38f-498">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-499">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-499">SDK version</span></span> | <span data-ttu-id="8f38f-500">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-501">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-502">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="8f38f-503">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="8f38f-504">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="8f38f-505">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="8f38f-506">デバッグ ビルドで [Razor ランタイム コンパイル](/aspnet/core/mvc/views/view-compilation#runtime-compilation)を使用するようにプロジェクトが構成されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="8f38f-507">.NET Core 3.1 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="8f38f-508">angular、react</span><span class="sxs-lookup"><span data-stu-id="8f38f-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8f38f-509">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8f38f-509">The type of authentication to use.</span></span> <span data-ttu-id="8f38f-510">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="8f38f-511">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-511">The possible values are:</span></span>

  - <span data-ttu-id="8f38f-512">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8f38f-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8f38f-513">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-514">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-515">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-516">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-516">Turns off HTTPS.</span></span> <span data-ttu-id="8f38f-517">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8f38f-518">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8f38f-519">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-520">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-521">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-522">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-523">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-524">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-524">SDK version</span></span> | <span data-ttu-id="8f38f-525">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-526">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-527">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8f38f-528">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="8f38f-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="8f38f-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-530">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-531">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-532">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-533">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-534">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-534">SDK version</span></span> | <span data-ttu-id="8f38f-535">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-536">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-537">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8f38f-538">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="8f38f-539">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-540">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="8f38f-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="8f38f-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="8f38f-542">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="8f38f-543">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="8f38f-544">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="8f38f-545">webapi</span><span class="sxs-lookup"><span data-stu-id="8f38f-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="8f38f-546">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="8f38f-546">The type of authentication to use.</span></span> <span data-ttu-id="8f38f-547">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-547">The possible values are:</span></span>

  - <span data-ttu-id="8f38f-548">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="8f38f-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="8f38f-549">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="8f38f-550">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="8f38f-551">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="8f38f-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-552">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8f38f-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8f38f-553">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8f38f-554">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="8f38f-555">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8f38f-556">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="8f38f-557">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8f38f-558">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-559">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="8f38f-560">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-560">The Client ID for this project.</span></span> <span data-ttu-id="8f38f-561">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-562">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="8f38f-563">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="8f38f-563">The domain for the directory tenant.</span></span> <span data-ttu-id="8f38f-564">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-565">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="8f38f-566">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8f38f-567">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8f38f-568">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="8f38f-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="8f38f-569">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="8f38f-570">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="8f38f-571">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="8f38f-572">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8f38f-572">Turns off HTTPS.</span></span> <span data-ttu-id="8f38f-573">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="8f38f-574">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="8f38f-575">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8f38f-576">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8f38f-577">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8f38f-578">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="8f38f-579">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f38f-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="8f38f-580">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="8f38f-580">SDK version</span></span> | <span data-ttu-id="8f38f-581">既定値</span><span class="sxs-lookup"><span data-stu-id="8f38f-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="8f38f-582">3.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="8f38f-583">3.0</span><span class="sxs-lookup"><span data-stu-id="8f38f-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="8f38f-584">2.1</span><span class="sxs-lookup"><span data-stu-id="8f38f-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="8f38f-585">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8f38f-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="8f38f-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="8f38f-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="8f38f-587">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="8f38f-588">使用例</span><span class="sxs-lookup"><span data-stu-id="8f38f-588">Examples</span></span>

- <span data-ttu-id="8f38f-589">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="8f38f-590">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="8f38f-591">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="8f38f-592">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="8f38f-593">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="8f38f-594">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="8f38f-595">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="8f38f-596">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="8f38f-597">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="8f38f-598">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="8f38f-599">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="8f38f-600">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8f38f-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="8f38f-601">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f38f-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="8f38f-602">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f38f-602">See also</span></span>

- [<span data-ttu-id="8f38f-603">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="8f38f-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="8f38f-604">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="8f38f-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="8f38f-605">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="8f38f-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="8f38f-606">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="8f38f-606">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
