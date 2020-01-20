---
title: dotnet new 用の項目テンプレートを作成する - .NET Core CLI
description: dotnet new コマンド用の項目テンプレートを作成する方法を説明します。 項目テンプレートには、任意の数のファイルを含めることができます。
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: fa0ae18221c33d196960239411f8860a561b20ee
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340378"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="5cb5e-104">チュートリアル: 項目テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="5cb5e-105">.NET Core では、プロジェクト、ファイル、さらにはリソースを生成するテンプレートを作成して配置することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-105">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="5cb5e-106">このチュートリアルは、`dotnet new` コマンドで使用するテンプレートの作成、インストール、アンインストール方法を説明するシリーズのパート 1 です。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="5cb5e-107">シリーズのこのパートで学習する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="5cb5e-108">項目テンプレートのクラスを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-108">Create a class for an item template</span></span>
> * <span data-ttu-id="5cb5e-109">テンプレートの構成フォルダーとファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="5cb5e-110">ファイル パスからテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="5cb5e-110">Install a template from a file path</span></span>
> * <span data-ttu-id="5cb5e-111">項目テンプレートをテストする</span><span class="sxs-lookup"><span data-stu-id="5cb5e-111">Test an item template</span></span>
> * <span data-ttu-id="5cb5e-112">項目テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5cb5e-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5cb5e-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5cb5e-113">Prerequisites</span></span>

* <span data-ttu-id="5cb5e-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
* <span data-ttu-id="5cb5e-115">参照記事「[dotnet new のカスタム テンプレート](../tools/custom-templates.md)」を確認しておきます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="5cb5e-116">この参照記事では、テンプレートの基本と、テンプレートをまとめる方法が説明されています。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="5cb5e-117">ここでは、この情報の一部を繰り返して示します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="5cb5e-118">ターミナルを開いて、_working\templates_ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="5cb5e-119">必要なフォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-119">Create the required folders</span></span>

<span data-ttu-id="5cb5e-120">このシリーズでは、テンプレートのソースが含まれる "作業フォルダー" と、テンプレートをテストするための "テスト フォルダー" を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="5cb5e-121">作業フォルダーとテスト フォルダーは、同じ親フォルダーの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="5cb5e-122">まず、親フォルダーを作成します。名前は何でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="5cb5e-123">次に、_working_ という名前のサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="5cb5e-124">_working_ フォルダー内に、_templates_ という名前のサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="5cb5e-125">次に、親フォルダーの下に _test_ という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="5cb5e-126">フォルダー構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-126">The folder structure should look like the following:</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="5cb5e-127">項目テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-127">Create an item template</span></span>

<span data-ttu-id="5cb5e-128">項目テンプレートは、1 つ以上のファイルを含む特定の種類のテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="5cb5e-129">この種類のテンプレートは、構成、コード、ソリューションなどのファイルを生成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="5cb5e-130">この例では、文字列型に拡張メソッドを追加するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="5cb5e-131">ターミナルで、_working\templates_ フォルダーに移動し、_extensions_ という名前の新しいサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="5cb5e-132">このフォルダーに入ります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="5cb5e-133">_CommonExtensions.cs_ という名前の新しいファイルを作成し、お好みのテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="5cb5e-134">このクラスにより、文字列のコンテンツを反転させる `Reverse` という名前の拡張メソッドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="5cb5e-135">次のコードを貼り付けて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="5cb5e-136">テンプレートのコンテンツを作成したので、テンプレートのルート フォルダーでテンプレートの構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="5cb5e-137">テンプレートの構成を作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-137">Create the template config</span></span>

