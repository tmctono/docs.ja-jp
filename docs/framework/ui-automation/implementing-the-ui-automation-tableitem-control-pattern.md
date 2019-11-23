---
title: UI オートメーション TableItem コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 4374666ba5e03720413614c63b00ba987f81f58f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447083"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="2ad95-102">UI オートメーション TableItem コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="2ad95-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="2ad95-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2ad95-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2ad95-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ad95-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2ad95-105">このトピックでは、イベントおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.ITableItemProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ad95-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="2ad95-106">その他のリファレンスへのリンクは、概要の最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="2ad95-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="2ad95-107"><xref:System.Windows.Automation.Provider.ITableProvider> を実装するコンテナーの子コントロールをサポートするために、<xref:System.Windows.Automation.TableItemPattern> コントロール パターンが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2ad95-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="2ad95-108">個々のセル機能へのアクセスは、必要な <xref:System.Windows.Automation.Provider.IGridItemProvider> の同時実装によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="2ad95-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="2ad95-109">このコントロール パターンは <xref:System.Windows.Automation.Provider.IGridItemProvider> と同様です。異なる点は、<xref:System.Windows.Automation.Provider.ITableItemProvider> を実装するコントロールは、個々のセルとその行および列情報の間の関係をプログラムによって公開しなければならないことです。</span><span class="sxs-lookup"><span data-stu-id="2ad95-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="2ad95-110">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ad95-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2ad95-111">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="2ad95-111">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="2ad95-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2ad95-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="2ad95-113">ITableItemProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="2ad95-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="2ad95-114">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="2ad95-114">Required member</span></span>|<span data-ttu-id="2ad95-115">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="2ad95-115">Member type</span></span>|<span data-ttu-id="2ad95-116">ノート</span><span class="sxs-lookup"><span data-stu-id="2ad95-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="2ad95-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ad95-117">Method</span></span>|<span data-ttu-id="2ad95-118">None</span><span class="sxs-lookup"><span data-stu-id="2ad95-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="2ad95-119">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ad95-119">Method</span></span>|<span data-ttu-id="2ad95-120">None</span><span class="sxs-lookup"><span data-stu-id="2ad95-120">None</span></span>|  
  
 <span data-ttu-id="2ad95-121">このコントロール パターンに関連付けられるプロパティやイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="2ad95-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="2ad95-122">例外</span><span class="sxs-lookup"><span data-stu-id="2ad95-122">Exceptions</span></span>  
 <span data-ttu-id="2ad95-123">このコントロール パターンに関連付けられた例外はありません。</span><span class="sxs-lookup"><span data-stu-id="2ad95-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad95-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ad95-124">See also</span></span>

- [<span data-ttu-id="2ad95-125">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="2ad95-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="2ad95-126">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="2ad95-126">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="2ad95-127">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="2ad95-127">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="2ad95-128">UI オートメーション Table コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="2ad95-128">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="2ad95-129">UI オートメーション GridItem コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="2ad95-129">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="2ad95-130">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="2ad95-130">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="2ad95-131">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="2ad95-131">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
