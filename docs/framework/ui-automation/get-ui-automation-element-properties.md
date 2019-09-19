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
ms.openlocfilehash: 158ebf29bb504dd11f9e8416011226fc5846873e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043615"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="e51aa-102">UI オートメーション要素のプロパティの取得</span><span class="sxs-lookup"><span data-stu-id="e51aa-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="e51aa-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="e51aa-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e51aa-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="e51aa-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e51aa-105">このトピックでは、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]要素のプロパティを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="e51aa-106">現在のプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="e51aa-107">取得する<xref:System.Windows.Automation.AutomationElement>プロパティが含まれているを取得します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="e51aa-108">を<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>呼び出すか、 <xref:System.Windows.Automation.AutomationElement.Current%2A>プロパティ構造体を取得して、そのメンバーの1つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="e51aa-109">キャッシュされたプロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="e51aa-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="e51aa-110">取得する<xref:System.Windows.Automation.AutomationElement>プロパティが含まれているを取得します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="e51aa-111">プロパティは、 <xref:System.Windows.Automation.CacheRequest>で指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e51aa-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="e51aa-112">を<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>呼び出すか、 <xref:System.Windows.Automation.AutomationElement.Cached%2A>プロパティ構造体を取得して、そのメンバーの1つから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e51aa-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e51aa-113">例</span><span class="sxs-lookup"><span data-stu-id="e51aa-113">Example</span></span>  
 <span data-ttu-id="e51aa-114">次の例は、 <xref:System.Windows.Automation.AutomationElement>の現在のプロパティを取得するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e51aa-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="e51aa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e51aa-115">See also</span></span>

- [<span data-ttu-id="e51aa-116">クライアントの UI オートメーション プロパティ</span><span class="sxs-lookup"><span data-stu-id="e51aa-116">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="e51aa-117">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="e51aa-117">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="e51aa-118">UI オートメーション クライアントにおけるキャッシュ</span><span class="sxs-lookup"><span data-stu-id="e51aa-118">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
