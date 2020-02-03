---
title: '方法 : ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742844"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="7654f-102">方法 : ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7654f-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="7654f-103"><xref:System.Windows.Forms.ToolStrip> コントロールの <xref:System.Windows.Forms.ToolStrip.Stretch%2A> プロパティを `true`に設定すると、コントロールによってコンテナーが端から端に挿入され、コンテナーのサイズが変更されるときにサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="7654f-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="7654f-104">この構成では、<xref:System.Windows.Forms.ToolStripTextBox>などのコントロールの項目を拡張して、使用可能な領域を塗りつぶすと共に、コントロールのサイズを変更するときにサイズを変更すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7654f-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="7654f-105">この拡大は、Microsoft® Internet Explorer のアドレスバーと同様の外観と動作を実現する場合などに便利です。</span><span class="sxs-lookup"><span data-stu-id="7654f-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7654f-106">例</span><span class="sxs-lookup"><span data-stu-id="7654f-106">Example</span></span>  
 <span data-ttu-id="7654f-107">次のコード例では、`ToolStripSpringTextBox`と呼ばれる <xref:System.Windows.Forms.ToolStripTextBox> から派生したクラスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7654f-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="7654f-108">このクラスは、<xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> メソッドをオーバーライドして、他のすべての項目の合計幅が減算された後に、親 <xref:System.Windows.Forms.ToolStrip> コントロールの使用可能な幅を計算します。</span><span class="sxs-lookup"><span data-stu-id="7654f-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="7654f-109">このコード例には、<xref:System.Windows.Forms.Form> クラスと、新しい動作を示すための `Program` クラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="7654f-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7654f-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7654f-110">Compiling the Code</span></span>  
 <span data-ttu-id="7654f-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7654f-111">This example requires:</span></span>  
  
- <span data-ttu-id="7654f-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7654f-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7654f-113">参照</span><span class="sxs-lookup"><span data-stu-id="7654f-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7654f-114">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="7654f-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="7654f-115">方法: StatusStrip 内で Spring プロパティを対話的に使用する</span><span class="sxs-lookup"><span data-stu-id="7654f-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
