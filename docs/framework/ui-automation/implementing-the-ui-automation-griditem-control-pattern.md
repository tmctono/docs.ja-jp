---
title: UI オートメーション GridItem コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: d561587e6bb98ba857b27ba89b4c1a45ba964ffd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180194"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="9177f-102">UI オートメーション GridItem コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="9177f-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="9177f-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9177f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9177f-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9177f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9177f-105">ここでは、プロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IGridItemProvider>を実装するガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="9177f-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="9177f-106">その他のリファレンスへのリンクは、概要の最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="9177f-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="9177f-107"><xref:System.Windows.Automation.GridItemPattern> コントロール パターンは、<xref:System.Windows.Automation.Provider.IGridProvider> を実装するコンテナーの個々の子コントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9177f-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="9177f-108">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9177f-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="9177f-109">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="9177f-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="9177f-110"><xref:System.Windows.Automation.Provider.IGridProvider> を実装する場合は、次のガイドラインと規則に留意してください。</span><span class="sxs-lookup"><span data-stu-id="9177f-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="9177f-111">グリッドの座標は 0 から始まり、左上のセルの座標が (0, 0) です。</span><span class="sxs-lookup"><span data-stu-id="9177f-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="9177f-112">結合されたセルが報告する <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> および <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> プロパティは、UI オートメーション プロバイダーによって定義された、基になるアンカー セルに基づきます。</span><span class="sxs-lookup"><span data-stu-id="9177f-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="9177f-113">通常、これは、最上位の左端の行または列です。</span><span class="sxs-lookup"><span data-stu-id="9177f-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="9177f-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> は、セルの結合や分割などのアクティブなグリッド操作を提供しません。</span><span class="sxs-lookup"><span data-stu-id="9177f-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="9177f-115"><xref:System.Windows.Automation.Provider.IGridItemProvider> を実装するコントロールは、一般にキーボードを使用して横断できます (つまり、UI オートメーション クライアントが隣接するコントロールに移動できます)。</span><span class="sxs-lookup"><span data-stu-id="9177f-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="9177f-116">IGridItemProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="9177f-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="9177f-117"><xref:System.Windows.Automation.Provider.IGridItemProvider>の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="9177f-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="9177f-118">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="9177f-118">Required members</span></span>|<span data-ttu-id="9177f-119">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="9177f-119">Member type</span></span>|<span data-ttu-id="9177f-120">Notes</span><span class="sxs-lookup"><span data-stu-id="9177f-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="9177f-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9177f-121">Property</span></span>|<span data-ttu-id="9177f-122">なし</span><span class="sxs-lookup"><span data-stu-id="9177f-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="9177f-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9177f-123">Property</span></span>|<span data-ttu-id="9177f-124">なし</span><span class="sxs-lookup"><span data-stu-id="9177f-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="9177f-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9177f-125">Property</span></span>|<span data-ttu-id="9177f-126">なし</span><span class="sxs-lookup"><span data-stu-id="9177f-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="9177f-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9177f-127">Property</span></span>|<span data-ttu-id="9177f-128">なし</span><span class="sxs-lookup"><span data-stu-id="9177f-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="9177f-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9177f-129">Property</span></span>|<span data-ttu-id="9177f-130">なし</span><span class="sxs-lookup"><span data-stu-id="9177f-130">None</span></span>|  
  
 <span data-ttu-id="9177f-131">このコントロール パターンに関連するメソッドまたはイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="9177f-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="9177f-132">例外</span><span class="sxs-lookup"><span data-stu-id="9177f-132">Exceptions</span></span>  
 <span data-ttu-id="9177f-133">このコントロール パターンに関連付けられた例外はありません。</span><span class="sxs-lookup"><span data-stu-id="9177f-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9177f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="9177f-134">See also</span></span>

- [<span data-ttu-id="9177f-135">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="9177f-135">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="9177f-136">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="9177f-136">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="9177f-137">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="9177f-137">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="9177f-138">UI オートメーション Grid コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="9177f-138">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="9177f-139">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="9177f-139">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="9177f-140">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="9177f-140">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
