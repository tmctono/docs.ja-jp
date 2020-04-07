---
title: Windows フォーム アプリを .NET Core に移植する
description: .NET Framework Windows フォーム アプリケーションを .NET Core for Windows に移植する方法について説明します。
author: Thraka
ms.author: adegeo
ms.date: 01/24/2020
ms.openlocfilehash: 80b4bb225d6a6748743d91a4c70e8b09c10cc94b
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635509"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="959cd-103">Windows フォーム デスクトップ アプリを .NET Core に移植する方法</span><span class="sxs-lookup"><span data-stu-id="959cd-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="959cd-104">この記事では、Windows フォームベースのデスクトップ アプリを、.NET Framework から .NET Core 3.0 以降に移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="959cd-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0 or later.</span></span> <span data-ttu-id="959cd-105">.NET Core 3.0 SDK には、Windows Forms アプリケーションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="959cd-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="959cd-106">Windows Forms は、まだ Windows 専用のフレームワークであるため、Windows 上でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="959cd-107">この例では、.NET Core CLI を使用して、プロジェクトの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="959cd-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="959cd-108">この記事では、さまざまな名前が使用して、移行で使用されるファイルの種類を識別しています。</span><span class="sxs-lookup"><span data-stu-id="959cd-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="959cd-109">実際のファイルの名前とは異なっているため、自分のプロジェクトを移行するときは、次の一覧の名前に置き換えて説明をお読みください。</span><span class="sxs-lookup"><span data-stu-id="959cd-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="959cd-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="959cd-110">File</span></span> | <span data-ttu-id="959cd-111">説明</span><span class="sxs-lookup"><span data-stu-id="959cd-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="959cd-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="959cd-112">**MyApps.sln**</span></span> | <span data-ttu-id="959cd-113">ソリューション ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-113">The name of the solution file.</span></span> |
| <span data-ttu-id="959cd-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="959cd-114">**MyForms.csproj**</span></span> | <span data-ttu-id="959cd-115">移植する .NET Framework Windows Forms プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="959cd-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="959cd-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="959cd-117">作成する新しい .NET Core プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="959cd-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="959cd-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="959cd-119">.NET Core Windows Forms アプリの実行可能ファイル。</span><span class="sxs-lookup"><span data-stu-id="959cd-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="959cd-120">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="959cd-120">Prerequisites</span></span>

