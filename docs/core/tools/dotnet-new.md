---
title: dotnet new コマンド
description: dotnet new コマンドは、指定されたテンプレートに基づいて新しい .NET Core プロジェクトを作成します。
ms.date: 04/10/2020
ms.openlocfilehash: 39301ad95761848b60b45cb5c18ede937f70c32c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283976"
---
# <a name="dotnet-new"></a><span data-ttu-id="d1ef4-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d1ef4-103">dotnet new</span></span>

<span data-ttu-id="d1ef4-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d1ef4-105">名前</span><span class="sxs-lookup"><span data-stu-id="d1ef4-105">Name</span></span>

<span data-ttu-id="d1ef4-106">`dotnet new` - 指定したテンプレートに基づいて、新しいプロジェクト、構成ファイル、またはソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d1ef4-107">構文</span><span class="sxs-lookup"><span data-stu-id="d1ef4-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="d1ef4-108">説明</span><span class="sxs-lookup"><span data-stu-id="d1ef4-108">Description</span></span>

<span data-ttu-id="d1ef4-109">`dotnet new` コマンドは、テンプレートに基づいて、.NET Core プロジェクトまたはその他の成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="d1ef4-110">このコマンドは、[テンプレート エンジン](https://github.com/dotnet/templating)を呼び出し、指定されたテンプレートとオプションに基づいて、ディスク上に成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="d1ef4-111">暗黙的な復元</span><span class="sxs-lookup"><span data-stu-id="d1ef4-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="d1ef4-112">引数</span><span class="sxs-lookup"><span data-stu-id="d1ef4-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="d1ef4-113">コマンドが呼び出されたときにインスタンス化するテンプレート。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d1ef4-114">各テンプレートには、渡すことができるオプションが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d1ef4-115">詳細については、[テンプレートのオプション](#template-options)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="d1ef4-116">`dotnet new --list` または `dotnet new -l` を実行すると、インストールされているすべてのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="d1ef4-117">`TEMPLATE` の値が返されたテーブルの「**テンプレート**」列または「**短い形式の名前**」列のテキストと完全に一致しない場合、それら 2 つの列で部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="d1ef4-118">.NET Core 3.0 SDK 以降では、次の条件で `dotnet new` コマンドを呼び出すと、CLI によって NuGet.org 内のテンプレートが検索されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="d1ef4-119">`dotnet new` の呼び出し時に、CLI でテンプレートの一致を (部分的にも) 検出できない場合。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="d1ef4-120">テンプレートの新しいバージョンが利用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="d1ef4-121">この場合、プロジェクトまたは成果物が作成されますが、更新されたバージョンのテンプレートについて、CLI によって警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="d1ef4-122">次の表は、.NET Core SDK にプレインストールされているテンプレートの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="d1ef4-123">テンプレートの既定の言語は、角かっこで示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="d1ef4-124">短い名前のリンクをクリックすると、特定のテンプレート オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="d1ef4-125">テンプレート</span><span class="sxs-lookup"><span data-stu-id="d1ef4-125">Templates</span></span>                                    | <span data-ttu-id="d1ef4-126">短い名前</span><span class="sxs-lookup"><span data-stu-id="d1ef4-126">Short name</span></span>                      | <span data-ttu-id="d1ef4-127">言語</span><span class="sxs-lookup"><span data-stu-id="d1ef4-127">Language</span></span>     | <span data-ttu-id="d1ef4-128">Tags</span><span class="sxs-lookup"><span data-stu-id="d1ef4-128">Tags</span></span>                                  | <span data-ttu-id="d1ef4-129">導入時期</span><span class="sxs-lookup"><span data-stu-id="d1ef4-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="d1ef4-130">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-130">Console Application</span></span>                          | [<span data-ttu-id="d1ef4-131">console</span><span class="sxs-lookup"><span data-stu-id="d1ef4-131">console</span></span>](#console)             | <span data-ttu-id="d1ef4-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-132">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="d1ef4-133">Common/Console</span></span>                        | <span data-ttu-id="d1ef4-134">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-134">1.0</span></span>        |
| <span data-ttu-id="d1ef4-135">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-135">Class library</span></span>                                | [<span data-ttu-id="d1ef4-136">classlib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-136">classlib</span></span>](#classlib)           | <span data-ttu-id="d1ef4-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-137">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="d1ef4-138">Common/Library</span></span>                        | <span data-ttu-id="d1ef4-139">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-139">1.0</span></span>        |
| <span data-ttu-id="d1ef4-140">WPF アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-140">WPF Application</span></span>                              | [<span data-ttu-id="d1ef4-141">wpf</span><span class="sxs-lookup"><span data-stu-id="d1ef4-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="d1ef4-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-142">[C#]</span></span>         | <span data-ttu-id="d1ef4-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="d1ef4-143">Common/WPF</span></span>                            | <span data-ttu-id="d1ef4-144">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-144">3.0</span></span>        |
| <span data-ttu-id="d1ef4-145">WPF クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-145">WPF Class library</span></span>                            | [<span data-ttu-id="d1ef4-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="d1ef4-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-147">[C#]</span></span>         | <span data-ttu-id="d1ef4-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="d1ef4-148">Common/WPF</span></span>                            | <span data-ttu-id="d1ef4-149">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-149">3.0</span></span>        |
| <span data-ttu-id="d1ef4-150">WPF カスタム コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="d1ef4-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="d1ef4-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-152">[C#]</span></span>         | <span data-ttu-id="d1ef4-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="d1ef4-153">Common/WPF</span></span>                            | <span data-ttu-id="d1ef4-154">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-154">3.0</span></span>        |
| <span data-ttu-id="d1ef4-155">WPF ユーザー コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="d1ef4-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="d1ef4-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-157">[C#]</span></span>         | <span data-ttu-id="d1ef4-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="d1ef4-158">Common/WPF</span></span>                            | <span data-ttu-id="d1ef4-159">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-159">3.0</span></span>        |
| <span data-ttu-id="d1ef4-160">Windows フォーム (WinForms) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="d1ef4-161">winforms</span><span class="sxs-lookup"><span data-stu-id="d1ef4-161">winforms</span></span>](#winforms)           | <span data-ttu-id="d1ef4-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-162">[C#]</span></span>         | <span data-ttu-id="d1ef4-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="d1ef4-163">Common/WinForms</span></span>                       | <span data-ttu-id="d1ef4-164">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-164">3.0</span></span>        |
| <span data-ttu-id="d1ef4-165">Windows フォーム (WinForms) クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="d1ef4-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="d1ef4-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-167">[C#]</span></span>         | <span data-ttu-id="d1ef4-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="d1ef4-168">Common/WinForms</span></span>                       | <span data-ttu-id="d1ef4-169">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-169">3.0</span></span>        |
| <span data-ttu-id="d1ef4-170">Worker Service</span><span class="sxs-lookup"><span data-stu-id="d1ef4-170">Worker Service</span></span>                               | [<span data-ttu-id="d1ef4-171">worker</span><span class="sxs-lookup"><span data-stu-id="d1ef4-171">worker</span></span>](#web-others)           | <span data-ttu-id="d1ef4-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-172">[C#]</span></span>         | <span data-ttu-id="d1ef4-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="d1ef4-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="d1ef4-174">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-174">3.0</span></span>        |
| <span data-ttu-id="d1ef4-175">単体テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d1ef4-175">Unit Test Project</span></span>                            | [<span data-ttu-id="d1ef4-176">mstest</span><span class="sxs-lookup"><span data-stu-id="d1ef4-176">mstest</span></span>](#test)                 | <span data-ttu-id="d1ef4-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-177">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="d1ef4-178">Test/MSTest</span></span>                           | <span data-ttu-id="d1ef4-179">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-179">1.0</span></span>        |
| <span data-ttu-id="d1ef4-180">NUnit 3 テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d1ef4-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="d1ef4-181">nunit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="d1ef4-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-182">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-183">Test/NUnit</span></span>                            | <span data-ttu-id="d1ef4-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="d1ef4-184">2.1.400</span></span>    |
| <span data-ttu-id="d1ef4-185">NUnit 3 テスト項目</span><span class="sxs-lookup"><span data-stu-id="d1ef4-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="d1ef4-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-186">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-187">Test/NUnit</span></span>                            | <span data-ttu-id="d1ef4-188">2.2</span><span class="sxs-lookup"><span data-stu-id="d1ef4-188">2.2</span></span>        |
| <span data-ttu-id="d1ef4-189">xUnit テスト プロジェクト</span><span class="sxs-lookup"><span data-stu-id="d1ef4-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="d1ef4-190">xunit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-190">xunit</span></span>](#test)                  | <span data-ttu-id="d1ef4-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d1ef4-191">[C#], F#, VB</span></span> | <span data-ttu-id="d1ef4-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-192">Test/xUnit</span></span>                            | <span data-ttu-id="d1ef4-193">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-193">1.0</span></span>        |
| <span data-ttu-id="d1ef4-194">Razor コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d1ef4-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="d1ef4-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-195">[C#]</span></span>         | <span data-ttu-id="d1ef4-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1ef4-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="d1ef4-197">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-197">3.0</span></span>        |
| <span data-ttu-id="d1ef4-198">Razor ページ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-198">Razor Page</span></span>                                   | [<span data-ttu-id="d1ef4-199">page</span><span class="sxs-lookup"><span data-stu-id="d1ef4-199">page</span></span>](#page)                   | <span data-ttu-id="d1ef4-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-200">[C#]</span></span>         | <span data-ttu-id="d1ef4-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1ef4-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="d1ef4-202">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-202">2.0</span></span>        |
| <span data-ttu-id="d1ef4-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="d1ef4-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="d1ef4-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="d1ef4-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="d1ef4-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-205">[C#]</span></span>         | <span data-ttu-id="d1ef4-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1ef4-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="d1ef4-207">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-207">2.0</span></span>        |
| <span data-ttu-id="d1ef4-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d1ef4-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="d1ef4-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-209">[C#]</span></span>         | <span data-ttu-id="d1ef4-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1ef4-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="d1ef4-211">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-211">2.0</span></span>        |
| <span data-ttu-id="d1ef4-212">Blazor サーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-212">Blazor Server App</span></span>                            | [<span data-ttu-id="d1ef4-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="d1ef4-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="d1ef4-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-214">[C#]</span></span>         | <span data-ttu-id="d1ef4-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="d1ef4-215">Web/Blazor</span></span>                            | <span data-ttu-id="d1ef4-216">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-216">3.0</span></span>        |
| <span data-ttu-id="d1ef4-217">Blazor WebAssembly アプリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="d1ef4-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-218">[C#]</span></span>         | <span data-ttu-id="d1ef4-219">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="d1ef4-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="d1ef4-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="d1ef4-220">3.1.300</span></span>    |
| <span data-ttu-id="d1ef4-221">ASP.NET Core 空</span><span class="sxs-lookup"><span data-stu-id="d1ef4-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="d1ef4-222">web</span><span class="sxs-lookup"><span data-stu-id="d1ef4-222">web</span></span>](#web)                     | <span data-ttu-id="d1ef4-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d1ef4-223">[C#], F#</span></span>     | <span data-ttu-id="d1ef4-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="d1ef4-224">Web/Empty</span></span>                             | <span data-ttu-id="d1ef4-225">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-225">1.0</span></span>        |
| <span data-ttu-id="d1ef4-226">ASP.NET Core Web アプリ (モデル ビュー コントローラー)</span><span class="sxs-lookup"><span data-stu-id="d1ef4-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="d1ef4-227">mvc</span><span class="sxs-lookup"><span data-stu-id="d1ef4-227">mvc</span></span>](#web-options)             | <span data-ttu-id="d1ef4-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d1ef4-228">[C#], F#</span></span>     | <span data-ttu-id="d1ef4-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="d1ef4-229">Web/MVC</span></span>                               | <span data-ttu-id="d1ef4-230">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-230">1.0</span></span>        |
| <span data-ttu-id="d1ef4-231">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="d1ef4-232">webapp、razor</span><span class="sxs-lookup"><span data-stu-id="d1ef4-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="d1ef4-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-233">[C#]</span></span>         | <span data-ttu-id="d1ef4-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="d1ef4-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="d1ef4-235">2.2、2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="d1ef4-236">Angular 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d1ef4-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="d1ef4-237">angular</span><span class="sxs-lookup"><span data-stu-id="d1ef4-237">angular</span></span>](#spa)                 | <span data-ttu-id="d1ef4-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-238">[C#]</span></span>         | <span data-ttu-id="d1ef4-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="d1ef4-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d1ef4-240">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-240">2.0</span></span>        |
| <span data-ttu-id="d1ef4-241">React.js 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d1ef4-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="d1ef4-242">react</span><span class="sxs-lookup"><span data-stu-id="d1ef4-242">react</span></span>](#spa)                   | <span data-ttu-id="d1ef4-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-243">[C#]</span></span>         | <span data-ttu-id="d1ef4-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="d1ef4-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d1ef4-245">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-245">2.0</span></span>        |
| <span data-ttu-id="d1ef4-246">React.js および Redux 付きの ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d1ef4-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="d1ef4-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="d1ef4-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="d1ef4-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-248">[C#]</span></span>         | <span data-ttu-id="d1ef4-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="d1ef4-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="d1ef4-250">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-250">2.0</span></span>        |
| <span data-ttu-id="d1ef4-251">Razor クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-251">Razor Class Library</span></span>                          | [<span data-ttu-id="d1ef4-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="d1ef4-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-253">[C#]</span></span>         | <span data-ttu-id="d1ef4-254">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="d1ef4-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="d1ef4-255">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-255">2.1</span></span>        |
| <span data-ttu-id="d1ef4-256">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="d1ef4-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="d1ef4-257">webapi</span><span class="sxs-lookup"><span data-stu-id="d1ef4-257">webapi</span></span>](#webapi)               | <span data-ttu-id="d1ef4-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d1ef4-258">[C#], F#</span></span>     | <span data-ttu-id="d1ef4-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="d1ef4-259">Web/WebAPI</span></span>                            | <span data-ttu-id="d1ef4-260">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-260">1.0</span></span>        |
| <span data-ttu-id="d1ef4-261">ASP.NET Core gRPC サービス</span><span class="sxs-lookup"><span data-stu-id="d1ef4-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="d1ef4-262">grpc</span><span class="sxs-lookup"><span data-stu-id="d1ef4-262">grpc</span></span>](#web-others)             | <span data-ttu-id="d1ef4-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="d1ef4-263">[C#]</span></span>         | <span data-ttu-id="d1ef4-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="d1ef4-264">Web/gRPC</span></span>                              | <span data-ttu-id="d1ef4-265">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-265">3.0</span></span>        |
| <span data-ttu-id="d1ef4-266">dotnet gitignore ファイル</span><span class="sxs-lookup"><span data-stu-id="d1ef4-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="d1ef4-267">構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-267">Config</span></span>                                | <span data-ttu-id="d1ef4-268">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-268">3.0</span></span>        |
| <span data-ttu-id="d1ef4-269">global.json file</span><span class="sxs-lookup"><span data-stu-id="d1ef4-269">global.json file</span></span>                             | [<span data-ttu-id="d1ef4-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="d1ef4-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="d1ef4-271">構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-271">Config</span></span>                                | <span data-ttu-id="d1ef4-272">2.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-272">2.0</span></span>        |
| <span data-ttu-id="d1ef4-273">NuGet 構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="d1ef4-274">構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-274">Config</span></span>                                | <span data-ttu-id="d1ef4-275">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-275">1.0</span></span>        |
| <span data-ttu-id="d1ef4-276">dotnet ローカル ツール マニフェスト ファイル</span><span class="sxs-lookup"><span data-stu-id="d1ef4-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="d1ef4-277">構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-277">Config</span></span>                                | <span data-ttu-id="d1ef4-278">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-278">3.0</span></span>        |
| <span data-ttu-id="d1ef4-279">Web 構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="d1ef4-280">構成</span><span class="sxs-lookup"><span data-stu-id="d1ef4-280">Config</span></span>                                | <span data-ttu-id="d1ef4-281">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-281">1.0</span></span>        |
| <span data-ttu-id="d1ef4-282">ソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="d1ef4-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="d1ef4-283">ソリューション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-283">Solution</span></span>                              | <span data-ttu-id="d1ef4-284">1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-284">1.0</span></span>        |
| <span data-ttu-id="d1ef4-285">プロトコル バッファー ファイル</span><span class="sxs-lookup"><span data-stu-id="d1ef4-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="d1ef4-286">proto</span><span class="sxs-lookup"><span data-stu-id="d1ef4-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="d1ef4-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="d1ef4-287">Web/gRPC</span></span>                              | <span data-ttu-id="d1ef4-288">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="d1ef4-289">オプション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="d1ef4-290">指定されたコマンドが実行されてテンプレートが作成された場合に起きることの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="d1ef4-291">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="d1ef4-292">既存のファイルを変更する場合でも、コンテンツが強制的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d1ef4-293">これは、選択されたテンプレートによって出力ディレクトリ内の既存のファイルがオーバーライドされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d1ef4-294">コマンドのヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-294">Prints out help for the command.</span></span> <span data-ttu-id="d1ef4-295">`dotnet new` コマンド自体、または任意のテンプレートに対して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="d1ef4-296">たとえば、`dotnet new mvc --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="d1ef4-297">指定された `PATH` または `NUGET_ID` からテンプレート パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d1ef4-298">テンプレート パッケージのプレリリース版をインストールする場合は、`<package-name>::<package-version>` の形式でバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="d1ef4-299">既定では、`dotnet new` は、バージョンに対して \* を渡します。これは最後の安定したパッケージのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="d1ef4-300">「[使用例](#examples)」のセクションで、例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="d1ef4-301">このコマンドの実行時にテンプレートのバージョンが既にインストールされていたら、テンプレートは指定されたバージョンか、最新の安定したバージョン (バージョンが指定されていない場合) に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="d1ef4-302">カスタム テンプレートの作成方法については、[「dotnet new のカスタム テンプレート」](custom-templates.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="d1ef4-303">指定した名前を含むテンプレートを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="d1ef4-304">名前が指定されていない場合、すべてのテンプレートが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="d1ef4-305">作成するテンプレートの言語。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-305">The language of the template to create.</span></span> <span data-ttu-id="d1ef4-306">使用できる言語は、テンプレートによって異なります ([引数](#arguments)の既定値を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d1ef4-307">一部のテンプレートでは無効です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d1ef4-308">一部のシェルは `#` を特殊文字として解釈します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="d1ef4-309">そのような場合は、言語パラメーター値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="d1ef4-310">たとえば、`dotnet new console -lang "F#"` のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="d1ef4-311">作成される出力の名前です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-311">The name for the created output.</span></span> <span data-ttu-id="d1ef4-312">名前が指定されていない場合、現在のディレクトリの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="d1ef4-313">インストール中に使用する NuGet ソースを 1 つ指定します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="d1ef4-314">.NET Core 2.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="d1ef4-315">生成された出力を配置する場所。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-315">Location to place the generated output.</span></span> <span data-ttu-id="d1ef4-316">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="d1ef4-317">使用可能な種類に基づいて、テンプレートをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-317">Filters templates based on available types.</span></span> <span data-ttu-id="d1ef4-318">事前定義されている値は `project`、`item`、`other` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="d1ef4-319">指定された `PATH` または `NUGET_ID` でテンプレート パックがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d1ef4-320">`<PATH|NUGET_ID>` 値が指定されないと、現在インストールされているすべてのテンプレート パックとそれらに関連付けられているテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="d1ef4-321">`NUGET_ID` を指定した場合、バージョン番号は含めないでください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="d1ef4-322">このオプションにパラメーターを指定しないと、コマンドによって、インストールされたテンプレートとそれらに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d1ef4-323">`PATH` を使用してテンプレートをアンインストールするには、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d1ef4-324">たとえば、*C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* は有効ですが、 *./GarciaSoftware.ConsoleTemplate.CSharp* が含まれるフォルダーから、そのパスを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="d1ef4-325">テンプレートのパスの最後にある終端ディレクトリのスラッシュは含めないでください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="d1ef4-326">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認され、それらがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="d1ef4-327">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="d1ef4-328">現在インストールされているテンプレート パックに利用できる更新プログラムがあるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="d1ef4-329">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="d1ef4-330">テンプレート オプション</span><span class="sxs-lookup"><span data-stu-id="d1ef4-330">Template options</span></span>

<span data-ttu-id="d1ef4-331">プロジェクト テンプレートはそれぞれ、追加のオプションが与えられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-331">Each project template may have additional options available.</span></span> <span data-ttu-id="d1ef4-332">コア テンプレートの場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="d1ef4-333">コンソール</span><span class="sxs-lookup"><span data-stu-id="d1ef4-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-334">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-335">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d1ef4-336">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-337">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-337">SDK version</span></span> | <span data-ttu-id="d1ef4-338">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-339">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-340">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d1ef4-341">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d1ef4-342">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="d1ef4-343">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-343">Not supported for F#.</span></span> <span data-ttu-id="d1ef4-344">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-345">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-346">指定した場合、プロジェクトの作成中には暗黙的な復元が実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="d1ef4-347">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="d1ef4-348">classlib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-349">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-350">値: .NET Core クラス ライブラリを作成するには `netcoreapp<version>`、.NET 標準クラス ライブラリを作成するには `netstandard<version>` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d1ef4-351">既定値は `netstandard2.0` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d1ef4-352">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d1ef4-353">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="d1ef4-354">F# に対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-354">Not supported for F#.</span></span> <span data-ttu-id="d1ef4-355">.NET Core 2.2 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-356">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-357">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="d1ef4-358">wpf、wpflib、wpfcustomcontrollib、wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-359">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-360">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="d1ef4-361">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d1ef4-362">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d1ef4-363">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="d1ef4-364">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-365">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="d1ef4-366">winforms、winformslib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="d1ef4-367">作成されたプロジェクト ファイルの `LangVersion` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="d1ef4-368">たとえば、C# 7.3 を使うには `--langVersion 7.3` を使います。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="d1ef4-369">既定の C# バージョンの一覧については、「[既定値](../../csharp/language-reference/configure-language-version.md#defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-370">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="d1ef4-371">worker、grpc</span><span class="sxs-lookup"><span data-stu-id="d1ef4-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-372">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-373">既定値は `netcoreapp3.1` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="d1ef4-374">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-375">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-376">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="d1ef4-377">mstest、xunit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-378">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-379">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d1ef4-380">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-381">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-381">SDK version</span></span> | <span data-ttu-id="d1ef4-382">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-383">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-384">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="d1ef4-385">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-386">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="d1ef4-387">nunit</span><span class="sxs-lookup"><span data-stu-id="d1ef4-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-388">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="d1ef4-389">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-390">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-390">SDK version</span></span> | <span data-ttu-id="d1ef4-391">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-392">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-393">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d1ef4-394">2.2</span><span class="sxs-lookup"><span data-stu-id="d1ef4-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="d1ef4-395">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="d1ef4-396">[dotnet pack](dotnet-pack.md) を使用してプロジェクトのパッケージ化が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-397">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="d1ef4-398">ページ (page)</span><span class="sxs-lookup"><span data-stu-id="d1ef4-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="d1ef4-399">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-399">Namespace for the generated code.</span></span> <span data-ttu-id="d1ef4-400">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="d1ef4-401">PageModel なしでページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="d1ef4-402">viewimports、proto</span><span class="sxs-lookup"><span data-stu-id="d1ef4-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="d1ef4-403">生成されるコードの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-403">Namespace for the generated code.</span></span> <span data-ttu-id="d1ef4-404">既定値は `MyApp.Namespace` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="d1ef4-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="d1ef4-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d1ef4-406">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-406">The type of authentication to use.</span></span> <span data-ttu-id="d1ef4-407">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-407">The possible values are:</span></span>

  - <span data-ttu-id="d1ef4-408">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d1ef4-409">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="d1ef4-410">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d1ef4-411">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d1ef4-412">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="d1ef4-413">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-414">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d1ef4-415">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-416">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d1ef4-417">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d1ef4-418">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="d1ef4-419">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="d1ef4-420">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="d1ef4-421">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="d1ef4-422">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-423">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d1ef4-424">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d1ef4-425">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d1ef4-426">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-426">The Client ID for this project.</span></span> <span data-ttu-id="d1ef4-427">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d1ef4-428">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d1ef4-429">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-429">The domain for the directory tenant.</span></span> <span data-ttu-id="d1ef4-430">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-431">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d1ef4-432">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d1ef4-433">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-434">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="d1ef4-435">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d1ef4-436">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-437">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d1ef4-438">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d1ef4-439">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-440">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-441">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-441">Turns off HTTPS.</span></span> <span data-ttu-id="d1ef4-442">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が `--auth` 用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d1ef4-443">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d1ef4-444">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-445">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="d1ef4-446">Web</span><span class="sxs-lookup"><span data-stu-id="d1ef4-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-447">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-448">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-449">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-450">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-451">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-451">SDK version</span></span> | <span data-ttu-id="d1ef4-452">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-453">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-454">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d1ef4-455">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="d1ef4-456">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-457">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="d1ef4-458">mvc、webapp</span><span class="sxs-lookup"><span data-stu-id="d1ef4-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d1ef4-459">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-459">The type of authentication to use.</span></span> <span data-ttu-id="d1ef4-460">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-460">The possible values are:</span></span>

  - <span data-ttu-id="d1ef4-461">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d1ef4-462">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="d1ef4-463">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d1ef4-464">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d1ef4-465">`MultiOrg` - 複数のテナントに対する組織認証です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="d1ef4-466">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-467">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d1ef4-468">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-469">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d1ef4-470">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d1ef4-471">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="d1ef4-472">このプロジェクトのリセット パスワード ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="d1ef4-473">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="d1ef4-474">このプロジェクトの編集プロファイル ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="d1ef4-475">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-476">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d1ef4-477">`SingleOrg` 認証または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d1ef4-478">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d1ef4-479">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-479">The Client ID for this project.</span></span> <span data-ttu-id="d1ef4-480">`IndividualB2C` 認証、`SingleOrg` 認証、または `MultiOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d1ef4-481">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d1ef4-482">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-482">The domain for the directory tenant.</span></span> <span data-ttu-id="d1ef4-483">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-484">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d1ef4-485">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d1ef4-486">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-487">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="d1ef4-488">リダイレクト URI のアプリケーションの基本パス内の要求パスです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d1ef4-489">`SingleOrg` 認証または `IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-490">既定値は `/signin-oidc` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d1ef4-491">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d1ef4-492">`SingleOrg` 認証または `MultiOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-493">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-494">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-494">Turns off HTTPS.</span></span> <span data-ttu-id="d1ef4-495">このオプションは、`Individual`、`IndividualB2C`、`SingleOrg`、または `MultiOrg` が使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d1ef4-496">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d1ef4-497">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-498">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-499">.NET Core 3.0 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="d1ef4-500">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-501">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-501">SDK version</span></span> | <span data-ttu-id="d1ef4-502">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-503">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-504">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="d1ef4-505">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="d1ef4-506">プロジェクトに BrowserLink を含めます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="d1ef4-507">.NET Core 2.2 および 3.1 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="d1ef4-508">デバッグ ビルドで [Razor ランタイム コンパイル](/aspnet/core/mvc/views/view-compilation#runtime-compilation)を使用するようにプロジェクトが構成されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="d1ef4-509">.NET Core 3.1.201 SDK 以降で利用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="d1ef4-510">angular、react</span><span class="sxs-lookup"><span data-stu-id="d1ef4-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d1ef4-511">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-511">The type of authentication to use.</span></span> <span data-ttu-id="d1ef4-512">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="d1ef4-513">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-513">The possible values are:</span></span>

  - <span data-ttu-id="d1ef4-514">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d1ef4-515">`Individual` - 個別認証です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-516">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-517">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-518">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-518">Turns off HTTPS.</span></span> <span data-ttu-id="d1ef4-519">このオプションは、認証が `None` の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d1ef4-520">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d1ef4-521">`Individual` 認証または `IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-522">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-523">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-524">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-525">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-526">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-526">SDK version</span></span> | <span data-ttu-id="d1ef4-527">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-528">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-529">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d1ef4-530">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="d1ef4-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="d1ef4-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-532">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-533">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-534">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-535">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-536">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-536">SDK version</span></span> | <span data-ttu-id="d1ef4-537">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-538">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-539">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d1ef4-540">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="d1ef4-541">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-542">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="d1ef4-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="d1ef4-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="d1ef4-544">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="d1ef4-545">このライブラリへのコンポーネントに加え、従来の Razor ページとビューの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="d1ef4-546">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="d1ef4-547">webapi</span><span class="sxs-lookup"><span data-stu-id="d1ef4-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="d1ef4-548">使う認証の種類。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-548">The type of authentication to use.</span></span> <span data-ttu-id="d1ef4-549">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-549">The possible values are:</span></span>

  - <span data-ttu-id="d1ef4-550">`None` - 認証は行われません (既定)。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="d1ef4-551">`IndividualB2C` - Azure AD B2C での個別認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="d1ef4-552">`SingleOrg` - 単一のテナントに対する組織認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="d1ef4-553">`Windows` - Windows 認証。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-554">接続先の Azure Active Directory B2C インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d1ef4-555">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d1ef4-556">既定値は `https://login.microsoftonline.com/tfp/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="d1ef4-557">このプロジェクト用のサインインおよびサインアップ ポリシー ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d1ef4-558">`IndividualB2C` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="d1ef4-559">接続先の Azure Active Directory インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d1ef4-560">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-561">既定値は `https://login.microsoftonline.com/` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="d1ef4-562">このプロジェクトのクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-562">The Client ID for this project.</span></span> <span data-ttu-id="d1ef4-563">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-564">既定値は `11111111-1111-1111-11111111111111111` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="d1ef4-565">ディレクトリ テナントのドメインです。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-565">The domain for the directory tenant.</span></span> <span data-ttu-id="d1ef4-566">`IndividualB2C` 認証または `SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-567">既定値は `qualified.domain.name` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="d1ef4-568">接続先のディレクトリの TenantId ID です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d1ef4-569">`SingleOrg` 認証で使用します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d1ef4-570">既定値は `22222222-2222-2222-2222-222222222222` です。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="d1ef4-571">このアプリケーションにディレクトリへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="d1ef4-572">`SingleOrg` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="d1ef4-573">生成されたテンプレートから *launchSettings.json* が除外されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="d1ef4-574">HTTPS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-574">Turns off HTTPS.</span></span> <span data-ttu-id="d1ef4-575">`app.UseHsts` と `app.UseHttpsRedirection` は `Startup.Configure` に追加されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="d1ef4-576">このオプションは、`IndividualB2C` または `SingleOrg` が認証用に使用されない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="d1ef4-577">SQLite ではなく LocalDB が使用されるように指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d1ef4-578">`IndividualB2C` 認証にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d1ef4-579">ターゲットにする[フレームワーク](../../standard/frameworks.md)が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d1ef4-580">.NET Core 2.2 SDK では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="d1ef4-581">次の表は、使用する SDK バージョン番号に対応した既定値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="d1ef4-582">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ef4-582">SDK version</span></span> | <span data-ttu-id="d1ef4-583">既定値</span><span class="sxs-lookup"><span data-stu-id="d1ef4-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="d1ef4-584">3.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="d1ef4-585">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ef4-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="d1ef4-586">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ef4-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="d1ef4-587">プロジェクトの作成中に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="d1ef4-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="d1ef4-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="d1ef4-589">*global.json* ファイル内で使用する .NET Core SDK のバージョンが指定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="d1ef4-590">使用例</span><span class="sxs-lookup"><span data-stu-id="d1ef4-590">Examples</span></span>

- <span data-ttu-id="d1ef4-591">テンプレート名を指定することによって、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="d1ef4-592">現在のディレクトリに、F# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="d1ef4-593">指定されたディレクトリ内に .NET Standard クラス ライブラリ プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="d1ef4-594">認証なしで、現在のディレクトリに新しい ASP.NET Core C# MVC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="d1ef4-595">新しい xUnit プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="d1ef4-596">シングル ページ アプリケーション (SPA) テンプレートに使用できるすべてのテンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="d1ef4-597">部分文字列 *we* に一致するすべてのテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="d1ef4-598">完全一致が見つからないので、短い名前と名前の両方の列に対して部分文字列一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="d1ef4-599">*ng* に一致するテンプレートの呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="d1ef4-600">一致が 1 つだけでない場合、部分的に一致するテンプレートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="d1ef4-601">ASP.NET Core 用の SPA テンプレートのバージョン 2.0 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="d1ef4-602">インストールされているテンプレートとそれらに関する詳細や、それらのアンインストール方法を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="d1ef4-603">現在のディレクトリに *global.json* が作成され、SDK バージョンが 3.1.101 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef4-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="d1ef4-604">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1ef4-604">See also</span></span>

- [<span data-ttu-id="d1ef4-605">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="d1ef4-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="d1ef4-606">dotnet new のカスタム テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="d1ef4-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="d1ef4-607">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="d1ef4-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="d1ef4-608">dotnet new で使用できるテンプレート</span><span class="sxs-lookup"><span data-stu-id="d1ef4-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