<span data-ttu-id="5cb5e-138">.NET Core では、テンプレートが、テンプレートのルートに存在する特別なフォルダーと構成ファイルによって認識されます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-138">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="5cb5e-139">このチュートリアルでは、テンプレート フォルダーは _working\templates\extensions_ にあります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="5cb5e-140">テンプレートを作成すると、特別な構成フォルダーを除く、テンプレート フォルダー内のすべてのファイルとフォルダーがテンプレートの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="5cb5e-141">この構成フォルダーの名前は _.template.config_ です。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="5cb5e-142">まず、 _.template.config_ という名前の新しいサブフォルダーを作成し、このフォルダーに入ります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="5cb5e-143">次に、_template.json_ という名前の新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="5cb5e-144">フォルダー構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="5cb5e-145">お好みのテキスト エディターで _template.json_ を開き、次の JSON コードを貼り付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="5cb5e-146">この構成ファイルには、テンプレートのすべての設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="5cb5e-147">`name` や `shortName` などの基本設定を確認できますが、`item` に設定された `tags/type` 値もあります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="5cb5e-148">これにより、テンプレートが項目テンプレートとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="5cb5e-149">作成するテンプレートの種類に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="5cb5e-150">`item` および `project` 値は、ユーザーが検索しているテンプレートの種類を簡単にフィルター処理できるように .NET Core で推奨されている一般的な名前です。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-150">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="5cb5e-151">`classifications` 項目は、`dotnet new` を実行してテンプレートの一覧を取得したときに表示される **tags** 列を表します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="5cb5e-152">ユーザーは分類タグに基づいて検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="5cb5e-153">\*.json ファイル内の `tags` プロパティと、`classifications` の tags 一覧を混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="5cb5e-154">これらは残念ながら同じ名前を付けられてしまった 2 つの異なるものです。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="5cb5e-155">*template.json* ファイルの完全スキーマは [JSON Schema Store](http://json.schemastore.org/template) にあります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="5cb5e-156">*template.json* ファイルについて詳しくは、[dotnet テンプレート wiki](https://github.com/dotnet/templating/wiki) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="5cb5e-157">有効な _.template.config/template.json_ ファイルを用意したので、テンプレートをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="5cb5e-158">ターミナルで _extensions_ フォルダーに移動し、次のコマンドを実行して現在のフォルダーにあるテンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="5cb5e-159">**Windows の場合**: `dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="5cb5e-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="5cb5e-160">**Linux または macOS の場合**: `dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="5cb5e-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="5cb5e-161">このコマンドにより、インストールされているテンプレートの一覧が出力されます。作成したテンプレートも含まれているはずです。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a><span data-ttu-id="5cb5e-162">項目テンプレートをテストする</span><span class="sxs-lookup"><span data-stu-id="5cb5e-162">Test the item template</span></span>

<span data-ttu-id="5cb5e-163">項目テンプレートをインストールしたので、テストします。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="5cb5e-164">_test/_ フォルダーに移動し、`dotnet new console` を使用して新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="5cb5e-165">これにより、`dotnet run` コマンドを使用して簡単にテストできる作業プロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```console
C:\test> dotnet new console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

```console
C:\test> dotnet run
Hello World!
```

<span data-ttu-id="5cb5e-166">次に、`dotnet new stringext` を実行して、テンプレートから _CommonExtensions.cs_ を生成します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-166">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```console
C:\test> dotnet new stringext
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="5cb5e-167">テンプレートによって提供される拡張メソッドを使用して、`"Hello World"` 文字列を反転するように _Program.cs_ 内のコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-167">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="5cb5e-168">プログラムをもう一度実行すると、結果が反転されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-168">Run the program again and you'll see that the result is reversed.</span></span>

```console
C:\test> dotnet run
!dlroW olleH
```

<span data-ttu-id="5cb5e-169">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="5cb5e-169">Congratulations!</span></span> <span data-ttu-id="5cb5e-170">.NET Core で項目テンプレートを作成し、配置しました。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-170">You created and deployed an item template with .NET Core.</span></span> <span data-ttu-id="5cb5e-171">このチュートリアル シリーズの次のパートの準備として、作成したテンプレートをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="5cb5e-172">また、必ず _test_ フォルダーからすべてのファイルを削除してください。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="5cb5e-173">これにより、このチュートリアルの次の主要なセクションの準備が整った状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="5cb5e-174">テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5cb5e-174">Uninstall the template</span></span>

<span data-ttu-id="5cb5e-175">ファイル パスを使用してテンプレートをインストールしたので、**絶対**ファイル パスを使用してアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-175">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="5cb5e-176">`dotnet new -u` コマンドを実行すると、インストールされているテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="5cb5e-177">作成したテンプレートは最後に表示されているはずです。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-177">Your template should be listed last.</span></span> <span data-ttu-id="5cb5e-178">一覧にあるパスを使用して、`dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` コマンドでテンプレートをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-178">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```console
C:\working> dotnet new -u
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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

```console
C:\working> dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="5cb5e-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="5cb5e-179">Next steps</span></span>

<span data-ttu-id="5cb5e-180">このチュートリアルでは、項目テンプレートを作成しました。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-180">In this tutorial, you created an item template.</span></span> <span data-ttu-id="5cb5e-181">プロジェクト テンプレートを作成する方法については、このチュートリアル シリーズの続きを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb5e-181">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5cb5e-182">プロジェクト テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5cb5e-182">Create a project template</span></span>](cli-templates-create-project-template.md)