- <span data-ttu-id="959cd-121">デザイナー作業を行う必要がある場合、[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) 以降。</span><span class="sxs-lookup"><span data-stu-id="959cd-121">[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) or later for any designer work you want to do.</span></span> <span data-ttu-id="959cd-122">最新の[プレビュー バージョンの Visual Studio](https://visualstudio.microsoft.com/vs/preview/) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="959cd-122">We recommend to update to the latest [Preview version of Visual Studio](https://visualstudio.microsoft.com/vs/preview/)</span></span>

  <span data-ttu-id="959cd-123">次の Visual Studio ワークロードをインストールします。</span><span class="sxs-lookup"><span data-stu-id="959cd-123">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="959cd-124">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="959cd-124">.NET desktop development</span></span>
  - <span data-ttu-id="959cd-125">.NET Core クロスプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="959cd-125">.NET Core cross-platform development</span></span>

- <span data-ttu-id="959cd-126">問題なくビルドされて実行されているソリューション内の作業用 Windows Forms プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="959cd-126">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="959cd-127">C# でコードを書いたプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="959cd-127">A project coded in C#.</span></span>

> [!NOTE]
> <span data-ttu-id="959cd-128">.NET Core 3.0 プロジェクトは、**Visual Studio 2019** 以降のバージョンでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="959cd-128">.NET Core 3.0 projects are only supported in **Visual Studio 2019** or a later version.</span></span> <span data-ttu-id="959cd-129">**Visual Studio 2019 version 16.5 Preview 1** 以降では、.NET Core Windows フォーム デザイナーもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="959cd-129">Starting with **Visual Studio 2019 version 16.5 Preview 1**, the .NET Core Windows Forms designer is also supported.</span></span>
>
> <span data-ttu-id="959cd-130">デザイナーを有効にするには、 **[ツール]**  >  **[オプション]**  >  **[環境]**  >  **[プレビュー機能]** に移動し、 **[Use the preview Windows Forms designer for .NET Core apps]\(プレビュー版 Windows フォーム デザイナー (.NET Core アプリ) を使用する\)** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="959cd-130">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

### <a name="consider"></a><span data-ttu-id="959cd-131">次の例を考えてみましょう</span><span class="sxs-lookup"><span data-stu-id="959cd-131">Consider</span></span>

<span data-ttu-id="959cd-132">.NET Framework Windows Forms アプリケーションを移植するときは、いくつかの点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="959cd-133">アプリケーションが移行に適した候補であることを確認する。</span><span class="sxs-lookup"><span data-stu-id="959cd-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="959cd-134">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) を使用して、プロジェクトを .NET Core 3.0 に移行できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="959cd-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="959cd-135">プロジェクトが .NET Core 3.0 では問題が発生する場合は、アナライザーによってこれらの問題を特定できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="959cd-136">Windows Forms の別のバージョンを使用している。</span><span class="sxs-lookup"><span data-stu-id="959cd-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="959cd-137">.NET Core 3.0 Preview 1 がリリースされたときに、Windows フォームは GitHub でオープン ソースになりました。</span><span class="sxs-lookup"><span data-stu-id="959cd-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="959cd-138">.NET Core Windows フォームのコードは、.NET Framework Windows フォーム コード ベースからの 1 つの分岐です。</span><span class="sxs-lookup"><span data-stu-id="959cd-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="959cd-139">違いの存在によって、アプリが移植されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="959cd-140">[Windows 互換機能パック][compat-pack]が移行に役立つ可能性がある。</span><span class="sxs-lookup"><span data-stu-id="959cd-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="959cd-141">.NET Framework で利用できる一部の API は、.NET Core 3.0 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="959cd-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="959cd-142">[Windows 互換機能パック][compat-pack]によって多数の API が追加され、Windows Forms アプリの .NET Core との互換性が促進される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="959cd-143">自分のプロジェクトで使用されている NuGet パッケージを更新する。</span><span class="sxs-lookup"><span data-stu-id="959cd-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="959cd-144">移行する前に、常に NuGet パッケージの最新バージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="959cd-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="959cd-145">アプリケーションで NuGet パッケージを参照している場合は、最新バージョンに更新してください。</span><span class="sxs-lookup"><span data-stu-id="959cd-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="959cd-146">アプリケーションが正常にビルドされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="959cd-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="959cd-147">アップグレード後にパッケージ エラーが発生した場合は、コードを壊さない最新のバージョンにパッケージをダウングレードします。</span><span class="sxs-lookup"><span data-stu-id="959cd-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="959cd-148">新しい SDK プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="959cd-148">Create a new SDK project</span></span>

<span data-ttu-id="959cd-149">作成する新しい .NET Core 3.0 プロジェクトは、.NET Framework プロジェクトとは別のディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-149">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="959cd-150">両方が同じディレクトリに配置されている場合は、**obj** ディレクトリ内に生成されているファイルと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-150">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="959cd-151">この例では、**SolutionFolder** ディレクトリに **MyFormsAppCore** という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="959cd-151">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="959cd-152">次に、**MyFormsAppCore** ディレクトリに **MyFormsCore.csproj** プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-152">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="959cd-153">このファイルは、任意のテキスト エディターを使用して手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-153">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="959cd-154">次の XML に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="959cd-154">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="959cd-155">プロジェクト ファイルを手動で作成しない場合は、Visual Studio または .NET Core SDK を使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-155">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="959cd-156">ただし、プロジェクト ファイル以外のプロジェクト テンプレートによって生成されるすべてのファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-156">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="959cd-157">SDK を使用するには、次のコマンドを **SolutionFolder** ディレクトリから実行します。</span><span class="sxs-lookup"><span data-stu-id="959cd-157">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="959cd-158">**MyFormsCore.csproj** を作成した後、ディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="959cd-158">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="959cd-159">**SolutionFolder** ディレクトリから Visual Studio または .NET Core CLI を使用して、**MyFormsCore.csproj** プロジェクトを **MyApps.sln** に追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-159">Add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="959cd-160">アセンブリ情報の生成を修正する</span><span class="sxs-lookup"><span data-stu-id="959cd-160">Fix assembly info generation</span></span>

<span data-ttu-id="959cd-161">.NET Framework で作成された Windows Forms プロジェクトには、生成されるアセンブリのバージョンなどのアセンブリの属性を格納する `AssemblyInfo.cs` ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="959cd-161">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="959cd-162">SDK スタイルのプロジェクトでは、SDK プロジェクト ファイルに基づいて、この情報が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-162">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="959cd-163">両方の種類の "アセンブリ情報" があると、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="959cd-163">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="959cd-164">この問題は、自動生成を無効にして、既存の `AssemblyInfo.cs` ファイルをプロジェクトに強制的に使用させることで解決します。</span><span class="sxs-lookup"><span data-stu-id="959cd-164">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="959cd-165">メインの `<PropertyGroup>` ノードに追加する 3 つの設定があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-165">There are three settings to add to the main `<PropertyGroup>` node.</span></span>

- <span data-ttu-id="959cd-166">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="959cd-166">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="959cd-167">このプロパティを `false` に設定すると、アセンブリ属性が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="959cd-167">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="959cd-168">これにより、.NET Framework プロジェクトからの既存の `AssemblyInfo.cs` ファイルとの競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-168">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="959cd-169">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="959cd-169">**AssemblyName**</span></span>\
<span data-ttu-id="959cd-170">このプロパティの値は、コンパイル時に作成される出力バイナリです。</span><span class="sxs-lookup"><span data-stu-id="959cd-170">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="959cd-171">名前には、拡張子を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="959cd-171">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="959cd-172">たとえば、`MyCoreApp` を使用すると、`MyCoreApp.exe` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-172">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="959cd-173">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="959cd-173">**RootNamespace**</span></span>\
<span data-ttu-id="959cd-174">プロジェクトで使用される既定の名前空間。</span><span class="sxs-lookup"><span data-stu-id="959cd-174">The default namespace used by your project.</span></span> <span data-ttu-id="959cd-175">これは、.NET Framework プロジェクトの既定の名前空間と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-175">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="959cd-176">これら 3 つの要素を、`MyFormsCore.csproj` ファイルの `<PropertyGroup>` ノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-176">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="959cd-177">ソース コードを追加する</span><span class="sxs-lookup"><span data-stu-id="959cd-177">Add source code</span></span>

<span data-ttu-id="959cd-178">現時点では、**MyFormsCore.csproj** プロジェクトには、コンパイルされるコードはありません。</span><span class="sxs-lookup"><span data-stu-id="959cd-178">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="959cd-179">既定では、.NET Core プロジェクトには、現在のディレクトリとすべての子ディレクトリ内のすべてのソース コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="959cd-179">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="959cd-180">相対パスを使用して、.NET Framework プロジェクトのコードが含まれるようにプロジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-180">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="959cd-181">.NET Framework プロジェクトで、フォームのアイコンとリソース用の **.resx** ファイルが使用されている場合は、それらも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-181">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span>

<span data-ttu-id="959cd-182">次の `<ItemGroup>` コードを、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-182">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="959cd-183">各ステートメントには、子ディレクトリを含むファイルの glob パターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="959cd-183">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="959cd-184">または、.NET Framework プロジェクトの各ファイルに対する `<Compile>` または `<EmbeddedResource>` エントリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-184">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="959cd-185">NuGet パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="959cd-185">Add NuGet packages</span></span>

<span data-ttu-id="959cd-186">.NET Framework プロジェクトによって参照される各 NuGet パッケージを.NET Core プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-186">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span>

<span data-ttu-id="959cd-187">ほとんどの場合、.NET Framework Windows Forms アプリには、**packages.config** プロジェクトによって参照されるすべての NuGet パッケージの一覧を含むファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="959cd-187">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="959cd-188">この一覧を調べて、.NET Core プロジェクトに追加する NuGet パッケージを決定できます。</span><span class="sxs-lookup"><span data-stu-id="959cd-188">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="959cd-189">たとえば、.NET Framework プロジェクトで `MetroFramework`、`MetroFramework.Design`、および `MetroFramework.Fonts` NuGet パッケージが参照されている場合は、**SolutionFolder** ディレクトリから Visual Studio または .NET Core CLI のいずれかを使用して、それぞれをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-189">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="959cd-190">上のコマンドによって、次の NuGet 参照が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-190">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="959cd-191">移植制御ライブラリ</span><span class="sxs-lookup"><span data-stu-id="959cd-191">Port control libraries</span></span>

<span data-ttu-id="959cd-192">Windows Forms 制御ライブラリ プロジェクトを移植する場合の指示は、.NET Framework Windows Forms アプリ プロジェクトの移植と同じですが、いくつかの設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="959cd-192">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="959cd-193">また、実行可能ファイルにコンパイルするのではなく、ライブラリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="959cd-193">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="959cd-194">実行可能プロジェクトとライブラリ プロジェクト間の違いは、ソース コードを含むファイルの glob パス以外はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="959cd-194">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="959cd-195">前の手順の例を使用して、作業するプロジェクトとファイルを展開しましょう。</span><span class="sxs-lookup"><span data-stu-id="959cd-195">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="959cd-196">ファイル</span><span class="sxs-lookup"><span data-stu-id="959cd-196">File</span></span> | <span data-ttu-id="959cd-197">説明</span><span class="sxs-lookup"><span data-stu-id="959cd-197">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="959cd-198">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="959cd-198">**MyApps.sln**</span></span> | <span data-ttu-id="959cd-199">ソリューション ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-199">The name of the solution file.</span></span> |
| <span data-ttu-id="959cd-200">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="959cd-200">**MyControls.csproj**</span></span> | <span data-ttu-id="959cd-201">移植する .NET Framework Windows Forms 制御プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-201">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="959cd-202">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="959cd-202">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="959cd-203">作成する新しい .NET Core ライブラリ プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="959cd-203">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="959cd-204">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="959cd-204">**MyCoreControls.dll**</span></span> | <span data-ttu-id="959cd-205">.NET Core Windows Forms 制御ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="959cd-205">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="959cd-206">`MyControlsCore.csproj` プロジェクトと前に作成した `MyFormsCore.csproj` プロジェクト間の違いを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="959cd-206">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="959cd-207">.NET Core Windows Forms 制御ライブラリ プロジェクト ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="959cd-207">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="959cd-208">ご覧のとおり、`<OutputType>` ノードが削除され、コンパイラでは、実行可能ファイルではなくライブラリが既定で生成されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-208">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="959cd-209">`<AssemblyName>` と `<RootNamespace>` が変更されました。</span><span class="sxs-lookup"><span data-stu-id="959cd-209">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="959cd-210">具体的には、`<RootNamespace>` が、移植する Windows Forms 制御ライブラリの名前空間と一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="959cd-210">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="959cd-211">最後に、`<Compile>` と `<EmbeddedResource>` ノードが、移植する Windows Forms 制御ライブラリのフォルダーを指すように調整されました。</span><span class="sxs-lookup"><span data-stu-id="959cd-211">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="959cd-212">次に、メインの .NET Core **MyFormsCore.csproj** プロジェクトに、新しい .NET Core Windows フォーム コントロール ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-212">Next, in the main .NET Core **MyFormsCore.csproj** project, add a reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="959cd-213">**SolutionFolder** ディレクトリから、Visual Studio または .NET Core CLI のいずれかを使用して、参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-213">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="959cd-214">前のコマンドにより、以下が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-214">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a><span data-ttu-id="959cd-215">コンパイルの問題</span><span class="sxs-lookup"><span data-stu-id="959cd-215">Compilation problems</span></span>

<span data-ttu-id="959cd-216">プロジェクトのコンパイルで問題が発生した場合は、.NET Framework では使用できるが .NET Core では使用できない Windows 専用 API が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="959cd-216">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="959cd-217">[Windows 互換機能パック][compat-pack] NuGet パッケージのプロジェクトへの追加を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="959cd-217">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="959cd-218">このパッケージは Windows でのみ実行され、約 20,000 の Windows API を .NET Core と .NET Standard プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="959cd-218">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="959cd-219">前のコマンドにより、以下が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-219">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="959cd-220">Windows フォーム デザイナー</span><span class="sxs-lookup"><span data-stu-id="959cd-220">Windows Forms Designer</span></span>

<span data-ttu-id="959cd-221">この記事で説明したように、Visual Studio 2019 では、.NET Framework プロジェクトでのみフォーム デザイナーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="959cd-221">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="959cd-222">サイドバイサイドの .NET Core プロジェクトを作成することで、.NET Framework プロジェクトを使用してフォームをデザインしながら、.NET Core でプロジェクトをテストできます。</span><span class="sxs-lookup"><span data-stu-id="959cd-222">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="959cd-223">ソリューション ファイルには、.NET Framework と .NET Core の両方のプロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="959cd-223">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="959cd-224">.NET Framework プロジェクトにフォームとコントロールを追加してデザインし、.NET Core プロジェクトに追加されたファイルの glob パターンに基づいて、新しいファイルまたは変更されたファイルが、.NET Core プロジェクトに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="959cd-224">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="959cd-225">Visual Studio 2019 で Windows Forms デザイナーがサポートされるようになったら、.NET Core プロジェクト ファイルの内容を .NET Framework プロジェクト ファイルにコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="959cd-225">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="959cd-226">その後、`<Source>` と `<EmbeddedResource>` 項目を使用して追加されたファイルの glob パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="959cd-226">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="959cd-227">アプリで使用されるすべてのプロジェクト参照のパスを修正します。</span><span class="sxs-lookup"><span data-stu-id="959cd-227">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="959cd-228">これにより、.NET Framework プロジェクトが .NET Core プロジェクトに効率的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="959cd-228">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="959cd-229">次の手順</span><span class="sxs-lookup"><span data-stu-id="959cd-229">Next steps</span></span>

- <span data-ttu-id="959cd-230">[.NET Framework から .NET Core への破壊的変更](../compatibility/fx-core.md)について学習する。</span><span class="sxs-lookup"><span data-stu-id="959cd-230">Learn about [breaking changes from .NET Framework to .NET Core](../compatibility/fx-core.md).</span></span>
- <span data-ttu-id="959cd-231">[Windows 互換機能パック][compat-pack]の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="959cd-231">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="959cd-232">.NET Framework Windows Forms プロジェクトの .NET Core への[移植に関するビデオ](https://www.youtube.com/watch?v=upVQEUc_KwU)を視聴する。</span><span class="sxs-lookup"><span data-stu-id="959cd-232">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
