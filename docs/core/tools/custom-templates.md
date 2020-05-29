---
title: dotnet new のカスタム テンプレート
description: あらゆる種類の .NET プロジェクトまたはファイルのカスタム テンプレートについて説明します。
author: thraka
ms.date: 05/20/2020
ms.openlocfilehash: 19855c99b240b66dfa819e70d4a1bee5c8ed14ed
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761916"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="8e7a6-103">dotnet new のカスタム テンプレート</span><span class="sxs-lookup"><span data-stu-id="8e7a6-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="8e7a6-104">[.NET Core SDK](https://dotnet.microsoft.com/download) には、既にインストールされて使用できる状態になっている多くのテンプレートが付属します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="8e7a6-105">[`dotnet new` コマンド](dotnet-new.md)は、テンプレートを使用する手段であるだけでなく、テンプレートをインストールおよびアンインストールする方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="8e7a6-106">.NET Core 2.0 以降から、アプリ、サービス、ツール、クラス ライブラリなど、あらゆる種類のプロジェクトを対象に独自のテンプレートを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="8e7a6-107">構成ファイルなど、1 つまたは複数の独立ファイルを出力するテンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="8e7a6-108">NuGet の *.nupkg* ファイルを直接参照するか、テンプレートが含まれるファイル システム ディレクトリを指定することで、任意の NuGet フィード上の NuGet パッケージからカスタム テンプレートをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="8e7a6-109">テンプレート エンジンの機能を利用すると、テンプレートを使うときに、値を置き換えたり、ファイルを含めたり除外したり、独自の処理操作を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="8e7a6-110">テンプレート エンジンはオープン ソースです。オンライン コード リポジトリは GitHub の [dotnet/templating](https://github.com/dotnet/templating/) にあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="8e7a6-111">GitHub の「[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)」 (dotnet new で利用できるテンプレート) には、サードパーティのテンプレートなど、テンプレートが他にもあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-111">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="8e7a6-112">カスタム テンプレートの作成と利用の詳細については、「[dotnet new の独自のテンプレートを作成する方法](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)」と「[dotnet/templating GitHub リポジトリ Wiki](https://github.com/dotnet/templating/wiki)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-112">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

> [!NOTE]
> <span data-ttu-id="8e7a6-113">テンプレートの例は、[dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) GitHub リポジトリで入手できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-113">Template examples are available at the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) GitHub repository.</span></span> <span data-ttu-id="8e7a6-114">ただし、これらの例はテンプレートの機能を学習するのに適したリソースですが、リポジトリはアーカイブされ、保守は行われていません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-114">However, while these examples are good resource for learning how the templates work, the repository is archived and no longer maintained.</span></span> <span data-ttu-id="8e7a6-115">これらの例は最新ではなく、機能しなくなっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-115">The examples may be out of date and no longer working.</span></span>

<span data-ttu-id="8e7a6-116">チュートリアルでテンプレートを作成するには、「[dotnet new のカスタム テンプレートを作成する](../tutorials/cli-templates-create-item-template.md)」チュートリアルをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-116">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="8e7a6-117">.NET の既定のテンプレート</span><span class="sxs-lookup"><span data-stu-id="8e7a6-117">.NET default templates</span></span>

<span data-ttu-id="8e7a6-118">[.NET Core SDK](https://dotnet.microsoft.com/download) をインストールすると、コンソール アプリ、クラス ライブラリ、単体テスト プロジェクト、ASP.NET Core アプリ ([Angular](https://angular.io/) プロジェクトと [React](https://facebook.github.io/react/) プロジェクトを含む)、構成ファイルなど、プロジェクトやファイルを作成するための 12 個を超える組み込みテンプレートが与えられます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-118">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="8e7a6-119">組み込みテンプレートの一覧を表示するには、`-l|--list` オプションを指定して `dotnet new` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-119">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="8e7a6-120">構成</span><span class="sxs-lookup"><span data-stu-id="8e7a6-120">Configuration</span></span>

<span data-ttu-id="8e7a6-121">テンプレートは次の部分から構成されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-121">A template is composed of the following parts:</span></span>

- <span data-ttu-id="8e7a6-122">ソース ファイルとフォルダー。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-122">Source files and folders.</span></span>
- <span data-ttu-id="8e7a6-123">構成ファイル (*template.json*)。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-123">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="8e7a6-124">ソース ファイルとフォルダー</span><span class="sxs-lookup"><span data-stu-id="8e7a6-124">Source files and folders</span></span>

<span data-ttu-id="8e7a6-125">ソース ファイルとフォルダーには、`dotnet new <TEMPLATE>` コマンドの実行時にテンプレート エンジンで使用されるすべてのファイルとフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-125">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="8e7a6-126">テンプレート エンジンは、ソース コードとして*実行可能なプロジェクト*を利用し、プロジェクトを生成するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-126">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="8e7a6-127">これにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-127">This has several benefits:</span></span>

- <span data-ttu-id="8e7a6-128">テンプレート エンジンでは、プロジェクトのソース コードに特別なトークンを挿入することを必要としません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-128">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="8e7a6-129">コード ファイルは特別なファイルではなく、テンプレート エンジンで利用するために変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-129">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="8e7a6-130">そのため、プロジェクトの利用時に通常利用しているツールでテンプレート コンテンツに対応できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-130">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="8e7a6-131">他のプロジェクトの場合と同じように、テンプレート プロジェクトをビルドし、実行し、デバッグします。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-131">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="8e7a6-132">*./.template.config/template.json* 構成ファイルをプロジェクトに追加するだけで、既存のプロジェクトからテンプレートを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-132">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="8e7a6-133">テンプレートに格納されるファイルやフォルダーは、正式な種類の .NET プロジェクトに限定されません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-133">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="8e7a6-134">テンプレート エンジンで出力として生成されるファイルが 1 つだけであっても、ソース ファイルとフォルダーは、テンプレートを使って作成するすべてのコンテンツで構成できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-134">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="8e7a6-135">テンプレートによって生成されるファイルは、*template.json* 構成ファイルで提供するロジックと設定に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-135">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="8e7a6-136">ユーザーは、`dotnet new <TEMPLATE>` コマンドにオプションを渡すことによって、これらの設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-136">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="8e7a6-137">カスタム ロジックの一般的な例は、テンプレートによって展開されるコード ファイル内のクラスや変数に名前を提供する場合です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-137">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="8e7a6-138">template.json</span><span class="sxs-lookup"><span data-stu-id="8e7a6-138">template.json</span></span>

<span data-ttu-id="8e7a6-139">*template.json* ファイルは、テンプレートのルート ディレクトリの *.template.config* フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-139">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="8e7a6-140">このファイルは、テンプレート エンジンに構成情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-140">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="8e7a6-141">最小構成には、次の表に示すメンバーが必要です。この最小構成があれば、実際に機能するテンプレートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-141">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="8e7a6-142">メンバー</span><span class="sxs-lookup"><span data-stu-id="8e7a6-142">Member</span></span>            | <span data-ttu-id="8e7a6-143">種類</span><span class="sxs-lookup"><span data-stu-id="8e7a6-143">Type</span></span>          | <span data-ttu-id="8e7a6-144">説明</span><span class="sxs-lookup"><span data-stu-id="8e7a6-144">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="8e7a6-145">URI</span><span class="sxs-lookup"><span data-stu-id="8e7a6-145">URI</span></span>           | <span data-ttu-id="8e7a6-146">*template.json* ファイルの JSON スキーマ。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-146">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="8e7a6-147">エディターが JSON スキーマ対応であれば、スキーマの指定時、JSON 編集機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-147">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="8e7a6-148">たとえば、[Visual Studio Code](https://code.visualstudio.com/) の場合、IntelliSense を有効にするためにこのメンバーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-148">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="8e7a6-149">値として `http://json.schemastore.org/template` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-149">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="8e7a6-150">string</span><span class="sxs-lookup"><span data-stu-id="8e7a6-150">string</span></span>        | <span data-ttu-id="8e7a6-151">テンプレートの作成者。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-151">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="8e7a6-152">array(string)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-152">array(string)</span></span> | <span data-ttu-id="8e7a6-153">テンプレートのゼロ以上の特性。ユーザーがこれを利用し、テンプレートを探すことがあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-153">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="8e7a6-154">`dotnet new -l|--list` コマンドでテンプレートの一覧を生成したとき、*Tags* 列が表示される場合、この列にも分類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-154">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="8e7a6-155">string</span><span class="sxs-lookup"><span data-stu-id="8e7a6-155">string</span></span>        | <span data-ttu-id="8e7a6-156">このテンプレートの一意の名前。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-156">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="8e7a6-157">string</span><span class="sxs-lookup"><span data-stu-id="8e7a6-157">string</span></span>        | <span data-ttu-id="8e7a6-158">ユーザーに対して表示されるテンプレートの名前。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-158">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="8e7a6-159">string</span><span class="sxs-lookup"><span data-stu-id="8e7a6-159">string</span></span>        | <span data-ttu-id="8e7a6-160">テンプレートを選択するための既定の省略名。テンプレート名が GUI 経由で選択されるのではなく、ユーザーによって指定される環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-160">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="8e7a6-161">たとえば、CLI コマンドでコマンド プロンプトからテンプレートを利用するときに省略名が便利です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-161">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="8e7a6-162">*template.json* ファイルの完全スキーマは [JSON Schema Store](http://json.schemastore.org/template) にあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-162">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="8e7a6-163">*template.json* ファイルについて詳しくは、[dotnet テンプレート wiki](https://github.com/dotnet/templating/wiki) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-163">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="8e7a6-164">例</span><span class="sxs-lookup"><span data-stu-id="8e7a6-164">Example</span></span>

<span data-ttu-id="8e7a6-165">たとえば、次に示すテンプレート フォルダーには、2 つのコンテンツ ファイル *console.cs* と *readme.txt* が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-165">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="8e7a6-166">*template.json* ファイルが含まれる、 *.template.config* という名前の必須フォルダーがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-166">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="8e7a6-167">*template.json* ファイルは次のようなものです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-167">The *template.json* file looks like the following:</span></span>

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

<span data-ttu-id="8e7a6-168">*mytemplate* フォルダーは、インストール可能なテンプレート パックです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-168">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="8e7a6-169">パックがインストールされたら、`shortName` を `dotnet new` コマンドで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-169">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="8e7a6-170">たとえば、`dotnet new adatumconsole` では、`console.cs` および `readme.txt` ファイルが現在のフォルダーに出力されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-170">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="8e7a6-171">テンプレートをパッケージ化し、NuGet パッケージ (nupkg ファイル) を作成する</span><span class="sxs-lookup"><span data-stu-id="8e7a6-171">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="8e7a6-172">カスタム テンプレートは、[dotnet pack](dotnet-pack.md) コマンドと *.csproj* ファイルでパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-172">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="8e7a6-173">または、[nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) コマンドと *.nuspec* ファイルで [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-173">Alternatively, [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="8e7a6-174">ただし、NuGet の場合、Windows では .NET Framework が、Linux と MacOS では [Mono](https://www.mono-project.com/) が必要です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-174">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and MacOS.</span></span>

<span data-ttu-id="8e7a6-175">*.csproj* ファイルは、従来のコード プロジェクトの *.csproj* ファイルと若干異なります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-175">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="8e7a6-176">次の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-176">Note the following settings:</span></span>

01. <span data-ttu-id="8e7a6-177">設定 `<PackageType>` が追加され、`Template` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-177">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="8e7a6-178">設定 `<PackageVersion>` が追加され、有効な [NuGet のバージョン番号](/nuget/reference/package-versioning)に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-178">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="8e7a6-179">設定 `<PackageId>` が追加され、一意の識別子に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-179">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="8e7a6-180">この識別子は、テンプレート パックのアンインストールに使われ、テンプレート パックを登録するために NuGet フィードによって使われます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-180">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="8e7a6-181">ジェネリック メタデータの設定 `<Title>`、`<Authors>`、`<Description>`、`<PackageTags>` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-181">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="8e7a6-182">テンプレート プロセスによって生成されるバイナリを使わない場合でも、設定 `<TargetFramework>` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-182">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="8e7a6-183">次の例では、`netstandard2.0` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-183">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="8e7a6-184">*.nupkg* NuGet パッケージの形式のテンプレート パックでは、すべてのテンプレートをパッケージ内の *content* フォルダーに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-184">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="8e7a6-185">生成された *.nupkg* をテンプレート パックとしてインストールできるようにするため、 *.csproj* ファイルに追加する設定がさらにいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-185">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="8e7a6-186">プロジェクトで**コンテンツ**として設定されるすべてのファイルを NuGet パッケージに含めるには、設定 `<IncludeContentInPack>` を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-186">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="8e7a6-187">コンパイラによって生成されたすべてのバイナリを NuGet パッケージから除外するには、設定 `<IncludeBuildOutput>` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-187">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="8e7a6-188">設定 `<ContentTargetFolders>` を `content` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-188">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="8e7a6-189">これにより、**コンテンツ**として設定されたファイルは、NuGet パッケージ内の *content* フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-189">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="8e7a6-190">NuGet パッケージのこのフォルダーは、dotnet テンプレート システムによって解析されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-190">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="8e7a6-191">すべてのコード ファイルをテンプレート プロジェクトによってコンパイルされないように除外する簡単な方法は、プロジェクト ファイルの `<ItemGroup>` 要素内で `<Compile Remove="**\*" />` 項目を使うことです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-191">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="8e7a6-192">テンプレート パックを構成する簡単な方法は、すべてのテンプレートを個別のフォルダーに格納した後、 *.csproj* ファイルと同じディレクトリにある *templates* フォルダーの内部に各テンプレート フォルダーを格納することです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-192">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="8e7a6-193">これにより、1 つのプロジェクト項目を使って、すべてのファイルとフォルダーを**コンテンツ**として *templates* に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-193">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="8e7a6-194">`<ItemGroup>` 要素の内部に、`<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` 項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-194">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="8e7a6-195">上記のすべてのガイドラインに従う *.csproj* ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-195">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="8e7a6-196">*templates* 子フォルダーを *content* パッケージ フォルダーにパッケージ化し、すべてのコード ファイルをコンパイルから除外します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-196">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

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

<span data-ttu-id="8e7a6-197">次の例では、 *.csproj* を使用してテンプレート パックを作成するファイルとフォルダーの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-197">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="8e7a6-198">*MyDotnetTemplates.csproj* ファイルと *templates* フォルダーはどちらも、*project_folder* という名前のディレクトリのルートにあります。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-198">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="8e7a6-199">*templates* フォルダーには、*mytemplate1* と *mytemplate2* の 2 つのテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-199">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="8e7a6-200">各テンプレートには、コンテンツ ファイルと、*template.json* 構成ファイルが格納された *.template.config* フォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-200">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

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

## <a name="installing-a-template"></a><span data-ttu-id="8e7a6-201">テンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="8e7a6-201">Installing a template</span></span>

<span data-ttu-id="8e7a6-202">パッケージをインストールするには、[dotnet new -i|--install](dotnet-new.md) コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-202">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="8e7a6-203">nuget.org に保存されている NuGet パッケージからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="8e7a6-203">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="8e7a6-204">テンプレート パッケージをインストールするには、NuGet パッケージ識別子を使います。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-204">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="8e7a6-205">ローカル nupkg ファイルからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="8e7a6-205">To install a template from a local nupkg file</span></span>

<span data-ttu-id="8e7a6-206">*.nupkg* NuGet パッケージ ファイルに対するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-206">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="8e7a6-207">ファイル システム ディレクトリからテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="8e7a6-207">To install a template from a file system directory</span></span>

<span data-ttu-id="8e7a6-208">テンプレートはテンプレート フォルダーからインストールできます (上の例の *mytemplate1* フォルダーなど)。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-208">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="8e7a6-209">*.template.config* フォルダーのフォルダー パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-209">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="8e7a6-210">テンプレート ディレクトリへのパスは、絶対パスである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-210">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="8e7a6-211">ただし、フォルダーからインストールされたテンプレートをアンインストールするには、絶対パスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-211">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="8e7a6-212">インストールされているテンプレートの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="8e7a6-212">Get a list of installed templates</span></span>

<span data-ttu-id="8e7a6-213">他のパラメーターを何も指定しない uninstall コマンドでは、インストールされているすべてのテンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-213">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="8e7a6-214">そのコマンドでは、次のような出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-214">That command returns something similar to the following output:</span></span>

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

<span data-ttu-id="8e7a6-215">`Currently installed items:` の後の第 1 レベルの項目は、テンプレートのアンインストールで使われる識別子です。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-215">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="8e7a6-216">上の例では、`Microsoft.DotNet.Common.ItemTemplates` と `Microsoft.DotNet.Common.ProjectTemplates.3.0` の一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-216">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="8e7a6-217">ファイル システム パスを使ってテンプレートをインストールした場合、この識別子は *.template.config* フォルダーのフォルダー パスです。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-217">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="8e7a6-218">テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="8e7a6-218">Uninstalling a template</span></span>

<span data-ttu-id="8e7a6-219">パッケージをアンインストールするには、[dotnet new -u|--uninstall](dotnet-new.md) コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-219">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="8e7a6-220">NuGet フィードまたは直接 *.nupkg* ファイルでパッケージをインストールした場合は、識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-220">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="8e7a6-221">*.template.config* フォルダーに対するパスを指定してパッケージをインストールした場合は、その**絶対**パスを使ってパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-221">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="8e7a6-222">テンプレートの絶対パスは、`dotnet new -u` コマンドによって提供される出力で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-222">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="8e7a6-223">詳しくは、前の「[インストールされているテンプレートの一覧を取得する](#get-a-list-of-installed-templates)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-223">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="8e7a6-224">カスタム テンプレートを利用してプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="8e7a6-224">Create a project using a custom template</span></span>

<span data-ttu-id="8e7a6-225">テンプレートがインストールされたら、事前インストールされている他のテンプレートの場合と同様に、`dotnet new <TEMPLATE>` コマンドを実行してテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-225">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="8e7a6-226">テンプレートの設定で構成したテンプレート固有のオプションなど、[オプション](dotnet-new.md#options)を `dotnet new` コマンドに対して指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-226">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="8e7a6-227">テンプレートの省略名 (短い名前) をコマンドに直接指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7a6-227">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="8e7a6-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e7a6-228">See also</span></span>

- [<span data-ttu-id="8e7a6-229">dotnet new のカスタム テンプレートを作成する (チュートリアル)</span><span class="sxs-lookup"><span data-stu-id="8e7a6-229">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="8e7a6-230">dotnet/templating GitHub リポジトリ Wiki</span><span class="sxs-lookup"><span data-stu-id="8e7a6-230">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="8e7a6-231">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="8e7a6-231">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="8e7a6-232">dotnet new の独自のテンプレートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8e7a6-232">How to create your own templates for dotnet new</span></span>](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [<span data-ttu-id="8e7a6-233">JSON Schema Store の *template.json* スキーマ</span><span class="sxs-lookup"><span data-stu-id="8e7a6-233">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
