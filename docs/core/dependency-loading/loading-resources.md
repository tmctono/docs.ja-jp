---
title: サテライト アセンブリの読み込みアルゴリズム - .NET Core
description: .NET Core でのサテライト アセンブリ読み込みアルゴリズムの詳細の説明
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "72303624"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="9230b-103">サテライト アセンブリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="9230b-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="9230b-104">サテライト アセンブリは、言語およびカルチャ用にカスタマイズされたローカライズされたリソースを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="9230b-105">サテライトアセンブリは、一般的なマネージド アセンブリとは異なる読み込みアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="9230b-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="9230b-106">サテライト アセンブリが読み込まれるタイミング</span><span class="sxs-lookup"><span data-stu-id="9230b-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="9230b-107">サテライト アセンブリは、ローカライズされたリソースを読み込むときに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9230b-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="9230b-108">ローカライズされたリソースを読み込む基本的な API は <xref:System.Resources.ResourceManager?displayProperty=fullName> クラスです。</span><span class="sxs-lookup"><span data-stu-id="9230b-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="9230b-109">最終的に <xref:System.Resources.ResourceManager> クラスは、<xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> ごとに <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9230b-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="9230b-110">上位レベルの API は、低レベルの API を抽象化する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9230b-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="9230b-111">アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="9230b-111">Algorithm</span></span>

<span data-ttu-id="9230b-112">.NET Core リソース フォールバック プロセスには次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9230b-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="9230b-113">`active` <xref:System.Runtime.Loader.AssemblyLoadContext> インスタンスを決定します。</span><span class="sxs-lookup"><span data-stu-id="9230b-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="9230b-114">いずれの場合も、`active` インスタンスは実行中のアセンブリの <xref:System.Runtime.Loader.AssemblyLoadContext> です。</span><span class="sxs-lookup"><span data-stu-id="9230b-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="9230b-115">`active` インスタンスは、要求されたカルチャのサテライト アセンブリの読み込みを、以下の優先順位で試行します。</span><span class="sxs-lookup"><span data-stu-id="9230b-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="9230b-116">キャッシュを調べます。</span><span class="sxs-lookup"><span data-stu-id="9230b-116">Checking its cache.</span></span>
    - <span data-ttu-id="9230b-117">現在実行中のアセンブリのディレクトリで、要求された <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (`es-MX` など) と一致するサブディレクトリがないか調べます。</span><span class="sxs-lookup"><span data-stu-id="9230b-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="9230b-118">この機能は、3.0 より前の .NET Core では実装されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="9230b-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="9230b-119">Linux と macOS では、サブディレクトリは大文字と小文字が区別されるため、次のいずれかでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9230b-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        > - <span data-ttu-id="9230b-120">大文字と小文字が完全に一致している。</span><span class="sxs-lookup"><span data-stu-id="9230b-120">Exactly match case.</span></span>
        > - <span data-ttu-id="9230b-121">小文字になっている。</span><span class="sxs-lookup"><span data-stu-id="9230b-121">Be in lower case.</span></span>

    - <span data-ttu-id="9230b-122">`active` が <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> インスタンスの場合は、[既定のサテライト (リソース) アセンブリ プローブ](default-probing.md#satellite-resource-assembly-probing) ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="9230b-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="9230b-123"><xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9230b-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="9230b-124"><xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="9230b-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="9230b-125"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="9230b-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="9230b-126">サテライト アセンブリが読み込まれる場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9230b-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="9230b-127"><xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9230b-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="9230b-128">アセンブリ内で要求されたリソースが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="9230b-129">ランタイムによってアセンブリ内でリソースが見つかると、それを使用します。</span><span class="sxs-lookup"><span data-stu-id="9230b-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="9230b-130">リソースが見つからない場合は、検索を続けます。</span><span class="sxs-lookup"><span data-stu-id="9230b-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9230b-131">サテライト アセンブリ内のリソースを見つけるために、ランタイムでは現在の <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> の <xref:System.Resources.ResourceManager> によって要求されたリソース ファイルが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9230b-132">リソース ファイル内で、要求されたリソース名が検索されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="9230b-133">いずれかが見つからない場合、リソースは見つからなかったものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9230b-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="9230b-134">次に、ランタイムは、考えられる多数のレベルについて親カルチャ アセンブリを検索し、それぞれで手順 2 および 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9230b-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="9230b-135">各カルチャの親は 1 つだけで、<xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> プロパティによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="9230b-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="9230b-136">カルチャの <xref:System.Globalization.CultureInfo.Parent%2A> プロパティが <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> のとき、親カルチャの検索は停止します。</span><span class="sxs-lookup"><span data-stu-id="9230b-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="9230b-137"><xref:System.Globalization.CultureInfo.InvariantCulture> については、手順 2 および 3 に戻らず、手順 5 に進みます。</span><span class="sxs-lookup"><span data-stu-id="9230b-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="9230b-138">リソースがまだ見つからない場合は、既定の (フォールバック) カルチャのリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="9230b-139">通常、既定のカルチャのリソースは、メイン アプリケーション アセンブリに格納されています。</span><span class="sxs-lookup"><span data-stu-id="9230b-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="9230b-140">ただし、<xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> プロパティに <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9230b-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9230b-141">この値は、リソースの最終的なフォールバックの場所が、メイン アセンブリではなくサテライト アセンブリであることを示します。</span><span class="sxs-lookup"><span data-stu-id="9230b-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9230b-142">既定のカルチャは、最終的なフォールバックです。</span><span class="sxs-lookup"><span data-stu-id="9230b-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="9230b-143">したがって、既定のリソース ファイルにリソースの網羅的なセットを常に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9230b-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="9230b-144">これは、例外がスローされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9230b-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="9230b-145">網羅的なセットを含めることにより、すべてのリソースに対してフォールバックが提供され、固有のカルチャではなくても、常に少なくとも 1 つのリソースがユーザーに存在することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="9230b-146">最後に、</span><span class="sxs-lookup"><span data-stu-id="9230b-146">Finally,</span></span>
   - <span data-ttu-id="9230b-147">ランタイムで既定の (フォールバック) カルチャのリソース ファイルが見つからない場合は、<xref:System.Resources.MissingManifestResourceException> または <xref:System.Resources.MissingSatelliteAssemblyException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9230b-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="9230b-148">リソース ファイルが見つかり、要求されたリソースが存在しない場合は、要求から `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="9230b-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
