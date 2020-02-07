---
title: dotnet new 用のテンプレート パックを作成する
description: dotnet new コマンド用のテンプレート パックをビルドする csproj ファイルを作成する方法を説明します。
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 3a72f68f5634c9ee5b137baf12a279130861e61a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787837"
---
# <a name="tutorial-create-a-template-pack"></a><span data-ttu-id="51460-103">チュートリアル: テンプレート パックを作成する</span><span class="sxs-lookup"><span data-stu-id="51460-103">Tutorial: Create a template pack</span></span>

<span data-ttu-id="51460-104">.NET Core では、プロジェクト、ファイル、さらにはリソースを生成するテンプレートを作成して配置することができます。</span><span class="sxs-lookup"><span data-stu-id="51460-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="51460-105">このチュートリアルは、`dotnet new` コマンドで使用するテンプレートの作成、インストール、アンインストール方法を説明するシリーズのパート 3 です。</span><span class="sxs-lookup"><span data-stu-id="51460-105">This tutorial is part three of a series that teaches you how to create, install, and uninstall templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="51460-106">シリーズのこのパートで学習する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51460-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="51460-107">テンプレート パックをビルドするための \*.csproj プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="51460-107">Create a \*.csproj project to build a template pack</span></span>
> * <span data-ttu-id="51460-108">パックのためのプロジェクト ファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="51460-108">Configure the project file for packing</span></span>
> * <span data-ttu-id="51460-109">NuGet パッケージ ファイルからテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="51460-109">Install a template from a NuGet package file</span></span>
> * <span data-ttu-id="51460-110">パッケージ ID を使用してテンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="51460-110">Uninstall a template by package ID</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51460-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51460-111">Prerequisites</span></span>

* <span data-ttu-id="51460-112">このチュートリアル シリーズの[パート 1](cli-templates-create-item-template.md) と[パート 2](cli-templates-create-project-template.md) を完了します。</span><span class="sxs-lookup"><span data-stu-id="51460-112">Complete [part 1](cli-templates-create-item-template.md) and [part 2](cli-templates-create-project-template.md) of this tutorial series.</span></span>

  <span data-ttu-id="51460-113">このチュートリアルでは、チュートリアルの最初の 2 つのパートで作成した 2 つのテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="51460-113">This tutorial uses the two templates created in the first two parts of this tutorial.</span></span> <span data-ttu-id="51460-114">そのテンプレートをフォルダーとして _working\templates\\_ フォルダー内にコピーしていれば、別のテンプレートを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="51460-114">You can use a different template as long as you copy the template, as a folder, into the _working\templates\\_ folder.</span></span>

* <span data-ttu-id="51460-115">ターミナルを開いて _working\\_ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="51460-115">Open a terminal and navigate to the _working\\_ folder.</span></span>

## <a name="create-a-template-pack-project"></a><span data-ttu-id="51460-116">テンプレート パック プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="51460-116">Create a template pack project</span></span>

<span data-ttu-id="51460-117">テンプレート パックは、1 つのファイルにパッケージ化された 1 つ以上のテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="51460-117">A template pack is one or more templates packaged into a file.</span></span> <span data-ttu-id="51460-118">パックをインストール/アンインストールすると、そのパックに含まれているすべてのテンプレートが追加/削除されます。</span><span class="sxs-lookup"><span data-stu-id="51460-118">When you install or uninstall a pack, all templates contained in the pack are added or removed, respectively.</span></span> <span data-ttu-id="51460-119">このチュートリアル シリーズのこれまでのパートでは、個別のテンプレートのみを扱いました。</span><span class="sxs-lookup"><span data-stu-id="51460-119">The previous parts of this tutorial series only worked with individual templates.</span></span> <span data-ttu-id="51460-120">パックされていないテンプレートを共有するには、テンプレート フォルダーをコピーし、そのフォルダーを介してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51460-120">To share a non-packed template, you have to copy the template folder and install via that folder.</span></span> <span data-ttu-id="51460-121">テンプレート パックは複数のテンプレートを含めることができ、1つのファイルであるため、より簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="51460-121">Because a template pack can have more than one template in it, and is a single file, sharing is easier.</span></span>

