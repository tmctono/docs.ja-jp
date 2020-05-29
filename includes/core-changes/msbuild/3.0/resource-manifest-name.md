---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206222"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="e8869-101">リソース マニフェストのファイル名の変更</span><span class="sxs-lookup"><span data-stu-id="e8869-101">Resource manifest file name change</span></span>

<span data-ttu-id="e8869-102">.NET Core 3.0 以降では、既定の場合、MSBuild によってリソース ファイルに対して異なるマニフェスト ファイル名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8869-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e8869-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e8869-103">Version introduced</span></span>

<span data-ttu-id="e8869-104">3.0</span><span class="sxs-lookup"><span data-stu-id="e8869-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="e8869-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="e8869-105">Change description</span></span>

<span data-ttu-id="e8869-106">.NET Core 3.0 より前では、プロジェクト ファイルの `EmbeddedResource` 項目に `LogicalName`、`ManifestResourceName`、または `DependentUpon` メタデータが指定されなかった場合、MSBuild ではパターン `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` でマニフェスト ファイル名が生成されていました。</span><span class="sxs-lookup"><span data-stu-id="e8869-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="e8869-107">`RootNamespace` がプロジェクト ファイルで定義されていない場合は、既定でそのプロジェクトの名前になります。</span><span class="sxs-lookup"><span data-stu-id="e8869-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="e8869-108">たとえば、ルート プロジェクト ディレクトリ内の *Form1* という名前のリソース ファイルに対して生成されたマニフェスト名は、*MyProject.Form1.resources* でした。</span><span class="sxs-lookup"><span data-stu-id="e8869-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="e8869-109">.NET Core 3.0 以降では、あるリソース ファイルが同じ名前のソース ファイルと併置されている場合 (たとえば、*Form1.resx* と *Form1.cs*)、MSBuild ではそのソース ファイルの型情報が使用されてパターン `<Namespace>.<ClassName>.resources` でマニフェスト ファイル名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8869-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="e8869-110">名前空間とクラス名は、併置されたソース ファイルの最初の型から抽出されます。</span><span class="sxs-lookup"><span data-stu-id="e8869-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="e8869-111">たとえば、*Form1.cs* という名前のソース ファイルと併置されている *Form1* という名前のリソース ファイルに対して生成されたマニフェスト名は、*MyNamespace.Form1.resources* になります。</span><span class="sxs-lookup"><span data-stu-id="e8869-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="e8869-112">重要な注意点として、.NET Core の以前のバージョンとはファイル名の最初の部分が異なります (*MyProject* ではなく *MyNamespace*)。</span><span class="sxs-lookup"><span data-stu-id="e8869-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="e8869-113">プロジェクト ファイルの `EmbeddedResource` 項目で `LogicalName`、`ManifestResourceName`、または `DependentUpon` メタデータが指定されている場合、この変更はそのリソース ファイルには影響しません。</span><span class="sxs-lookup"><span data-stu-id="e8869-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="e8869-114">この破壊的変更は、.NET Core プロジェクトへの `EmbeddedResourceUseDependentUponConvention` プロパティの追加によって導入されました。</span><span class="sxs-lookup"><span data-stu-id="e8869-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="e8869-115">既定では、リソース ファイルは .NET Core プロジェクト ファイルに明示的にリストされていないため、生成された *.resources* ファイルに名前を付ける方法を指定するための `DependentUpon` メタデータはありません。</span><span class="sxs-lookup"><span data-stu-id="e8869-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="e8869-116">`EmbeddedResourceUseDependentUponConvention` が `true` に設定されている場合 (既定)、MSBuild では併置されたソース ファイルが検索され、そのファイルから名前空間とクラス名が抽出されます。</span><span class="sxs-lookup"><span data-stu-id="e8869-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="e8869-117">`EmbeddedResourceUseDependentUponConvention` を `false` に設定すると、MSBuild では `RootNamespace` と相対ファイル パスを組み合わせた前の動作に従ってマニフェスト名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8869-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e8869-118">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e8869-118">Recommended action</span></span>

<span data-ttu-id="e8869-119">ほとんどの場合、開発者側でアクションを取る必要はなく、アプリは引き続き動作するはずです。</span><span class="sxs-lookup"><span data-stu-id="e8869-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="e8869-120">ただし、この変更によってアプリに影響が出ている場合は、次のいずれかを実行してください。</span><span class="sxs-lookup"><span data-stu-id="e8869-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="e8869-121">新しいマニフェスト名を要求するようにコードを変更する。</span><span class="sxs-lookup"><span data-stu-id="e8869-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="e8869-122">プロジェクト ファイルで `EmbeddedResourceUseDependentUponConvention` を `false` に設定して、新しい名前付け規則を無効にする。</span><span class="sxs-lookup"><span data-stu-id="e8869-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="e8869-123">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e8869-123">Category</span></span>

<span data-ttu-id="e8869-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="e8869-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e8869-125">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e8869-125">Affected APIs</span></span>

<span data-ttu-id="e8869-126">N/A</span><span class="sxs-lookup"><span data-stu-id="e8869-126">N/A</span></span>
