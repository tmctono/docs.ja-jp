---
title: .NET Core ランタイムと SDK をバージョン管理する方法
description: この記事では、.NET Core SDK と ランタイムをバージョン管理する方法について説明します (セマンティック バージョニングと似ています)。
author: bleroy
ms.date: 07/26/2018
ms.custom: seodec18
ms.openlocfilehash: e060eac3a63ff869a2fe51fae0166b75329fcb49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61646866"
---
# <a name="overview-of-how-net-core-is-versioned"></a><span data-ttu-id="c10b7-103">.NET Core をバージョン管理する方法の概要</span><span class="sxs-lookup"><span data-stu-id="c10b7-103">Overview of how .NET Core is versioned</span></span>

<span data-ttu-id="c10b7-104">.NET Core とは .NET Core ランタイムと .NET Core SDK を示しており、これにはアプリケーションを開発するのに必要なツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-104">.NET Core refers to the .NET Core Runtime and the .NET Core SDK, which contains the tools you need to develop applications.</span></span> <span data-ttu-id="c10b7-105">.NET Core SDK は、前のバージョンの .NET Core ランタイムをどれでも使用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-105">.NET Core SDKs are designed to work with any previous version of the .NET Core Runtime.</span></span> <span data-ttu-id="c10b7-106">この記事では、ランタイムおよび SDK のバージョン戦略について説明します。</span><span class="sxs-lookup"><span data-stu-id="c10b7-106">This article explains the runtime and the SDK version strategy.</span></span> <span data-ttu-id="c10b7-107">.NET Standard のバージョン番号については、[.NET Standard](../../standard/net-standard.md#net-implementation-support) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b7-107">An explanation of version numbers for .NET Standard can be found in the article introducing [.NET Standard](../../standard/net-standard.md#net-implementation-support).</span></span>

<span data-ttu-id="c10b7-108">.NET Core ランタイムと .NET Core SDK ではそれぞれ異なるレートで新しい機能が追加されます。一般に、運用環境で使用しているランタイムが .NET Core ランタイムによって変更されるよりも速く、.NET Core SDK でのツールの更新が行われます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-108">The .NET Core Runtime and .NET Core SDK add new features at a different rate - in general the .NET Core SDK provides updated tools more quickly than the .NET Core Runtime changes the runtime you use in production.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="c10b7-109">バージョン管理の詳細</span><span class="sxs-lookup"><span data-stu-id="c10b7-109">Versioning details</span></span>

<span data-ttu-id="c10b7-110">".NET Core 2.1" は、.NET Core ランタイムのバージョン番号を示しています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-110">".NET Core 2.1" refers to the .NET Core Runtime version number.</span></span> <span data-ttu-id="c10b7-111">.NET Core ランタイムでは、バージョン管理に対してメジャー/マイナー/パッチ アプローチが使用されており、これは[セマンティック バージョニング](#semantic-versioning)に従っています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-111">The .NET Core Runtime has a major/minor/patch approach to versioning that follows [semantic versioning](#semantic-versioning).</span></span>

<span data-ttu-id="c10b7-112">.NET Core SDK の場合は、セマンティック バージョニングに従っていません。</span><span class="sxs-lookup"><span data-stu-id="c10b7-112">The .NET Core SDK doesn't follow semantic versioning.</span></span> <span data-ttu-id="c10b7-113">.NET Core SDK の方が速くリリースされます。そのバージョンでは、揃えられたランタイムと SDK 独自のマイナー/パッチ リリースの両方が示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c10b7-113">The .NET Core SDK releases faster and its versions must communicate both the aligned runtime and the SDK's own minor and patch releases.</span></span> <span data-ttu-id="c10b7-114">.NET Core SDK バージョンの 1 番目と 2 番目の位置は、一緒にリリースされる .NET Core ランタイムと揃えられます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-114">The first two positions of the .NET Core SDK version are locked to the .NET Core Runtime it released with.</span></span> <span data-ttu-id="c10b7-115">SDK の各バージョンでは、このランタイムまたはより低いバージョンに対するアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-115">Each version of the SDK can create applications for this runtime or any lower version.</span></span>

<span data-ttu-id="c10b7-116">SDK バージョン番号の 3 番目の位置には、マイナー番号とパッチ番号の両方が示されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-116">The third position of the SDK version number communicates both the minor and patch number.</span></span> <span data-ttu-id="c10b7-117">マイナー バージョンには 100 が乗算されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-117">The minor version is multiplied by 100.</span></span> <span data-ttu-id="c10b7-118">マイナー バージョン 1、パッチ バージョン 2 の場合は、102 と表現されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-118">Minor version 1, patch version 2 would be represented as 102.</span></span> <span data-ttu-id="c10b7-119">最後の 2 桁はパッチの番号を示しています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-119">The final two digits represent the patch number.</span></span> <span data-ttu-id="c10b7-120">たとえば、.NET Core 2.2 のリリースの場合、次の表のようなリリースが作成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c10b7-120">For example, the release of .NET Core 2.2 may create releases like the following table:</span></span>

| <span data-ttu-id="c10b7-121">変更</span><span class="sxs-lookup"><span data-stu-id="c10b7-121">Change</span></span>                | <span data-ttu-id="c10b7-122">.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="c10b7-122">.NET Core Runtime</span></span> | <span data-ttu-id="c10b7-123">.NET Core SDK (\*)</span><span class="sxs-lookup"><span data-stu-id="c10b7-123">.NET Core SDK (\*)</span></span> |
|-----------------------|-------------------|-------------------|
| <span data-ttu-id="c10b7-124">初期リリース</span><span class="sxs-lookup"><span data-stu-id="c10b7-124">Initial release</span></span>       | <span data-ttu-id="c10b7-125">2.2.0</span><span class="sxs-lookup"><span data-stu-id="c10b7-125">2.2.0</span></span>             | <span data-ttu-id="c10b7-126">2.2.100</span><span class="sxs-lookup"><span data-stu-id="c10b7-126">2.2.100</span></span>           |
| <span data-ttu-id="c10b7-127">SDK パッチ</span><span class="sxs-lookup"><span data-stu-id="c10b7-127">SDK Patch</span></span>             | <span data-ttu-id="c10b7-128">2.2.0</span><span class="sxs-lookup"><span data-stu-id="c10b7-128">2.2.0</span></span>             | <span data-ttu-id="c10b7-129">2.2.101</span><span class="sxs-lookup"><span data-stu-id="c10b7-129">2.2.101</span></span>           |
| <span data-ttu-id="c10b7-130">ランタイムおよび SDK パッチ</span><span class="sxs-lookup"><span data-stu-id="c10b7-130">Runtime and SDK Patch</span></span> | <span data-ttu-id="c10b7-131">2.2.1</span><span class="sxs-lookup"><span data-stu-id="c10b7-131">2.2.1</span></span>             | <span data-ttu-id="c10b7-132">2.2.102</span><span class="sxs-lookup"><span data-stu-id="c10b7-132">2.2.102</span></span>           |
| <span data-ttu-id="c10b7-133">SDK 機能変更</span><span class="sxs-lookup"><span data-stu-id="c10b7-133">SDK Feature change</span></span>    | <span data-ttu-id="c10b7-134">2.2.1</span><span class="sxs-lookup"><span data-stu-id="c10b7-134">2.2.1</span></span>             | <span data-ttu-id="c10b7-135">2.2.200</span><span class="sxs-lookup"><span data-stu-id="c10b7-135">2.2.200</span></span>           |

<span data-ttu-id="c10b7-136">(\*) 上記の表では、今後リリースされる 2.2 .NET Core Runtime が例として使用されています。 .NET Core 2.1 に対する最初の SDK が 2.1.300 であることが、履歴アーティファクトで示されていたからです。</span><span class="sxs-lookup"><span data-stu-id="c10b7-136">(\*) This chart uses a future 2.2 .NET Core Runtime as the example because a historic artifact meant the first SDK for .NET Core 2.1 is 2.1.300.</span></span> <span data-ttu-id="c10b7-137">詳細については、「[.NET Core のバージョンの選択](selection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b7-137">For more information, See the [.NET Core version selection](selection.md).</span></span>

<span data-ttu-id="c10b7-138">注: </span><span class="sxs-lookup"><span data-stu-id="c10b7-138">NOTES:</span></span>

* <span data-ttu-id="c10b7-139">SDK において、ランタイムの機能更新プログラムの前に 10 の機能更新プログラムがある場合、バージョン番号は 1000 シリーズに展開され、番号は 2.2.1000 のようになります。これは 2.2.900 に続く機能リリースを示しています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-139">If the SDK has 10 feature updates before a runtime feature update, version numbers roll into the 1000 series with numbers like 2.2.1000 as the feature release following 2.2.900.</span></span> <span data-ttu-id="c10b7-140">このような状況が発生することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="c10b7-140">This situation isn't expected to occur.</span></span>
* <span data-ttu-id="c10b7-141">機能リリースなしで 99 のパッチ リリースは、発生しません。</span><span class="sxs-lookup"><span data-stu-id="c10b7-141">99 patch releases without a feature release won't occur.</span></span> <span data-ttu-id="c10b7-142">リリースがこの数に近づくと、機能リリースが強制的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-142">If a release approaches this number, it forces a feature release.</span></span>

<span data-ttu-id="c10b7-143">詳細については、[dotnet/designs](https://github.com/dotnet/designs/pull/29) リポジトリにある初期の提案を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b7-143">You can see more details in the initial proposal at the [dotnet/designs](https://github.com/dotnet/designs/pull/29) repository.</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="c10b7-144">セマンティック バージョン管理</span><span class="sxs-lookup"><span data-stu-id="c10b7-144">Semantic versioning</span></span>

<span data-ttu-id="c10b7-145">.NET Core *ランタイム*は、[セマンティック バージョニング (SemVer)](https://semver.org/) にほぼ準拠しています。`MAJOR.MINOR.PATCH` バージョン管理の使用が採用され、バージョン番号のさまざまな部分を使用して変更の程度と種類が記述されています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-145">The .NET Core *Runtime* roughly adheres to [Semantic Versioning (SemVer)](https://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="c10b7-146">省略可能な `PRERELEASE` と `BUILDNUMBER` の部分はサポートされるリリースに含まれることはなく、ソース ターゲットからローカルでビルドされた夜間のビルドおよびサポートされていないプレビュー リリースにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="c10b7-146">The optional `PRERELEASE` and `BUILDNUMBER` parts are never part of supported releases and only exist on nightly builds, local builds from source targets, and unsupported preview releases.</span></span>

### <a name="understand-runtime-version-number-changes"></a><span data-ttu-id="c10b7-147">ランタイム バージョン番号の変更を理解する</span><span class="sxs-lookup"><span data-stu-id="c10b7-147">Understand runtime version number changes</span></span>

<span data-ttu-id="c10b7-148">`MAJOR` は次のときに増分されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-148">`MAJOR` is incremented when:</span></span>

* <span data-ttu-id="c10b7-149">製品に重大な変更が加えられた。または製品の方向性が新しくなった。</span><span class="sxs-lookup"><span data-stu-id="c10b7-149">Significant changes occur to the product, or a new product direction.</span></span>
* <span data-ttu-id="c10b7-150">互換性に影響する変更が行われた。</span><span class="sxs-lookup"><span data-stu-id="c10b7-150">Breaking changes were taken.</span></span> <span data-ttu-id="c10b7-151">互換性に影響する変更の受け入れには大きな制約があります。</span><span class="sxs-lookup"><span data-stu-id="c10b7-151">There's a high bar to accepting breaking changes.</span></span>
* <span data-ttu-id="c10b7-152">古いバージョンがサポート対象から除外された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-152">An old version is no longer supported.</span></span>
* <span data-ttu-id="c10b7-153">既存の依存関係の新しい `MAJOR` バージョンが採用された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-153">A newer `MAJOR` version of an existing dependency is adopted.</span></span>

<span data-ttu-id="c10b7-154">`MINOR` は次のときに増分されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-154">`MINOR` is incremented when:</span></span>

* <span data-ttu-id="c10b7-155">パブリック API アクセス領域が追加された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-155">Public API surface area is added.</span></span>
* <span data-ttu-id="c10b7-156">新しい動作が追加された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-156">A new behavior is added.</span></span>
* <span data-ttu-id="c10b7-157">既存の依存関係の新しい `MINOR` バージョンが採用された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-157">A newer `MINOR` version of an existing dependency is adopted.</span></span>
* <span data-ttu-id="c10b7-158">新しい依存関係が導入された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-158">A new dependency is introduced.</span></span>

<span data-ttu-id="c10b7-159">`PATCH` は次のときに増分されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-159">`PATCH` is incremented when:</span></span>

* <span data-ttu-id="c10b7-160">バグの修正が行われた。</span><span class="sxs-lookup"><span data-stu-id="c10b7-160">Bug fixes are made.</span></span>
* <span data-ttu-id="c10b7-161">より新しいプラットフォームのサポートが追加された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-161">Support for a newer platform is added.</span></span>
* <span data-ttu-id="c10b7-162">既存の依存関係の新しい `PATCH` バージョンが採用された。</span><span class="sxs-lookup"><span data-stu-id="c10b7-162">A newer `PATCH` version of an existing dependency is adopted.</span></span>
* <span data-ttu-id="c10b7-163">前のケースのいずれかに一致しない他の変更。</span><span class="sxs-lookup"><span data-stu-id="c10b7-163">Any other change doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="c10b7-164">複数の変更が存在する場合、個々の変更によって影響を受ける最高位置の要素が増分され、それに続く要素はゼロにリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-164">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="c10b7-165">たとえば、`MAJOR` が増分され、`MINOR` と `PATCH` はゼロにリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-165">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="c10b7-166">`MINOR` が増分されるときには、`PATCH` はゼロにリセットされますが、`MAJOR` は変更されません。</span><span class="sxs-lookup"><span data-stu-id="c10b7-166">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

## <a name="version-numbers-in-file-names"></a><span data-ttu-id="c10b7-167">ファイル名に含まれるバージョン番号</span><span class="sxs-lookup"><span data-stu-id="c10b7-167">Version numbers in file names</span></span>

<span data-ttu-id="c10b7-168">.NET Core でダウンロードされるファイルには、バージョンが伴います (たとえば、`dotnet-sdk-2.1.300-win10-x64.exe` のように)。</span><span class="sxs-lookup"><span data-stu-id="c10b7-168">The files downloaded for .NET Core carry the version, for example, `dotnet-sdk-2.1.300-win10-x64.exe`.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="c10b7-169">プレビュー バージョン</span><span class="sxs-lookup"><span data-stu-id="c10b7-169">Preview versions</span></span>

<span data-ttu-id="c10b7-170">プレビュー バージョンには、`-preview[number]-([build]|"final")` がバージョンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-170">Preview versions have a `-preview[number]-([build]|"final")` appended to the version.</span></span> <span data-ttu-id="c10b7-171">たとえば、`2.0.0-preview1-final` のようにします。</span><span class="sxs-lookup"><span data-stu-id="c10b7-171">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="c10b7-172">サービスのバージョン</span><span class="sxs-lookup"><span data-stu-id="c10b7-172">Servicing versions</span></span>

<span data-ttu-id="c10b7-173">リリースされると、通常はリリース ブランチが毎日のビルドの生成を停止し、代わりにサービスのビルドの生成を開始します。</span><span class="sxs-lookup"><span data-stu-id="c10b7-173">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="c10b7-174">サービスのバージョンには、`-servicing-[number]` がバージョンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-174">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="c10b7-175">たとえば、`2.0.1-servicing-006924` のようにします。</span><span class="sxs-lookup"><span data-stu-id="c10b7-175">For example, `2.0.1-servicing-006924`.</span></span>

## <a name="relationship-to-net-standard-versions"></a><span data-ttu-id="c10b7-176">.NET Standard との関係</span><span class="sxs-lookup"><span data-stu-id="c10b7-176">Relationship to .NET Standard versions</span></span>

<span data-ttu-id="c10b7-177">.NET Standard は、.NET 参照アセンブリで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-177">.NET Standard consists of a .NET reference assembly.</span></span> <span data-ttu-id="c10b7-178">各プラットフォームに固有の複数の実装があります。</span><span class="sxs-lookup"><span data-stu-id="c10b7-178">There are multiple implementations specific to each platform.</span></span> <span data-ttu-id="c10b7-179">参照アセンブリには、指定された .NET Standard バージョンの一部である .NET API の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-179">The reference assembly contains the definition of .NET APIs which are part of a given .NET Standard version.</span></span> <span data-ttu-id="c10b7-180">各実装では、特定のプラットフォームに対する .NET Standard コントラクトが満たされます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-180">Each implementation fulfills the .NET Standard contract on the specific platform.</span></span> <span data-ttu-id="c10b7-181">.NET Standard の詳細については、.NET ガイド内の [.NET Standard](../../standard/net-standard.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b7-181">You can learn more about .NET Standard in the article on [.NET Standard](../../standard/net-standard.md) in the .NET Guide.</span></span>

<span data-ttu-id="c10b7-182">.NET Standard 参照アセンブリでは、`MAJOR.MINOR` バージョン管理スキームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-182">The .NET Standard reference assembly uses a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="c10b7-183">.NET Standard の場合、`PATCH` レベルは有用ではありません。 .NET Standard では、API 仕様しか公開されず (実装は対象外)、定義上、API に対する変更はいずれも機能セット内の変更を示すものであり、`MINOR` バージョンとなるためです。</span><span class="sxs-lookup"><span data-stu-id="c10b7-183">`PATCH` level isn't useful for .NET Standard because it exposes only an API specification (no implementation) and by definition any change to the API would represent a change in the feature set, and thus a new `MINOR` version.</span></span>

<span data-ttu-id="c10b7-184">各プラットフォーム上の実装の場合は、通常、プラットフォーム リリースの一部として更新されるので、そのプラットフォーム上で .NET Standard を使用しているプログラマには明らかにされません。</span><span class="sxs-lookup"><span data-stu-id="c10b7-184">The implementations on each platform may be updated, typically as part of the platform release, and thus not evident to the programmers using .NET Standard on that platform.</span></span>

<span data-ttu-id="c10b7-185">.NET Core の各バージョンでは、.NET Standard のバージョンが実装されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-185">Each version of .NET Core implements a version of .NET Standard.</span></span> <span data-ttu-id="c10b7-186">.NET Standard のバージョンを実装すると、以前のバージョンの .NET Standard のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-186">Implementing a version of .NET Standard implies support for previous versions of .NET Standard.</span></span> <span data-ttu-id="c10b7-187">.NET Standard と .NET Core のバージョンは独立しています。</span><span class="sxs-lookup"><span data-stu-id="c10b7-187">.NET Standard and .NET Core version independently.</span></span> <span data-ttu-id="c10b7-188">.NET Core 2.0 によって .NET Standard 2.0 が実装されるのは偶然です。</span><span class="sxs-lookup"><span data-stu-id="c10b7-188">It's a coincidence that .NET Core 2.0 implements .NET Standard 2.0.</span></span> <span data-ttu-id="c10b7-189">.NET core 2.1 では .NET Standard 2.0 も実装されます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-189">.NET Core 2.1 also implements .NET Standard 2.0.</span></span> <span data-ttu-id="c10b7-190">.NET Core では、.NET Standard の将来のバージョンについても、リリースされた場合はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c10b7-190">.NET Core will support future versions of .NET Standard as they become available.</span></span>

| <span data-ttu-id="c10b7-191">.NET Core</span><span class="sxs-lookup"><span data-stu-id="c10b7-191">.NET Core</span></span> | <span data-ttu-id="c10b7-192">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="c10b7-192">.NET Standard</span></span> |
|-----------|---------------|
| <span data-ttu-id="c10b7-193">1</span><span class="sxs-lookup"><span data-stu-id="c10b7-193">1.0</span></span>       | <span data-ttu-id="c10b7-194">最大 1.6</span><span class="sxs-lookup"><span data-stu-id="c10b7-194">up to 1.6</span></span>     |
| <span data-ttu-id="c10b7-195">2.0</span><span class="sxs-lookup"><span data-stu-id="c10b7-195">2.0</span></span>       | <span data-ttu-id="c10b7-196">最大 2.0</span><span class="sxs-lookup"><span data-stu-id="c10b7-196">up to 2.0</span></span>     |
| <span data-ttu-id="c10b7-197">2.1</span><span class="sxs-lookup"><span data-stu-id="c10b7-197">2.1</span></span>       | <span data-ttu-id="c10b7-198">最大 2.0</span><span class="sxs-lookup"><span data-stu-id="c10b7-198">up to 2.0</span></span>     |

## <a name="see-also"></a><span data-ttu-id="c10b7-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="c10b7-199">See also</span></span>

- [<span data-ttu-id="c10b7-200">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="c10b7-200">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="c10b7-201">.NET Core の配布パッケージ</span><span class="sxs-lookup"><span data-stu-id="c10b7-201">.NET Core distribution packaging</span></span>](../build/distribution-packaging.md)
- [<span data-ttu-id="c10b7-202">.NET Core サポート ライフサイクルのファクト シート</span><span class="sxs-lookup"><span data-stu-id="c10b7-202">.NET Core Support Lifecycle Fact Sheet</span></span>](https://www.microsoft.com/net/core/support)
- [<span data-ttu-id="c10b7-203">.NET core 2 + バージョン バインディング</span><span class="sxs-lookup"><span data-stu-id="c10b7-203">.NET Core 2+ Version Binding</span></span>](https://github.com/dotnet/designs/issues/3)
- [<span data-ttu-id="c10b7-204">.NET Core の Docker イメージ</span><span class="sxs-lookup"><span data-stu-id="c10b7-204">Docker images for .NET Core</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