<span data-ttu-id="51460-122">テンプレート パックは、NuGet パッケージ ( _.nupkg_) ファイルによって表されます。</span><span class="sxs-lookup"><span data-stu-id="51460-122">Template packs are represented by a NuGet package (_.nupkg_) file.</span></span> <span data-ttu-id="51460-123">また、すべての NuGet パッケージと同様に、テンプレート パックを NuGet フィードにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="51460-123">And, like any NuGet package, you can upload the template pack to a NuGet feed.</span></span> <span data-ttu-id="51460-124">`dotnet new -i` コマンドでは、NuGet パッケージ フィードからのテンプレート パックのインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="51460-124">The `dotnet new -i` command supports installing template pack from a NuGet package feed.</span></span> <span data-ttu-id="51460-125">さらに、 _.nupkg_ ファイルからテンプレート パックを直接インストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="51460-125">Additionally, you can install a template pack from a _.nupkg_ file directly.</span></span>

<span data-ttu-id="51460-126">通常は、C# プロジェクト ファイルを使用してコードをコンパイルし、バイナリを生成します。</span><span class="sxs-lookup"><span data-stu-id="51460-126">Normally you use a C# project file to compile code and produce a binary.</span></span> <span data-ttu-id="51460-127">しかし、プロジェクトを使用してテンプレート パックを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="51460-127">However, the project can also be used to generate a template pack.</span></span> <span data-ttu-id="51460-128">_.csproj_ の設定を変更して、コードがコンパイルされないようにし、代わりにテンプレートのすべての資産をリソースとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="51460-128">By changing the settings of the _.csproj_, you can prevent it from compiling any code and instead include all the assets of your templates as resources.</span></span> <span data-ttu-id="51460-129">このプロジェクトをビルドすると、テンプレート パックの NuGet パッケージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="51460-129">When this project is built, it produces a template pack NuGet package.</span></span>

