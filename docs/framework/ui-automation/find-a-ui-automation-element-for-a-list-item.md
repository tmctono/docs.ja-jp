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
ms.openlocfilehash: ca4fdfabc4202ae9c9a36d4c511ebefc3ddd058d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969015"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="bc3ff-102">リスト項目の UI オートメーション要素の検索</span><span class="sxs-lookup"><span data-stu-id="bc3ff-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="bc3ff-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="bc3ff-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bc3ff-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="bc3ff-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="bc3ff-105">このトピックでは、項目の<xref:System.Windows.Automation.AutomationElement>インデックスがわかっている場合に、リスト内の項目のを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3ff-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc3ff-106">例</span><span class="sxs-lookup"><span data-stu-id="bc3ff-106">Example</span></span>  
 <span data-ttu-id="bc3ff-107">次の例では、指定した項目をリストから取得する2つ<xref:System.Windows.Automation.TreeWalker>の方法を示し<xref:System.Windows.Automation.AutomationElement.FindAll%2A>ます。1つはを使用し、もう1つはを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc3ff-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="bc3ff-108">最初の手法はコントロールに対して[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]より高速になる傾向がありますが、2番目の方法は Windows Presentation Foundation (WPF) コントロールの方が高速です。</span><span class="sxs-lookup"><span data-stu-id="bc3ff-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="bc3ff-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc3ff-109">See also</span></span>

- [<span data-ttu-id="bc3ff-110">UI オートメーション要素の取得</span><span class="sxs-lookup"><span data-stu-id="bc3ff-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
