---
title: .NET Framework および特別なリリース
description: .NET およびアウトオブバンドのリリースについて説明します。 クロスプラットフォームでの開発の強化や新機能の導入を目的として、新しい機能をアウトオブバンド (OOB) でリリースしています。
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 9653696f46279e0c23418f92030d64839cc20518
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618767"
---
# <a name="net-framework-and-out-of-band-releases"></a><span data-ttu-id="8f11a-104">.NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="8f11a-104">.NET Framework and out-of-band releases</span></span>

<span data-ttu-id="8f11a-105">.NET Framework は、UWP アプリや従来のデスクトップ アプリや Web アプリなどのさまざまなプラットフォームに対応し、コードの再利用を最大化するために進化しました。</span><span class="sxs-lookup"><span data-stu-id="8f11a-105">.NET Framework has evolved to accommodate different platforms, such as UWP apps and traditional desktop and web apps, and to maximize code reuse.</span></span> <span data-ttu-id="8f11a-106">通常の .NET Framework のリリースに加えて、クロスプラットフォームでの開発の強化や新機能の導入を目的として、新しい機能をアウトオブバンド (OOB) リリースによって提供しています。</span><span class="sxs-lookup"><span data-stu-id="8f11a-106">In addition to regular .NET Framework releases, new features are released out of band (OOB) to improve cross-platform development or to introduce new functionality.</span></span>

## <a name="advantages-of-oob-releases"></a><span data-ttu-id="8f11a-107">OOB リリースの長所</span><span class="sxs-lookup"><span data-stu-id="8f11a-107">Advantages of OOB releases</span></span>

<span data-ttu-id="8f11a-108">新しいコンポーネントやコンポーネントに対する更新プログラムをアウトオブバンドで提供することにより、Microsoft では .NET Framework の更新プログラムをより頻繁に提供できます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-108">Shipping new components or updates to components out of band enables Microsoft to provide more frequent updates to .NET Framework.</span></span> <span data-ttu-id="8f11a-109">また、カスタマーからのフィードバックにすばやく収集して対応できます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-109">In addition, we can gather and respond to customer feedback more quickly.</span></span>

<span data-ttu-id="8f11a-110">独自のアプリで OOB 機能を使用する場合、OOB アセンブリはアプリのパッケージで配置されるため、ユーザーはアプリを実行するために最新バージョンの .NET Framework をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f11a-110">When you use an OOB feature in your app, your users do not have to install the latest version of .NET Framework to run your app, because the OOB assemblies deploy with your app package.</span></span>

## <a name="how-oob-packages-are-distributed"></a><span data-ttu-id="8f11a-111">OOB パッケージの配布方法</span><span class="sxs-lookup"><span data-stu-id="8f11a-111">How OOB packages are distributed</span></span>

