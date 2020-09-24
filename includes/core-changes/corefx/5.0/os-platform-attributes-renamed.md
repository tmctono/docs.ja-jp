---
ms.openlocfilehash: 8c739d8f355ffa6a6e09cbe4c531b188acede5bd
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720305"
---
### <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="2ec22-101">OSPlatform 属性の名前変更または削除</span><span class="sxs-lookup"><span data-stu-id="2ec22-101">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="2ec22-102">.NET 5.0 Preview 8 で実装された、`MinimumOSPlatformAttribute`、`RemovedInOSPlatformAttribute`、および `ObsoletedInOSPlatformAttribute` 属性が、削除または名前変更されました。</span><span class="sxs-lookup"><span data-stu-id="2ec22-102">The following attributes that were introduced in .NET 5.0 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2ec22-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="2ec22-103">Change description</span></span>

<span data-ttu-id="2ec22-104">.NET 5.0 Preview 8 で <xref:System.Runtime.Versioning> 名前空間に次の属性が実装されました。</span><span class="sxs-lookup"><span data-stu-id="2ec22-104">.NET 5.0 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="2ec22-105">.NET 5.0 Preview 8 のプロジェクトで、`net5.0-windows` などの[ターゲット フレームワーク モニカー](../../../../docs/standard/frameworks.md)を使用し、.NET 5 の OS 固有のフレーバーをターゲットとしている場合、ビルドでは、アセンブリレベルの `System.Runtime.Versioning.MinimumOSPlatformAttribute` 属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2ec22-105">In .NET 5.0 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="2ec22-106">.NET 5.0 RC1 では、`ObsoletedInOSPlatformAttribute` が削除され、`MinimumOSPlatformAttribute` と `RemovedInOSPlatformAttribute` が次のように名前変更されています。</span><span class="sxs-lookup"><span data-stu-id="2ec22-106">In .NET 5.0 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="2ec22-107">Preview 8 での名前</span><span class="sxs-lookup"><span data-stu-id="2ec22-107">Preview 8 name</span></span> | <span data-ttu-id="2ec22-108">RC1 以降での名前</span><span class="sxs-lookup"><span data-stu-id="2ec22-108">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="2ec22-109">.NET 5.0 RC1 以降のプロジェクトで、`net5.0-windows` などの[ターゲット フレームワーク モニカー](../../../../docs/standard/frameworks.md)を使用し、.NET 5 の OS 固有のフレーバーをターゲットとしている場合、ビルドでは、アセンブリレベルの <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2ec22-109">In .NET 5.0 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2ec22-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="2ec22-110">Reason for change</span></span>

<span data-ttu-id="2ec22-111">.NET 5.0 Preview 8 で API をサポートするプラットフォームの指定に、<xref:System.Runtime.Versioning> に属性が実装されました。</span><span class="sxs-lookup"><span data-stu-id="2ec22-111">.NET 5.0 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="2ec22-112">これらの属性は、プラットフォーム固有の API がそれらの API をサポートしないプラットフォームで使用された場合に、ビルド警告を生成する、[プラットフォーム互換性アナライザー](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility)によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ec22-112">The attributes are consumed by the [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) to produce build warnings when platform-specific APIs are consumed on platforms that don't supported those APIs.</span></span>

<span data-ttu-id="2ec22-113">.NET 5.0 RC1 では、プラットフォーム互換性アナライザーにプラットフォームを除外する機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="2ec22-113">For .NET 5.0 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="2ec22-114">この機能を使用すると、API を OS プラットフォームで完全にサポートされていないものとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="2ec22-114">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="2ec22-115">この機能では、より適切な名前を使用するなど、属性への変更が求められています。</span><span class="sxs-lookup"><span data-stu-id="2ec22-115">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="2ec22-116">不要になった `ObsoletedInOSPlatformAttribute` は、削除されています。</span><span class="sxs-lookup"><span data-stu-id="2ec22-116">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2ec22-117">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2ec22-117">Version introduced</span></span>

<span data-ttu-id="2ec22-118">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="2ec22-118">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2ec22-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="2ec22-119">Recommended action</span></span>

<span data-ttu-id="2ec22-120">プロジェクトのターゲットを .NET 5.0 Preview 8 から .NET 5.0 RC1 に変更した場合、これらの変更によりビルド エラーまたは実行時エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2ec22-120">When you retarget your project from .NET 5.0 Preview 8 to .NET 5.0 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="2ec22-121">たとえば、`MinimumOSPlatformAttribute` を名前変更すると、エラーが発生する可能性があります。これは、この属性がビルド時にプラットフォーム固有のアセンブリに適用されますが、古い成果物では古い API 名を参照したままであるためです。</span><span class="sxs-lookup"><span data-stu-id="2ec22-121">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="2ec22-122">ビルド時のエラーの例:</span><span class="sxs-lookup"><span data-stu-id="2ec22-122">Example build-time errors:</span></span>

- <span data-ttu-id="2ec22-123">**エラー CS0246:型または名前空間の名前 'MinimumOSPlatformAttribute' が見つかりませんでした (using ディレクティブまたはアセンブリ参照が指定されていることを確認してください)**</span><span class="sxs-lookup"><span data-stu-id="2ec22-123">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="2ec22-124">**エラー CS0246:型または名前空間の名前 'RemovedInOSPlatformAttribute' が見つかりませんでした (using ディレクティブまたはアセンブリ参照が指定されていることを確認してください)**</span><span class="sxs-lookup"><span data-stu-id="2ec22-124">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="2ec22-125">**エラー CS0246:型または名前空間の名前 'ObsoletedInOSPlatformAttribute' が見つかりませんでした (using ディレクティブまたはアセンブリ参照が指定されていることを確認してください)**</span><span class="sxs-lookup"><span data-stu-id="2ec22-125">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="2ec22-126">ランタイム エラーの例:</span><span class="sxs-lookup"><span data-stu-id="2ec22-126">Example run-time error:</span></span>

<span data-ttu-id="2ec22-127">**未処理の例外。System.TypeLoadException:アセンブリから型 'System.Runtime.Versioning.MinimumOSPlatformAttribute' を読み込むことができませんでした 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span><span class="sxs-lookup"><span data-stu-id="2ec22-127">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="2ec22-128">これらのエラーを解決するには:</span><span class="sxs-lookup"><span data-stu-id="2ec22-128">To resolve these errors:</span></span>

- <span data-ttu-id="2ec22-129">`MinimumOSPlatformAttribute` に対する参照を <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> に更新します。</span><span class="sxs-lookup"><span data-stu-id="2ec22-129">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="2ec22-130">`RemovedInOSPlatformAttribute` に対する参照を <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> に更新します。</span><span class="sxs-lookup"><span data-stu-id="2ec22-130">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="2ec22-131">`ObsoletedInOSPlatformAttribute` に対する参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="2ec22-131">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="2ec22-132">古いビルド成果物を削除して、自分のプロジェクトをリビルドします (またはクリーンおよびビルドを実行します)。</span><span class="sxs-lookup"><span data-stu-id="2ec22-132">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

#### <a name="category"></a><span data-ttu-id="2ec22-133">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="2ec22-133">Category</span></span>

<span data-ttu-id="2ec22-134">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="2ec22-134">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2ec22-135">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2ec22-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

#### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
