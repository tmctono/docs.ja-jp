---
title: アプリのパフォーマンスを最適化する
description: これらのリソースを使用して、パフォーマンスの計画やハードウェアの活用など、Windows Presentation Foundation アプリケーションのパフォーマンスを向上させます。
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 165caaf102a66988db0254839a947b8e262a386d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166329"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="fd7ce-103">WPF アプリケーションのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="fd7ce-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="fd7ce-104">このセクションは、アプリケーションのパフォーマンスを向上させる方法を探している [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーション開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="fd7ce-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="fd7ce-105">Microsoft .NET Framework および [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を初めて使用する開発者は、まず、両方のプラットフォームについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd7ce-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="fd7ce-106">このセクションは、両方の実用的な知識を持つことを前提として、アプリケーションを稼働させるために十分に理解しているプログラマ向けに書かれています。</span><span class="sxs-lookup"><span data-stu-id="fd7ce-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd7ce-107">このセクションで提供されているパフォーマンス データは、512 RAM と ATI Radeon 9700 グラフィックス カードを搭載した 2.8 GHz PC で実行されている [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fd7ce-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd7ce-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fd7ce-108">In This Section</span></span>  
 [<span data-ttu-id="fd7ce-109">アプリケーション パフォーマンスの計画</span><span class="sxs-lookup"><span data-stu-id="fd7ce-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="fd7ce-110">ハードウェアの活用</span><span class="sxs-lookup"><span data-stu-id="fd7ce-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="fd7ce-111">レイアウトとデザイン</span><span class="sxs-lookup"><span data-stu-id="fd7ce-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="fd7ce-112">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="fd7ce-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="fd7ce-113">オブジェクトの動作</span><span class="sxs-lookup"><span data-stu-id="fd7ce-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="fd7ce-114">アプリケーション リソース</span><span class="sxs-lookup"><span data-stu-id="fd7ce-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 <span data-ttu-id="fd7ce-115">[[テキスト]](optimizing-performance-text.md)</span><span class="sxs-lookup"><span data-stu-id="fd7ce-115">[Text](optimizing-performance-text.md)</span></span>  
  
 [<span data-ttu-id="fd7ce-116">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="fd7ce-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="fd7ce-117">コントロール</span><span class="sxs-lookup"><span data-stu-id="fd7ce-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="fd7ce-118">パフォーマンスに関するその他の推奨事項</span><span class="sxs-lookup"><span data-stu-id="fd7ce-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="fd7ce-119">アプリケーションの起動時間</span><span class="sxs-lookup"><span data-stu-id="fd7ce-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd7ce-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd7ce-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="fd7ce-121">グラフィックスの描画層</span><span class="sxs-lookup"><span data-stu-id="fd7ce-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="fd7ce-122">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="fd7ce-123">レイアウト</span><span class="sxs-lookup"><span data-stu-id="fd7ce-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="fd7ce-124">WPF のツリー</span><span class="sxs-lookup"><span data-stu-id="fd7ce-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="fd7ce-125">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="fd7ce-126">DrawingVisual オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="fd7ce-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="fd7ce-127">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="fd7ce-128">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="fd7ce-129">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="fd7ce-129">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="fd7ce-130">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="fd7ce-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="fd7ce-131">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="fd7ce-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="fd7ce-132">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="fd7ce-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="fd7ce-133">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-133">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="fd7ce-134">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="fd7ce-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="fd7ce-135">アニメーションのヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="fd7ce-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="fd7ce-136">チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="fd7ce-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
