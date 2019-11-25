---
ms.openlocfilehash: 394ed636cece766d61b1a10403b98c73f1d3cb93
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041261"
---
# <a name="labels-and-projects-roadmap"></a><span data-ttu-id="c3e58-101">ラベルとプロジェクトのロードマップ</span><span class="sxs-lookup"><span data-stu-id="c3e58-101">Labels and projects roadmap</span></span>

<span data-ttu-id="c3e58-102">.NET docs チームは、[GitHub ラベル](https://github.com/dotnet/docs/labels) を広範に使用して、作業を整理します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-102">The .NET docs team makes extensive use of [GitHub labels](https://github.com/dotnet/docs/labels) to organize our work.</span></span> <span data-ttu-id="c3e58-103">ラベルの組み合わせに基づいてフィルター処理することで、[.NET docs Web サイト](https://docs.microsoft.com/dotnet)上の目的のセクションにすばやく焦点を合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-103">By filtering on combinations of labels, we can quickly focus on sections of interest on the [.NET docs website](https://docs.microsoft.com/dotnet).</span></span> 

<span data-ttu-id="c3e58-104">また、[GitHub プロジェクト](https://github.com/dotnet/docs/projects)を使用して、スプリントやその他の目標志向のエピックを整理します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-104">We also use [GitHub projects](https://github.com/dotnet/docs/projects) to organize sprints and other goal-oriented epics.</span></span>

<span data-ttu-id="c3e58-105">このロードマップでは、これらの組織ツールの使用方法について説明するほか、目的の領域を見つけるために使用できる便利なフィルターへのリンクも用意されています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-105">This roadmap explains how we use these organizational tools and has links to handy filters we use to find areas of interest.</span></span>

## <a name="labels"></a><span data-ttu-id="c3e58-106">ラベル</span><span class="sxs-lookup"><span data-stu-id="c3e58-106">Labels</span></span>

<span data-ttu-id="c3e58-107">これが [dotnet/docs](https://github.com/dotnet/docs) に投稿する初めての経験である場合は、[up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) イシューから開始してください。</span><span class="sxs-lookup"><span data-stu-id="c3e58-107">If this is your first experience contributing to [dotnet/docs](https://github.com/dotnet/docs), start with the [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) issues.</span></span> <span data-ttu-id="c3e58-108">これらは、より範囲が絞られたイシューです。</span><span class="sxs-lookup"><span data-stu-id="c3e58-108">These are issues that have a more focused scope.</span></span> <span data-ttu-id="c3e58-109">これは、最初の投稿を作成するのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="c3e58-109">They are a great way to make your first contribution.</span></span> <span data-ttu-id="c3e58-110">up-for-grabs ビューから、領域や優先度に基づいてイシューをさらにフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-110">From the up-for-grabs view, you can further filter issues based on areas and priority.</span></span> <span data-ttu-id="c3e58-111">最初の投稿を小さくする必要がある場合は、[good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) を持つ初心者向けの適切なイシューが特定されています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-111">We've identified good issues for beginners with the [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) if you want to try a smaller first contribution.</span></span>

<span data-ttu-id="c3e58-112">ラベルを使用して、さまざまな方法でイシューを分類します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-112">We use labels to classify issues in many different ways:</span></span>

- <span data-ttu-id="c3e58-113">[.NET ガイド](#find-a-single-net-guide) と [ガイドのセクション](#search-one-section-of-a-guide)。</span><span class="sxs-lookup"><span data-stu-id="c3e58-113">[.NET Guides](#find-a-single-net-guide) and [sections of a guide](#search-one-section-of-a-guide).</span></span>
- [<span data-ttu-id="c3e58-114">ターゲット リリース</span><span class="sxs-lookup"><span data-stu-id="c3e58-114">Target release</span></span>](#releases)
- [<span data-ttu-id="c3e58-115">優先順位</span><span class="sxs-lookup"><span data-stu-id="c3e58-115">Priority</span></span>](#priority)

<span data-ttu-id="c3e58-116">各セット (ガイド、リリース、優先順位) からのラベルを組み合わせて、範囲を絞って作業対象のイシューを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-116">You can combine a label from each set (guide, release, priority) to create a narrow focus to find issues you want to work on.</span></span>

### <a name="find-a-single-net-guide"></a><span data-ttu-id="c3e58-117">単一の .NET ガイドを検索する</span><span class="sxs-lookup"><span data-stu-id="c3e58-117">Find a single .NET guide</span></span>

<span data-ttu-id="c3e58-118">アーキテクチャ電子書籍ごとに、および .NET ガイドごとにラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-118">We use labels for each of the architecture e-books and for each .NET Guide.</span></span> 

<span data-ttu-id="c3e58-119">![:book: guide、明るい緑色の背景](./images/guide.png "アーキテクチャ ガイド ラベルのプレフィックス")</span><span class="sxs-lookup"><span data-stu-id="c3e58-119">![:book: guide on light green background](./images/guide.png "Prefix for architecture guide labels")</span></span>

<span data-ttu-id="c3e58-120">アーキテクチャの電子書籍には、`:book: guide` プレフィックスが付いていて、背景は明るい緑色になっています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-120">Architecture e-books are noted with the `:book: guide` prefix and have a light green background.</span></span> <span data-ttu-id="c3e58-121">これらは、推奨アーキテクチャをカバーする長い形式の領域です。</span><span class="sxs-lookup"><span data-stu-id="c3e58-121">These are the long-form areas that cover recommended architecture.</span></span> <span data-ttu-id="c3e58-122">.NET アーキテクチャ ガイドごとにフィルター処理された現在のイシューを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-122">Here are current issues filtered for each of the .NET architecture guides.</span></span>

- [<span data-ttu-id="c3e58-123">ASP.NET Core Web アプリ</span><span class="sxs-lookup"><span data-stu-id="c3e58-123">ASP.NET Core web apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [<span data-ttu-id="c3e58-124">Blazor</span><span class="sxs-lookup"><span data-stu-id="c3e58-124">Blazor</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [<span data-ttu-id="c3e58-125">クラウド ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c3e58-125">Cloud Native</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [<span data-ttu-id="c3e58-126">Docker ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="c3e58-126">Docker lifecycle</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [<span data-ttu-id="c3e58-127">gRPC</span><span class="sxs-lookup"><span data-stu-id="c3e58-127">gRPC</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [<span data-ttu-id="c3e58-128">w/ Windows コンテナーの最新化</span><span class="sxs-lookup"><span data-stu-id="c3e58-128">Modernizing w/ Windows containers</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [<span data-ttu-id="c3e58-129">.NET マイクロサービス</span><span class="sxs-lookup"><span data-stu-id="c3e58-129">.NET Microservices</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [<span data-ttu-id="c3e58-130">サーバーレス アプリ</span><span class="sxs-lookup"><span data-stu-id="c3e58-130">Serverless apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

<span data-ttu-id="c3e58-131">このラベル スタイルは、[フレームワーク デザインのガイドライン](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-131">This label style is also applied to the [Framework design guidelines](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines).</span></span> <span data-ttu-id="c3e58-132">この領域には同じラベル デザインがありますが、コミュニティ PR はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c3e58-132">This area has the same label design, but community PRs are discouraged.</span></span> <span data-ttu-id="c3e58-133">これは許可を得て転載された資料です。編集しないでください。</span><span class="sxs-lookup"><span data-stu-id="c3e58-133">This is material reprinted with permission and should not be edited.</span></span>

<span data-ttu-id="c3e58-134">![:books:Area、濃い青色の背景](./images/area.png ".NET ガイド領域ラベルのプレフィックス")</span><span class="sxs-lookup"><span data-stu-id="c3e58-134">![:books: Area on dark blue background](./images/area.png "Prefix for .NET Guide area labels")</span></span>

<span data-ttu-id="c3e58-135">各 .NET ガイドには `:books: Area` プレフィックスが付いていて、背景は濃い青色になっています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-135">Each .NET Guide is noted with the `:books: Area` prefix and has a dark blue background.</span></span> <span data-ttu-id="c3e58-136">.NET ガイドごとにフィルター処理された現在のイシューを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-136">Here are current issues filtered for each of the .NET guides.</span></span>

- [<span data-ttu-id="c3e58-137">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c3e58-137">API Reference</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [<span data-ttu-id="c3e58-138">Azure .NET SDK</span><span class="sxs-lookup"><span data-stu-id="c3e58-138">Azure .NET SDK</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [<span data-ttu-id="c3e58-139">C# のガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-139">C# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [<span data-ttu-id="c3e58-140">デスクトップ ガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-140">Desktop Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [<span data-ttu-id="c3e58-141">F# のガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-141">F# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [<span data-ttu-id="c3e58-142">ML.NET ガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-142">ML.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- <span data-ttu-id="c3e58-143">[.NET アーキテクチャ ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 削除可能です</span><span class="sxs-lookup"><span data-stu-id="c3e58-143">[.NET Architecture Guide](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - Could be removed</span></span>
- [<span data-ttu-id="c3e58-144">.NET Core のガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-144">.NET Core Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [<span data-ttu-id="c3e58-145">.NET for Apache Spark ガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-145">.NET for Apache Spark Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [<span data-ttu-id="c3e58-146">.NET Framework ガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-146">.NET Framework Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [<span data-ttu-id="c3e58-147">.NET のガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-147">.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- <span data-ttu-id="c3e58-148">[Roslyn API リファレンス](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 削除可能です。</span><span class="sxs-lookup"><span data-stu-id="c3e58-148">[Roslyn API Reference](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - could be removed.</span></span>
- [<span data-ttu-id="c3e58-149">Visual Basic のガイド</span><span class="sxs-lookup"><span data-stu-id="c3e58-149">Visual Basic Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a><span data-ttu-id="c3e58-150">ガイドの 1 つのセクションを検索する</span><span class="sxs-lookup"><span data-stu-id="c3e58-150">Search one section of a guide</span></span>

<span data-ttu-id="c3e58-151">![:card_file_box:Area、濃さが中程度の青色の背景](./images/technology.png ".NET ガイド サブ区分ラベルのプレフィックス")</span><span class="sxs-lookup"><span data-stu-id="c3e58-151">![:card_file_box: Area on medium blue background](./images/technology.png "Prefix for .NET Guide sub-area labels")</span></span>

<span data-ttu-id="c3e58-152">.NET ガイドは大きいので、これらのラベルでは、ガイドのセクションによってスコープがさらに制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-152">The .NET guides are large, so these labels further limit the scope by a section of a guide.</span></span> <span data-ttu-id="c3e58-153">各 .NET ガイドのサブ領域には `:card_file_box: Technology` プレフィックスが付いていて、背景は中程度の濃さの青色になっています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-153">Each .NET Guide subarea is noted with the `:card_file_box: Technology` prefix and has a medium blue background.</span></span> <span data-ttu-id="c3e58-154">これらのラベルの多くは複数のガイドに適用されますが、他は 1 つのガイドにのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-154">Many of these labels apply to multiple guides, while others are in only one guide.</span></span> <span data-ttu-id="c3e58-155">領域をフィルター処理したら、以下のラベルのいずれかを追加して、イシューの範囲をさらに制限します。</span><span class="sxs-lookup"><span data-stu-id="c3e58-155">After filtering on an area, add one of these labels to further limit the scope of issues.</span></span>

- <span data-ttu-id="c3e58-156">AppCompat</span><span class="sxs-lookup"><span data-stu-id="c3e58-156">AppCompat</span></span>
- <span data-ttu-id="c3e58-157">非同期タスク</span><span class="sxs-lookup"><span data-stu-id="c3e58-157">Async Task</span></span>
- <span data-ttu-id="c3e58-158">C# の詳細な概念</span><span class="sxs-lookup"><span data-stu-id="c3e58-158">C# Advanced concepts</span></span>
- <span data-ttu-id="c3e58-159">C# コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c3e58-159">C# compiler</span></span>
- <span data-ttu-id="c3e58-160">C# の基礎</span><span class="sxs-lookup"><span data-stu-id="c3e58-160">C# Fundamentals</span></span>
- <span data-ttu-id="c3e58-161">C# はじめに</span><span class="sxs-lookup"><span data-stu-id="c3e58-161">C# Get Started</span></span>
- <span data-ttu-id="c3e58-162">C# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="c3e58-162">C# Language Reference</span></span>
- <span data-ttu-id="c3e58-163">C# Null 安全性</span><span class="sxs-lookup"><span data-stu-id="c3e58-163">C# Null safety</span></span>
- <span data-ttu-id="c3e58-164">C# 新機能</span><span class="sxs-lookup"><span data-stu-id="c3e58-164">C# What's new</span></span>
- <span data-ttu-id="c3e58-165">CLI</span><span class="sxs-lookup"><span data-stu-id="c3e58-165">CLI</span></span>
- <span data-ttu-id="c3e58-166">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="c3e58-166">Data Access</span></span>
- <span data-ttu-id="c3e58-167">Docker</span><span class="sxs-lookup"><span data-stu-id="c3e58-167">Docker</span></span>
- <span data-ttu-id="c3e58-168">インストーラー</span><span class="sxs-lookup"><span data-stu-id="c3e58-168">Installers</span></span>
- <span data-ttu-id="c3e58-169">LINQ</span><span class="sxs-lookup"><span data-stu-id="c3e58-169">LINQ</span></span>
- <span data-ttu-id="c3e58-170">NCL</span><span class="sxs-lookup"><span data-stu-id="c3e58-170">NCL</span></span>
- <span data-ttu-id="c3e58-171">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="c3e58-171">.NET Standard</span></span>
- <span data-ttu-id="c3e58-172">Roslyn API</span><span class="sxs-lookup"><span data-stu-id="c3e58-172">Roslyn APIs</span></span>
- <span data-ttu-id="c3e58-173">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c3e58-173">Security</span></span>
- <span data-ttu-id="c3e58-174">WCF</span><span class="sxs-lookup"><span data-stu-id="c3e58-174">WCF</span></span>
- <span data-ttu-id="c3e58-175">WF</span><span class="sxs-lookup"><span data-stu-id="c3e58-175">WF</span></span>
- <span data-ttu-id="c3e58-176">WIF</span><span class="sxs-lookup"><span data-stu-id="c3e58-176">WIF</span></span>
- <span data-ttu-id="c3e58-177">WinForms</span><span class="sxs-lookup"><span data-stu-id="c3e58-177">WinForms</span></span>
- <span data-ttu-id="c3e58-178">WPF</span><span class="sxs-lookup"><span data-stu-id="c3e58-178">WPF</span></span>

### <a name="releases"></a><span data-ttu-id="c3e58-179">リリース</span><span class="sxs-lookup"><span data-stu-id="c3e58-179">Releases</span></span>

<span data-ttu-id="c3e58-180">![:checkered_flag:Release:、濃い黄色](./images/release.png "リリース ラベルのプレフィックス")</span><span class="sxs-lookup"><span data-stu-id="c3e58-180">![:checkered_flag: Release: on dark yellow](./images/release.png "Prefix for release labels")</span></span>

<span data-ttu-id="c3e58-181">特定のリリースにタグが付けられたイシューには、`:checkered_flag: Release:` プレフィックスが付いていて、背景は濃い黄色になっています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-181">Issues tagged for a specific release are noted with the `:checkered_flag: Release:` prefix and have a dark yellow background.</span></span> 

- <span data-ttu-id="c3e58-182">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c3e58-182">.NET Core 2.2</span></span>
- <span data-ttu-id="c3e58-183">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c3e58-183">.NET Core 3.0</span></span>

### <a name="priority"></a><span data-ttu-id="c3e58-184">優先度</span><span class="sxs-lookup"><span data-stu-id="c3e58-184">Priority</span></span>

<span data-ttu-id="c3e58-185">優先順位ラベルはすべて、`P` の後に 1 桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-185">Priority labels are all `P` followed by a single digit.</span></span> <span data-ttu-id="c3e58-186">数値が小さいほど優先度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="c3e58-186">Lower numbers are higher priority:</span></span>

- <span data-ttu-id="c3e58-187">P0</span><span class="sxs-lookup"><span data-stu-id="c3e58-187">P0</span></span>
- <span data-ttu-id="c3e58-188">P1</span><span class="sxs-lookup"><span data-stu-id="c3e58-188">P1</span></span>
- <span data-ttu-id="c3e58-189">P2</span><span class="sxs-lookup"><span data-stu-id="c3e58-189">P2</span></span>

### <a name="what-about-the-other-labels"></a><span data-ttu-id="c3e58-190">他のラベルについてはどうでしょうか?</span><span class="sxs-lookup"><span data-stu-id="c3e58-190">What about the other labels?</span></span>

<span data-ttu-id="c3e58-191">イシューのさまざまな分類を管理するためにコンテンツ チームが使用するラベルが他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="c3e58-191">There are many other labels used by the content teams to manage different classifications of issues.</span></span> <span data-ttu-id="c3e58-192">コンテンツ チームに所属していない場合、そのような他のラベルは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="c3e58-192">If you're not on the content team, you can ignore these other labels.</span></span>

## <a name="projects"></a><span data-ttu-id="c3e58-193">プロジェクト</span><span class="sxs-lookup"><span data-stu-id="c3e58-193">Projects</span></span>

<span data-ttu-id="c3e58-194">共同作成者は、[.NET コミュニティ コラボレーター用のプロジェクト](https://github.com/dotnet/docs/projects/35)を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3e58-194">Contributors should check the [Projects for .NET community collaborators](https://github.com/dotnet/docs/projects/35).</span></span> <span data-ttu-id="c3e58-195">メンテナンス、ドキュメントの更新、および新しいコンテンツ タスク用のさまざまな列が作成されています。</span><span class="sxs-lookup"><span data-stu-id="c3e58-195">We've created different columns for maintenance, document updates, and new content tasks.</span></span> <span data-ttu-id="c3e58-196">これにより、目的のタスクを検索することができます</span><span class="sxs-lookup"><span data-stu-id="c3e58-196">This can be a way to find tasks of interest.</span></span> <span data-ttu-id="c3e58-197">(プロジェクト ビューは、前述のラベルを使用してフィルター処理できます)。</span><span class="sxs-lookup"><span data-stu-id="c3e58-197">(Note that the project view can be filtered using the labels described above.)</span></span> 

<span data-ttu-id="c3e58-198">また、プロジェクトは、他に次の 2 つの方法でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-198">We also use projects in two other ways:</span></span>

- <span data-ttu-id="c3e58-199">Month YYYY プロジェクト タイプ: これらは、各月の作業計画のスクラム ボードです。</span><span class="sxs-lookup"><span data-stu-id="c3e58-199">Month YYYY project types: These are scrum boards for each month's working plan.</span></span>
- <span data-ttu-id="c3e58-200">長期エピック: これらは、作業が数か月にわたって行われる場合、目標に向けてタスクを整理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3e58-200">Long-running epics: These are used to organize tasks toward a goal when the work will occur over several months.</span></span>
