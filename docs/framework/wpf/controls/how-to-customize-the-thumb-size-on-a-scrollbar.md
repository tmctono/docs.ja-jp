---
title: '方法: ScrollBar のつまみのサイズをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207280"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="cb0bf-102">方法: ScrollBar のつまみのサイズをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cb0bf-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="cb0bf-103">このトピックでは、設定する方法を説明します、<xref:System.Windows.Controls.Primitives.Thumb>の<xref:System.Windows.Controls.Primitives.ScrollBar>固定サイズの最小サイズを指定する方法を<xref:System.Windows.Controls.Primitives.Thumb>の<xref:System.Windows.Controls.Primitives.ScrollBar>します。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0bf-104">例</span><span class="sxs-lookup"><span data-stu-id="cb0bf-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="cb0bf-105">説明</span><span class="sxs-lookup"><span data-stu-id="cb0bf-105">Description</span></span>  
 <span data-ttu-id="cb0bf-106">次の例では、作成、<xref:System.Windows.Controls.Primitives.ScrollBar>を持つ、<xref:System.Windows.Controls.Primitives.Thumb>固定サイズです。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="cb0bf-107">例のセット、<xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A>のプロパティ、<xref:System.Windows.Controls.Primitives.Thumb>に<xref:System.Double.NaN>の高さを設定し、<xref:System.Windows.Controls.Primitives.Thumb>します。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="cb0bf-108">水平方向を作成する<xref:System.Windows.Controls.Primitives.ScrollBar>で、<xref:System.Windows.Controls.Primitives.Thumb>固定幅を持つの幅を設定、<xref:System.Windows.Controls.Primitives.Thumb>します。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="cb0bf-109">コード</span><span class="sxs-lookup"><span data-stu-id="cb0bf-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="cb0bf-110">説明</span><span class="sxs-lookup"><span data-stu-id="cb0bf-110">Description</span></span>  
 <span data-ttu-id="cb0bf-111">次の例では、作成、<xref:System.Windows.Controls.Primitives.ScrollBar>を持つ、<xref:System.Windows.Controls.Primitives.Thumb>最小サイズ。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="cb0bf-112">値を設定する例では、<xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>します。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="cb0bf-113">水平方向を作成する<xref:System.Windows.Controls.Primitives.ScrollBar>で、<xref:System.Windows.Controls.Primitives.Thumb>幅の最小値を持つ、設定、<xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>します。</span><span class="sxs-lookup"><span data-stu-id="cb0bf-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="cb0bf-114">コード</span><span class="sxs-lookup"><span data-stu-id="cb0bf-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cb0bf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb0bf-115">See also</span></span>

- [<span data-ttu-id="cb0bf-116">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cb0bf-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
