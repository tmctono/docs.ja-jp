---
title: リスト項目の UI オートメーション要素の検索
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 7fe1f564e8c9fb967c0b7b4e8b12712962bdedc7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179661"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="c847e-102">リスト項目の UI オートメーション要素の検索</span><span class="sxs-lookup"><span data-stu-id="c847e-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="c847e-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="c847e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c847e-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="c847e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c847e-105">このトピックでは、取得する方法を示します、<xref:System.Windows.Automation.AutomationElement>項目のインデックスがわかっている場合、リスト内の項目にします。</span><span class="sxs-lookup"><span data-stu-id="c847e-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c847e-106">例</span><span class="sxs-lookup"><span data-stu-id="c847e-106">Example</span></span>  
 <span data-ttu-id="c847e-107">次の例では、2 つの方法を使用して、一覧から、指定した項目を取得する<xref:System.Windows.Automation.TreeWalker>とその他の using<xref:System.Windows.Automation.AutomationElement.FindAll%2A>します。</span><span class="sxs-lookup"><span data-stu-id="c847e-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="c847e-108">最初の手法の高速化する傾向にあります[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]コントロールではなく、2 つ目は、Windows Presentation Foundation (WPF) コントロールの高速です。</span><span class="sxs-lookup"><span data-stu-id="c847e-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="c847e-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c847e-109">See also</span></span>

- [<span data-ttu-id="c847e-110">UI オートメーション要素の取得</span><span class="sxs-lookup"><span data-stu-id="c847e-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
