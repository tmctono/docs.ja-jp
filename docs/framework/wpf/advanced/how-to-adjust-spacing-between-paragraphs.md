---
title: '方法: 段落間の間隔を調整する'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777014"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="c0d30-102">方法: 段落間の間隔を調整する</span><span class="sxs-lookup"><span data-stu-id="c0d30-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="c0d30-103">この例では、調整またはフロー コンテンツ内の段落の間隔を排除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c0d30-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="c0d30-104">フロー コンテンツ内にある段落間に表示される余分なスペースが余白の段落に設定の結果したがって、段落の間隔は、段落のマージンを調整することによって制御できます。</span><span class="sxs-lookup"><span data-stu-id="c0d30-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="c0d30-105">2 つの段落の間の余分なスペースを完全に取り除く設定には、段落のマージン**0**します。</span><span class="sxs-lookup"><span data-stu-id="c0d30-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="c0d30-106">段落全体を通じて等間隔に整列させる<xref:System.Windows.Documents.FlowDocument>、内のすべての段落の均一余白値を設定するスタイルを使用して、<xref:System.Windows.Documents.FlowDocument>します。</span><span class="sxs-lookup"><span data-stu-id="c0d30-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="c0d30-107">隣接する 2 つの段落のマージンが「折りたたみ」に注意してください、2 つの余白のうち大きい方ではなくを約 2 倍になります。</span><span class="sxs-lookup"><span data-stu-id="c0d30-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="c0d30-108">そのため、隣接する 2 つの段落では、それぞれ 20 ピクセルと 40 ピクセルの余白がある、段落の間の結果として得られる領域は 40 ピクセル、2 つの余白の値のうち、大きい方です。</span><span class="sxs-lookup"><span data-stu-id="c0d30-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0d30-109">例</span><span class="sxs-lookup"><span data-stu-id="c0d30-109">Example</span></span>  
 <span data-ttu-id="c0d30-110">次の例では、すべての余白を設定するスタイルを使用して<xref:System.Windows.Documents.Paragraph>内の要素を<xref:System.Windows.Documents.FlowDocument>に**0**で段落の間の余分なスペースが事実上なくなります、<xref:System.Windows.Documents.FlowDocument>します。</span><span class="sxs-lookup"><span data-stu-id="c0d30-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
