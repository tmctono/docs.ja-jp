---
title: UI オートメーション ScrollItem コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 1e33a64e66bc084e8cc5f75ece2ac2a4d7ea85aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447137"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="f7066-102">UI オートメーション ScrollItem コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="f7066-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="f7066-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f7066-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f7066-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7066-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="f7066-105">このトピックでは、プロパティ、メソッド、イベントに関する情報など、<xref:System.Windows.Automation.Provider.IScrollItemProvider> の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7066-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="f7066-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="f7066-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="f7066-107"><xref:System.Windows.Automation.ScrollItemPattern> コントロール パターンは、<xref:System.Windows.Automation.Provider.IScrollProvider> を実装するコンテナーの個々の子コントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7066-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="f7066-108">このコントロール パターンは、子コントロールとそのコンテナーの間の通信チャネルとして機能することで、ビューポート内に現在表示されているコンテンツ (または領域) がコンテナーによって確実に変更され、子コントロールが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7066-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="f7066-109">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7066-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f7066-110">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="f7066-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f7066-111">スクロール項目コントロール パターンを実装する場合は、次のガイドラインと規則にご留意ください。</span><span class="sxs-lookup"><span data-stu-id="f7066-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="f7066-112">ウィンドウ コントロールまたはキャンバス コントロール内の項目で、IScrollItemProvider インターフェイスを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7066-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="f7066-113">代わりに、<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> の正しい位置を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7066-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="f7066-114">これにより、UI オートメーション クライアント アプリケーションは、<xref:System.Windows.Automation.ScrollPattern> コントロール パターン メソッドをコンテナーで使用して、子項目を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7066-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="f7066-115">IScrollItemProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="f7066-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="f7066-116">IScrollProvider インターフェイスを実装するには、次のメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="f7066-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="f7066-117">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="f7066-117">Required members</span></span>|<span data-ttu-id="f7066-118">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="f7066-118">Member type</span></span>|<span data-ttu-id="f7066-119">ノート</span><span class="sxs-lookup"><span data-stu-id="f7066-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="f7066-120">-   Method</span><span class="sxs-lookup"><span data-stu-id="f7066-120">-   Method</span></span>|<span data-ttu-id="f7066-121">None</span><span class="sxs-lookup"><span data-stu-id="f7066-121">None</span></span>|  
  
 <span data-ttu-id="f7066-122">このコントロール パターンに関連付けられるプロパティやイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="f7066-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="f7066-123">例外</span><span class="sxs-lookup"><span data-stu-id="f7066-123">Exceptions</span></span>  
 <span data-ttu-id="f7066-124">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7066-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="f7066-125">例外の種類</span><span class="sxs-lookup"><span data-stu-id="f7066-125">Exception Type</span></span>|<span data-ttu-id="f7066-126">条件</span><span class="sxs-lookup"><span data-stu-id="f7066-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="f7066-127">項目をビューにスクロールできない場合:</span><span class="sxs-lookup"><span data-stu-id="f7066-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="f7066-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7066-128">See also</span></span>

- [<span data-ttu-id="f7066-129">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="f7066-129">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="f7066-130">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="f7066-130">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="f7066-131">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="f7066-131">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="f7066-132">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="f7066-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="f7066-133">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="f7066-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
