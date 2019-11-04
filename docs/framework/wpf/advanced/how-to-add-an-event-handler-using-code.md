---
title: '方法 : コードを使用してイベント ハンドラーを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460432"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="8be81-102">方法 : コードを使用してイベント ハンドラーを追加する</span><span class="sxs-lookup"><span data-stu-id="8be81-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="8be81-103">この例では、コードを使用して、イベントハンドラーを要素に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8be81-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="8be81-104">イベントハンドラーを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 要素に追加し、その要素を含むマークアップページが既に読み込まれている場合は、コードを使用してハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be81-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="8be81-105">また、コードを使用してアプリケーションの要素ツリーを完全に構築し、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して要素を宣言しない場合は、特定のメソッドを呼び出して、構築された要素ツリーにイベントハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8be81-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8be81-106">例</span><span class="sxs-lookup"><span data-stu-id="8be81-106">Example</span></span>  
 <span data-ttu-id="8be81-107">次の例では、最初に [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]で定義された既存のページに新しい <xref:System.Windows.Controls.Button> を追加します。</span><span class="sxs-lookup"><span data-stu-id="8be81-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="8be81-108">分離コードファイルは、イベントハンドラーメソッドを実装し、そのメソッドを <xref:System.Windows.Controls.Button>の新しいイベントハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8be81-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="8be81-109">このC#例では、`+=` 演算子を使用して、ハンドラーをイベントに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="8be81-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="8be81-110">これは、共通言語ランタイム (CLR) イベント処理モデルでハンドラーを割り当てるために使用される演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="8be81-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="8be81-111">Microsoft Visual Basic では、イベントハンドラーを追加する手段として、この演算子はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8be81-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="8be81-112">代わりに、次の2つの方法のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="8be81-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="8be81-113"><xref:System.Windows.UIElement.AddHandler%2A> メソッドを `AddressOf` 演算子と共に使用して、イベントハンドラーの実装を参照します。</span><span class="sxs-lookup"><span data-stu-id="8be81-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="8be81-114">イベントハンドラー定義の一部として、`Handles` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8be81-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="8be81-115">この手法は、ここでは示していません。「 [Visual Basic と WPF のイベント処理」を](visual-basic-and-wpf-event-handling.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be81-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="8be81-116">最初に解析された [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページでイベントハンドラーを追加する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="8be81-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="8be81-117">イベントハンドラーを追加するオブジェクト要素内で、処理するイベントの名前と一致する属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="8be81-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="8be81-118">次に、[[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]] ページの分離コードファイルで定義したイベントハンドラーメソッドの名前として、その属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8be81-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="8be81-119">詳細については、「 [XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md) 」または「[ルーティングイベントの概要](routed-events-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be81-119">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be81-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8be81-120">See also</span></span>

- [<span data-ttu-id="8be81-121">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="8be81-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="8be81-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8be81-122">How-to Topics</span></span>](events-how-to-topics.md)
