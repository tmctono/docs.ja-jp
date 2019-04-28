---
title: WPF アプリケーションのパフォーマンスの最適化
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 53291a0e428b723cd7a6e7b1184639a7b3c3b972
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772984"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="59cfc-102">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="59cfc-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="59cfc-103">このセクションへの参照[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーション開発者がアプリケーションのパフォーマンスを向上させる方法を探しています。</span><span class="sxs-lookup"><span data-stu-id="59cfc-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="59cfc-104">Microsoft .NET Framework で新しく導入した開発者のかどうかと[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、両方のプラットフォームで自分で最初理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59cfc-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="59cfc-105">ここでは、両方の実用的な知識を前提としていて、既に起動して実行して、アプリケーションを十分に把握するプログラマが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="59cfc-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59cfc-106">このセクションで提供されるパフォーマンス データがに基づいて[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]RAM と、ATI Radeon 9700 を 512 2.8 GHz の PC で実行されているアプリケーションのグラフィックス カード。</span><span class="sxs-lookup"><span data-stu-id="59cfc-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59cfc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="59cfc-107">In This Section</span></span>  
 [<span data-ttu-id="59cfc-108">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="59cfc-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="59cfc-109">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="59cfc-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="59cfc-110">レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="59cfc-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="59cfc-111">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="59cfc-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="59cfc-112">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="59cfc-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="59cfc-113">アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="59cfc-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 <span data-ttu-id="59cfc-114">[[テキスト]](optimizing-performance-text.md)</span><span class="sxs-lookup"><span data-stu-id="59cfc-114">[Text](optimizing-performance-text.md)</span></span>  
  
 [<span data-ttu-id="59cfc-115">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="59cfc-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="59cfc-116">コントロール</span><span class="sxs-lookup"><span data-stu-id="59cfc-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="59cfc-117">パフォーマンスに関するその他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="59cfc-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="59cfc-118">アプリケーションの起動時間</span><span class="sxs-lookup"><span data-stu-id="59cfc-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="59cfc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="59cfc-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="59cfc-120">グラフィックスの描画層</span><span class="sxs-lookup"><span data-stu-id="59cfc-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="59cfc-121">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="59cfc-122">レイアウト</span><span class="sxs-lookup"><span data-stu-id="59cfc-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="59cfc-123">WPF のツリー</span><span class="sxs-lookup"><span data-stu-id="59cfc-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="59cfc-124">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="59cfc-125">DrawingVisual オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="59cfc-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="59cfc-126">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="59cfc-127">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="59cfc-128">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="59cfc-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="59cfc-129">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="59cfc-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="59cfc-130">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="59cfc-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="59cfc-131">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="59cfc-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="59cfc-132">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="59cfc-133">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="59cfc-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="59cfc-134">アニメーションのヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="59cfc-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="59cfc-135">チュートリアル: WPF アプリケーションでアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="59cfc-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
