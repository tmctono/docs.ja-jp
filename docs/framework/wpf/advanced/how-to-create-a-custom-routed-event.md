---
title: '方法: カスタム ルーティング イベントを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401471"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="59fd5-102">方法: カスタム ルーティング イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="59fd5-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="59fd5-103">カスタムイベントでイベントルーティングをサポートするには、 <xref:System.Windows.RoutedEvent> <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>メソッドを使用してを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59fd5-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="59fd5-104">この例では、カスタム ルーティング イベント作成の基本を紹介します。</span><span class="sxs-lookup"><span data-stu-id="59fd5-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59fd5-105">例</span><span class="sxs-lookup"><span data-stu-id="59fd5-105">Example</span></span>  
 <span data-ttu-id="59fd5-106">次の例に示すように、最初に<xref:System.Windows.RoutedEvent> <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>メソッドを使用してを登録します。</span><span class="sxs-lookup"><span data-stu-id="59fd5-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="59fd5-107">慣例により、 <xref:System.Windows.RoutedEvent>静的なフィールド名はサフィックス***イベント***で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59fd5-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="59fd5-108">この例では`Tap` 、イベントの名前はで、イベントのルーティング方法は<xref:System.Windows.RoutingStrategy.Bubble>です。</span><span class="sxs-lookup"><span data-stu-id="59fd5-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="59fd5-109">登録呼び出しの後に、イベントの追加と削除の共通言語ランタイム (CLR) イベントアクセサーを提供できます。</span><span class="sxs-lookup"><span data-stu-id="59fd5-109">After the registration call, you can provide add-and-remove common language runtime (CLR) event accessors for the event.</span></span>  
  
 <span data-ttu-id="59fd5-110">この特別な例では `OnTap` 仮想メソッド経由でイベントが発生していますが、イベントの発生や変更に対するイベントの反応の仕方はニーズによって変わります。</span><span class="sxs-lookup"><span data-stu-id="59fd5-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="59fd5-111">また、この例では、基本的にのサブ<xref:System.Windows.Controls.Button>クラス全体が実装されていることに注意してください。そのサブクラスは[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]個別のアセンブリとして構築され、別のページでカスタムクラスとしてインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="59fd5-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="59fd5-112">これはサブクラス化されたコントロールを他のコントロールで構成されたツリーに挿入できるという概念を示すものです。この状況では、このようなコントロールのカスタム イベントには、あらゆるネイティブ [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 要素とまったく同じイベント ルーティング機能が与えられます。</span><span class="sxs-lookup"><span data-stu-id="59fd5-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="59fd5-113">トンネリングイベントは同じように作成されます<xref:System.Windows.RoutedEvent.RoutingStrategy%2A>が、 <xref:System.Windows.RoutingStrategy.Tunnel>が登録呼び出しでに設定されます。</span><span class="sxs-lookup"><span data-stu-id="59fd5-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="59fd5-114">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のトンネル イベントには接頭辞として "Preview" という単語が付く決まりになっています。</span><span class="sxs-lookup"><span data-stu-id="59fd5-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="59fd5-115">バブリング イベントの動作例については、「[ルーティング イベントを処理する](how-to-handle-a-routed-event.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59fd5-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fd5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="59fd5-116">See also</span></span>

- [<span data-ttu-id="59fd5-117">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="59fd5-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="59fd5-118">入力の概要</span><span class="sxs-lookup"><span data-stu-id="59fd5-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="59fd5-119">コントロールの作成の概要</span><span class="sxs-lookup"><span data-stu-id="59fd5-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
