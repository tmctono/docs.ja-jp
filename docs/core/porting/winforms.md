---
title: Windows Forms アプリを .NET Core 3.0 に移植する
description: .NET Framework Windows Forms アプリケーションを .NET Core 3.0 for Windows に移植する方法について説明します。
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.custom: ''
ms.openlocfilehash: 64920f1d226fcc8265d0be252d4751f2ba278cc1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973288"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="c3eee-103">Windows フォーム デスクトップ アプリを .NET Core に移植する方法</span><span class="sxs-lookup"><span data-stu-id="c3eee-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="c3eee-104">この記事では、Windows Forms ベースのデスクトップ アプリを、.NET Framework から .NET Core 3.0 に移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="c3eee-105">.NET Core 3.0 SDK には、Windows Forms アプリケーションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3eee-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="c3eee-106">Windows Forms は、まだ Windows 専用のフレームワークであるため、Windows 上でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="c3eee-107">この例では、.NET Core CLI を使用して、プロジェクトの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="c3eee-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="c3eee-108">この記事では、さまざまな名前が使用して、移行で使用されるファイルの種類を識別しています。</span><span class="sxs-lookup"><span data-stu-id="c3eee-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="c3eee-109">実際のファイルの名前とは異なっているため、自分のプロジェクトを移行するときは、次の一覧の名前に置き換えて説明をお読みください。</span><span class="sxs-lookup"><span data-stu-id="c3eee-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="c3eee-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="c3eee-110">File</span></span> | <span data-ttu-id="c3eee-111">説明</span><span class="sxs-lookup"><span data-stu-id="c3eee-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="c3eee-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="c3eee-112">**MyApps.sln**</span></span> | <span data-ttu-id="c3eee-113">ソリューション ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-113">The name of the solution file.</span></span> |
| <span data-ttu-id="c3eee-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="c3eee-114">**MyForms.csproj**</span></span> | <span data-ttu-id="c3eee-115">移植する .NET Framework Windows Forms プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="c3eee-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="c3eee-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="c3eee-117">作成する新しい .NET Core プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="c3eee-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="c3eee-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="c3eee-119">.NET Core Windows Forms アプリの実行可能ファイル。</span><span class="sxs-lookup"><span data-stu-id="c3eee-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="c3eee-120">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c3eee-120">Prerequisites</span></span>

