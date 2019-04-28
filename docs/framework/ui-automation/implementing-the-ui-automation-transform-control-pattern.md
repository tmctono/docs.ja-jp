---
title: UI オートメーション Transform コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: d038991da4048e3279ae974cbf4d3e53691349af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645774"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="38a0a-102">UI オートメーション Transform コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="38a0a-102">Implementing the UI Automation Transform Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="38a0a-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="38a0a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="38a0a-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="38a0a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="38a0a-105">このトピックでは、プロパティ、メソッド、イベントに関する情報など、 <xref:System.Windows.Automation.Provider.ITransformProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="38a0a-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="38a0a-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="38a0a-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="38a0a-107"><xref:System.Windows.Automation.TransformPattern> コントロール パターンは、2 次元空間で移動、サイズ変更、または回転できるコントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="38a0a-107">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="38a0a-108">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38a0a-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="38a0a-109">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="38a0a-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="38a0a-110">Transform コントロール パターンを実装する場合は、次のガイドラインと規則にご留意ください。</span><span class="sxs-lookup"><span data-stu-id="38a0a-110">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="38a0a-111">このコントロール パターンのサポートは、デスクトップ上のオブジェクトに制限されません。</span><span class="sxs-lookup"><span data-stu-id="38a0a-111">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="38a0a-112">コンテナーの境界内で子が自由に移動、サイズ変更、または回転できるようにする場合は、そのコンテナー オブジェクトの子もこのコントロール パターンをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a0a-112">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="38a0a-113">操作後の画面位置が完全にそのコンテナーの座標外となり、キーボードやマウスからアクセスできなくなる場合 (たとえば、トップレベルのウィンドウが画面外に移動したり、子オブジェクトがコンテナーのビューポートの境界外へ移動したりする場合) は、オブジェクトの移動、サイズ変更、および回転はできません。</span><span class="sxs-lookup"><span data-stu-id="38a0a-113">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="38a0a-114">このような場合、上辺または左辺の座標をコンテナーの境界内にオーバーライドして、要求された画面座標のできるだけ近くにオブジェクトが配置されます。</span><span class="sxs-lookup"><span data-stu-id="38a0a-114">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="38a0a-115">マルチモニター システムでは、結合したデスクトップ画面座標の完全に外へオブジェクトを移動、サイズ変更、または回転した場合、プライマリ モニター上の、要求された画面座標のできるだけ近くにオブジェクトが配置されます。</span><span class="sxs-lookup"><span data-stu-id="38a0a-115">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="38a0a-116">すべてのパラメーターとプロパティの値は絶対値で、ロケールには依存しません。</span><span class="sxs-lookup"><span data-stu-id="38a0a-116">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="38a0a-117">ITransformProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="38a0a-117">Required Members for ITransformProvider</span></span>  
 <span data-ttu-id="38a0a-118"><xref:System.Windows.Automation.Provider.ITransformProvider>の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="38a0a-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="38a0a-119">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="38a0a-119">Required members</span></span>|<span data-ttu-id="38a0a-120">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="38a0a-120">Member type</span></span>|<span data-ttu-id="38a0a-121">メモ</span><span class="sxs-lookup"><span data-stu-id="38a0a-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="38a0a-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38a0a-122">Property</span></span>|<span data-ttu-id="38a0a-123">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="38a0a-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38a0a-124">Property</span></span>|<span data-ttu-id="38a0a-125">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="38a0a-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38a0a-126">Property</span></span>|<span data-ttu-id="38a0a-127">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="38a0a-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="38a0a-128">Method</span></span>|<span data-ttu-id="38a0a-129">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="38a0a-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="38a0a-130">Method</span></span>|<span data-ttu-id="38a0a-131">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="38a0a-132">メソッド</span><span class="sxs-lookup"><span data-stu-id="38a0a-132">Method</span></span>|<span data-ttu-id="38a0a-133">なし</span><span class="sxs-lookup"><span data-stu-id="38a0a-133">None</span></span>|  
  
 <span data-ttu-id="38a0a-134">このコントロール パターンには、関連するイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="38a0a-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="38a0a-135">例外</span><span class="sxs-lookup"><span data-stu-id="38a0a-135">Exceptions</span></span>  
 <span data-ttu-id="38a0a-136">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a0a-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="38a0a-137">例外の種類</span><span class="sxs-lookup"><span data-stu-id="38a0a-137">Exception Type</span></span>|<span data-ttu-id="38a0a-138">条件</span><span class="sxs-lookup"><span data-stu-id="38a0a-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="38a0a-139">If、<xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty>は false です。</span><span class="sxs-lookup"><span data-stu-id="38a0a-139">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="38a0a-140">If、<xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty>は false です。</span><span class="sxs-lookup"><span data-stu-id="38a0a-140">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="38a0a-141">If、<xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty>は false です。</span><span class="sxs-lookup"><span data-stu-id="38a0a-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38a0a-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="38a0a-142">See also</span></span>

- [<span data-ttu-id="38a0a-143">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="38a0a-143">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="38a0a-144">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="38a0a-144">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="38a0a-145">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="38a0a-145">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="38a0a-146">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="38a0a-146">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="38a0a-147">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="38a0a-147">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
