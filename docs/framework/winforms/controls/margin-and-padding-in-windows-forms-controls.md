---
title: コントロールの余白と埋め込み
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: 02cabccd0d51a3501a8aafb8733a5273deef6c49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728564"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="22705-102">Windows フォーム コントロールでのマージンと埋め込み</span><span class="sxs-lookup"><span data-stu-id="22705-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="22705-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="22705-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="22705-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、これを実現する多くのレイアウト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="22705-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="22705-105">最も重要な 2 つは、<xref:System.Windows.Forms.Control.Margin%2A> プロパティと <xref:System.Windows.Forms.Control.Padding%2A> プロパティです。</span><span class="sxs-lookup"><span data-stu-id="22705-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="22705-106"><xref:System.Windows.Forms.Control.Margin%2A> プロパティは、その他のコントロールで、コントロールの枠線からの指定された距離を保持するコントロールの周囲のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="22705-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="22705-107"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールの内容 (<xref:System.Windows.Forms.Control.Text%2A> プロパティの値など) で、コントロールの枠線からの指定した距離を保持するコントロールの内部のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="22705-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="22705-108">次の図は、コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティと <xref:System.Windows.Forms.Control.Margin%2A> プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="22705-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="22705-109">![Windows フォームコントロールの埋め込みと余白](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="22705-109">![Padding And Margin for Windows Forms Controls](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="22705-110">Visual Studio では、この機能のデザイン時サポートがあります。</span><span class="sxs-lookup"><span data-stu-id="22705-110">There is design-time support for this feature in Visual Studio.</span></span> <span data-ttu-id="22705-111">「[チュートリアル: 埋め込み、余白、AutoSize プロパティを使用した Windows フォームコントロールのレイアウト](windows-forms-controls-padding-autosize.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="22705-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22705-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="22705-112">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
