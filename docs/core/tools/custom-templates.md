---
title: dotnet new のカスタム テンプレート
description: あらゆる種類の .NET プロジェクトまたはファイルのカスタム テンプレートについて説明します。
author: thraka
ms.date: 06/14/2019
ms.openlocfilehash: 7a599973a1914f0df187557e48718263f16546f3
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117807"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="d5c27-103">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="d5c27-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="d5c27-104">[.NET Core SDK](https://dotnet.microsoft.com/download) には、既にインストールされて使用できる状態になっている多くのテンプレートが付属します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="d5c27-105">[`dotnet new` コマンド](dotnet-new.md)は、テンプレートを使用する手段であるだけでなく、テンプレートをインストールおよびアンインストールする方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="d5c27-106">.NET Core 2.0 以降から、アプリ、サービス、ツール、クラス ライブラリなど、あらゆる種類のプロジェクトを対象に独自のテンプレートを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d5c27-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="d5c27-107">構成ファイルなど、1 つまたは複数の独立ファイルを出力するテンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="d5c27-108">NuGet の *.nupkg* ファイルを直接参照するか、テンプレートが含まれるファイル システム ディレクトリを指定することで、任意の NuGet フィード上の NuGet パッケージからカスタム テンプレートをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="d5c27-109">テンプレート エンジンの機能を利用すると、テンプレートを使うときに、値を置き換えたり、ファイルを含めたり除外したり、独自の処理操作を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="d5c27-110">テンプレート エンジンはオープン ソースです。オンライン コード リポジトリは GitHub の [dotnet/templating](https://github.com/dotnet/templating/) にあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="d5c27-111">テンプレートのサンプルが必要であれば、[dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) リポジトリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-111">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="d5c27-112">GitHub の「[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)」 (dotnet new で利用できるテンプレート) には、サードパーティのテンプレートなど、テンプレートが他にもあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-112">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="d5c27-113">カスタム テンプレートの作成と利用の詳細については、「[dotnet new の独自のテンプレートを作成する方法](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)」と「[dotnet/templating GitHub リポジトリ Wiki](https://github.com/dotnet/templating/wiki)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-113">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="d5c27-114">チュートリアルでテンプレートを作成するには、「[dotnet new のカスタム テンプレートを作成する](../tutorials/create-custom-template.md)」チュートリアルをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-114">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/create-custom-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="d5c27-115">.NET の既定のテンプレート</span><span class="sxs-lookup"><span data-stu-id="d5c27-115">.NET default templates</span></span>

<span data-ttu-id="d5c27-116">[.NET Core SDK](https://dotnet.microsoft.com/download) をインストールすると、コンソール アプリ、クラス ライブラリ、単体テスト プロジェクト、ASP.NET Core アプリ ([Angular](https://angular.io/) プロジェクトと [React](https://facebook.github.io/react/) プロジェクトを含む)、構成ファイルなど、プロジェクトやファイルを作成するための 12 個を超える組み込みテンプレートが与えられます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-116">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="d5c27-117">組み込みテンプレートの一覧を表示するには、`-l|--list` オプションを指定して `dotnet new` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-117">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="d5c27-118">構成</span><span class="sxs-lookup"><span data-stu-id="d5c27-118">Configuration</span></span>

<span data-ttu-id="d5c27-119">テンプレートは次の部分から構成されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-119">A template is composed of the following parts:</span></span>

- <span data-ttu-id="d5c27-120">ソース ファイルとフォルダー。</span><span class="sxs-lookup"><span data-stu-id="d5c27-120">Source files and folders.</span></span>
- <span data-ttu-id="d5c27-121">構成ファイル (*template.json*)。</span><span class="sxs-lookup"><span data-stu-id="d5c27-121">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="d5c27-122">ソース ファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="d5c27-122">Source files and folders</span></span>

<span data-ttu-id="d5c27-123">ソース ファイルとフォルダーには、`dotnet new <TEMPLATE>` コマンドの実行時にテンプレート エンジンで使用されるすべてのファイルとフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-123">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="d5c27-124">テンプレート エンジンは、ソース コードとして*実行可能なプロジェクト*を利用し、プロジェクトを生成するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d5c27-124">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="d5c27-125">これにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-125">This has several benefits:</span></span>

- <span data-ttu-id="d5c27-126">テンプレート エンジンでは、プロジェクトのソース コードに特別なトークンを挿入することを必要としません。</span><span class="sxs-lookup"><span data-stu-id="d5c27-126">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="d5c27-127">コード ファイルは特別なファイルではなく、テンプレート エンジンで利用するために変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d5c27-127">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="d5c27-128">そのため、プロジェクトの利用時に通常利用しているツールでテンプレート コンテンツに対応できます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-128">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="d5c27-129">他のプロジェクトの場合と同じように、テンプレート プロジェクトをビルドし、実行し、デバッグします。</span><span class="sxs-lookup"><span data-stu-id="d5c27-129">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="d5c27-130">*./.template.config/template.json* 構成ファイルをプロジェクトに追加するだけで、既存のプロジェクトからテンプレートを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-130">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="d5c27-131">テンプレートに格納されるファイルやフォルダーは、正式な種類の .NET プロジェクトに限定されません。</span><span class="sxs-lookup"><span data-stu-id="d5c27-131">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="d5c27-132">テンプレート エンジンで出力として生成されるファイルが 1 つだけであっても、ソース ファイルとフォルダーは、テンプレートを使って作成するすべてのコンテンツで構成できます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-132">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="d5c27-133">テンプレートによって生成されるファイルは、*template.json* 構成ファイルで提供するロジックと設定に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-133">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="d5c27-134">ユーザーは、`dotnet new <TEMPLATE>` コマンドにオプションを渡すことによって、これらの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-134">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="d5c27-135">カスタム ロジックの一般的な例は、テンプレートによって展開されるコード ファイル内のクラスや変数に名前を提供する場合です。</span><span class="sxs-lookup"><span data-stu-id="d5c27-135">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="d5c27-136">template.json</span><span class="sxs-lookup"><span data-stu-id="d5c27-136">template.json</span></span>

<span data-ttu-id="d5c27-137">*template.json* ファイルは、テンプレートのルート ディレクトリの *.template.config* フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-137">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="d5c27-138">このファイルは、テンプレート エンジンに構成情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-138">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="d5c27-139">最小構成には、次の表に示すメンバーが必要です。この最小構成があれば、実際に機能するテンプレートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-139">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="d5c27-140">メンバー</span><span class="sxs-lookup"><span data-stu-id="d5c27-140">Member</span></span>            | <span data-ttu-id="d5c27-141">型</span><span class="sxs-lookup"><span data-stu-id="d5c27-141">Type</span></span>          | <span data-ttu-id="d5c27-142">説明</span><span class="sxs-lookup"><span data-stu-id="d5c27-142">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="d5c27-143">URI</span><span class="sxs-lookup"><span data-stu-id="d5c27-143">URI</span></span>           | <span data-ttu-id="d5c27-144">*template.json* ファイルの JSON スキーマ。</span><span class="sxs-lookup"><span data-stu-id="d5c27-144">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="d5c27-145">エディターが JSON スキーマ対応であれば、スキーマの指定時、JSON 編集機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-145">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="d5c27-146">たとえば、[Visual Studio Code](https://code.visualstudio.com/) の場合、IntelliSense を有効にするためにこのメンバーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-146">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="d5c27-147">値として `http://json.schemastore.org/template` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-147">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="d5c27-148">string</span><span class="sxs-lookup"><span data-stu-id="d5c27-148">string</span></span>        | <span data-ttu-id="d5c27-149">テンプレートの作成者。</span><span class="sxs-lookup"><span data-stu-id="d5c27-149">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="d5c27-150">array(string)</span><span class="sxs-lookup"><span data-stu-id="d5c27-150">array(string)</span></span> | <span data-ttu-id="d5c27-151">テンプレートのゼロ以上の特性。ユーザーがこれを利用し、テンプレートを探すことがあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-151">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="d5c27-152">`dotnet new -l|--list` コマンドでテンプレートの一覧を生成したとき、*Tags* 列が表示される場合、この列にも分類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-152">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="d5c27-153">string</span><span class="sxs-lookup"><span data-stu-id="d5c27-153">string</span></span>        | <span data-ttu-id="d5c27-154">このテンプレートの一意の名前。</span><span class="sxs-lookup"><span data-stu-id="d5c27-154">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="d5c27-155">string</span><span class="sxs-lookup"><span data-stu-id="d5c27-155">string</span></span>        | <span data-ttu-id="d5c27-156">ユーザーに対して表示されるテンプレートの名前。</span><span class="sxs-lookup"><span data-stu-id="d5c27-156">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="d5c27-157">string</span><span class="sxs-lookup"><span data-stu-id="d5c27-157">string</span></span>        | <span data-ttu-id="d5c27-158">テンプレートを選択するための既定の省略名。テンプレート名が GUI 経由で選択されるのではなく、ユーザーによって指定される環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-158">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="d5c27-159">たとえば、CLI コマンドでコマンド プロンプトからテンプレートを利用するときに省略名が便利です。</span><span class="sxs-lookup"><span data-stu-id="d5c27-159">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="d5c27-160">*template.json* ファイルの完全スキーマは [JSON Schema Store](http://json.schemastore.org/template) にあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-160">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="d5c27-161">*template.json* ファイルについて詳しくは、[dotnet テンプレート wiki](https://github.com/dotnet/templating/wiki) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-161">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="d5c27-162">例</span><span class="sxs-lookup"><span data-stu-id="d5c27-162">Example</span></span>

<span data-ttu-id="d5c27-163">たとえば、次に示すテンプレート フォルダーには、2 つのコンテンツ ファイル *console.cs* と *readme.txt* が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-163">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="d5c27-164">*template.json* ファイルが含まれる、 *.template.config* という名前の必須フォルダーがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-164">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="d5c27-165">*template.json* ファイルは次のようなものです。</span><span class="sxs-lookup"><span data-stu-id="d5c27-165">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="d5c27-166">*mytemplate* フォルダーは、インストール可能なテンプレート パックです。</span><span class="sxs-lookup"><span data-stu-id="d5c27-166">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="d5c27-167">パックがインストールされたら、`shortName` を `dotnet new` コマンドで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-167">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="d5c27-168">たとえば、`dotnet new adatumconsole` では、`console.cs` および `readme.txt` ファイルが現在のフォルダーに出力されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-168">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="d5c27-169">テンプレートをパッケージ化し、NuGet パッケージ (nupkg ファイル) を作成する</span><span class="sxs-lookup"><span data-stu-id="d5c27-169">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="d5c27-170">カスタム テンプレートは、[dotnet pack](dotnet-pack.md) コマンドと *.csproj* ファイルでパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-170">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="d5c27-171">または、[nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) コマンドと *.nuspec* ファイルで [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-171">Alternatively, [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="d5c27-172">ただし、NuGet の場合、Windows では .NET Framework が、Linux と MacOS では [Mono](https://www.mono-project.com/) が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5c27-172">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and MacOS.</span></span>

<span data-ttu-id="d5c27-173">*.csproj* ファイルは、従来のコード プロジェクトの *.csproj* ファイルと若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-173">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="d5c27-174">次の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-174">Note the following settings:</span></span>

01. <span data-ttu-id="d5c27-175">設定 `<PackageType>` が追加され、`Template` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-175">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="d5c27-176">設定 `<PackageVersion>` が追加され、有効な [NuGet のバージョン番号](/nuget/reference/package-versioning)に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-176">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="d5c27-177">設定 `<PackageId>` が追加され、一意の識別子に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-177">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="d5c27-178">この識別子は、テンプレート パックのアンインストールに使われ、テンプレート パックを登録するために NuGet フィードによって使われます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-178">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="d5c27-179">ジェネリック メタデータの設定 `<Title>`、`<Authors>`、`<Description>`、`<PackageTags>` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-179">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="d5c27-180">テンプレート プロセスによって生成されるバイナリを使わない場合でも、設定 `<TargetFramework>` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-180">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="d5c27-181">次の例では、`netstandard2.0` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d5c27-181">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="d5c27-182">*.nupkg* NuGet パッケージの形式のテンプレート パックでは、すべてのテンプレートをパッケージ内の *content* フォルダーに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-182">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="d5c27-183">生成された *.nupkg* をテンプレート パックとしてインストールできるようにするため、 *.csproj* ファイルに追加する設定がさらにいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-183">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="d5c27-184">プロジェクトで**コンテンツ**として設定されるすべてのファイルを NuGet パッケージに含めるには、設定 `<IncludeContentInPack>` を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-184">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="d5c27-185">コンパイラによって生成されたすべてのバイナリを NuGet パッケージから除外するには、設定 `<IncludeBuildOutput>` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-185">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="d5c27-186">設定 `<ContentTargetFolders>` を `content` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-186">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="d5c27-187">これにより、**コンテンツ**として設定されたファイルは、NuGet パッケージ内の *content* フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-187">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="d5c27-188">NuGet パッケージのこのフォルダーは、dotnet テンプレート システムによって解析されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-188">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="d5c27-189">すべてのコード ファイルをテンプレート プロジェクトによってコンパイルされないように除外する簡単な方法は、プロジェクト ファイルの `<ItemGroup>` 要素内で `<Compile Remove="**\*" />` 項目を使うことです。</span><span class="sxs-lookup"><span data-stu-id="d5c27-189">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="d5c27-190">テンプレート パックを構成する簡単な方法は、すべてのテンプレートを個別のフォルダーに格納した後、 *.csproj* ファイルと同じディレクトリにある *templates* フォルダーの内部に各テンプレート フォルダーを格納することです。</span><span class="sxs-lookup"><span data-stu-id="d5c27-190">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="d5c27-191">これにより、1 つのプロジェクト項目を使って、すべてのファイルとフォルダーを**コンテンツ**として *templates* に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-191">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="d5c27-192">`<ItemGroup>` 要素の内部に、`<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` 項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-192">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="d5c27-193">上記のすべてのガイドラインに従う *.csproj* ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-193">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="d5c27-194">*templates* 子フォルダーを *content* パッケージ フォルダーにパッケージ化し、すべてのコード ファイルをコンパイルから除外します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-194">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="d5c27-195">次の例では、 *.csproj* を使用してテンプレート パックを作成するファイルとフォルダーの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-195">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="d5c27-196">*MyDotnetTemplates.csproj* ファイルと *templates* フォルダーはどちらも、*project_folder* という名前のディレクトリのルートにあります。</span><span class="sxs-lookup"><span data-stu-id="d5c27-196">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="d5c27-197">*templates* フォルダーには、*mytemplate1* と *mytemplate2* の 2 つのテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5c27-197">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="d5c27-198">各テンプレートには、コンテンツ ファイルと、*template.json* 構成ファイルが格納された *.template.config* フォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-198">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="d5c27-199">テンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="d5c27-199">Installing a template</span></span>

<span data-ttu-id="d5c27-200">パッケージをインストールするには、[dotnet new -i|--install](dotnet-new.md) コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="d5c27-200">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="d5c27-201">nuget.org に保存されている NuGet パッケージからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d5c27-201">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="d5c27-202">テンプレート パッケージをインストールするには、NuGet パッケージ識別子を使います。</span><span class="sxs-lookup"><span data-stu-id="d5c27-202">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="d5c27-203">ローカル nupkg ファイルからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d5c27-203">To install a template from a local nupkg file</span></span>

<span data-ttu-id="d5c27-204">*.nupkg* NuGet パッケージ ファイルに対するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-204">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="d5c27-205">ファイル システム ディレクトリからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d5c27-205">To install a template from a file system directory</span></span>

<span data-ttu-id="d5c27-206">テンプレートはテンプレート フォルダーからインストールできます (上の例の *mytemplate1* フォルダーなど)。</span><span class="sxs-lookup"><span data-stu-id="d5c27-206">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="d5c27-207">*.template.config* フォルダーのフォルダー パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-207">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="d5c27-208">テンプレート ディレクトリへのパスは、絶対パスである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5c27-208">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="d5c27-209">ただし、フォルダーからインストールされたテンプレートをアンインストールするには、絶対パスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5c27-209">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="d5c27-210">インストールされているテンプレートの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="d5c27-210">Get a list of installed templates</span></span>

<span data-ttu-id="d5c27-211">他のパラメーターを何も指定しない uninstall コマンドでは、インストールされているすべてのテンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-211">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="d5c27-212">そのコマンドでは、次のような出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-212">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="d5c27-213">`Currently installed items:` の後の第 1 レベルの項目は、テンプレートのアンインストールで使われる識別子です。</span><span class="sxs-lookup"><span data-stu-id="d5c27-213">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="d5c27-214">上の例では、`Microsoft.DotNet.Common.ItemTemplates` と `Microsoft.DotNet.Common.ProjectTemplates.3.0` の一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="d5c27-214">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="d5c27-215">ファイル システム パスを使ってテンプレートをインストールした場合、この識別子は *.template.config* フォルダーのフォルダー パスです。</span><span class="sxs-lookup"><span data-stu-id="d5c27-215">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="d5c27-216">テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d5c27-216">Uninstalling a template</span></span>

<span data-ttu-id="d5c27-217">パッケージをアンインストールするには、[dotnet new -u|--uninstall](dotnet-new.md) コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="d5c27-217">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="d5c27-218">NuGet フィードまたは直接 *.nupkg* ファイルでパッケージをインストールした場合は、識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-218">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="d5c27-219">*.template.config* フォルダーに対するパスを指定してパッケージをインストールした場合は、その**絶対**パスを使ってパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d5c27-219">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="d5c27-220">テンプレートの絶対パスは、`dotnet new -u` コマンドによって提供される出力で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-220">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="d5c27-221">詳しくは、前の「[インストールされているテンプレートの一覧を取得する](#get-a-list-of-installed-templates)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5c27-221">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="d5c27-222">カスタム テンプレートを利用してプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d5c27-222">Create a project using a custom template</span></span>

<span data-ttu-id="d5c27-223">テンプレートがインストールされたら、事前インストールされている他のテンプレートの場合と同様に、`dotnet new <TEMPLATE>` コマンドを実行してテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-223">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="d5c27-224">テンプレートの設定で構成したテンプレート固有のオプションなど、[オプション](dotnet-new.md#options)を `dotnet new` コマンドに対して指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5c27-224">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="d5c27-225">テンプレートの省略名 (短い名前) をコマンドに直接指定します。</span><span class="sxs-lookup"><span data-stu-id="d5c27-225">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="d5c27-226">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5c27-226">See also</span></span>

- [<span data-ttu-id="d5c27-227">dotnet new のカスタム テンプレートを作成する (チュートリアル)</span><span class="sxs-lookup"><span data-stu-id="d5c27-227">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="d5c27-228">dotnet/templating GitHub リポジトリ Wiki</span><span class="sxs-lookup"><span data-stu-id="d5c27-228">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="d5c27-229">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="d5c27-229">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="d5c27-230">dotnet new の独自のテンプレートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d5c27-230">How to create your own templates for dotnet new</span></span>](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [<span data-ttu-id="d5c27-231">JSON Schema Store の *template.json* スキーマ</span><span class="sxs-lookup"><span data-stu-id="d5c27-231">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
