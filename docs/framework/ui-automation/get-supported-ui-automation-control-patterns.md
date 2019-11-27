---
title: サポートされている UI オートメーション コントロール パターンの取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: b1da13cf5eb39a61f40848a5f199cfd39b16d7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435641"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="66e0d-102">サポートされている UI オートメーション コントロール パターンの取得</span><span class="sxs-lookup"><span data-stu-id="66e0d-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
> <span data-ttu-id="66e0d-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="66e0d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="66e0d-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66e0d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="66e0d-105">このトピックでは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 要素からコントロール パターン オブジェクトを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="66e0d-106">すべてのコントロール パターンの取得</span><span class="sxs-lookup"><span data-stu-id="66e0d-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="66e0d-107">対象とするコントロール パターンを持つ <xref:System.Windows.Automation.AutomationElement> を取得します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="66e0d-108">要素からすべてのコントロール パターンを取得するために、<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="66e0d-109">クライアントでは <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> を使用しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66e0d-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="66e0d-110">このメソッドは内部で既存のコントロール パターンごとに <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> を呼び出すため、パフォーマンスに重大な影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66e0d-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="66e0d-111">可能であれば、クライアントでは主なパターンに対して <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> を呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="66e0d-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="66e0d-112">特定のコントロール パターンの取得</span><span class="sxs-lookup"><span data-stu-id="66e0d-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="66e0d-113">対象とするコントロール パターンを持つ <xref:System.Windows.Automation.AutomationElement> を取得します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="66e0d-114">特定のパターンを照会するために、<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> または <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="66e0d-115">これらのメソッドは同様ですが、パターンが見つからない場合、<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> では例外が発生し、<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> では `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="66e0d-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e0d-116">例</span><span class="sxs-lookup"><span data-stu-id="66e0d-116">Example</span></span>  
 <span data-ttu-id="66e0d-117">次の例では、リスト項目の <xref:System.Windows.Automation.AutomationElement> を検索し、その要素から <xref:System.Windows.Automation.SelectionItemPattern> を取得します。</span><span class="sxs-lookup"><span data-stu-id="66e0d-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="66e0d-118">参照</span><span class="sxs-lookup"><span data-stu-id="66e0d-118">See also</span></span>

- [<span data-ttu-id="66e0d-119">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="66e0d-119">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
