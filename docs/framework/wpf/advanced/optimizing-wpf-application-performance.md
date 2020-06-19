---
title: アプリのパフォーマンスを最適化する
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 54d69e87ef2a9c5318e394422e3bcfcabcc76210
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646249"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="803dc-102">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="803dc-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="803dc-103">このセクションは、アプリケーションのパフォーマンスを向上させる方法を探している [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーション開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="803dc-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="803dc-104">Microsoft .NET Framework および [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を初めて使用する開発者は、まず、両方のプラットフォームについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="803dc-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="803dc-105">このセクションは、両方の実用的な知識を持つことを前提として、アプリケーションを稼働させるために十分に理解しているプログラマ向けに書かれています。</span><span class="sxs-lookup"><span data-stu-id="803dc-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="803dc-106">このセクションで提供されているパフォーマンス データは、512 RAM と ATI Radeon 9700 グラフィックス カードを搭載した 2.8 GHz PC で実行されている [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="803dc-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="803dc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="803dc-107">In This Section</span></span>  
 [<span data-ttu-id="803dc-108">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="803dc-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="803dc-109">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="803dc-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="803dc-110">レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="803dc-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="803dc-111">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="803dc-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="803dc-112">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="803dc-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="803dc-113">アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="803dc-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 <span data-ttu-id="803dc-114">[[テキスト]](optimizing-performance-text.md)</span><span class="sxs-lookup"><span data-stu-id="803dc-114">[Text](optimizing-performance-text.md)</span></span>  
  
 [<span data-ttu-id="803dc-115">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="803dc-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="803dc-116">コントロール</span><span class="sxs-lookup"><span data-stu-id="803dc-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="803dc-117">パフォーマンスに関するその他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="803dc-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="803dc-118">アプリケーションの起動時間</span><span class="sxs-lookup"><span data-stu-id="803dc-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="803dc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="803dc-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="803dc-120">グラフィックスの描画層</span><span class="sxs-lookup"><span data-stu-id="803dc-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="803dc-121">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="803dc-122">レイアウト</span><span class="sxs-lookup"><span data-stu-id="803dc-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="803dc-123">WPF のツリー</span><span class="sxs-lookup"><span data-stu-id="803dc-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="803dc-124">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="803dc-125">DrawingVisual オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="803dc-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="803dc-126">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="803dc-127">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="803dc-128">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="803dc-128">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="803dc-129">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="803dc-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="803dc-130">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="803dc-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="803dc-131">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="803dc-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="803dc-132">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="803dc-133">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="803dc-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="803dc-134">アニメーションのヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="803dc-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="803dc-135">チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="803dc-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