<span data-ttu-id="51460-130">作成するパックには、これまでに作成した[項目テンプレート](cli-templates-create-item-template.md)と[パッケージ テンプレート](cli-templates-create-project-template.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51460-130">The pack you'll create will include the [item template](cli-templates-create-item-template.md) and [package template](cli-templates-create-project-template.md) previously created.</span></span> <span data-ttu-id="51460-131">これらの 2 つのテンプレートを _working\templates\\_ フォルダーでグループ化したので、 _.csproj_ ファイル用に _working_ フォルダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51460-131">Because we grouped the two templates into the _working\templates\\_ folder, we can use the _working_ folder for the _.csproj_ file.</span></span>

<span data-ttu-id="51460-132">ターミナルで _working_ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="51460-132">In your terminal, navigate to the _working_ folder.</span></span> <span data-ttu-id="51460-133">新しいプロジェクトを作成し、名前を `templatepack`、出力フォルダーを現在のフォルダーに設定します。</span><span class="sxs-lookup"><span data-stu-id="51460-133">Create a new project and set the name to `templatepack` and the output folder to the current folder.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

<span data-ttu-id="51460-134">`-n` パラメーターを指定すると、 _.csproj_ のファイル名が _templatepack.csproj_ に設定されます。</span><span class="sxs-lookup"><span data-stu-id="51460-134">The `-n` parameter sets the _.csproj_ filename to _templatepack.csproj_.</span></span> <span data-ttu-id="51460-135">`-o` パラメーターを指定すると、現在のディレクトリにファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="51460-135">The `-o` parameter creates the files in the current directory.</span></span> <span data-ttu-id="51460-136">次の出力のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51460-136">You should see a result similar to the following output.</span></span>

```console
C:\working> dotnet new console -n templatepack -o .
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

<span data-ttu-id="51460-137">次に、お好みのテキスト エディターで _templatepack.csproj_ ファイルを開き、コンテンツを次の XML で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="51460-137">Next, open the _templatepack.csproj_ file in your favorite editor and replace the content with the following XML:</span></span>

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

<span data-ttu-id="51460-138">上の XML 内の `<PropertyGroup>` の設定は、3 つのグループに分かれています。</span><span class="sxs-lookup"><span data-stu-id="51460-138">The `<PropertyGroup>` settings in the XML above is broken into three groups.</span></span> <span data-ttu-id="51460-139">最初のグループでは、NuGet パッケージに必要なプロパティが処理されます。</span><span class="sxs-lookup"><span data-stu-id="51460-139">The first group deals with properties required for a NuGet package.</span></span> <span data-ttu-id="51460-140">`<Package` の 3 つの設定は、NuGet フィード上でパッケージを識別するための NuGet パッケージ プロパティと関係しています。</span><span class="sxs-lookup"><span data-stu-id="51460-140">The three `<Package` settings have to do with the NuGet package properties to identify your package on a NuGet feed.</span></span> <span data-ttu-id="51460-141">具体的には、`<PackageId>` 値は、ディレクトリ パスではなく単一の名前を使用してテンプレート パックをアンインストールするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51460-141">Specifically the `<PackageId>` value is used to uninstall the template pack with a single name instead of a directory path.</span></span> <span data-ttu-id="51460-142">また、NuGet フィードからテンプレート パックをインストールするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="51460-142">It can also be used to install the template pack from a NuGet feed.</span></span> <span data-ttu-id="51460-143">`<Title>`、`<PackageTags>` などの残りの設定は、NuGet フィードに表示されるメタデータに関連しています。</span><span class="sxs-lookup"><span data-stu-id="51460-143">The remaining settings such as `<Title>` and `<PackageTags>` have to do with metadata displayed on the NuGet feed.</span></span> <span data-ttu-id="51460-144">NuGet の設定の詳細については、[NuGet と MSBuild のプロパティ](/nuget/reference/msbuild-targets)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51460-144">For more information about NuGet settings, see [NuGet and MSBuild properties](/nuget/reference/msbuild-targets).</span></span>

<span data-ttu-id="51460-145">`<TargetFramework>` の設定は、パック コマンドを実行してプロジェクトのコンパイルとパッケージ化を行うときに MSBuild が正しく実行されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51460-145">The `<TargetFramework>` setting must be set so that MSBuild will run properly when you run the pack command to compile and pack the project.</span></span>

<span data-ttu-id="51460-146">最後の 3 つの設定は、プロジェクトが作成されたときにテンプレートが NuGet パック内の適切なフォルダーに含まれるよう、プロジェクトを正しく構成することに関連しています。</span><span class="sxs-lookup"><span data-stu-id="51460-146">The last three settings have to do with configuring the project correctly to include the templates in the appropriate folder in the NuGet pack when it's created.</span></span>

<span data-ttu-id="51460-147">`<ItemGroup>` には 2 つの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51460-147">The `<ItemGroup>` contains two settings.</span></span> <span data-ttu-id="51460-148">まず、`<Content>` 設定では、_templates_ フォルダー内のすべてのものがコンテンツとして含められます。</span><span class="sxs-lookup"><span data-stu-id="51460-148">First, the `<Content>` setting includes everything in the _templates_ folder as content.</span></span> <span data-ttu-id="51460-149">また、コンパイル済みのコード (テンプレートをテストしてコンパイルした場合) が含まれないようにするために、すべての _bin_ または _obj_ フォルダーを除外するよう設定されます。</span><span class="sxs-lookup"><span data-stu-id="51460-149">It's also set to exclude any _bin_ folder or _obj_ folder to prevent any compiled code (if you tested and compiled your templates) from being included.</span></span> <span data-ttu-id="51460-150">次に、`<Compile>` 設定では、すべてのコード ファイルがその場所に関係なくコンパイルから除外されます。</span><span class="sxs-lookup"><span data-stu-id="51460-150">Second, the `<Compile>` setting excludes all code files from compiling no matter where they're located.</span></span> <span data-ttu-id="51460-151">この設定により、テンプレート パックの作成に使用されているプロジェクトで _templates_ フォルダー階層内のコードのコンパイルが試行されなくなります。</span><span class="sxs-lookup"><span data-stu-id="51460-151">This setting prevents the project being used to create a template pack from trying to compile the code in the _templates_ folder hierarchy.</span></span>

## <a name="build-and-install"></a><span data-ttu-id="51460-152">ビルドしてインストールする</span><span class="sxs-lookup"><span data-stu-id="51460-152">Build and install</span></span>

<span data-ttu-id="51460-153">このファイルを保存してから、パック コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51460-153">Save this file and then run the pack command</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="51460-154">このコマンドを実行すると、プロジェクトがビルドされ、_working\bin\Debug_ フォルダー内に NuGet パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="51460-154">This command will build your project and create a NuGet package in This should be the _working\bin\Debug_ folder.</span></span>

```console
C:\working> dotnet pack
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

<span data-ttu-id="51460-155">次に、`dotnet new -i PATH_TO_NUPKG_FILE` コマンドを使用してテンプレート パック ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="51460-155">Next, install the template pack file with the `dotnet new -i PATH_TO_NUPKG_FILE` command.</span></span>

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

<span data-ttu-id="51460-156">NuGet パッケージを NuGet フィードにアップロードした場合は、`dotnet new -i PACKAGEID` コマンドを使用できます。ここで、`PACKAGEID` は _.csproj_ ファイルに含まれる `<PackageId>` 設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="51460-156">If you uploaded the NuGet package to a NuGet feed, you can use the `dotnet new -i PACKAGEID` command where `PACKAGEID` is the same as the `<PackageId>` setting from the _.csproj_ file.</span></span> <span data-ttu-id="51460-157">このパッケージ ID は、NuGet パッケージ識別子と同じです。</span><span class="sxs-lookup"><span data-stu-id="51460-157">This package ID is the same as the NuGet package identifier.</span></span>

## <a name="uninstall-the-template-pack"></a><span data-ttu-id="51460-158">テンプレート パックをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="51460-158">Uninstall the template pack</span></span>

<span data-ttu-id="51460-159">テンプレート パックを削除する方法は、テンプレート パックをインストールした方法 ( _.nupkg_ ファイルを使用して直接、または NuGet フィードを使用) にかかわらず同じです。</span><span class="sxs-lookup"><span data-stu-id="51460-159">No matter how you installed the template pack, either with the _.nupkg_ file directly or by NuGet feed, removing a template pack is the same.</span></span> <span data-ttu-id="51460-160">アンインストールするテンプレートの `<PackageId>` を使用します。</span><span class="sxs-lookup"><span data-stu-id="51460-160">Use the `<PackageId>` of the template you want to uninstall.</span></span> <span data-ttu-id="51460-161">`dotnet new -u` コマンドを実行すると、インストールされているテンプレートの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="51460-161">You can get a list of templates that are installed by running the `dotnet new -u` command.</span></span>

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
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="51460-162">`dotnet new -u AdatumCorporation.Utility.Templates` を実行してテンプレートをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="51460-162">Run `dotnet new -u AdatumCorporation.Utility.Templates` to uninstall the template.</span></span> <span data-ttu-id="51460-163">`dotnet new` コマンドを実行するとヘルプ情報が出力され、前にインストールしたテンプレートが除外されているはずです。</span><span class="sxs-lookup"><span data-stu-id="51460-163">The `dotnet new` command will output help information that should omit the templates you previously installed.</span></span>

<span data-ttu-id="51460-164">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="51460-164">Congratulations!</span></span> <span data-ttu-id="51460-165">テンプレート パックをインストールしてアンインストールしました。</span><span class="sxs-lookup"><span data-stu-id="51460-165">you've installed and uninstalled a template pack.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51460-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="51460-166">Next steps</span></span>

<span data-ttu-id="51460-167">テンプレートの詳細については、ほとんどを既に説明しましたが、記事「[dotnet new のカスタム テンプレート](../tools/custom-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51460-167">To learn more about templates, most of which you've already learned, see the [Custom templates for dotnet new](../tools/custom-templates.md) article.</span></span>

* [<span data-ttu-id="51460-168">dotnet/templating GitHub リポジトリ Wiki</span><span class="sxs-lookup"><span data-stu-id="51460-168">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
* [<span data-ttu-id="51460-169">dotnet/dotnet-template-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="51460-169">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
* [<span data-ttu-id="51460-170">JSON Schema Store の *template.json* スキーマ</span><span class="sxs-lookup"><span data-stu-id="51460-170">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
