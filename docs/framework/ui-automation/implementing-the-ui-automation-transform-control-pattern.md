---
title: UI オートメーション Transform コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: c0a46580ad2673b56fefe7228f2549a2e19d2c14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447060"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="4d312-102">UI オートメーション Transform コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="4d312-102">Implementing the UI Automation Transform Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="4d312-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="4d312-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4d312-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d312-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="4d312-105">このトピックでは、プロパティ、メソッド、イベントに関する情報など、 <xref:System.Windows.Automation.Provider.ITransformProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d312-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="4d312-106">その他のリファレンスへのリンクは、このトピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="4d312-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="4d312-107"><xref:System.Windows.Automation.TransformPattern> コントロール パターンは、2 次元空間で移動、サイズ変更、または回転できるコントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d312-107">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="4d312-108">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d312-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4d312-109">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="4d312-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4d312-110">Transform コントロール パターンを実装する場合は、次のガイドラインと規則にご留意ください。</span><span class="sxs-lookup"><span data-stu-id="4d312-110">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="4d312-111">このコントロール パターンのサポートは、デスクトップ上のオブジェクトに制限されません。</span><span class="sxs-lookup"><span data-stu-id="4d312-111">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="4d312-112">コンテナーの境界内で子が自由に移動、サイズ変更、または回転できるようにする場合は、そのコンテナー オブジェクトの子もこのコントロール パターンをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d312-112">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="4d312-113">操作後の画面位置が完全にそのコンテナーの座標外となり、キーボードやマウスからアクセスできなくなる場合 (たとえば、トップレベルのウィンドウが画面外に移動したり、子オブジェクトがコンテナーのビューポートの境界外へ移動したりする場合) は、オブジェクトの移動、サイズ変更、および回転はできません。</span><span class="sxs-lookup"><span data-stu-id="4d312-113">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="4d312-114">このような場合、上辺または左辺の座標をコンテナーの境界内にオーバーライドして、要求された画面座標のできるだけ近くにオブジェクトが配置されます。</span><span class="sxs-lookup"><span data-stu-id="4d312-114">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="4d312-115">マルチモニター システムでは、結合したデスクトップ画面座標の完全に外へオブジェクトを移動、サイズ変更、または回転した場合、プライマリ モニター上の、要求された画面座標のできるだけ近くにオブジェクトが配置されます。</span><span class="sxs-lookup"><span data-stu-id="4d312-115">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="4d312-116">すべてのパラメーターとプロパティの値は絶対値で、ロケールには依存しません。</span><span class="sxs-lookup"><span data-stu-id="4d312-116">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="4d312-117">ITransformProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="4d312-117">Required Members for ITransformProvider</span></span>  
 <span data-ttu-id="4d312-118"><xref:System.Windows.Automation.Provider.ITransformProvider>の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d312-118">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="4d312-119">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="4d312-119">Required members</span></span>|<span data-ttu-id="4d312-120">メンバーの種類</span><span class="sxs-lookup"><span data-stu-id="4d312-120">Member type</span></span>|<span data-ttu-id="4d312-121">説明</span><span class="sxs-lookup"><span data-stu-id="4d312-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="4d312-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4d312-122">Property</span></span>|<span data-ttu-id="4d312-123">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="4d312-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4d312-124">Property</span></span>|<span data-ttu-id="4d312-125">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="4d312-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4d312-126">Property</span></span>|<span data-ttu-id="4d312-127">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="4d312-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="4d312-128">Method</span></span>|<span data-ttu-id="4d312-129">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="4d312-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="4d312-130">Method</span></span>|<span data-ttu-id="4d312-131">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="4d312-132">メソッド</span><span class="sxs-lookup"><span data-stu-id="4d312-132">Method</span></span>|<span data-ttu-id="4d312-133">なし</span><span class="sxs-lookup"><span data-stu-id="4d312-133">None</span></span>|  
  
 <span data-ttu-id="4d312-134">このコントロール パターンには、関連するイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="4d312-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4d312-135">例外</span><span class="sxs-lookup"><span data-stu-id="4d312-135">Exceptions</span></span>  
 <span data-ttu-id="4d312-136">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d312-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="4d312-137">例外の種類</span><span class="sxs-lookup"><span data-stu-id="4d312-137">Exception Type</span></span>|<span data-ttu-id="4d312-138">条件</span><span class="sxs-lookup"><span data-stu-id="4d312-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="4d312-139">-<xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> が false の場合。</span><span class="sxs-lookup"><span data-stu-id="4d312-139">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="4d312-140">-<xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> が false の場合。</span><span class="sxs-lookup"><span data-stu-id="4d312-140">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="4d312-141">-<xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> が false の場合。</span><span class="sxs-lookup"><span data-stu-id="4d312-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d312-142">参照</span><span class="sxs-lookup"><span data-stu-id="4d312-142">See also</span></span>

- [<span data-ttu-id="4d312-143">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="4d312-143">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="4d312-144">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="4d312-144">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="4d312-145">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="4d312-145">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="4d312-146">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="4d312-146">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="4d312-147">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="4d312-147">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
