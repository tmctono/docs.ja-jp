---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702845"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="4a6ff-101">.NET Core アプリケーションの依存関係を管理する</span><span class="sxs-lookup"><span data-stu-id="4a6ff-101">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="4a6ff-102">この記事では、プロジェクト ファイルを編集するか、CLI を使用して依存関係を追加および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-102">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="4a6ff-103">\<PackageReference> 要素</span><span class="sxs-lookup"><span data-stu-id="4a6ff-103">The \<PackageReference> element</span></span>

<span data-ttu-id="4a6ff-104">`<PackageReference>` プロジェクト ファイル要素の構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-104">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="4a6ff-105">`Include` 属性では、プロジェクトに追加するパッケージの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-105">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="4a6ff-106">`Version` 属性では、取得するバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-106">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="4a6ff-107">バージョンは、[NuGet のバージョン ルール](/nuget/create-packages/dependency-versions#version-ranges)に従って指定します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-107">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="4a6ff-108">プロジェクト ファイルの構文に詳しくない場合は、詳細について、[MSBuild プロジェクトのリファレンス](/visualstudio/msbuild/msbuild-project-file-schema-reference) ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-108">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="4a6ff-109">次の例に示すように、条件を使用して、特定のターゲットでのみ使用できる依存関係を追加します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-109">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="4a6ff-110">前の例の依存関係は、指定されたターゲットでビルドが行われている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-110">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="4a6ff-111">条件の `$(TargetFramework)` は、プロジェクトで設定される MSBuild プロパティです。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-111">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="4a6ff-112">最も一般的な .NET Core アプリケーションの場合、これを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-112">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="4a6ff-113">プロジェクト ファイルを編集して依存関係を追加する</span><span class="sxs-lookup"><span data-stu-id="4a6ff-113">Add a dependency by editing the project file</span></span>

<span data-ttu-id="4a6ff-114">依存関係を追加するには、`<ItemGroup>` 要素内に `<PackageReference>` 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-114">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="4a6ff-115">既存の `<ItemGroup>` に追加するか、新しく作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-115">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="4a6ff-116">次の例では、`dotnet new console` によって作成された既定のコンソール アプリケーション プロジェクトを使用しています。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-116">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="4a6ff-117">CLI を使用して依存関係を追加する</span><span class="sxs-lookup"><span data-stu-id="4a6ff-117">Add a dependency by using the CLI</span></span>

<span data-ttu-id="4a6ff-118">依存関係を追加するには、次の例に示すように、[dotnet add package](dotnet-add-package.md) コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-118">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="4a6ff-119">プロジェクト ファイルを編集して依存関係を削除する</span><span class="sxs-lookup"><span data-stu-id="4a6ff-119">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="4a6ff-120">依存関係を削除するには、プロジェクト ファイルから `<PackageReference>` 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-120">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="4a6ff-121">CLI を使用して依存関係を削除する</span><span class="sxs-lookup"><span data-stu-id="4a6ff-121">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="4a6ff-122">依存関係を削除するには、次の例に示すように、[dotnet remove package](dotnet-remove-package.md) コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a6ff-122">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="4a6ff-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a6ff-123">See also</span></span>

* [<span data-ttu-id="4a6ff-124">プロジェクト ファイルのパッケージ参照</span><span class="sxs-lookup"><span data-stu-id="4a6ff-124">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="4a6ff-125">[dotnet list package コマンド](dotnet-list-package.md)</span><span class="sxs-lookup"><span data-stu-id="4a6ff-125">[dotnet list package command](dotnet-list-package.md)</span></span>
