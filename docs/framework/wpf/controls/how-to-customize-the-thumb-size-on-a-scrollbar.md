---
title: '方法: ScrollBar のつまみのサイズをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911054"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="566c1-102">方法: ScrollBar のつまみのサイズをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="566c1-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="566c1-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ScrollBar> の <xref:System.Windows.Controls.Primitives.Thumb> を固定サイズに設定する方法と、<xref:System.Windows.Controls.Primitives.ScrollBar> の <xref:System.Windows.Controls.Primitives.Thumb> に最小サイズを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="566c1-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="566c1-104">例</span><span class="sxs-lookup"><span data-stu-id="566c1-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="566c1-105">説明</span><span class="sxs-lookup"><span data-stu-id="566c1-105">Description</span></span>  
 <span data-ttu-id="566c1-106">次の例では、<xref:System.Windows.Controls.Primitives.Thumb> が固定サイズの <xref:System.Windows.Controls.Primitives.ScrollBar> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="566c1-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="566c1-107">この例では、<xref:System.Windows.Controls.Primitives.Thumb> の <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> プロパティが <xref:System.Double.NaN> に設定され、高さ <xref:System.Windows.Controls.Primitives.Thumb> が設定されています。</span><span class="sxs-lookup"><span data-stu-id="566c1-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="566c1-108"><xref:System.Windows.Controls.Primitives.Thumb> の幅を固定して水平 <xref:System.Windows.Controls.Primitives.ScrollBar> を作成するには、幅 <xref:System.Windows.Controls.Primitives.Thumb> を設定します。</span><span class="sxs-lookup"><span data-stu-id="566c1-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="566c1-109">コード</span><span class="sxs-lookup"><span data-stu-id="566c1-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="566c1-110">説明</span><span class="sxs-lookup"><span data-stu-id="566c1-110">Description</span></span>  
 <span data-ttu-id="566c1-111">次の例では、<xref:System.Windows.Controls.Primitives.Thumb> が最小サイズの <xref:System.Windows.Controls.Primitives.ScrollBar> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="566c1-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="566c1-112">この例では、値 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> が設定されています。</span><span class="sxs-lookup"><span data-stu-id="566c1-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="566c1-113"><xref:System.Windows.Controls.Primitives.Thumb> の幅を最小にして水平 <xref:System.Windows.Controls.Primitives.ScrollBar> を作成するには、<xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> を設定します。</span><span class="sxs-lookup"><span data-stu-id="566c1-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="566c1-114">コード</span><span class="sxs-lookup"><span data-stu-id="566c1-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="566c1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="566c1-115">See also</span></span>

- [<span data-ttu-id="566c1-116">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="566c1-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
