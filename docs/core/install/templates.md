---
title: SDK テンプレートのインストールと管理 - .NET Core
description: Windows、Linux、macOS に .NET Core テンプレートをインストールする方法について説明します。
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324486"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="7c52d-103">.NET のプロジェクトと項目のテンプレートを管理する</span><span class="sxs-lookup"><span data-stu-id="7c52d-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="7c52d-104">.NET Core 付属のテンプレート システムを利用すると、NuGet、NuGet パッケージ ファイル、ファイル システム ディレクトリからテンプレートをインストールしたり、アンインストールしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="7c52d-105">この記事では、.NET Core SDK CLI を使用して .NET Core テンプレートを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="7c52d-106">テンプレートの作成方法については、「[チュートリアル: テンプレートを作成する](../tutorials/cli-templates-create-item-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c52d-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="7c52d-107">テンプレートのインストール</span><span class="sxs-lookup"><span data-stu-id="7c52d-107">Install template</span></span>

<span data-ttu-id="7c52d-108">テンプレートは `-i` パラメーターを指定して [dotnet new](../tools/dotnet-new.md) SDK コマンドを実行することでインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="7c52d-109">テンプレートの NuGet パッケージ ID かテンプレート ファイルが含まれるフォルダーの NuGet パッケージ ID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="7c52d-110">NuGet でホストされるパッケージ</span><span class="sxs-lookup"><span data-stu-id="7c52d-110">NuGet hosted package</span></span>

<span data-ttu-id="7c52d-111">.NET CLI テンプレートは広範囲に配布する目的で [NuGet](https://www.nuget.org/) にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="7c52d-112">テンプレートはプライベート フィードからもインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="7c52d-113">テンプレートを NuGet フィードにアップロードする代わりに、*nupkg* テンプレート ファイルを配布し、手動でインストールできます。詳細は「[ローカル NuGet パッケージ](#local-nuget-package)」セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="7c52d-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="7c52d-114">NuGet フィード構成の詳細については、「[dotnet nuget add source](../tools/dotnet-nuget-add-source.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c52d-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="7c52d-115">既定の NuGet フィードからテンプレート パックをインストールするには、`dotnet new -i {package-id}` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="7c52d-116">特定のバージョンの既定の NuGet フィードからテンプレート パックをインストールするには、`dotnet new -i {package-id}::{version}` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="7c52d-117">ローカル NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="7c52d-117">Local NuGet package</span></span>

<span data-ttu-id="7c52d-118">テンプレート パックが作成されると、*nupkg* ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="7c52d-119">*nupkg* ファイルにテンプレートが含まれる場合、`dotnet new -i {path-to-package}` コマンドでそれをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="7c52d-120">フォルダー</span><span class="sxs-lookup"><span data-stu-id="7c52d-120">Folder</span></span>

<span data-ttu-id="7c52d-121">*nupkg* ファイルからテンプレートをインストールする代わりに、`dotnet new -i {folder-path}` コマンドで直接、フォルダーからテンプレートをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="7c52d-122">指定されたフォルダーは、見つかったテンプレートのテンプレート パック ID として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="7c52d-123">指定されたフォルダーの階層で見つかったテンプレートはすべてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="7c52d-124">コマンドで指定された `{folder-path}` は、見つかったすべてのコマンドのテンプレート パック ID になります。</span><span class="sxs-lookup"><span data-stu-id="7c52d-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="7c52d-125">「[テンプレート リスト](#list-templates)」セクションに指定されているとおり、インストールされているテンプレートのリストは `dotnet new -u` コマンドで取得できます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="7c52d-126">この例では、テンプレート パック ID はインストールに使用されるフォルダーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="7c52d-127">テンプレートをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7c52d-127">Uninstall template</span></span>

<span data-ttu-id="7c52d-128">テンプレートは `-u` パラメーターを指定して [dotnet new](../tools/dotnet-new.md) SDK コマンドを実行することでアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="7c52d-129">テンプレートの NuGet パッケージ ID かテンプレート ファイルが含まれるフォルダーの NuGet パッケージ ID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="7c52d-130">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="7c52d-130">NuGet package</span></span>

<span data-ttu-id="7c52d-131">NuGet フィードまたは *nupkg* ファイルから NuGet テンプレート パックをインストールした後、NuGet パッケージ ID を参照してアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="7c52d-132">テンプレート パックをアンインストールするには、`dotnet new -u {package-id}` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="7c52d-133">フォルダー</span><span class="sxs-lookup"><span data-stu-id="7c52d-133">Folder</span></span>

<span data-ttu-id="7c52d-134">テンプレートが[フォルダー パス](#folder)からインストールされるとき、そのフォルダー パスがテンプレート パック ID になります。</span><span class="sxs-lookup"><span data-stu-id="7c52d-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="7c52d-135">テンプレート パックをアンインストールするには、`dotnet new -u {package-folder-path}` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="7c52d-136">テンプレート リスト</span><span class="sxs-lookup"><span data-stu-id="7c52d-136">List templates</span></span>

<span data-ttu-id="7c52d-137">パッケージ ID なしで標準的なアンインストール コマンドを使用することで、各テンプレートをアンインストールするコマンドと共に、インストール済みのテンプレートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="7c52d-138">他の SDK からテンプレートをインストールする</span><span class="sxs-lookup"><span data-stu-id="7c52d-138">Install templates from other SDKs</span></span>

<span data-ttu-id="7c52d-139">SDK の各バージョンを順番にインストールしている場合、たとえば、SDK 2.0 をインストールし、次に SDK 2.1 をインストールするといった具合にインストールしている場合、各 SDK のテンプレートがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7c52d-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="7c52d-140">ただし、3.1 など、最新版の SDK から始める場合、[LTS (長期サポート) リリース](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)のテンプレートのみが含まれます。これは SDK 3.1 のリリース時点で SDK 2.1 と SDK 3.1 になります。</span><span class="sxs-lookup"><span data-stu-id="7c52d-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="7c52d-141">その他のリリースのテンプレートは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7c52d-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="7c52d-142">.NET Core テンプレートは NuGet で入手できて、他のあらゆるテンプレートと同じようにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7c52d-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="7c52d-143">詳細については、「[NuGet でホストされているパッケージをインストールする](#nuget-hosted-package)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c52d-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="7c52d-144">SDK</span><span class="sxs-lookup"><span data-stu-id="7c52d-144">SDK</span></span>              | <span data-ttu-id="7c52d-145">NuGet パッケージ ID</span><span class="sxs-lookup"><span data-stu-id="7c52d-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7c52d-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7c52d-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="7c52d-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7c52d-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="7c52d-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7c52d-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="7c52d-149">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7c52d-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="7c52d-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7c52d-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="7c52d-151">ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7c52d-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="7c52d-152">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7c52d-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="7c52d-153">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7c52d-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="7c52d-154">たとえば、.NET Core SDK には .NET Core 2.1 と .NET Core 3.1 を対象とするコンソール アプリ向けのテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c52d-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="7c52d-155">.NET Core 3.0 を対象にする場合、3.0 テンプレートをインストールする必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="7c52d-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="7c52d-156">.NET Core 3.0 を対象とするアプリを作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="7c52d-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="7c52d-157">エラー メッセージが表示された場合、テンプレートをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c52d-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="7c52d-158">入力内容と一致するインストール済みテンプレートが見つかりません。オンラインで検索してください...</span><span class="sxs-lookup"><span data-stu-id="7c52d-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="7c52d-159">.NET Core 3.0 プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7c52d-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="7c52d-160">アプリをもう一度作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="7c52d-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="7c52d-161">プロジェクトが作成されたことを示すメッセージが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="7c52d-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="7c52d-162">テンプレート "Console Application" が正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="7c52d-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="7c52d-163">作成後のアクションを処理しています...path-to-project-file.csproj で "dotnet restore" を実行しています...復元対象のプロジェクトを決定しています...path-to-project-file.csproj の復元は 1.05 秒後に完了します。</span><span class="sxs-lookup"><span data-stu-id="7c52d-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="7c52d-164">正常に復元されました。</span><span class="sxs-lookup"><span data-stu-id="7c52d-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c52d-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c52d-165">See also</span></span>

- [<span data-ttu-id="7c52d-166">チュートリアル: 項目テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="7c52d-166">Tutorial: Create an item template</span></span>](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
