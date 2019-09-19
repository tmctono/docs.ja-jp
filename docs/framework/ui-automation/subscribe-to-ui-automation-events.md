---
title: UI オートメーション イベントのサブスクライブ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: 1e148869f619729c72eae67892d4767eed9f8fb3
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042640"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="7b7ae-102">UI オートメーション イベントのサブスクライブ</span><span class="sxs-lookup"><span data-stu-id="7b7ae-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
> <span data-ttu-id="7b7ae-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7b7ae-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7b7ae-105">このトピックでは、UI オートメーション プロバイダーによって生成されるイベントをサブスクライブする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b7ae-106">例</span><span class="sxs-lookup"><span data-stu-id="7b7ae-106">Example</span></span>  
 <span data-ttu-id="7b7ae-107">次のコード例では、ボタンなどのコントロールが呼び出された場合に生成されるイベントに対してイベント ハンドラーを登録し、アプリケーション フォームが閉じられた時にそのイベント ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="7b7ae-108">イベントは、パラメーターとして <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A> に渡される <xref:System.Windows.Automation.AutomationEvent> によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="7b7ae-109">例</span><span class="sxs-lookup"><span data-stu-id="7b7ae-109">Example</span></span>  
 <span data-ttu-id="7b7ae-110">次の例は、[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] を使用して、フォーカスが変更された場合に生成されるイベントをサブスクライブする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="7b7ae-111">イベント ハンドラーの登録は、アプリケーションのシャットダウン時に呼び出されるメソッドで解除されるか、UI イベントの通知が必要なくなった時に解除されます。</span><span class="sxs-lookup"><span data-stu-id="7b7ae-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="7b7ae-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b7ae-112">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="7b7ae-113">UI オートメーション イベントの概要</span><span class="sxs-lookup"><span data-stu-id="7b7ae-113">UI Automation Events Overview</span></span>](ui-automation-events-overview.md)
