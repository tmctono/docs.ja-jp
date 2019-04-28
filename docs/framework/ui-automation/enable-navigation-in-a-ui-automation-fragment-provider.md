---
title: UI オートメーション フラグメント プロバイダーでのナビゲーションの有効化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: e97494e01a81ad75820cd3cffa51b5a508152355
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645917"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="51dc8-102">UI オートメーション フラグメント プロバイダーでのナビゲーションの有効化</span><span class="sxs-lookup"><span data-stu-id="51dc8-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="51dc8-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="51dc8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="51dc8-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="51dc8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="51dc8-105">このトピックのコード例では、フラグメント内の要素に対して UI オートメーション プロバイダーでのナビゲーションを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="51dc8-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51dc8-106">例</span><span class="sxs-lookup"><span data-stu-id="51dc8-106">Example</span></span>  
 <span data-ttu-id="51dc8-107">次のコード例では、リスト内のリスト項目に対して <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> を実装しています。</span><span class="sxs-lookup"><span data-stu-id="51dc8-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="51dc8-108">親要素はリスト ボックス要素で、兄弟要素はそのリスト コレクション内の他の項目です。</span><span class="sxs-lookup"><span data-stu-id="51dc8-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="51dc8-109">このメソッドは正しくない方向の場合に `null` (Visual Basic では`Nothing` ) を返します。このケースでは、 <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> と <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>がこれに相当します (要素に子がないため)。</span><span class="sxs-lookup"><span data-stu-id="51dc8-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="51dc8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="51dc8-110">See also</span></span>

- [<span data-ttu-id="51dc8-111">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="51dc8-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="51dc8-112">サーバー側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="51dc8-112">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