- <span data-ttu-id="c3eee-121">実行したいデザイナー作業用の [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="c3eee-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="c3eee-122">次の Visual Studio ワークロードをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3eee-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="c3eee-123">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="c3eee-123">.NET desktop development</span></span>
  - <span data-ttu-id="c3eee-124">.NET クロスプラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="c3eee-124">.NET cross-platform development</span></span>

- <span data-ttu-id="c3eee-125">問題なくビルドされて実行されているソリューション内の作業用 Windows Forms プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c3eee-125">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="c3eee-126">プロジェクトは C# でコーディングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="c3eee-127">最新の [.NET Core 3.0](https://aka.ms/netcore3download) のプレビューをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3eee-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="c3eee-128">**Visual Studio 2017** では、.NET Core 3.0 プロジェクトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c3eee-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="c3eee-129">**Visual Studio 2019** では .NET Core 3.0 プロジェクトはサポートされていますが、.NET Core 3.0 Windows Forms プロジェクト用のビジュアル デザイナーはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c3eee-129">**Visual Studio 2019** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 Windows Forms projects.</span></span> <span data-ttu-id="c3eee-130">ビジュアル デザイナーを使用するには、.NET Core プロジェクトとフォーム ファイルを共有するソリューション内に .NET Windows Forms プロジェクトを配置する必要です。</span><span class="sxs-lookup"><span data-stu-id="c3eee-130">To use the visual designer, you must have a .NET Windows Forms project in your solution that shares the forms files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="c3eee-131">次の例を考えてみましょう</span><span class="sxs-lookup"><span data-stu-id="c3eee-131">Consider</span></span>

<span data-ttu-id="c3eee-132">.NET Framework Windows Forms アプリケーションを移植するときは、いくつかの点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="c3eee-133">アプリケーションが移行に適した候補であることを確認する。</span><span class="sxs-lookup"><span data-stu-id="c3eee-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="c3eee-134">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) を使用して、プロジェクトを .NET Core 3.0 に移行できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="c3eee-135">プロジェクトが .NET Core 3.0 では問題が発生する場合は、アナライザーによってこれらの問題を特定できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="c3eee-136">Windows Forms の別のバージョンを使用している。</span><span class="sxs-lookup"><span data-stu-id="c3eee-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="c3eee-137">.NET Core 3.0 Preview 1 がリリースされたときに、Windows フォームは GitHub でオープン ソースになりました。</span><span class="sxs-lookup"><span data-stu-id="c3eee-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="c3eee-138">.NET Core Windows フォームのコードは、.NET Framework Windows フォーム コード ベースからの 1 つの分岐です。</span><span class="sxs-lookup"><span data-stu-id="c3eee-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="c3eee-139">違いの存在によって、アプリが移植されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="c3eee-140">[Windows 互換機能パック][compat-pack]が移行に役立つ可能性がある。</span><span class="sxs-lookup"><span data-stu-id="c3eee-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="c3eee-141">.NET Framework で利用できる一部の API は、.NET Core 3.0 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="c3eee-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="c3eee-142">[Windows 互換機能パック][compat-pack]によって多数の API が追加され、Windows Forms アプリの .NET Core との互換性が促進される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="c3eee-143">自分のプロジェクトで使用されている NuGet パッケージを更新する。</span><span class="sxs-lookup"><span data-stu-id="c3eee-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="c3eee-144">移行する前に、常に NuGet パッケージの最新バージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3eee-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="c3eee-145">アプリケーションで NuGet パッケージを参照している場合は、最新バージョンに更新してください。</span><span class="sxs-lookup"><span data-stu-id="c3eee-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="c3eee-146">アプリケーションが正常にビルドされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="c3eee-147">アップグレード後にパッケージ エラーが発生した場合は、コードを壊さない最新のバージョンにパッケージをダウングレードします。</span><span class="sxs-lookup"><span data-stu-id="c3eee-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="c3eee-148">Visual Studio 2019 では、.NET Core 3.0 のフォーム デザイナーはまだサポートされていない</span><span class="sxs-lookup"><span data-stu-id="c3eee-148">Visual Studio 2019 doesn't yet support the Forms Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="c3eee-149">現時点では、Visual Studio のフォーム デザイナーを使用する場合は、既存の .NET Framework Windows Forms プロジェクト ファイルを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-149">Currently, you need to keep your existing .NET Framework Windows Forms project file if you want to use the Forms Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="c3eee-150">新しい SDK プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c3eee-150">Create a new SDK project</span></span>

<span data-ttu-id="c3eee-151">作成する新しい .NET Core 3.0 プロジェクトは、.NET Framework プロジェクトとは別のディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="c3eee-152">両方が同じディレクトリに配置されている場合は、**obj** ディレクトリ内に生成されているファイルと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="c3eee-153">この例では、**SolutionFolder** ディレクトリに **MyFormsAppCore** という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-153">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="c3eee-154">次に、**MyFormsAppCore** ディレクトリに **MyFormsCore.csproj** プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-154">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="c3eee-155">このファイルは、任意のテキスト エディターを使用して手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="c3eee-156">次の XML に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="c3eee-157">プロジェクト ファイルを手動で作成しない場合は、Visual Studio または .NET Core SDK を使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="c3eee-158">ただし、プロジェクト ファイル以外のプロジェクト テンプレートによって生成されるすべてのファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="c3eee-159">SDK を使用するには、次のコマンドを **SolutionFolder** ディレクトリから実行します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="c3eee-160">**MyFormsCore.csproj** を作成した後、ディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-160">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="c3eee-161">**SolutionFolder** ディレクトリから Visual Studio または .NET Core CLI を使用して、**MyFormsCore.csproj** プロジェクトを **MyApps.sln** に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-161">You'll want to add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="c3eee-162">アセンブリ情報の生成を修正する</span><span class="sxs-lookup"><span data-stu-id="c3eee-162">Fix assembly info generation</span></span>

<span data-ttu-id="c3eee-163">.NET Framework で作成された Windows Forms プロジェクトには、生成されるアセンブリのバージョンなどのアセンブリの属性を格納する `AssemblyInfo.cs` ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3eee-163">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="c3eee-164">SDK スタイルのプロジェクトでは、SDK プロジェクト ファイルに基づいて、この情報が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="c3eee-165">両方の種類の "アセンブリ情報" があると、競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="c3eee-166">この問題は、自動生成を無効にして、既存の `AssemblyInfo.cs` ファイルをプロジェクトに強制的に使用させることで解決します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="c3eee-167">メインの `<PropertyGroup>` ノードに追加する 3 つの設定があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="c3eee-168">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="c3eee-168">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="c3eee-169">このプロパティを `false` に設定すると、アセンブリ属性が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="c3eee-170">これにより、.NET Framework プロジェクトからの既存の `AssemblyInfo.cs` ファイルとの競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="c3eee-171">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="c3eee-171">**AssemblyName**</span></span>\
<span data-ttu-id="c3eee-172">このプロパティの値は、コンパイル時に作成される出力バイナリです。</span><span class="sxs-lookup"><span data-stu-id="c3eee-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="c3eee-173">名前には、拡張子を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3eee-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="c3eee-174">たとえば、`MyCoreApp` を使用すると、`MyCoreApp.exe` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="c3eee-175">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="c3eee-175">**RootNamespace**</span></span>\
<span data-ttu-id="c3eee-176">プロジェクトで使用される既定の名前空間。</span><span class="sxs-lookup"><span data-stu-id="c3eee-176">The default namespace used by your project.</span></span> <span data-ttu-id="c3eee-177">これは、.NET Framework プロジェクトの既定の名前空間と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="c3eee-178">これら 3 つの要素を、`MyFormsCore.csproj` ファイルの `<PropertyGroup>` ノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-178">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

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

## <a name="add-source-code"></a><span data-ttu-id="c3eee-179">ソース コードを追加する</span><span class="sxs-lookup"><span data-stu-id="c3eee-179">Add source code</span></span>

<span data-ttu-id="c3eee-180">現時点では、**MyFormsCore.csproj** プロジェクトには、コンパイルされるコードはありません。</span><span class="sxs-lookup"><span data-stu-id="c3eee-180">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="c3eee-181">既定では、.NET Core プロジェクトには、現在のディレクトリとすべての子ディレクトリ内のすべてのソース コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="c3eee-182">相対パスを使用して、.NET Framework プロジェクトのコードが含まれるようにプロジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="c3eee-183">.NET Framework プロジェクトで、フォームのアイコンとリソース用の **.resx** ファイルが使用されている場合は、それらも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-183">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span> 

<span data-ttu-id="c3eee-184">次の `<ItemGroup>` コードを、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-184">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="c3eee-185">各ステートメントには、子ディレクトリを含むファイルの glob パターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3eee-185">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="c3eee-186">または、.NET Framework プロジェクトの各ファイルに対する `<Compile>` または `<EmbeddedResource>` エントリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-186">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="c3eee-187">NuGet パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="c3eee-187">Add NuGet packages</span></span>

<span data-ttu-id="c3eee-188">.NET Framework プロジェクトによって参照される各 NuGet パッケージを.NET Core プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-188">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="c3eee-189">ほとんどの場合、.NET Framework Windows Forms アプリには、**packages.config** プロジェクトによって参照されるすべての NuGet パッケージの一覧を含むファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-189">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="c3eee-190">この一覧を調べて、.NET Core プロジェクトに追加する NuGet パッケージを決定できます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-190">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="c3eee-191">たとえば、.NET Framework プロジェクトで `MetroFramework`、`MetroFramework.Design`、および `MetroFramework.Fonts` NuGet パッケージが参照されている場合は、**SolutionFolder** ディレクトリから Visual Studio または .NET Core CLI のいずれかを使用して、それぞれをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-191">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="c3eee-192">上のコマンドによって、次の NuGet 参照が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-192">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="c3eee-193">移植制御ライブラリ</span><span class="sxs-lookup"><span data-stu-id="c3eee-193">Port control libraries</span></span>

<span data-ttu-id="c3eee-194">Windows Forms 制御ライブラリ プロジェクトを移植する場合の指示は、.NET Framework Windows Forms アプリ プロジェクトの移植と同じですが、いくつかの設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-194">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="c3eee-195">また、実行可能ファイルにコンパイルするのではなく、ライブラリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="c3eee-195">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="c3eee-196">実行可能プロジェクトとライブラリ プロジェクト間の違いは、ソース コードを含むファイルの glob パス以外はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="c3eee-196">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="c3eee-197">前の手順の例を使用して、作業するプロジェクトとファイルを展開しましょう。</span><span class="sxs-lookup"><span data-stu-id="c3eee-197">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="c3eee-198">ファイル</span><span class="sxs-lookup"><span data-stu-id="c3eee-198">File</span></span> | <span data-ttu-id="c3eee-199">説明</span><span class="sxs-lookup"><span data-stu-id="c3eee-199">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="c3eee-200">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="c3eee-200">**MyApps.sln**</span></span> | <span data-ttu-id="c3eee-201">ソリューション ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-201">The name of the solution file.</span></span> |
| <span data-ttu-id="c3eee-202">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="c3eee-202">**MyControls.csproj**</span></span> | <span data-ttu-id="c3eee-203">移植する .NET Framework Windows Forms 制御プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-203">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="c3eee-204">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="c3eee-204">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="c3eee-205">作成する新しい .NET Core ライブラリ プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="c3eee-205">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="c3eee-206">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="c3eee-206">**MyCoreControls.dll**</span></span> | <span data-ttu-id="c3eee-207">.NET Core Windows Forms 制御ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="c3eee-207">The .NET Core Windows Forms Controls library.</span></span> |

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

<span data-ttu-id="c3eee-208">`MyControlsCore.csproj` プロジェクトと前に作成した `MyFormsCore.csproj` プロジェクト間の違いを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="c3eee-208">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

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

<span data-ttu-id="c3eee-209">.NET Core Windows Forms 制御ライブラリ プロジェクト ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-209">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

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

<span data-ttu-id="c3eee-210">ご覧のとおり、`<OutputType>` ノードが削除され、コンパイラでは、実行可能ファイルではなくライブラリが既定で生成されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-210">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="c3eee-211">`<AssemblyName>` と `<RootNamespace>` が変更されました。</span><span class="sxs-lookup"><span data-stu-id="c3eee-211">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="c3eee-212">具体的には、`<RootNamespace>` が、移植する Windows Forms 制御ライブラリの名前空間と一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="c3eee-212">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="c3eee-213">最後に、`<Compile>` と `<EmbeddedResource>` ノードが、移植する Windows Forms 制御ライブラリのフォルダーを指すように調整されました。</span><span class="sxs-lookup"><span data-stu-id="c3eee-213">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="c3eee-214">次に、メインの .NET Core **MyFormsCore.csproj** プロジェクトに、新しい .NET Core Windows Forms 制御ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-214">Next, in the main .NET Core **MyFormsCore.csproj** project add reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="c3eee-215">**SolutionFolder** ディレクトリから、Visual Studio または .NET Core CLI のいずれかを使用して、参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-215">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="c3eee-216">前のコマンドにより、以下が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-216">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="c3eee-217">コンパイルの問題</span><span class="sxs-lookup"><span data-stu-id="c3eee-217">Problems compiling</span></span>

<span data-ttu-id="c3eee-218">プロジェクトのコンパイルで問題が発生した場合は、.NET Framework では使用できるが .NET Core では使用できない Windows 専用 API が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3eee-218">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="c3eee-219">[Windows 互換機能パック][compat-pack] NuGet パッケージのプロジェクトへの追加を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-219">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="c3eee-220">このパッケージは Windows でのみ実行され、約 20,000 の Windows API を .NET Core と .NET Standard プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-220">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="c3eee-221">前のコマンドにより、以下が **MyFormsCore.csproj** プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-221">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="c3eee-222">Windows フォーム デザイナー</span><span class="sxs-lookup"><span data-stu-id="c3eee-222">Windows Forms Designer</span></span>

<span data-ttu-id="c3eee-223">この記事で説明したように、Visual Studio 2019 では、.NET Framework プロジェクトでのみフォーム デザイナーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-223">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="c3eee-224">サイドバイサイドの .NET Core プロジェクトを作成することで、.NET Framework プロジェクトを使用してフォームをデザインしながら、.NET Core でプロジェクトをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-224">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="c3eee-225">ソリューション ファイルには、.NET Framework と .NET Core の両方のプロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-225">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="c3eee-226">.NET Framework プロジェクトにフォームとコントロールを追加してデザインし、.NET Core プロジェクトに追加されたファイルの glob パターンに基づいて、新しいファイルまたは変更されたファイルが、.NET Core プロジェクトに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-226">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="c3eee-227">Visual Studio 2019 で Windows Forms デザイナーがサポートされるようになったら、.NET Core プロジェクト ファイルの内容を .NET Framework プロジェクト ファイルにコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-227">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="c3eee-228">その後、`<Source>` と `<EmbeddedResource>` 項目を使用して追加されたファイルの glob パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-228">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="c3eee-229">アプリで使用されるすべてのプロジェクト参照のパスを修正します。</span><span class="sxs-lookup"><span data-stu-id="c3eee-229">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="c3eee-230">これにより、.NET Framework プロジェクトが .NET Core プロジェクトに効率的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="c3eee-230">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="c3eee-231">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3eee-231">Next steps</span></span>

- <span data-ttu-id="c3eee-232">[Windows 互換機能パック][compat-pack]の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="c3eee-232">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="c3eee-233">.NET Framework Windows Forms プロジェクトの .NET Core への[移植に関するビデオ](https://www.youtube.com/watch?v=upVQEUc_KwU)を視聴する。</span><span class="sxs-lookup"><span data-stu-id="c3eee-233">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
