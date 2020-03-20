---
title: .NET Framework および特別なリリース
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 058bc1a5180060d3c3c6ba4ead1f074a14336b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181574"
---
# <a name="net-framework-and-out-of-band-releases"></a><span data-ttu-id="df2ea-102">.NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="df2ea-102">.NET Framework and out-of-band releases</span></span>

<span data-ttu-id="df2ea-103">.NET Framework は、UWP アプリや従来のデスクトップ アプリや Web アプリなどのさまざまなプラットフォームに対応し、コードの再利用を最大化するために進化しました。</span><span class="sxs-lookup"><span data-stu-id="df2ea-103">.NET Framework has evolved to accommodate different platforms, such as UWP apps and traditional desktop and web apps, and to maximize code reuse.</span></span> <span data-ttu-id="df2ea-104">通常の .NET Framework のリリースに加えて、クロスプラットフォームでの開発の強化や新機能の導入を目的として、新しい機能をアウトオブバンド (OOB) リリースによって提供しています。</span><span class="sxs-lookup"><span data-stu-id="df2ea-104">In addition to regular .NET Framework releases, new features are released out of band (OOB) to improve cross-platform development or to introduce new functionality.</span></span>

## <a name="advantages-of-oob-releases"></a><span data-ttu-id="df2ea-105">OOB リリースの長所</span><span class="sxs-lookup"><span data-stu-id="df2ea-105">Advantages of OOB releases</span></span>

<span data-ttu-id="df2ea-106">新しいコンポーネントやコンポーネントに対する更新プログラムをアウトオブバンドで提供することにより、Microsoft では .NET Framework の更新プログラムをより頻繁に提供できます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-106">Shipping new components or updates to components out of band enables Microsoft to provide more frequent updates to .NET Framework.</span></span> <span data-ttu-id="df2ea-107">また、カスタマーからのフィードバックにすばやく収集して対応できます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-107">In addition, we can gather and respond to customer feedback more quickly.</span></span>

<span data-ttu-id="df2ea-108">独自のアプリで OOB 機能を使用する場合、OOB アセンブリはアプリのパッケージで配置されるため、ユーザーはアプリを実行するために最新バージョンの .NET Framework をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df2ea-108">When you use an OOB feature in your app, your users do not have to install the latest version of .NET Framework to run your app, because the OOB assemblies deploy with your app package.</span></span>

## <a name="how-oob-packages-are-distributed"></a><span data-ttu-id="df2ea-109">OOB パッケージの配布方法</span><span class="sxs-lookup"><span data-stu-id="df2ea-109">How OOB packages are distributed</span></span>