<span data-ttu-id="8f11a-112">共通言語ランタイム (CLR) のコア コンポーネントの OOB リリースは、.NET 用パッケージ マネージャーである [NuGet](https://www.nuget.org/) を通じて配布されます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-112">OOB releases for core common language runtime (CLR) components are delivered through [NuGet](https://www.nuget.org/), which is the package manager for .NET.</span></span> <span data-ttu-id="8f11a-113">NuGet を使用すると、Visual Studio 内からライブラリを簡単に参照して .NET Framework プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-113">NuGet enables you to browse and add libraries to your .NET Framework projects easily from within Visual Studio.</span></span> <span data-ttu-id="8f11a-114">NuGet パッケージ マネージャーは、Visual Studio 2012 以降の Visual Studio のすべてのエディションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f11a-114">NuGet Package Manager is included with all editions of Visual Studio starting with Visual Studio 2012.</span></span> <span data-ttu-id="8f11a-115">Visual Studio の **[ツール]** メニューで **NuGet パッケージ マネージャー**を探します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-115">Look for **NuGet Package Manager** on the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="8f11a-116">インストールされていない場合は、[NuGet のインストール](/nuget/install-nuget-client-tools)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8f11a-116">If it's not installed, follow the instructions on [Installing NuGet](/nuget/install-nuget-client-tools).</span></span> <span data-ttu-id="8f11a-117">NuGet の詳細については、[NuGet のドキュメント](/nuget)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f11a-117">For more information about NuGet, see the [NuGet docs](/nuget).</span></span>

## <a name="use-a-nuget-oob-package"></a><span data-ttu-id="8f11a-118">NuGet OOB パッケージを使用する</span><span class="sxs-lookup"><span data-stu-id="8f11a-118">Use a NuGet OOB package</span></span>

<span data-ttu-id="8f11a-119">NuGet パッケージ マネージャーがインストールされている場合、Visual Studio のソリューション エクスプローラーを使用して、NuGet パッケージへの参照を確認し、追加できます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-119">If NuGet Package Manager is installed, you can browse and add references to NuGet packages by using Solution Explorer in Visual Studio:</span></span>

1. <span data-ttu-id="8f11a-120">Visual Studio でプロジェクトのショートカット メニューを開き、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-120">Open the shortcut menu for your project in Visual Studio, and then choose **Manage NuGet Packages**.</span></span> <span data-ttu-id="8f11a-121">(このオプションは、 **[プロジェクト]** メニューからも使用できます。)</span><span class="sxs-lookup"><span data-stu-id="8f11a-121">(This option is also available from the **Project** menu.)</span></span>

2. <span data-ttu-id="8f11a-122">左ペインで、 **[オンライン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-122">In the left pane, choose **Online**.</span></span>

3. <span data-ttu-id="8f11a-123">プレリリースのパッケージを使用する場合は、中央のペインのドロップダウン リスト ボックスで **[安定版パッケージのみ]** の代わりに **[リリース前のパッケージを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-123">If you want to use prerelease packages, in the drop-down list box in the middle pane, choose **Include Prerelease** instead of **Stable Only**.</span></span>

4. <span data-ttu-id="8f11a-124">右ペインで、 **[検索]** ボックスを使用して使用するパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-124">In the right pane, use the **Search** box to locate the package you would like to use.</span></span> <span data-ttu-id="8f11a-125">Microsoft の一部のパッケージは、Microsoft .NET Framework のロゴで識別され、すべて発行者は Microsoft となっています。</span><span class="sxs-lookup"><span data-stu-id="8f11a-125">Some Microsoft packages are identified by the Microsoft .NET Framework logo, and all identify Microsoft as the publisher.</span></span>

![NuGet パッケージ マネージャー。](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

<span data-ttu-id="8f11a-127">OOB パッケージを使用するアプリケーションを配置する場合は、前述のとおり、OOB のアセンブリは、アプリのパッケージに付属しています。</span><span class="sxs-lookup"><span data-stu-id="8f11a-127">As mentioned previously, when you deploy an app that uses an OOB package, the OOB assemblies will ship with your app package.</span></span>

## <a name="types-of-oob-releases"></a><span data-ttu-id="8f11a-128">OOB のリリースの種類</span><span class="sxs-lookup"><span data-stu-id="8f11a-128">Types of OOB releases</span></span>

<span data-ttu-id="8f11a-129">通常、OOB パッケージには、1 つ以上のプレリリース バージョンと 1 つの安定したバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="8f11a-129">Typically, an OOB package has one or more prerelease versions and a stable version.</span></span> <span data-ttu-id="8f11a-130">プレリリースに含まれるライセンスでは通常、再配布は許可されませんが、パッケージを試用して、フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-130">The license that accompanies a prerelease doesn't typically allow redistribution, but enables you to try out a package and provide feedback.</span></span> <span data-ttu-id="8f11a-131">フィードバックはパッケージに対する更新プログラムに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-131">Feedback is incorporated in any updates made to the package.</span></span> <span data-ttu-id="8f11a-132">最終リリースは NuGet を使って安定したパッケージとして配布され、アプリと共に NuGet パッケージを再配布できるライセンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-132">A final release is distributed as a stable package with NuGet and includes a license that lets you redistribute the NuGet package with your app.</span></span> <span data-ttu-id="8f11a-133">安定したパッケージは Microsoft によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f11a-133">Stable packages are supported by Microsoft.</span></span> <span data-ttu-id="8f11a-134">Microsoft では、IntelliSense のサポートや、ブログの投稿、フォーラムでの回答などの別の種類のドキュメントを、すべてのパッケージについて提供します。</span><span class="sxs-lookup"><span data-stu-id="8f11a-134">Microsoft provides IntelliSense support as well as other types of documentation such as blog posts and forum answers for all packages.</span></span> <span data-ttu-id="8f11a-135">また、すべてのパッケージではありませんが、一部のパッケージについてはソース コードも利用できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f11a-135">In addition, source code may be available with some, but not all, packages.</span></span> <span data-ttu-id="8f11a-136">新しいパッケージや更新パッケージに関するお知らせについては、「[.NET Framework ブログ](https://devblogs.microsoft.com/dotnet/)」を受信登録できます。</span><span class="sxs-lookup"><span data-stu-id="8f11a-136">For announcements regarding new and updated packages, you can subscribe to [the .NET Framework Blog](https://devblogs.microsoft.com/dotnet/).</span></span>

<span data-ttu-id="8f11a-137">リリース前のパッケージと安定版パッケージの両方を検索するには、NuGet パッケージ マネージャーで **[リリース前のパッケージを含める]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="8f11a-137">To find both prerelease and stable packages, choose **Include Prerelease** in NuGet Package Manager.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f11a-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f11a-138">See also</span></span>

- [<span data-ttu-id="8f11a-139">はじめに</span><span class="sxs-lookup"><span data-stu-id="8f11a-139">Getting started</span></span>](index.md)
