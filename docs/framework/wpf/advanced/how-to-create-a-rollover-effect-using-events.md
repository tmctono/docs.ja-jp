---
title: '方法: イベントを使用してロールオーバー効果を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960387"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="e40d7-102">方法: イベントを使用してロールオーバー効果を作成する</span><span class="sxs-lookup"><span data-stu-id="e40d7-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="e40d7-103">この例では、マウスポインターが要素によって占有されている領域を離れるときに、要素の色を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e40d7-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="e40d7-104">この例は、 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルと分離コードファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e40d7-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e40d7-105">この例では、イベントの使用方法を示していますが、これと同じ効果を<xref:System.Windows.Trigger>得るには、スタイルでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e40d7-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="e40d7-106">詳しくは、「 [スタイルとテンプレート](../controls/styling-and-templating.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e40d7-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e40d7-107">例</span><span class="sxs-lookup"><span data-stu-id="e40d7-107">Example</span></span>  
 <span data-ttu-id="e40d7-108">[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]次の例では、の<xref:System.Windows.Input.Mouse.MouseEnter> <xref:System.Windows.Controls.Border>周囲<xref:System.Windows.Controls.TextBlock>で構成されるユーザーインターフェイスを作成<xref:System.Windows.Controls.Border>し<xref:System.Windows.UIElement.MouseLeave> 、にイベントハンドラーとイベントハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="e40d7-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="e40d7-109">次のコードでは、 <xref:System.Windows.UIElement.MouseEnter>イベント<xref:System.Windows.UIElement.MouseLeave>ハンドラーとイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e40d7-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="e40d7-110">マウスポインターがに<xref:System.Windows.Controls.Border>入ると、 <xref:System.Windows.Controls.Border>の背景が赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e40d7-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="e40d7-111">マウスポインターがから<xref:System.Windows.Controls.Border>離れると、 <xref:System.Windows.Controls.Border>の背景が白に戻されます。</span><span class="sxs-lookup"><span data-stu-id="e40d7-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
