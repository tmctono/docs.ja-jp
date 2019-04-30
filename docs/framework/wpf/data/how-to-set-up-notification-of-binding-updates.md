---
title: '方法: バインディングの更新の通知を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: 4185198312ed98f9aaa1388626600d9f21abae55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051989"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="bdc3f-102">方法: バインディングの更新の通知を設定する</span><span class="sxs-lookup"><span data-stu-id="bdc3f-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="bdc3f-103">この例では、バインドのバインディング ターゲット (ターゲット) またはバインディング ソース (ソース) のプロパティが更新されたときに通知するように設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdc3f-104">例</span><span class="sxs-lookup"><span data-stu-id="bdc3f-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="bdc3f-105">は、バインドのソースまたはターゲットが更新されるたびにデータ更新イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-105">raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="bdc3f-106">内部的には、このイベントは、バインドされたデータが変更されているため、更新する必要があることを [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] に通知するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="bdc3f-107">これらのイベントをするには、また、一方向または双方向のバインドが適切に機能が使用してデータ クラスを実装する必要がありますに注意してください、<xref:System.ComponentModel.INotifyPropertyChanged>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="bdc3f-108">詳細については、「[プロパティの変更通知を実装する](how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-108">For more information, see [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="bdc3f-109">設定、<xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>または<xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>するプロパティ (または両方)`true`バインドにします。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="bdc3f-110">このイベントをリッスンするために提供するハンドラーは、変更を通知する要素に直接アタッチするか、コンテキスト内の何かが変更されたことを認識する場合は、全体的なデータ コンテキストにアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="bdc3f-111">ターゲットのプロパティが更新されたときの通知を設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="bdc3f-112">その後、EventHandler\<T> デリゲート (この例では *OnTargetUpdated*) に基づいて、イベントを処理するハンドラーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="bdc3f-113">イベントのパラメーターを使用して、変更されたプロパティの詳細 (型や、複数の要素に同じハンドラーがアタッチされている場合の特定の要素など) を確認できます。これは、1 つの要素に複数のバインドされたプロパティがある場合に役に立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bdc3f-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc3f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdc3f-114">See also</span></span>

- [<span data-ttu-id="bdc3f-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="bdc3f-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="bdc3f-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="bdc3f-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
