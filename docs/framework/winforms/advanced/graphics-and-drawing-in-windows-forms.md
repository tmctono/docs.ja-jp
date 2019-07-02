---
title: Windows フォームにおけるグラフィックスと描画
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505545"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="4e262-102">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="4e262-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="4e262-103">共通言語ランタイムは、高度な実装の Windows グラフィックス デバイス インターフェイス (GDI) と呼ばれる GDI + を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e262-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="4e262-104">GDI + を使用してグラフィックスを作成、テキストを描画およびグラフィカル イメージ オブジェクトとして操作することができます。</span><span class="sxs-lookup"><span data-stu-id="4e262-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="4e262-105">GDI + はパフォーマンスと使いやすさを提供しています。</span><span class="sxs-lookup"><span data-stu-id="4e262-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="4e262-106">GDI + を使用すると、Windows フォームとコントロールのグラフィカル イメージをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="4e262-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="4e262-107">GDI + できません使用する Web フォームで直接、イメージの Web サーバー コントロールからグラフィカル イメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4e262-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="4e262-108">このセクションでは、GDI + プログラミングの基礎を紹介するトピックを紹介します。</span><span class="sxs-lookup"><span data-stu-id="4e262-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="4e262-109">このセクションは、包括的なリファレンスを意図したものではありませんが、<xref:System.Drawing.Graphics>、<xref:System.Drawing.Pen>、<xref:System.Drawing.Brush>、および <xref:System.Drawing.Color> の各オブジェクトに関する情報が含まれ、図形の描画、テキストの描画、イメージの表示などのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e262-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="4e262-110">詳細については、次を参照してください。 [GDI + の参照](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)します。</span><span class="sxs-lookup"><span data-stu-id="4e262-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="4e262-111">すぐに開始する場合、「[グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e262-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="4e262-112">Windows フォームで線、図形、テキストなどを描画するためのコードの使用方法に関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="4e262-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e262-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4e262-113">In This Section</span></span>  
 [<span data-ttu-id="4e262-114">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="4e262-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="4e262-115">グラフィックスに関連するマネージド クラスの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="4e262-116">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="4e262-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="4e262-117">マネージ GDI + クラスについてを説明します。</span><span class="sxs-lookup"><span data-stu-id="4e262-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="4e262-118">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="4e262-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="4e262-119">方法を完全な GDI + を使用してタスクのさまざまなマネージ クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4e262-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4e262-120">参照</span><span class="sxs-lookup"><span data-stu-id="4e262-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="4e262-121">GDI + の基本的なグラフィックス機能へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="4e262-122">2 次元グラフィックスおよびベクター グラフィックス機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="4e262-123">高度な GDI + イメージング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="4e262-124">高度な GDI + タイポグラフィ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="4e262-125">この名前空間のクラスを使用して、フォントのコレクションを作成して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4e262-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="4e262-126">印刷機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e262-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4e262-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e262-127">Related Sections</span></span>  
 [<span data-ttu-id="4e262-128">コントロールのカスタム描画およびレンダリング</span><span class="sxs-lookup"><span data-stu-id="4e262-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="4e262-129">描画コントロールのコードを提供する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4e262-129">Details how to provide code for painting controls.</span></span>
