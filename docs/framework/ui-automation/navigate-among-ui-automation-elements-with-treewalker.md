---
title: TreeWalker を使用した UI オートメーション要素間の移動
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 5c14a660481ed14c0d9f379c80f2d6934a3b6dcb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443173"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="a0e2c-102">TreeWalker を使用した UI オートメーション要素間の移動</span><span class="sxs-lookup"><span data-stu-id="a0e2c-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="a0e2c-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a0e2c-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a0e2c-105">このトピックには、<xref:System.Windows.Automation.TreeWalker> クラスを使用して [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] の要素間を移動する方法を示すコード例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0e2c-106">例</span><span class="sxs-lookup"><span data-stu-id="a0e2c-106">Example</span></span>  
 <span data-ttu-id="a0e2c-107">次の例では、<xref:System.Windows.Automation.TreeWalker.GetParent%2A> を使用して、ルート要素 (desktop) が見つかるまで [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] ツリーをウォークします。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="a0e2c-108">指定された要素の親ウィンドウである、そのすぐ下にある要素。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="a0e2c-109">例</span><span class="sxs-lookup"><span data-stu-id="a0e2c-109">Example</span></span>  
 <span data-ttu-id="a0e2c-110">次の例では、<xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> と <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> を使用して、コントロールビューにあり、有効になっている [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 要素のサブツリー全体を表示する <xref:System.Windows.Forms.TreeView> を作成します。</span><span class="sxs-lookup"><span data-stu-id="a0e2c-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="a0e2c-111">参照</span><span class="sxs-lookup"><span data-stu-id="a0e2c-111">See also</span></span>

- [<span data-ttu-id="a0e2c-112">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="a0e2c-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
