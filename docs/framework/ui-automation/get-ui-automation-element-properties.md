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
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968962"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="6258f-102">UI オートメーション要素のプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="6258f-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="6258f-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6258f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6258f-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="6258f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6258f-105">このトピックでは、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]要素のプロパティを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6258f-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="6258f-106">現在のプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6258f-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="6258f-107">取得する<xref:System.Windows.Automation.AutomationElement>プロパティが含まれているを取得します。</span><span class="sxs-lookup"><span data-stu-id="6258f-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="6258f-108">を<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>呼び出すか、 <xref:System.Windows.Automation.AutomationElement.Current%2A>プロパティ構造体を取得して、そのメンバーの1つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6258f-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="6258f-109">キャッシュされたプロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="6258f-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="6258f-110">取得する<xref:System.Windows.Automation.AutomationElement>プロパティが含まれているを取得します。</span><span class="sxs-lookup"><span data-stu-id="6258f-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="6258f-111">プロパティは、 <xref:System.Windows.Automation.CacheRequest>で指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6258f-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="6258f-112">を<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>呼び出すか、 <xref:System.Windows.Automation.AutomationElement.Cached%2A>プロパティ構造体を取得して、そのメンバーの1つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6258f-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6258f-113">例</span><span class="sxs-lookup"><span data-stu-id="6258f-113">Example</span></span>  
 <span data-ttu-id="6258f-114">次の例は、 <xref:System.Windows.Automation.AutomationElement>の現在のプロパティを取得するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6258f-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="6258f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6258f-115">See also</span></span>

- [<span data-ttu-id="6258f-116">クライアントの UI オートメーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="6258f-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="6258f-117">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="6258f-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="6258f-118">UI オートメーション クライアントにおけるキャッシュ</span><span class="sxs-lookup"><span data-stu-id="6258f-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
