---
title: UI オートメーション Toggle コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: c25f2d3b73e90adb3299ff8c4ff7c8a77fc5fc5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447077"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="d0884-102">UI オートメーション Toggle コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="d0884-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="d0884-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d0884-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d0884-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0884-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d0884-105">このトピックでは、メソッドおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IToggleProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0884-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="d0884-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="d0884-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d0884-107"><xref:System.Windows.Automation.TogglePattern> コントロール パターンは、一連の状態を順番に繰り返し、状態を一度設定したらそれを保持できるコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="d0884-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="d0884-108">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0884-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d0884-109">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="d0884-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d0884-110">Toggle コントロール パターンを実装する場合は、次のガイドラインと規則にご留意ください。</span><span class="sxs-lookup"><span data-stu-id="d0884-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d0884-111">ボタン、ツール バー ボタン、ハイパーリンクなど、アクティブになったときに状態を保持しないコントロールは、代わりに <xref:System.Windows.Automation.Provider.IInvokeProvider> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0884-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="d0884-112">コントロールは、 <xref:System.Windows.Automation.ToggleState> 、 <xref:System.Windows.Automation.ToggleState.On>、 <xref:System.Windows.Automation.ToggleState.Off> (サポートされている場合) の順にその <xref:System.Windows.Automation.ToggleState.Indeterminate>を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0884-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="d0884-113"><xref:System.Windows.Automation.TogglePattern> は、SetState(newState) メソッドを提供しません。これは、適切な <xref:System.Windows.Automation.ToggleState> の順番の繰り返しをせずに、3 つの状態を持つ CheckBox を直接設定することに関連する問題のためです。</span><span class="sxs-lookup"><span data-stu-id="d0884-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="d0884-114">RadioButton コントロールは <xref:System.Windows.Automation.Provider.IToggleProvider>を実装しません。これは、その正しい状態を順番に繰り返す機能がないためです。</span><span class="sxs-lookup"><span data-stu-id="d0884-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="d0884-115">IToggleProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="d0884-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="d0884-116"><xref:System.Windows.Automation.Provider.IToggleProvider>の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0884-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="d0884-117">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="d0884-117">Required member</span></span>|<span data-ttu-id="d0884-118">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="d0884-118">Member type</span></span>|<span data-ttu-id="d0884-119">ノート</span><span class="sxs-lookup"><span data-stu-id="d0884-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="d0884-120">メソッド</span><span class="sxs-lookup"><span data-stu-id="d0884-120">Method</span></span>|<span data-ttu-id="d0884-121">None</span><span class="sxs-lookup"><span data-stu-id="d0884-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="d0884-122">property</span><span class="sxs-lookup"><span data-stu-id="d0884-122">Property</span></span>|<span data-ttu-id="d0884-123">None</span><span class="sxs-lookup"><span data-stu-id="d0884-123">None</span></span>|  
  
 <span data-ttu-id="d0884-124">このコントロール パターンには、関連するイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="d0884-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="d0884-125">例外</span><span class="sxs-lookup"><span data-stu-id="d0884-125">Exceptions</span></span>  
 <span data-ttu-id="d0884-126">このコントロール パターンに関連付けられた例外はありません。</span><span class="sxs-lookup"><span data-stu-id="d0884-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0884-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0884-127">See also</span></span>

- [<span data-ttu-id="d0884-128">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="d0884-128">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d0884-129">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="d0884-129">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d0884-130">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="d0884-130">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d0884-131">UI オートメーションを使用した、チェック ボックスのトグル状態の取得</span><span class="sxs-lookup"><span data-stu-id="d0884-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="d0884-132">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="d0884-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d0884-133">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="d0884-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
