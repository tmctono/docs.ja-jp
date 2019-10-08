---
title: '方法: オブジェクトをマウス ポインターに追従させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005068"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="b2690-102">方法: オブジェクトをマウス ポインターに追従させる</span><span class="sxs-lookup"><span data-stu-id="b2690-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="b2690-103">この例では、マウスポインターが画面上を移動したときにオブジェクトの寸法を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b2690-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="b2690-104">この例には、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] を作成し、イベントハンドラーを作成する分離コードファイルを作成する @no__t 0 ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2690-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2690-105">例</span><span class="sxs-lookup"><span data-stu-id="b2690-105">Example</span></span>  
 <span data-ttu-id="b2690-106">次の XAML は、<xref:System.Windows.Controls.StackPanel> 内の <xref:System.Windows.Shapes.Ellipse> で構成される @no__t 0 を作成し、<xref:System.Windows.UIElement.MouseMove> イベントのイベントハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b2690-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="b2690-107">次のコードでは、<xref:System.Windows.UIElement.MouseMove> イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2690-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="b2690-108">マウスポインターを動かすと、<xref:System.Windows.Shapes.Ellipse> の高さと幅が増減します。</span><span class="sxs-lookup"><span data-stu-id="b2690-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="b2690-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2690-109">See also</span></span>

- [<span data-ttu-id="b2690-110">入力の概要</span><span class="sxs-lookup"><span data-stu-id="b2690-110">Input Overview</span></span>](input-overview.md)