<span data-ttu-id="df2ea-110">共通言語ランタイム (CLR) のコア コンポーネントの OOB リリースは、.NET 用パッケージ マネージャーである [NuGet](https://www.nuget.org/) を通じて配布されます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-110">OOB releases for core common language runtime (CLR) components are delivered through [NuGet](https://www.nuget.org/), which is the package manager for .NET.</span></span> <span data-ttu-id="df2ea-111">NuGet を使用すると、Visual Studio 内からライブラリを簡単に参照して .NET Framework プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-111">NuGet enables you to browse and add libraries to your .NET Framework projects easily from within Visual Studio.</span></span> <span data-ttu-id="df2ea-112">NuGet パッケージ マネージャーは、Visual Studio 2012 以降の Visual Studio のすべてのエディションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="df2ea-112">NuGet Package Manager is included with all editions of Visual Studio starting with Visual Studio 2012.</span></span> <span data-ttu-id="df2ea-113">Visual Studio の **[ツール]** メニューで **NuGet パッケージ マネージャー**を探します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-113">Look for **NuGet Package Manager** on the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="df2ea-114">インストールされていない場合は、[NuGet のインストール](/nuget/install-nuget-client-tools)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df2ea-114">If it's not installed, follow the instructions on [Installing NuGet](/nuget/install-nuget-client-tools).</span></span> <span data-ttu-id="df2ea-115">NuGet の詳細については、[NuGet のドキュメント](/nuget)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2ea-115">For more information about NuGet, see the [NuGet docs](/nuget).</span></span>

## <a name="use-a-nuget-oob-package"></a><span data-ttu-id="df2ea-116">NuGet OOB パッケージを使用する</span><span class="sxs-lookup"><span data-stu-id="df2ea-116">Use a NuGet OOB package</span></span>

<span data-ttu-id="df2ea-117">NuGet パッケージ マネージャーがインストールされている場合、Visual Studio のソリューション エクスプローラーを使用して、NuGet パッケージへの参照を確認し、追加できます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-117">If NuGet Package Manager is installed, you can browse and add references to NuGet packages by using Solution Explorer in Visual Studio:</span></span>

1. <span data-ttu-id="df2ea-118">Visual Studio でプロジェクトのショートカット メニューを開き、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-118">Open the shortcut menu for your project in Visual Studio, and then choose **Manage NuGet Packages**.</span></span> <span data-ttu-id="df2ea-119">(このオプションは、 **[プロジェクト]** メニューからも使用できます。)</span><span class="sxs-lookup"><span data-stu-id="df2ea-119">(This option is also available from the **Project** menu.)</span></span>

2. <span data-ttu-id="df2ea-120">左ペインで、 **[オンライン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-120">In the left pane, choose **Online**.</span></span>

3. <span data-ttu-id="df2ea-121">プレリリースのパッケージを使用する場合は、中央のペインのドロップダウン リスト ボックスで **[安定版パッケージのみ]** の代わりに **[リリース前のパッケージを含める]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-121">If you want to use prerelease packages, in the drop-down list box in the middle pane, choose **Include Prerelease** instead of **Stable Only**.</span></span>

4. <span data-ttu-id="df2ea-122">右ペインで、 **[検索]** ボックスを使用して使用するパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-122">In the right pane, use the **Search** box to locate the package you would like to use.</span></span> <span data-ttu-id="df2ea-123">Microsoft の一部のパッケージは、Microsoft .NET Framework のロゴで識別され、すべて発行者は Microsoft となっています。</span><span class="sxs-lookup"><span data-stu-id="df2ea-123">Some Microsoft packages are identified by the Microsoft .NET Framework logo, and all identify Microsoft as the publisher.</span></span>

![NuGet パッケージ マネージャー。](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

<span data-ttu-id="df2ea-125">OOB パッケージを使用するアプリケーションを配置する場合は、前述のとおり、OOB のアセンブリは、アプリのパッケージに付属しています。</span><span class="sxs-lookup"><span data-stu-id="df2ea-125">As mentioned previously, when you deploy an app that uses an OOB package, the OOB assemblies will ship with your app package.</span></span>

## <a name="types-of-oob-releases"></a><span data-ttu-id="df2ea-126">OOB のリリースの種類</span><span class="sxs-lookup"><span data-stu-id="df2ea-126">Types of OOB releases</span></span>

<span data-ttu-id="df2ea-127">通常、OOB パッケージには、1 つ以上のプレリリース バージョンと 1 つの安定したバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="df2ea-127">Typically, an OOB package has one or more prerelease versions and a stable version.</span></span> <span data-ttu-id="df2ea-128">プレリリースに含まれるライセンスでは通常、再配布は許可されませんが、パッケージを試用して、フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-128">The license that accompanies a prerelease doesn't typically allow redistribution, but enables you to try out a package and provide feedback.</span></span> <span data-ttu-id="df2ea-129">フィードバックはパッケージに対する更新プログラムに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-129">Feedback is incorporated in any updates made to the package.</span></span> <span data-ttu-id="df2ea-130">最終リリースは NuGet を使って安定したパッケージとして配布され、アプリと共に NuGet パッケージを再配布できるライセンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-130">A final release is distributed as a stable package with NuGet and includes a license that lets you redistribute the NuGet package with your app.</span></span> <span data-ttu-id="df2ea-131">安定したパッケージは Microsoft によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df2ea-131">Stable packages are supported by Microsoft.</span></span> <span data-ttu-id="df2ea-132">Microsoft では、IntelliSense のサポートや、ブログの投稿、フォーラムでの回答などの別の種類のドキュメントを、すべてのパッケージについて提供します。</span><span class="sxs-lookup"><span data-stu-id="df2ea-132">Microsoft provides IntelliSense support as well as other types of documentation such as blog posts and forum answers for all packages.</span></span> <span data-ttu-id="df2ea-133">また、すべてのパッケージではありませんが、一部のパッケージについてはソース コードも利用できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df2ea-133">In addition, source code may be available with some, but not all, packages.</span></span> <span data-ttu-id="df2ea-134">新しいパッケージや更新パッケージに関するお知らせについては、「[.NET Framework ブログ](https://devblogs.microsoft.com/dotnet/)」を受信登録できます。</span><span class="sxs-lookup"><span data-stu-id="df2ea-134">For announcements regarding new and updated packages, you can subscribe to [the .NET Framework Blog](https://devblogs.microsoft.com/dotnet/).</span></span>

<span data-ttu-id="df2ea-135">リリース前のパッケージと安定版パッケージの両方を検索するには、NuGet パッケージ マネージャーで **[リリース前のパッケージを含める]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="df2ea-135">To find both prerelease and stable packages, choose **Include Prerelease** in NuGet Package Manager.</span></span>

## <a name="see-also"></a><span data-ttu-id="df2ea-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="df2ea-136">See also</span></span>

- [<span data-ttu-id="df2ea-137">はじめに</span><span class="sxs-lookup"><span data-stu-id="df2ea-137">Getting started</span></span>](index.md)
