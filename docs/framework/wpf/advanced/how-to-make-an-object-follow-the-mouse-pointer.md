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
ms.openlocfilehash: b9b13b4eec3e42744ba2be6031ec841fb5f215e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051599"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="e6892-102">方法: オブジェクトをマウス ポインターに追従させる</span><span class="sxs-lookup"><span data-stu-id="e6892-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="e6892-103">この例では、マウス ポインターを画面に移動すると、オブジェクトのサイズを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e6892-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="e6892-104">例では、含まれています、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルを作成する、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]および分離コード ファイルをイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6892-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6892-105">例</span><span class="sxs-lookup"><span data-stu-id="e6892-105">Example</span></span>  
 <span data-ttu-id="e6892-106">次[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]を作成、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]から構成される、<xref:System.Windows.Shapes.Ellipse>内の<xref:System.Windows.Controls.StackPanel>、イベントのイベント ハンドラーをアタッチします、<xref:System.Windows.UIElement.MouseMove>イベント。</span><span class="sxs-lookup"><span data-stu-id="e6892-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="e6892-107">次のコードを作成、<xref:System.Windows.UIElement.MouseMove>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="e6892-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="e6892-108">マウス ポインターを置いたとき、高さと幅、<xref:System.Windows.Shapes.Ellipse>して増減されます。</span><span class="sxs-lookup"><span data-stu-id="e6892-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="e6892-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6892-109">See also</span></span>

- [<span data-ttu-id="e6892-110">入力の概要</span><span class="sxs-lookup"><span data-stu-id="e6892-110">Input Overview</span></span>](input-overview.md)
