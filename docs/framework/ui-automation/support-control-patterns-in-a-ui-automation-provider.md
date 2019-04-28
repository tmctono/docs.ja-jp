---
title: UI オートメーション プロバイダーでのコントロール パターンのサポート
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 65ec0f85bf0a63d0051ff9491623a65abee7a05c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982957"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="63a7b-102">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="63a7b-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="63a7b-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="63a7b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="63a7b-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="63a7b-105">このトピックでは、クライアント アプリケーションがコントロールを操作して、それらからデータを取得できるように、UI オートメーション プロバイダーに 1 つ以上のコントロール パターンを実装する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="63a7b-106">コントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="63a7b-106">Support Control Patterns</span></span>  
  
1. <span data-ttu-id="63a7b-107"><xref:System.Windows.Automation.Provider.IInvokeProvider> の <xref:System.Windows.Automation.InvokePattern>など、要素がサポートする必要のあるコントロール パターンの適切なインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2. <span data-ttu-id="63a7b-108"> <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="63a7b-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="63a7b-109">例</span><span class="sxs-lookup"><span data-stu-id="63a7b-109">Example</span></span>  
 <span data-ttu-id="63a7b-110">単一選択のカスタム リスト ボックスの <xref:System.Windows.Automation.Provider.ISelectionProvider> の実装例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="63a7b-111">3 つのプロパティを返し、現在選択されている項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="63a7b-112">例</span><span class="sxs-lookup"><span data-stu-id="63a7b-112">Example</span></span>  
 <span data-ttu-id="63a7b-113"><xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> を実装するクラスを返す <xref:System.Windows.Automation.Provider.ISelectionProvider>の実装例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63a7b-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="63a7b-114">同様に、この例は、null 参照では、ほとんどのリスト ボックス コントロールは他のパターンをサポートは (`Nothing` Microsoft Visual Basic .net)、その他のすべてのパターン識別子が返されます。</span><span class="sxs-lookup"><span data-stu-id="63a7b-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="63a7b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="63a7b-115">See also</span></span>

- [<span data-ttu-id="63a7b-116">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="63a7b-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="63a7b-117">サーバー側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="63a7b-117">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
