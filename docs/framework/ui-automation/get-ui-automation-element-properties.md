---
title: UI オートメーション要素のプロパティの取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 93e0fba4288ba3231bfed45252bdaa78892d008c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61610050"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="7ddca-102">UI オートメーション要素のプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="7ddca-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="7ddca-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7ddca-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7ddca-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7ddca-105">このトピックのプロパティを取得する方法を示しています、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]要素。</span><span class="sxs-lookup"><span data-stu-id="7ddca-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="7ddca-106">現在のプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="7ddca-107">取得、<xref:System.Windows.Automation.AutomationElement>を取得するプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="7ddca-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="7ddca-108">呼び出す<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>、または取得、<xref:System.Windows.Automation.AutomationElement.Current%2A>プロパティ構造とそのメンバーの 1 つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="7ddca-109">キャッシュされたプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="7ddca-110">取得、<xref:System.Windows.Automation.AutomationElement>を取得するプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="7ddca-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="7ddca-111">プロパティが指定されている必要があります、<xref:System.Windows.Automation.CacheRequest>します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="7ddca-112">呼び出す<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>、または取得、<xref:System.Windows.Automation.AutomationElement.Cached%2A>プロパティ構造とそのメンバーの 1 つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ddca-113">例</span><span class="sxs-lookup"><span data-stu-id="7ddca-113">Example</span></span>  
 <span data-ttu-id="7ddca-114">次の例では、現在のプロパティを取得するさまざまな方法を示しています、<xref:System.Windows.Automation.AutomationElement>します。</span><span class="sxs-lookup"><span data-stu-id="7ddca-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="7ddca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ddca-115">See also</span></span>

- [<span data-ttu-id="7ddca-116">クライアントの UI オートメーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="7ddca-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="7ddca-117">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="7ddca-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="7ddca-118">UI オートメーション クライアントにおけるキャッシュ</span><span class="sxs-lookup"><span data-stu-id="7ddca-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
