---
title: '方法: コードを使用してイベント ハンドラーを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 05eaae0f5b893f42d421717ac73373d4c79004c4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352192"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="83ddc-102">方法: コードを使用してイベント ハンドラーを追加する</span><span class="sxs-lookup"><span data-stu-id="83ddc-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="83ddc-103">この例では、コードを使用して要素にイベント ハンドラーを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="83ddc-104">イベント ハンドラーを追加する場合、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]要素と、要素を含むマークアップ ページが読み込まれた既に、コードを使用してハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83ddc-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="83ddc-105">または、まったくコードを使用してとを使用して任意の要素が宣言されていないアプリケーションの要素ツリーを構築するかどうか[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、構築される要素ツリーにイベント ハンドラーを追加する特定のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="83ddc-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83ddc-106">例</span><span class="sxs-lookup"><span data-stu-id="83ddc-106">Example</span></span>  
 <span data-ttu-id="83ddc-107">次の例は、新しい追加<xref:System.Windows.Controls.Button>で最初に定義されている既存のページに[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="83ddc-108">分離コード ファイルは、イベント ハンドラー メソッドを実装してに新しいイベント ハンドラーとしてそのメソッドを追加、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="83ddc-109">C#の例では、`+=`演算子をイベントにハンドラーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="83ddc-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="83ddc-110">これは、のハンドラーを割り当てるために使用する演算子と同じ、[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]イベント モデルを処理します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="83ddc-111">Microsoft Visual Basic では、イベント ハンドラーを追加するための手段としてこの演算子はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="83ddc-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="83ddc-112">代わりに、2 つの手法の 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="83ddc-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="83ddc-113">使用して、<xref:System.Windows.UIElement.AddHandler%2A>メソッド、と共に、`AddressOf`演算子、イベント ハンドラーの実装を参照します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="83ddc-114">使用して、`Handles`イベント ハンドラーの定義の一部としてキーワード。</span><span class="sxs-lookup"><span data-stu-id="83ddc-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="83ddc-115">この手法はここでは表示されません。参照してください[Visual Basic と WPF のイベント処理](visual-basic-and-wpf-event-handling.md)します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="83ddc-116">最初に解析済みのイベント ハンドラーの追加[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページははるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="83ddc-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="83ddc-117">イベント ハンドラーを追加するオブジェクトの要素内で処理するイベントの名前に一致する属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="83ddc-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="83ddc-118">分離コード ファイルで定義されているイベント ハンドラー メソッドの名前とその属性の値を指定し、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページ。</span><span class="sxs-lookup"><span data-stu-id="83ddc-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="83ddc-119">詳細については、[XAML の概要 (WPF)](xaml-overview-wpf.md)または[ルーティング イベントの概要](routed-events-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83ddc-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ddc-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="83ddc-120">See also</span></span>
- [<span data-ttu-id="83ddc-121">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="83ddc-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="83ddc-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="83ddc-122">How-to Topics</span></span>](events-how-to-topics.md)
