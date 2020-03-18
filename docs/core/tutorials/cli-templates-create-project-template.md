---
title: dotnet new 用のプロジェクト テンプレートを作成する
description: dotnet new コマンド用のプロジェクト テンプレートを作成する方法を説明します。
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503533"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="79ebb-103">チュートリアル: プロジェクト テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="79ebb-104">.NET Core では、プロジェクト、ファイル、さらにはリソースを生成するテンプレートを作成して配置することができます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="79ebb-105">このチュートリアルは、`dotnet new` コマンドで使用するテンプレートの作成、インストール、アンインストール方法を説明するシリーズのパート 2 です。</span><span class="sxs-lookup"><span data-stu-id="79ebb-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="79ebb-106">シリーズのこのパートで学習する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79ebb-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="79ebb-107">プロジェクト テンプレートのリソースを作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="79ebb-108">テンプレートの構成フォルダーとファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="79ebb-109">ファイル パスからテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="79ebb-109">Install a template from a file path</span></span>
> * <span data-ttu-id="79ebb-110">項目テンプレートをテストする</span><span class="sxs-lookup"><span data-stu-id="79ebb-110">Test an item template</span></span>
> * <span data-ttu-id="79ebb-111">項目テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="79ebb-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79ebb-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="79ebb-112">Prerequisites</span></span>

* <span data-ttu-id="79ebb-113">このチュートリアル シリーズの[パート 1](cli-templates-create-item-template.md) を完了します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="79ebb-114">ターミナルを開いて _working\templates_ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="79ebb-115">プロジェクト テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-115">Create a project template</span></span>

<span data-ttu-id="79ebb-116">プロジェクト テンプレートを使用すると、ユーザーがコードのワーキング セットを使用して簡単に作業を開始できる、すぐに実行できるプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="79ebb-117">.NET Core には、コンソール アプリケーションやクラス ライブラリなど、いくつかのプロジェクト テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79ebb-117">.NET Core includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="79ebb-118">この例では、C# 8.0 を有効にし、`async main` エントリ ポイントを生成する、新しいコンソール プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-118">In this example, you'll create a new console project that enables C# 8.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="79ebb-119">ターミナルで _working\templates_ フォルダーに移動し、_consoleasync_ という名前の新しいサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="79ebb-120">このサブフォルダーに入り、`dotnet new console` を実行して標準コンソール アプリケーションを生成します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="79ebb-121">このテンプレートによって生成されたファイルを編集して、新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="79ebb-122">Program.cs を変更する</span><span class="sxs-lookup"><span data-stu-id="79ebb-122">Modify Program.cs</span></span>

<span data-ttu-id="79ebb-123">_program.cs_ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="79ebb-124">コンソール プロジェクトでは非同期エントリ ポイントを使用しないので、それを追加しましょう。</span><span class="sxs-lookup"><span data-stu-id="79ebb-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="79ebb-125">コードを次のように変更し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-125">Change your code to the following and save the file.</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="79ebb-126">consoleasync.csproj を変更する</span><span class="sxs-lookup"><span data-stu-id="79ebb-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="79ebb-127">プロジェクトで使用される C# 言語のバージョンをバージョン 8.0 に更新しましょう。</span><span class="sxs-lookup"><span data-stu-id="79ebb-127">Let's update the C# language version the project uses to version 8.0.</span></span> <span data-ttu-id="79ebb-128">_consoleasync.csproj_ ファイルを編集し、`<LangVersion>` 設定を `<PropertyGroup>` ノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="79ebb-129">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="79ebb-129">Build the project</span></span>

<span data-ttu-id="79ebb-130">プロジェクト テンプレートを完成させる前にテストして、正しくコンパイルされ実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span>

<span data-ttu-id="79ebb-131">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-131">In your terminal, run the following command.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="79ebb-132">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-132">You get the following output.</span></span>

```console
Hello World with C# 8.0!
```

