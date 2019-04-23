---
title: '方法: Toolstriptextbox (Windows フォーム) にあるコマンド バーの残りの幅を入力するには'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 707fd2e470a9be1d61d2878eeff845b3cad270db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223577"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="19421-102">方法: Toolstriptextbox (Windows フォーム) にあるコマンド バーの残りの幅を入力するには</span><span class="sxs-lookup"><span data-stu-id="19421-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="19421-103">設定すると、<xref:System.Windows.Forms.ToolStrip.Stretch%2A>のプロパティを<xref:System.Windows.Forms.ToolStrip>に制御を`true`コントロールがエンド ツー エンドのコンテナーを入力し、そのコンテナーのサイズ変更時のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="19421-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="19421-104">この構成ですることが有用かもしれませんなど、コントロールの項目を拡張する、<xref:System.Windows.Forms.ToolStripTextBox>空き領域の塗りつぶし、およびコントロールのサイズ変更時にサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="19421-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="19421-105">この引き伸ばし役に立ちます、たとえば、外観と Microsoft® Internet Explorer のアドレス バーに似た動作を実現する場合。</span><span class="sxs-lookup"><span data-stu-id="19421-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19421-106">例</span><span class="sxs-lookup"><span data-stu-id="19421-106">Example</span></span>  
 <span data-ttu-id="19421-107">次のコード例から派生したクラスを提供します。<xref:System.Windows.Forms.ToolStripTextBox>と呼ばれる`ToolStripSpringTextBox`します。</span><span class="sxs-lookup"><span data-stu-id="19421-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="19421-108">このクラスのオーバーライド、 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 、親の使用可能な幅を計算するメソッド<xref:System.Windows.Forms.ToolStrip>の他のすべての項目の幅の合計を削除した後に制御します。</span><span class="sxs-lookup"><span data-stu-id="19421-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="19421-109">このコード例も用意されています。、<xref:System.Windows.Forms.Form>クラスと`Program`クラスの新しい動作を示します。</span><span class="sxs-lookup"><span data-stu-id="19421-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19421-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="19421-110">Compiling the Code</span></span>  
 <span data-ttu-id="19421-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19421-111">This example requires:</span></span>  
  
-   <span data-ttu-id="19421-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="19421-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19421-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="19421-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="19421-114">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="19421-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="19421-115">方法: Statusstrip 内で Spring プロパティを対話的に使用します。</span><span class="sxs-lookup"><span data-stu-id="19421-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
