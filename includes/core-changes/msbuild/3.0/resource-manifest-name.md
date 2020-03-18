---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968182"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="0f217-101">リソース マニフェストのファイル名</span><span class="sxs-lookup"><span data-stu-id="0f217-101">Resource manifest file names</span></span>

<span data-ttu-id="0f217-102">.NET Core 3.0 以降、生成されるリソース マニフェストのファイル名が変更されています。</span><span class="sxs-lookup"><span data-stu-id="0f217-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0f217-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="0f217-103">Version introduced</span></span>

<span data-ttu-id="0f217-104">3.0</span><span class="sxs-lookup"><span data-stu-id="0f217-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="0f217-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="0f217-105">Change description</span></span>

<span data-ttu-id="0f217-106">.NET Core 3.0 より前は、[DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) メタデータが MSBuild プロジェクト ファイルのリソース ( *.resx*) ファイルに対して設定された場合、生成されるマニフェスト名は *Namespace.Classname.resources* でした。</span><span class="sxs-lookup"><span data-stu-id="0f217-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="0f217-107">[DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) が設定されなかった場合、生成されるマニフェスト名は *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources* でした。</span><span class="sxs-lookup"><span data-stu-id="0f217-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="0f217-108">.NET Core 3.0 以降、たとえば Windows フォーム アプリで *.resx* ファイルが同じ名前のソース ファイルと併置される場合、リソース マニフェスト名は、ソース ファイル内の最初の型のフル ネームから生成されます。</span><span class="sxs-lookup"><span data-stu-id="0f217-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="0f217-109">たとえば、*Type.cs* が *Type.resx* と併置される場合、生成されるマニフェスト名は *Namespace.Classname.resources* になります。</span><span class="sxs-lookup"><span data-stu-id="0f217-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="0f217-110">ただし、 *.resx* ファイルの `EmbeddedResource` プロパティの属性を変更した場合、生成されるマニフェスト ファイル名は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f217-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="0f217-111">`EmbeddedResource` プロパティの `LogicalName` 属性が設定されている場合は、その値がリソース マニフェストのファイル名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f217-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="0f217-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f217-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="0f217-113">**生成されるリソース マニフェストのファイル名**:*SomeName.resources* ( *.resx* ファイル名、カルチャ、またはその他のメタデータには関係しません)。</span><span class="sxs-lookup"><span data-stu-id="0f217-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="0f217-114">`LogicalName` は設定されていないが、`EmbeddedResource` プロパティの `ManifestResourceName` 属性が設定されている場合は、その値とファイル拡張子 *.resources* の組み合わせがリソース マニフェストのファイル名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f217-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="0f217-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f217-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="0f217-116">**生成されるリソース マニフェストのファイル名**:*SomeName.resources* または *SomeName.fr-FR.resources*。</span><span class="sxs-lookup"><span data-stu-id="0f217-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="0f217-117">前の規則が適用されず、`EmbeddedResource` 要素の `DependentUpon` 属性がソース ファイルに設定されている場合、ソース ファイル内の最初のクラスの型名がリソース マニフェストのファイル名の中で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f217-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="0f217-118">具体的には、生成されるファイル名は *Namespace.Classname\[.Culture].resources* になります。</span><span class="sxs-lookup"><span data-stu-id="0f217-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="0f217-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f217-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="0f217-120">**生成されるリソース マニフェストのファイル名**:*Namespace.Classname.resources* または *Namespace.Classname.fr-FR.resources* (この `Namespace.Classname` が *MyTypes.cs* 内の最初のクラスの名前です)。</span><span class="sxs-lookup"><span data-stu-id="0f217-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="0f217-121">前の規則が適用されず、`EmbeddedResourceUseDependentUponConvention` が `true` であり (.NET Core の既定値)、同じ基本ファイル名を持つ *.resx* ファイルと併置されるソース ファイルが存在する場合、 *.resx* ファイルは一致するソース ファイルに依存し、生成される名前は前の規則と同じになります。</span><span class="sxs-lookup"><span data-stu-id="0f217-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="0f217-122">これは、.NET Core プロジェクトの "既定の設定" 規則です。</span><span class="sxs-lookup"><span data-stu-id="0f217-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="0f217-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f217-123">Examples:</span></span>
  
  <span data-ttu-id="0f217-124">*MyTypes.cs* ファイル、*MyTypes.resx* ファイル、*MyTypes.fr-FR.resx* ファイルが同じフォルダーに存在します。</span><span class="sxs-lookup"><span data-stu-id="0f217-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="0f217-125">**生成されるリソース マニフェストのファイル名**:*Namespace.Classname.resources* または *Namespace.Classname.fr-FR.resources* (この `Namespace.Classname` が *MyTypes.cs* 内の最初のクラスの名前です)。</span><span class="sxs-lookup"><span data-stu-id="0f217-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="0f217-126">上記の規則のいずれも当てはまらない場合、生成されるリソース マニフェストのファイル名は *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources* になります。</span><span class="sxs-lookup"><span data-stu-id="0f217-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="0f217-127">相対パスは、`EmbeddedResource` 要素の `Link` 属性が設定されていれば、その値になります。</span><span class="sxs-lookup"><span data-stu-id="0f217-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="0f217-128">それ以外の場合、相対パスは、`EmbeddedResource` 要素の `Identity` 属性の値になります。</span><span class="sxs-lookup"><span data-stu-id="0f217-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="0f217-129">Visual Studio では、これはプロジェクト ルートからソリューション エクスプローラー内のファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="0f217-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0f217-130">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="0f217-130">Recommended action</span></span>

<span data-ttu-id="0f217-131">生成されるマニフェスト名に満足できない場合は、以下を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0f217-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="0f217-132">前述の名前付け規則のいずれかに従って、リソース ファイルのメタデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="0f217-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="0f217-133">プロジェクト ファイルで `EmbeddedResourceUseDependentUponConvention` を `false` に設定して、新しい規則全体が無効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="0f217-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="0f217-134">`LogicalName` または `ManifestResourceName` 属性が存在する場合は、生成されるファイル名でそれらの値が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f217-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="0f217-135">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="0f217-135">Category</span></span>

<span data-ttu-id="0f217-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="0f217-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0f217-137">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0f217-137">Affected APIs</span></span>

<span data-ttu-id="0f217-138">N/A</span><span class="sxs-lookup"><span data-stu-id="0f217-138">N/A</span></span>