<span data-ttu-id="79ebb-133">`dotnet run` の使用によって作成された _obj_ および _bin_ フォルダーは削除できます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-133">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="79ebb-134">これらのファイルを削除すると、テンプレートに関連するファイルのみがテンプレートに含まれ、ビルド アクションの結果として生じたファイルが含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-134">Deleting these files ensures your template only includes the files related to your template and not any files that result of a build action.</span></span>

<span data-ttu-id="79ebb-135">テンプレートのコンテンツを作成したので、テンプレートのルート フォルダーでテンプレートの構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-135">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="79ebb-136">テンプレートの構成を作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-136">Create the template config</span></span>

<span data-ttu-id="79ebb-137">.NET Core では、テンプレートが、テンプレートのルートに存在する特別なフォルダーと構成ファイルによって認識されます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-137">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="79ebb-138">このチュートリアルでは、テンプレート フォルダーは _working\templates\consoleasync_ にあります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-138">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="79ebb-139">テンプレートを作成すると、特別な構成フォルダーを除く、テンプレート フォルダー内のすべてのファイルとフォルダーがテンプレートの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-139">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="79ebb-140">この構成フォルダーの名前は _.template.config_ です。</span><span class="sxs-lookup"><span data-stu-id="79ebb-140">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="79ebb-141">まず、 _.template.config_ という名前の新しいサブフォルダーを作成し、このフォルダーに入ります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-141">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="79ebb-142">次に、_template.json_ という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-142">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="79ebb-143">フォルダー構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-143">Your folder structure should look like this.</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="79ebb-144">お好みのテキスト エディターで _template.json_ を開き、次の json コードを貼り付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-144">Open the _template.json_ with your favorite text editor and paste in the following json code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="79ebb-145">この構成ファイルには、テンプレートのすべての設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-145">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="79ebb-146">`name` や `shortName` などの基本設定を確認できますが、`project` に設定された `tags/type` 値もあります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-146">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="79ebb-147">これにより、テンプレートがプロジェクト テンプレートとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-147">This designates your template as a project template.</span></span> <span data-ttu-id="79ebb-148">作成するテンプレートの種類に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="79ebb-148">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="79ebb-149">`item` および `project` 値は、ユーザーが検索しているテンプレートの種類を簡単にフィルター処理できるように .NET Core で推奨されている一般的な名前です。</span><span class="sxs-lookup"><span data-stu-id="79ebb-149">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="79ebb-150">`classifications` 項目は、`dotnet new` を実行してテンプレートの一覧を取得したときに表示される **tags** 列を表します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-150">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="79ebb-151">ユーザーは分類タグに基づいて検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-151">Users can also search based on classification tags.</span></span> <span data-ttu-id="79ebb-152">json ファイル内の `tags` プロパティと、`classifications` の tags 一覧を混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="79ebb-152">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="79ebb-153">これらは残念ながら同じ名前を付けられてしまった 2 つの異なるものです。</span><span class="sxs-lookup"><span data-stu-id="79ebb-153">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="79ebb-154">*template.json* ファイルの完全スキーマは [JSON Schema Store](http://json.schemastore.org/template) にあります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-154">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="79ebb-155">*template.json* ファイルについて詳しくは、[dotnet テンプレート wiki](https://github.com/dotnet/templating/wiki) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79ebb-155">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="79ebb-156">有効な _.template.config/template.json_ ファイルを用意したので、テンプレートをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="79ebb-156">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="79ebb-157">テンプレートをインストールする前に、テンプレートに含めたくない余分なファイルとフォルダー (_bin_ フォルダーや _obj_ フォルダーなど) を必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="79ebb-157">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="79ebb-158">ターミナルで _consoleasync_ フォルダーに移動し、`dotnet new -i .\` を実行して現在のフォルダーにあるテンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="79ebb-158">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="79ebb-159">Linux または macOS オペレーティング システムを使用している場合は、`dotnet new -i ./` のようにスラッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-159">If you're using a Linux or macOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="79ebb-160">このコマンドにより、インストールされているテンプレートの一覧が出力されます。作成したテンプレートも含まれているはずです。</span><span class="sxs-lookup"><span data-stu-id="79ebb-160">This command outputs the list of templates installed, which should include yours.</span></span>

```dotnetcli
dotnet new -i .\
```

<span data-ttu-id="79ebb-161">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-161">You get output similar to the following.</span></span>

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a><span data-ttu-id="79ebb-162">プロジェクト テンプレートをテストする</span><span class="sxs-lookup"><span data-stu-id="79ebb-162">Test the project template</span></span>

<span data-ttu-id="79ebb-163">項目テンプレートをインストールしたので、テストします。</span><span class="sxs-lookup"><span data-stu-id="79ebb-163">Now that you have an item template installed, test it.</span></span>

1. <span data-ttu-id="79ebb-164">_test_ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-164">Navigate to the _test_ folder</span></span>

1. <span data-ttu-id="79ebb-165">次のコマンドを使用して、新しいコンソール アプリケーションを作成します。これにより、`dotnet run` コマンドを使用して簡単にテストできる作業プロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-165">Create a new console application with the following command which generates a working project you can easily test with the `dotnet run` command.</span></span>

    ```dotnetcli
    dotnet new consoleasync
    ```

    <span data-ttu-id="79ebb-166">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-166">You get the following output.</span></span>

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. <span data-ttu-id="79ebb-167">次のコマンドを使用して、プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-167">Run the project using the following command.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="79ebb-168">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-168">You get the following output.</span></span>

    ```console
    Hello World with C# 8.0!
    ```

<span data-ttu-id="79ebb-169">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="79ebb-169">Congratulations!</span></span> <span data-ttu-id="79ebb-170">.NET Core でプロジェクト テンプレートを作成し、配置しました。</span><span class="sxs-lookup"><span data-stu-id="79ebb-170">You created and deployed a project template with .NET Core.</span></span> <span data-ttu-id="79ebb-171">このチュートリアル シリーズの次のパートの準備として、作成したテンプレートをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="79ebb-172">また、必ず _test_ フォルダーからすべてのファイルを削除してください。</span><span class="sxs-lookup"><span data-stu-id="79ebb-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="79ebb-173">これにより、このチュートリアルの次の主要なセクションの準備が整った状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="79ebb-174">テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="79ebb-174">Uninstall the template</span></span>

<span data-ttu-id="79ebb-175">ファイル パスを使用してテンプレートをインストールしたので、**絶対**ファイル パスを使用してアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ebb-175">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="79ebb-176">`dotnet new -u` コマンドを実行すると、インストールされているテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="79ebb-177">作成したテンプレートは最後に表示されているはずです。</span><span class="sxs-lookup"><span data-stu-id="79ebb-177">Your template should be listed last.</span></span> <span data-ttu-id="79ebb-178">一覧にあるパスを使用して、`dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` コマンドでテンプレートをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="79ebb-178">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="79ebb-179">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="79ebb-179">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

<span data-ttu-id="79ebb-180">テンプレートをアンインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ebb-180">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="79ebb-181">次の手順</span><span class="sxs-lookup"><span data-stu-id="79ebb-181">Next steps</span></span>

<span data-ttu-id="79ebb-182">このチュートリアルでは、プロジェクト テンプレートを作成しました。</span><span class="sxs-lookup"><span data-stu-id="79ebb-182">In this tutorial, you created a project template.</span></span> <span data-ttu-id="79ebb-183">項目テンプレートとプロジェクト テンプレートの両方を使いやすいファイルにパッケージ化する方法については、このチュートリアル シリーズの続きを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ebb-183">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="79ebb-184">テンプレート パックを作成する</span><span class="sxs-lookup"><span data-stu-id="79ebb-184">Create a template pack</span></span>](cli-templates-create-template-pack.md)
