---
title: UI オートメーション Window コントロール パターンの実装
description: UI オートメーションで Window コントロールパターンを実装するためのガイドラインと規則を確認します。 IWindowProvider インターフェイスに必要なメンバーを確認します。
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: e1d7429f86896947a10b73965caa7d771f54490b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168192"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="179fc-104">UI オートメーション Window コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="179fc-104">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="179fc-105">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="179fc-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="179fc-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="179fc-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="179fc-107">このトピックでは、 <xref:System.Windows.Automation.Provider.IWindowProvider>のプロパティ、メソッド、イベントに関する情報など、 <xref:System.Windows.Automation.WindowPattern> の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="179fc-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="179fc-108">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="179fc-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="179fc-109"><xref:System.Windows.Automation.WindowPattern>コントロールパターンは、従来のグラフィカルユーザーインターフェイス (GUI) 内で、ウィンドウベースの基本的な機能を提供するコントロールをサポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="179fc-109">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional graphical user interface (GUI).</span></span> <span data-ttu-id="179fc-110">このコントロールパターンを実装する必要があるコントロールの例としては、トップレベルアプリケーションウィンドウ、マルチドキュメントインターフェイス (MDI) 子ウィンドウ、サイズ変更可能な分割ペインコントロール、モーダルダイアログボックス、バルーンヘルプウィンドウなどがあります。</span><span class="sxs-lookup"><span data-stu-id="179fc-110">Examples of controls that must implement this control pattern include top-level application windows, multiple-document interface (MDI) child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="179fc-111">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="179fc-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="179fc-112">Window コントロール パターンを実装する場合は、次のガイドラインと規則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="179fc-112">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="179fc-113">UI オートメーションを使用してウィンドウのサイズと位置の両方を変更する機能をサポートするには、コントロールが <xref:System.Windows.Automation.Provider.ITransformProvider> に加えて <xref:System.Windows.Automation.Provider.IWindowProvider>を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="179fc-113">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="179fc-114">コントロールを移動、サイズ変更、最大化、最小化、および閉じられるようにするタイトル バーの要素とタイトル バーを格納するコントロールは、通常 <xref:System.Windows.Automation.Provider.IWindowProvider>を実装することが求められます。</span><span class="sxs-lookup"><span data-stu-id="179fc-114">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="179fc-115">ツールヒントのポップアップやコンボ ボックス、またはメニューのドロップダウンなどのコントロールは、通常 <xref:System.Windows.Automation.Provider.IWindowProvider>を実装しません。</span><span class="sxs-lookup"><span data-stu-id="179fc-115">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="179fc-116">バルーン ヘルプ ウィンドウは、ウィンドウと同様の閉じるボタンを提供することで、基本的なツールヒント ポップアップから区別されます。</span><span class="sxs-lookup"><span data-stu-id="179fc-116">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="179fc-117">全画面表示モードは、アプリケーション固有の機能であり、通常のウィンドウの動作ではないため、IWindowProvider によってサポートされません。</span><span class="sxs-lookup"><span data-stu-id="179fc-117">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="179fc-118">IWindowProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="179fc-118">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="179fc-119">IWindowProvider インターフェイスには、次のプロパティ、メソッド、イベントが必要です。</span><span class="sxs-lookup"><span data-stu-id="179fc-119">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="179fc-120">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="179fc-120">Required member</span></span>|<span data-ttu-id="179fc-121">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="179fc-121">Member type</span></span>|<span data-ttu-id="179fc-122">メモ</span><span class="sxs-lookup"><span data-stu-id="179fc-122">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="179fc-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-123">Property</span></span>|<span data-ttu-id="179fc-124">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="179fc-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-125">Property</span></span>|<span data-ttu-id="179fc-126">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="179fc-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-127">Property</span></span>|<span data-ttu-id="179fc-128">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="179fc-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-129">Property</span></span>|<span data-ttu-id="179fc-130">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="179fc-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-131">Property</span></span>|<span data-ttu-id="179fc-132">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="179fc-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="179fc-133">Property</span></span>|<span data-ttu-id="179fc-134">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="179fc-135">メソッド</span><span class="sxs-lookup"><span data-stu-id="179fc-135">Method</span></span>|<span data-ttu-id="179fc-136">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="179fc-137">メソッド</span><span class="sxs-lookup"><span data-stu-id="179fc-137">Method</span></span>|<span data-ttu-id="179fc-138">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-138">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="179fc-139">メソッド</span><span class="sxs-lookup"><span data-stu-id="179fc-139">Method</span></span>|<span data-ttu-id="179fc-140">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="179fc-141">Event</span><span class="sxs-lookup"><span data-stu-id="179fc-141">Event</span></span>|<span data-ttu-id="179fc-142">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="179fc-143">Event</span><span class="sxs-lookup"><span data-stu-id="179fc-143">Event</span></span>|<span data-ttu-id="179fc-144">なし</span><span class="sxs-lookup"><span data-stu-id="179fc-144">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="179fc-145">Event</span><span class="sxs-lookup"><span data-stu-id="179fc-145">Event</span></span>|<span data-ttu-id="179fc-146"><xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="179fc-146">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="179fc-147">例外</span><span class="sxs-lookup"><span data-stu-id="179fc-147">Exceptions</span></span>  
 <span data-ttu-id="179fc-148">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="179fc-148">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="179fc-149">例外の種類</span><span class="sxs-lookup"><span data-stu-id="179fc-149">Exception type</span></span>|<span data-ttu-id="179fc-150">条件</span><span class="sxs-lookup"><span data-stu-id="179fc-150">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="179fc-151">-要求された動作をコントロールがサポートしていない場合。</span><span class="sxs-lookup"><span data-stu-id="179fc-151">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="179fc-152">-パラメーターが有効な数値でない場合。</span><span class="sxs-lookup"><span data-stu-id="179fc-152">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="179fc-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="179fc-153">See also</span></span>

- [<span data-ttu-id="179fc-154">UI オートメーション コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="179fc-154">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="179fc-155">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="179fc-155">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="179fc-156">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="179fc-156">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="179fc-157">UI オートメーション ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="179fc-157">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="179fc-158">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="179fc-158">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
