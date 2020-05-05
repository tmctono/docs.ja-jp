---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 04/10/2020
ms.openlocfilehash: 9a68baafa7ac3e6ad2fdc8f1c6e8621d6e15f1ff
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506858"
---
# <a name="dotnet-new"></a><span data-ttu-id="2367f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2367f-103">dotnet new</span></span>

<span data-ttu-id="2367f-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2367f-105">名前</span><span class="sxs-lookup"><span data-stu-id="2367f-105">Name</span></span>

<span data-ttu-id="2367f-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2367f-107">構文</span><span class="sxs-lookup"><span data-stu-id="2367f-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="2367f-108">説明</span><span class="sxs-lookup"><span data-stu-id="2367f-108">Description</span></span>

<span data-ttu-id="2367f-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="2367f-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="2367f-111">暗黙的な復元</span><span class="sxs-lookup"><span data-stu-id="2367f-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="2367f-112">引数</span><span class="sxs-lookup"><span data-stu-id="2367f-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="2367f-113">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="2367f-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="2367f-114">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2367f-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="2367f-115">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2367f-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="2367f-116">`dotnet new --list` または `dotnet new -l` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="2367f-117">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="2367f-118">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="2367f-119">`dotnet new` の呼び出し時に、CLI でテンプレートの一致を (部分的にも) 検出できない場合。</span><span class="sxs-lookup"><span data-stu-id="2367f-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="2367f-120">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="2367f-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="2367f-121">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="2367f-122">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="2367f-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="2367f-123">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="2367f-124">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="2367f-125">テンプレート</span><span class="sxs-lookup"><span data-stu-id="2367f-125">Templates</span></span>                                    | <span data-ttu-id="2367f-126">短い名前</span><span class="sxs-lookup"><span data-stu-id="2367f-126">Short name</span></span>                      | <span data-ttu-id="2367f-127">言語</span><span class="sxs-lookup"><span data-stu-id="2367f-127">Language</span></span>     | <span data-ttu-id="2367f-128">Tags</span><span class="sxs-lookup"><span data-stu-id="2367f-128">Tags</span></span>                                  | <span data-ttu-id="2367f-129">導入時期</span><span class="sxs-lookup"><span data-stu-id="2367f-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="2367f-130">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2367f-130">Console Application</span></span>                          | [<span data-ttu-id="2367f-131">console</span><span class="sxs-lookup"><span data-stu-id="2367f-131">console</span></span>](#console)             | <span data-ttu-id="2367f-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-132">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="2367f-133">Common/Console</span></span>                        | <span data-ttu-id="2367f-134">1</span><span class="sxs-lookup"><span data-stu-id="2367f-134">1.0</span></span>        |
| <span data-ttu-id="2367f-135">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-135">Class library</span></span>                                | [<span data-ttu-id="2367f-136">classlib</span><span class="sxs-lookup"><span data-stu-id="2367f-136">classlib</span></span>](#classlib)           | <span data-ttu-id="2367f-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-137">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="2367f-138">Common/Library</span></span>                        | <span data-ttu-id="2367f-139">1</span><span class="sxs-lookup"><span data-stu-id="2367f-139">1.0</span></span>        |
| <span data-ttu-id="2367f-140">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2367f-140">WPF Application</span></span>                              | [<span data-ttu-id="2367f-141">wpf</span><span class="sxs-lookup"><span data-stu-id="2367f-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="2367f-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-142">[C#]</span></span>         | <span data-ttu-id="2367f-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="2367f-143">Common/WPF</span></span>                            | <span data-ttu-id="2367f-144">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-144">3.0</span></span>        |
| <span data-ttu-id="2367f-145">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-145">WPF Class library</span></span>                            | [<span data-ttu-id="2367f-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="2367f-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="2367f-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-147">[C#]</span></span>         | <span data-ttu-id="2367f-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="2367f-148">Common/WPF</span></span>                            | <span data-ttu-id="2367f-149">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-149">3.0</span></span>        |
| <span data-ttu-id="2367f-150">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="2367f-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="2367f-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="2367f-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-152">[C#]</span></span>         | <span data-ttu-id="2367f-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="2367f-153">Common/WPF</span></span>                            | <span data-ttu-id="2367f-154">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-154">3.0</span></span>        |
| <span data-ttu-id="2367f-155">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="2367f-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="2367f-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="2367f-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-157">[C#]</span></span>         | <span data-ttu-id="2367f-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="2367f-158">Common/WPF</span></span>                            | <span data-ttu-id="2367f-159">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-159">3.0</span></span>        |
| <span data-ttu-id="2367f-160">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2367f-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="2367f-161">winforms</span><span class="sxs-lookup"><span data-stu-id="2367f-161">winforms</span></span>](#winforms)           | <span data-ttu-id="2367f-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-162">[C#]</span></span>         | <span data-ttu-id="2367f-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="2367f-163">Common/WinForms</span></span>                       | <span data-ttu-id="2367f-164">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-164">3.0</span></span>        |
| <span data-ttu-id="2367f-165">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="2367f-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="2367f-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="2367f-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-167">[C#]</span></span>         | <span data-ttu-id="2367f-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="2367f-168">Common/WinForms</span></span>                       | <span data-ttu-id="2367f-169">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-169">3.0</span></span>        |
| <span data-ttu-id="2367f-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="2367f-170">Worker Service</span></span>                               | [<span data-ttu-id="2367f-171">worker</span><span class="sxs-lookup"><span data-stu-id="2367f-171">worker</span></span>](#web-others)           | <span data-ttu-id="2367f-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-172">[C#]</span></span>         | <span data-ttu-id="2367f-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="2367f-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="2367f-174">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-174">3.0</span></span>        |
| <span data-ttu-id="2367f-175">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2367f-175">Unit Test Project</span></span>                            | [<span data-ttu-id="2367f-176">mstest</span><span class="sxs-lookup"><span data-stu-id="2367f-176">mstest</span></span>](#test)                 | <span data-ttu-id="2367f-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-177">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="2367f-178">Test/MSTest</span></span>                           | <span data-ttu-id="2367f-179">1</span><span class="sxs-lookup"><span data-stu-id="2367f-179">1.0</span></span>        |
| <span data-ttu-id="2367f-180">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2367f-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="2367f-181">nunit</span><span class="sxs-lookup"><span data-stu-id="2367f-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="2367f-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-182">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="2367f-183">Test/NUnit</span></span>                            | <span data-ttu-id="2367f-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="2367f-184">2.1.400</span></span>    |
| <span data-ttu-id="2367f-185">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="2367f-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="2367f-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-186">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="2367f-187">Test/NUnit</span></span>                            | <span data-ttu-id="2367f-188">2.2</span><span class="sxs-lookup"><span data-stu-id="2367f-188">2.2</span></span>        |
| <span data-ttu-id="2367f-189">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="2367f-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="2367f-190">xunit</span><span class="sxs-lookup"><span data-stu-id="2367f-190">xunit</span></span>](#test)                  | <span data-ttu-id="2367f-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="2367f-191">[C#], F#, VB</span></span> | <span data-ttu-id="2367f-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="2367f-192">Test/xUnit</span></span>                            | <span data-ttu-id="2367f-193">1</span><span class="sxs-lookup"><span data-stu-id="2367f-193">1.0</span></span>        |
| <span data-ttu-id="2367f-194">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2367f-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="2367f-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-195">[C#]</span></span>         | <span data-ttu-id="2367f-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2367f-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="2367f-197">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-197">3.0</span></span>        |
| <span data-ttu-id="2367f-198">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="2367f-198">Razor Page</span></span>                                   | [<span data-ttu-id="2367f-199">page</span><span class="sxs-lookup"><span data-stu-id="2367f-199">page</span></span>](#page)                   | <span data-ttu-id="2367f-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-200">[C#]</span></span>         | <span data-ttu-id="2367f-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2367f-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="2367f-202">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-202">2.0</span></span>        |
| <span data-ttu-id="2367f-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="2367f-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="2367f-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="2367f-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="2367f-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-205">[C#]</span></span>         | <span data-ttu-id="2367f-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2367f-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="2367f-207">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-207">2.0</span></span>        |
| <span data-ttu-id="2367f-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="2367f-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="2367f-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-209">[C#]</span></span>         | <span data-ttu-id="2367f-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2367f-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="2367f-211">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-211">2.0</span></span>        |
| <span data-ttu-id="2367f-212">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="2367f-212">Blazor Server App</span></span>                            | [<span data-ttu-id="2367f-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="2367f-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="2367f-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-214">[C#]</span></span>         | <span data-ttu-id="2367f-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="2367f-215">Web/Blazor</span></span>                            | <span data-ttu-id="2367f-216">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-216">3.0</span></span>        |
| <span data-ttu-id="2367f-217">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="2367f-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="2367f-218">web</span><span class="sxs-lookup"><span data-stu-id="2367f-218">web</span></span>](#web)                     | <span data-ttu-id="2367f-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2367f-219">[C#], F#</span></span>     | <span data-ttu-id="2367f-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="2367f-220">Web/Empty</span></span>                             | <span data-ttu-id="2367f-221">1</span><span class="sxs-lookup"><span data-stu-id="2367f-221">1.0</span></span>        |
| <span data-ttu-id="2367f-222">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="2367f-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="2367f-223">mvc</span><span class="sxs-lookup"><span data-stu-id="2367f-223">mvc</span></span>](#web-options)             | <span data-ttu-id="2367f-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2367f-224">[C#], F#</span></span>     | <span data-ttu-id="2367f-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="2367f-225">Web/MVC</span></span>                               | <span data-ttu-id="2367f-226">1</span><span class="sxs-lookup"><span data-stu-id="2367f-226">1.0</span></span>        |
| <span data-ttu-id="2367f-227">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="2367f-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="2367f-228">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="2367f-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="2367f-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-229">[C#]</span></span>         | <span data-ttu-id="2367f-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="2367f-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="2367f-231">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="2367f-232">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2367f-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="2367f-233">angular</span><span class="sxs-lookup"><span data-stu-id="2367f-233">angular</span></span>](#spa)                 | <span data-ttu-id="2367f-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-234">[C#]</span></span>         | <span data-ttu-id="2367f-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="2367f-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2367f-236">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-236">2.0</span></span>        |
| <span data-ttu-id="2367f-237">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2367f-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="2367f-238">react</span><span class="sxs-lookup"><span data-stu-id="2367f-238">react</span></span>](#spa)                   | <span data-ttu-id="2367f-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-239">[C#]</span></span>         | <span data-ttu-id="2367f-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="2367f-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2367f-241">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-241">2.0</span></span>        |
| <span data-ttu-id="2367f-242">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2367f-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="2367f-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="2367f-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="2367f-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-244">[C#]</span></span>         | <span data-ttu-id="2367f-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="2367f-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="2367f-246">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-246">2.0</span></span>        |
| <span data-ttu-id="2367f-247">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2367f-247">Razor Class Library</span></span>                          | [<span data-ttu-id="2367f-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="2367f-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="2367f-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-249">[C#]</span></span>         | <span data-ttu-id="2367f-250">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="2367f-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="2367f-251">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-251">2.1</span></span>        |
| <span data-ttu-id="2367f-252">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="2367f-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="2367f-253">webapi</span><span class="sxs-lookup"><span data-stu-id="2367f-253">webapi</span></span>](#webapi)               | <span data-ttu-id="2367f-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="2367f-254">[C#], F#</span></span>     | <span data-ttu-id="2367f-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="2367f-255">Web/WebAPI</span></span>                            | <span data-ttu-id="2367f-256">1</span><span class="sxs-lookup"><span data-stu-id="2367f-256">1.0</span></span>        |
| <span data-ttu-id="2367f-257">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="2367f-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="2367f-258">grpc</span><span class="sxs-lookup"><span data-stu-id="2367f-258">grpc</span></span>](#web-others)             | <span data-ttu-id="2367f-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="2367f-259">[C#]</span></span>         | <span data-ttu-id="2367f-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="2367f-260">Web/gRPC</span></span>                              | <span data-ttu-id="2367f-261">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-261">3.0</span></span>        |
| <span data-ttu-id="2367f-262">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="2367f-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="2367f-263">構成</span><span class="sxs-lookup"><span data-stu-id="2367f-263">Config</span></span>                                | <span data-ttu-id="2367f-264">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-264">3.0</span></span>        |
| <span data-ttu-id="2367f-265">global.json file</span><span class="sxs-lookup"><span data-stu-id="2367f-265">global.json file</span></span>                             | [<span data-ttu-id="2367f-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="2367f-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="2367f-267">構成</span><span class="sxs-lookup"><span data-stu-id="2367f-267">Config</span></span>                                | <span data-ttu-id="2367f-268">2.0</span><span class="sxs-lookup"><span data-stu-id="2367f-268">2.0</span></span>        |
| <span data-ttu-id="2367f-269">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="2367f-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="2367f-270">構成</span><span class="sxs-lookup"><span data-stu-id="2367f-270">Config</span></span>                                | <span data-ttu-id="2367f-271">1</span><span class="sxs-lookup"><span data-stu-id="2367f-271">1.0</span></span>        |
| <span data-ttu-id="2367f-272">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="2367f-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="2367f-273">構成</span><span class="sxs-lookup"><span data-stu-id="2367f-273">Config</span></span>                                | <span data-ttu-id="2367f-274">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-274">3.0</span></span>        |
| <span data-ttu-id="2367f-275">Web 構成</span><span class="sxs-lookup"><span data-stu-id="2367f-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="2367f-276">構成</span><span class="sxs-lookup"><span data-stu-id="2367f-276">Config</span></span>                                | <span data-ttu-id="2367f-277">1</span><span class="sxs-lookup"><span data-stu-id="2367f-277">1.0</span></span>        |
| <span data-ttu-id="2367f-278">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="2367f-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="2367f-279">ソリューション</span><span class="sxs-lookup"><span data-stu-id="2367f-279">Solution</span></span>                              | <span data-ttu-id="2367f-280">1</span><span class="sxs-lookup"><span data-stu-id="2367f-280">1.0</span></span>        |
| <span data-ttu-id="2367f-281">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="2367f-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="2367f-282">proto</span><span class="sxs-lookup"><span data-stu-id="2367f-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="2367f-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="2367f-283">Web/gRPC</span></span>                              | <span data-ttu-id="2367f-284">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="2367f-285">オプション</span><span class="sxs-lookup"><span data-stu-id="2367f-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="2367f-286">指定されたコマンドが実行されてテンプレートが作成された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="2367f-287">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="2367f-288">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="2367f-289">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="2367f-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2367f-290">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="2367f-290">Prints out help for the command.</span></span> <span data-ttu-id="2367f-291">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2367f-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="2367f-292">たとえば、`dotnet new mvc --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="2367f-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="2367f-293">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2367f-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="2367f-294">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2367f-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="2367f-295">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="2367f-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="2367f-296">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2367f-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="2367f-297">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="2367f-298">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2367f-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="2367f-299">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2367f-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="2367f-300">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="2367f-301">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="2367f-301">The language of the template to create.</span></span> <span data-ttu-id="2367f-302">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="2367f-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="2367f-303">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="2367f-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2367f-304">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="2367f-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="2367f-305">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2367f-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="2367f-306">たとえば、`dotnet new console -lang "F#"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="2367f-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="2367f-307">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="2367f-307">The name for the created output.</span></span> <span data-ttu-id="2367f-308">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="2367f-309">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="2367f-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="2367f-310">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2367f-311">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="2367f-311">Location to place the generated output.</span></span> <span data-ttu-id="2367f-312">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="2367f-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="2367f-313">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2367f-313">Filters templates based on available types.</span></span> <span data-ttu-id="2367f-314">事前定義されている値は `project`、`item`、`other` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="2367f-315">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2367f-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="2367f-316">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="2367f-317">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="2367f-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="2367f-318">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2367f-319">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2367f-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="2367f-320">たとえば、*C:/Users/\<ユーザー>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2367f-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="2367f-321">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="2367f-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="2367f-322">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2367f-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="2367f-323">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="2367f-324">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="2367f-325">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="2367f-326">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="2367f-326">Template options</span></span>

<span data-ttu-id="2367f-327">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2367f-327">Each project template may have additional options available.</span></span> <span data-ttu-id="2367f-328">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="2367f-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="2367f-329">コンソール</span><span class="sxs-lookup"><span data-stu-id="2367f-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-330">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-331">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2367f-332">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-333">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-333">SDK version</span></span> | <span data-ttu-id="2367f-334">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-335">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-336">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2367f-337">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2367f-338">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="2367f-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="2367f-339">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2367f-339">Not supported for F#.</span></span> <span data-ttu-id="2367f-340">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-341">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2367f-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-342">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="2367f-343">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="2367f-344">classlib</span><span class="sxs-lookup"><span data-stu-id="2367f-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-345">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-346">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="2367f-347">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2367f-348">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2367f-349">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="2367f-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="2367f-350">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2367f-350">Not supported for F#.</span></span> <span data-ttu-id="2367f-351">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-352">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2367f-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-353">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="2367f-354">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="2367f-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-355">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-356">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="2367f-357">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2367f-358">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2367f-359">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="2367f-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="2367f-360">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2367f-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-361">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="2367f-362">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="2367f-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="2367f-363">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="2367f-364">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="2367f-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="2367f-365">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2367f-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-366">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="2367f-367">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="2367f-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-368">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-369">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="2367f-370">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-371">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-372">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="2367f-373">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="2367f-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-374">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-375">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="2367f-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2367f-376">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-377">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-377">SDK version</span></span> | <span data-ttu-id="2367f-378">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-379">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-380">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="2367f-381">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-382">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="2367f-383">nunit</span><span class="sxs-lookup"><span data-stu-id="2367f-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-384">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="2367f-385">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-386">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-386">SDK version</span></span> | <span data-ttu-id="2367f-387">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-388">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-389">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2367f-390">2.2</span><span class="sxs-lookup"><span data-stu-id="2367f-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="2367f-391">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="2367f-392">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-393">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="2367f-394">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="2367f-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="2367f-395">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="2367f-395">Namespace for the generated code.</span></span> <span data-ttu-id="2367f-396">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="2367f-397">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="2367f-398">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="2367f-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="2367f-399">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="2367f-399">Namespace for the generated code.</span></span> <span data-ttu-id="2367f-400">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="2367f-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="2367f-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="2367f-402">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="2367f-402">The type of authentication to use.</span></span> <span data-ttu-id="2367f-403">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-403">The possible values are:</span></span>

  - <span data-ttu-id="2367f-404">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="2367f-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2367f-405">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="2367f-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="2367f-406">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2367f-407">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2367f-408">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="2367f-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="2367f-409">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2367f-410">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="2367f-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2367f-411">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-412">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2367f-413">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2367f-414">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="2367f-415">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="2367f-416">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="2367f-417">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="2367f-418">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2367f-419">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="2367f-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2367f-420">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="2367f-421">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2367f-422">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-422">The Client ID for this project.</span></span> <span data-ttu-id="2367f-423">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="2367f-424">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2367f-425">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="2367f-425">The domain for the directory tenant.</span></span> <span data-ttu-id="2367f-426">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-427">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2367f-428">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2367f-429">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-430">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="2367f-431">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="2367f-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="2367f-432">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-433">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2367f-434">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2367f-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2367f-435">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-436">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-437">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-437">Turns off HTTPS.</span></span> <span data-ttu-id="2367f-438">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2367f-439">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2367f-440">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-441">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="2367f-442">Web</span><span class="sxs-lookup"><span data-stu-id="2367f-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-443">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-444">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-445">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2367f-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-446">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-447">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-447">SDK version</span></span> | <span data-ttu-id="2367f-448">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-449">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-450">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2367f-451">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="2367f-452">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-453">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="2367f-454">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="2367f-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="2367f-455">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="2367f-455">The type of authentication to use.</span></span> <span data-ttu-id="2367f-456">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-456">The possible values are:</span></span>

  - <span data-ttu-id="2367f-457">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="2367f-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2367f-458">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="2367f-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="2367f-459">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2367f-460">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2367f-461">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="2367f-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="2367f-462">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2367f-463">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="2367f-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2367f-464">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-465">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2367f-466">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2367f-467">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="2367f-468">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="2367f-469">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="2367f-470">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="2367f-471">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2367f-472">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="2367f-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2367f-473">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="2367f-474">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2367f-475">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-475">The Client ID for this project.</span></span> <span data-ttu-id="2367f-476">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="2367f-477">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2367f-478">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="2367f-478">The domain for the directory tenant.</span></span> <span data-ttu-id="2367f-479">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-480">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2367f-481">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2367f-482">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-483">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="2367f-484">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="2367f-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="2367f-485">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-486">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2367f-487">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2367f-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2367f-488">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-489">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-490">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-490">Turns off HTTPS.</span></span> <span data-ttu-id="2367f-491">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2367f-492">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2367f-493">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-494">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-495">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="2367f-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="2367f-496">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-497">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-497">SDK version</span></span> | <span data-ttu-id="2367f-498">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-499">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-500">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="2367f-501">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="2367f-502">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="2367f-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="2367f-503">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2367f-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="2367f-504">デバッグ ビルドで [Razor ランタイム コンパイル](/aspnet/core/mvc/views/view-compilation#runtime-compilation)を使用するようにプロジェクトが構成されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2367f-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="2367f-505">.NET Core 3.1.201 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="2367f-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="2367f-506">angular、react</span><span class="sxs-lookup"><span data-stu-id="2367f-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="2367f-507">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="2367f-507">The type of authentication to use.</span></span> <span data-ttu-id="2367f-508">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="2367f-509">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-509">The possible values are:</span></span>

  - <span data-ttu-id="2367f-510">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="2367f-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2367f-511">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="2367f-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-512">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-513">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-514">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-514">Turns off HTTPS.</span></span> <span data-ttu-id="2367f-515">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2367f-516">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2367f-517">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-518">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-519">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-520">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2367f-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-521">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-522">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-522">SDK version</span></span> | <span data-ttu-id="2367f-523">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-524">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-525">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2367f-526">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="2367f-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="2367f-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-528">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-529">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-530">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2367f-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-531">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-532">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-532">SDK version</span></span> | <span data-ttu-id="2367f-533">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-534">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-535">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2367f-536">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="2367f-537">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-538">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="2367f-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="2367f-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="2367f-540">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="2367f-541">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2367f-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="2367f-542">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="2367f-543">webapi</span><span class="sxs-lookup"><span data-stu-id="2367f-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="2367f-544">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="2367f-544">The type of authentication to use.</span></span> <span data-ttu-id="2367f-545">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2367f-545">The possible values are:</span></span>

  - <span data-ttu-id="2367f-546">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="2367f-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="2367f-547">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="2367f-548">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="2367f-549">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="2367f-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="2367f-550">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="2367f-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="2367f-551">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="2367f-552">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="2367f-553">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="2367f-554">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="2367f-555">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="2367f-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="2367f-556">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-557">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="2367f-558">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-558">The Client ID for this project.</span></span> <span data-ttu-id="2367f-559">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-560">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="2367f-561">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="2367f-561">The domain for the directory tenant.</span></span> <span data-ttu-id="2367f-562">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-563">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="2367f-564">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="2367f-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="2367f-565">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="2367f-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="2367f-566">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="2367f-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="2367f-567">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="2367f-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="2367f-568">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="2367f-569">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="2367f-570">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2367f-570">Turns off HTTPS.</span></span> <span data-ttu-id="2367f-571">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="2367f-572">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="2367f-573">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="2367f-574">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2367f-575">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="2367f-576">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="2367f-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="2367f-577">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="2367f-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="2367f-578">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="2367f-578">SDK version</span></span> | <span data-ttu-id="2367f-579">既定値</span><span class="sxs-lookup"><span data-stu-id="2367f-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="2367f-580">3.1</span><span class="sxs-lookup"><span data-stu-id="2367f-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="2367f-581">3.0</span><span class="sxs-lookup"><span data-stu-id="2367f-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="2367f-582">2.1</span><span class="sxs-lookup"><span data-stu-id="2367f-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="2367f-583">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="2367f-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="2367f-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="2367f-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="2367f-585">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="2367f-586">使用例</span><span class="sxs-lookup"><span data-stu-id="2367f-586">Examples</span></span>

- <span data-ttu-id="2367f-587">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="2367f-588">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="2367f-589">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="2367f-590">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="2367f-591">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367f-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="2367f-592">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2367f-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="2367f-593">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2367f-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="2367f-594">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="2367f-595">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="2367f-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="2367f-596">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2367f-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="2367f-597">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2367f-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="2367f-598">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2367f-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="2367f-599">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2367f-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="2367f-600">関連項目</span><span class="sxs-lookup"><span data-stu-id="2367f-600">See also</span></span>

- [<span data-ttu-id="2367f-601">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="2367f-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="2367f-602">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="2367f-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="2367f-603">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="2367f-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="2367f-604">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="2367f-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
