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
ms.openlocfilehash: 7ecf6edd37b656f7dd1d7e31506d0dd455592d9b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042977"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="1e432-102">TreeWalker を使用した UI オートメーション要素間の移動</span><span class="sxs-lookup"><span data-stu-id="1e432-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="1e432-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="1e432-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1e432-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="1e432-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="1e432-105">このトピックには、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <xref:System.Windows.Automation.TreeWalker>クラスを使用して要素間を移動する方法を示すコード例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e432-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e432-106">例</span><span class="sxs-lookup"><span data-stu-id="1e432-106">Example</span></span>  
 <span data-ttu-id="1e432-107">次の例で<xref:System.Windows.Automation.TreeWalker.GetParent%2A>は、を使用[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]して、ルート要素 (desktop) が見つかるまでツリーをウォークします。</span><span class="sxs-lookup"><span data-stu-id="1e432-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="1e432-108">指定された要素の親ウィンドウである、そのすぐ下にある要素。</span><span class="sxs-lookup"><span data-stu-id="1e432-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="1e432-109">例</span><span class="sxs-lookup"><span data-stu-id="1e432-109">Example</span></span>  
 <span data-ttu-id="1e432-110">次の例で<xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A>は<xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> 、およびを<xref:System.Windows.Forms.TreeView>使用して、コントロールビュー [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]内にあり、有効になっている要素のサブツリー全体を表示するを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e432-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="1e432-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e432-111">See also</span></span>

- [<span data-ttu-id="1e432-112">UI オートメーション要素の取得</span><span class="sxs-lookup"><span data-stu-id="1e432-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
