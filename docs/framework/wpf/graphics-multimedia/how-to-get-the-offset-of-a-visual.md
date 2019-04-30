---
title: '方法: ビジュアルのオフセットを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947494"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="b77fc-102">方法: ビジュアルのオフセットを取得する</span><span class="sxs-lookup"><span data-stu-id="b77fc-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="b77fc-103">これらの例では、その親または先祖、または子孫に対して相対的なビジュアル オブジェクトのオフセット値を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b77fc-104">例</span><span class="sxs-lookup"><span data-stu-id="b77fc-104">Example</span></span>  
 <span data-ttu-id="b77fc-105">次のマークアップ例は、<xref:System.Windows.Controls.TextBlock>で定義されている<xref:System.Windows.FrameworkElement.Margin%2A>4 の値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="b77fc-106">次のコード例を使用する方法を示しています、<xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A>のオフセットを取得するメソッドを<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b77fc-107">オフセット値が含まれている、返された内<xref:System.Windows.Vector>値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="b77fc-108">オフセットがアカウントには、<xref:System.Windows.FrameworkElement.Margin%2A>値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="b77fc-109">この場合、<xref:System.Windows.Vector.X%2A>は 4、および<xref:System.Windows.Vector.Y%2A>は 4 です。</span><span class="sxs-lookup"><span data-stu-id="b77fc-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="b77fc-110">返されるオフセット値は、の親に対する相対的な<xref:System.Windows.Media.Visual>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b77fc-111">親に相対でないオフセット値を取得する場合、<xref:System.Windows.Media.Visual>を使用して、<xref:System.Windows.Media.Visual.TransformToAncestor%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b77fc-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="b77fc-112">先祖からの相対オフセットの取得</span><span class="sxs-lookup"><span data-stu-id="b77fc-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="b77fc-113">次のマークアップ例は、<xref:System.Windows.Controls.TextBlock>内で 2 つの入れ子になっている<xref:System.Windows.Controls.StackPanel>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b77fc-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="b77fc-114">次の図は、マークアップの結果を示します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="b77fc-115">![オブジェクトのオフセット値](./media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="b77fc-115">![Offset values of objects](./media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="b77fc-116">TextBlock は、2 つの StackPanels 内で入れ子になった</span><span class="sxs-lookup"><span data-stu-id="b77fc-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="b77fc-117">次のコード例を使用する方法を示しています、<xref:System.Windows.Media.Visual.TransformToAncestor%2A>のオフセットを取得するメソッドを<xref:System.Windows.Controls.TextBlock>含むの基準とした<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="b77fc-118">オフセット値が含まれている、返された内<xref:System.Windows.Media.GeneralTransform>値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="b77fc-119">オフセットがアカウントには、<xref:System.Windows.FrameworkElement.Margin%2A>コンテナー内のすべてのオブジェクトの値<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="b77fc-120">この場合、 <xref:System.Windows.Vector.X%2A> 28 (16 + 8 + 4)、および<xref:System.Windows.Vector.Y%2A>は 28 です。</span><span class="sxs-lookup"><span data-stu-id="b77fc-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="b77fc-121">返されるオフセット値の先祖、<xref:System.Windows.Media.Visual>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b77fc-122">子孫に対する相対的なオフセットの値を取得する場合、<xref:System.Windows.Media.Visual>を使用して、<xref:System.Windows.Media.Visual.TransformToDescendant%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b77fc-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="b77fc-123">子に相対的なオフセットの取得</span><span class="sxs-lookup"><span data-stu-id="b77fc-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="b77fc-124">次のマークアップ例は、<xref:System.Windows.Controls.TextBlock>内に含まれる、<xref:System.Windows.Controls.StackPanel>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b77fc-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="b77fc-125">次のコード例を使用する方法を示しています、<xref:System.Windows.Media.Visual.TransformToDescendant%2A>のオフセットを取得するメソッドを<xref:System.Windows.Controls.StackPanel>その子の基準とした<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="b77fc-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b77fc-126">オフセット値が含まれている、返された内<xref:System.Windows.Media.GeneralTransform>値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="b77fc-127">オフセットがアカウントには、<xref:System.Windows.FrameworkElement.Margin%2A>すべてのオブジェクトの値。</span><span class="sxs-lookup"><span data-stu-id="b77fc-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="b77fc-128">この場合、 <xref:System.Windows.Vector.X%2A> -4、および<xref:System.Windows.Vector.Y%2A>-4 です。</span><span class="sxs-lookup"><span data-stu-id="b77fc-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="b77fc-129">オフセットの値は、親オブジェクトがその子オブジェクトを基準としてオフセット悪影響を及ぼすために、負の値です。</span><span class="sxs-lookup"><span data-stu-id="b77fc-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77fc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b77fc-130">See also</span></span>

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="b77fc-131">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="b77fc-131">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
