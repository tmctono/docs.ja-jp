---
title: グラフィックスと描画
description: グラフィックス、ペン、ブラシ、カラーの各オブジェクトについて、および Windows フォームで図形の描画、テキストの描画、画像の表示などのタスクを実行する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618403"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="cec4c-103">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="cec4c-103">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="cec4c-104">共通言語ランタイムは、GDI + と呼ばれる Windows グラフィックスデバイスインターフェイス (GDI) の高度な実装を使用します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-104">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="cec4c-105">GDI + を使用すると、グラフィックスの作成、テキストの描画、およびオブジェクトとしてのグラフィックイメージの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cec4c-105">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="cec4c-106">GDI + は、パフォーマンスと使いやすさを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="cec4c-106">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="cec4c-107">GDI + を使用して、Windows フォームとコントロールにグラフィカルイメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cec4c-107">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="cec4c-108">GDI + は Web フォームで直接使用することはできませんが、画像 Web サーバーコントロールを使用してグラフィカルイメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cec4c-108">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="cec4c-109">このセクションでは、GDI + プログラミングの基礎について説明するトピックを紹介します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-109">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="cec4c-110">このセクションは、包括的なリファレンスを意図したものではありませんが、<xref:System.Drawing.Graphics>、<xref:System.Drawing.Pen>、<xref:System.Drawing.Brush>、および <xref:System.Drawing.Color> の各オブジェクトに関する情報が含まれ、図形の描画、テキストの描画、イメージの表示などのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-110">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="cec4c-111">詳細については、「 [Gdi + リファレンス](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec4c-111">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="cec4c-112">すぐに開始する場合、「[グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cec4c-112">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="cec4c-113">Windows フォームで線、図形、テキストなどを描画するためのコードの使用方法に関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="cec4c-113">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cec4c-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cec4c-114">In This Section</span></span>  
 [<span data-ttu-id="cec4c-115">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="cec4c-115">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="cec4c-116">グラフィックスに関連するマネージド クラスの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-116">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="cec4c-117">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="cec4c-117">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="cec4c-118">マネージ GDI + クラスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-118">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="cec4c-119">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="cec4c-119">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="cec4c-120">GDI + マネージクラスを使用してさまざまなタスクを完了する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-120">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cec4c-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="cec4c-121">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="cec4c-122">GDI + の基本的なグラフィックス機能へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-122">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="cec4c-123">2 次元グラフィックスおよびベクター グラフィックス機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-123">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="cec4c-124">高度な GDI + イメージング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-124">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="cec4c-125">高度な GDI + タイポグラフィ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-125">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="cec4c-126">この名前空間のクラスを使用して、フォントのコレクションを作成して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cec4c-126">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="cec4c-127">印刷機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-127">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cec4c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cec4c-128">Related Sections</span></span>  
 [<span data-ttu-id="cec4c-129">コントロールのカスタム描画およびレンダリング</span><span class="sxs-lookup"><span data-stu-id="cec4c-129">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="cec4c-130">描画コントロールのコードを提供する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="cec4c-130">Details how to provide code for painting controls.</span></span>
