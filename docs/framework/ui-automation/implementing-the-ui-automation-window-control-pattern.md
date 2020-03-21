---
title: UI オートメーション Window コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: dd677ca9f610d463acc7c69f99767bd7b8781589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180033"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="f8713-102">UI オートメーション Window コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="f8713-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="f8713-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f8713-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f8713-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f8713-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="f8713-105">このトピックでは、 <xref:System.Windows.Automation.Provider.IWindowProvider>のプロパティ、メソッド、イベントに関する情報など、 <xref:System.Windows.Automation.WindowPattern> の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8713-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="f8713-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="f8713-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="f8713-107">コントロール<xref:System.Windows.Automation.WindowPattern>パターンは、従来のグラフィカル ユーザー インターフェイス (GUI) 内で基本的なウィンドウ ベースの機能を提供するコントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8713-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional graphical user interface (GUI).</span></span> <span data-ttu-id="f8713-108">このコントロール パターンを実装する必要があるコントロールの例としては、トップレベルのアプリケーション ウィンドウ、マルチ ドキュメント インターフェイス (MDI) 子ウィンドウ、拡張可能な分割ペイン コントロール、モーダル ダイアログ、バルーン ヘルプ ウィンドウなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f8713-108">Examples of controls that must implement this control pattern include top-level application windows, multiple-document interface (MDI) child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="f8713-109">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="f8713-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="f8713-110">Window コントロール パターンを実装する場合は、次のガイドラインと規則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8713-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="f8713-111">UI オートメーションを使用してウィンドウのサイズと位置の両方を変更する機能をサポートするには、コントロールが <xref:System.Windows.Automation.Provider.ITransformProvider> に加えて <xref:System.Windows.Automation.Provider.IWindowProvider>を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8713-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f8713-112">コントロールを移動、サイズ変更、最大化、最小化、および閉じられるようにするタイトル バーの要素とタイトル バーを格納するコントロールは、通常 <xref:System.Windows.Automation.Provider.IWindowProvider>を実装することが求められます。</span><span class="sxs-lookup"><span data-stu-id="f8713-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f8713-113">ツールヒントのポップアップやコンボ ボックス、またはメニューのドロップダウンなどのコントロールは、通常 <xref:System.Windows.Automation.Provider.IWindowProvider>を実装しません。</span><span class="sxs-lookup"><span data-stu-id="f8713-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="f8713-114">バルーン ヘルプ ウィンドウは、ウィンドウと同様の閉じるボタンを提供することで、基本的なツールヒント ポップアップから区別されます。</span><span class="sxs-lookup"><span data-stu-id="f8713-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="f8713-115">全画面表示モードは、アプリケーション固有の機能であり、通常のウィンドウの動作ではないため、IWindowProvider によってサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f8713-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="f8713-116">IWindowProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="f8713-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="f8713-117">IWindowProvider インターフェイスには、次のプロパティ、メソッド、イベントが必要です。</span><span class="sxs-lookup"><span data-stu-id="f8713-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="f8713-118">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="f8713-118">Required member</span></span>|<span data-ttu-id="f8713-119">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="f8713-119">Member type</span></span>|<span data-ttu-id="f8713-120">Notes</span><span class="sxs-lookup"><span data-stu-id="f8713-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="f8713-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-121">Property</span></span>|<span data-ttu-id="f8713-122">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="f8713-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-123">Property</span></span>|<span data-ttu-id="f8713-124">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="f8713-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-125">Property</span></span>|<span data-ttu-id="f8713-126">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="f8713-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-127">Property</span></span>|<span data-ttu-id="f8713-128">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="f8713-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-129">Property</span></span>|<span data-ttu-id="f8713-130">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="f8713-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8713-131">Property</span></span>|<span data-ttu-id="f8713-132">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="f8713-133">Method</span><span class="sxs-lookup"><span data-stu-id="f8713-133">Method</span></span>|<span data-ttu-id="f8713-134">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="f8713-135">Method</span><span class="sxs-lookup"><span data-stu-id="f8713-135">Method</span></span>|<span data-ttu-id="f8713-136">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="f8713-137">Method</span><span class="sxs-lookup"><span data-stu-id="f8713-137">Method</span></span>|<span data-ttu-id="f8713-138">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="f8713-139">Event</span><span class="sxs-lookup"><span data-stu-id="f8713-139">Event</span></span>|<span data-ttu-id="f8713-140">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="f8713-141">Event</span><span class="sxs-lookup"><span data-stu-id="f8713-141">Event</span></span>|<span data-ttu-id="f8713-142">なし</span><span class="sxs-lookup"><span data-stu-id="f8713-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="f8713-143">Event</span><span class="sxs-lookup"><span data-stu-id="f8713-143">Event</span></span>|<span data-ttu-id="f8713-144"><xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="f8713-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="f8713-145">例外</span><span class="sxs-lookup"><span data-stu-id="f8713-145">Exceptions</span></span>  
 <span data-ttu-id="f8713-146">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8713-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="f8713-147">例外の種類</span><span class="sxs-lookup"><span data-stu-id="f8713-147">Exception type</span></span>|<span data-ttu-id="f8713-148">条件</span><span class="sxs-lookup"><span data-stu-id="f8713-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="f8713-149">- コントロールが要求された動作をサポートしていない場合。</span><span class="sxs-lookup"><span data-stu-id="f8713-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="f8713-150">- パラメータが有効な数値でない場合。</span><span class="sxs-lookup"><span data-stu-id="f8713-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8713-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8713-151">See also</span></span>

- [<span data-ttu-id="f8713-152">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="f8713-152">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="f8713-153">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="f8713-153">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="f8713-154">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="f8713-154">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="f8713-155">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="f8713-155">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="f8713-156">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="f8713-156">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
