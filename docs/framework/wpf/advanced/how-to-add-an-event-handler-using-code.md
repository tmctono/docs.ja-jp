---
title: '方法: コードを使用してイベント ハンドラーを追加する'
description: この例を使用して、XAML を使用して宣言するのではなく、コードを使用して Windows Presentation Foundation の要素にイベント ハンドラーを追加する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166373"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="803f2-103">方法: コードを使用してイベント ハンドラーを追加する</span><span class="sxs-lookup"><span data-stu-id="803f2-103">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="803f2-104">この例では、コードを使用して、イベント ハンドラーを要素に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="803f2-104">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="803f2-105">イベント ハンドラーを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 要素に追加し、その要素を含むマークアップ ページが既に読み込まれている場合は、コードを使用してハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="803f2-105">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="803f2-106">または、コードを使用してアプリケーションの要素ツリーを全体的に構築し、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] を使用して要素を宣言しない場合は、特定のメソッドを呼び出して、構築された要素ツリーにイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="803f2-106">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="803f2-107">例</span><span class="sxs-lookup"><span data-stu-id="803f2-107">Example</span></span>  
 <span data-ttu-id="803f2-108">次の例では、最初に [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で定義された既存のページに新しい <xref:System.Windows.Controls.Button> を追加します。</span><span class="sxs-lookup"><span data-stu-id="803f2-108">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="803f2-109">分離コード ファイルでは、イベント ハンドラー メソッドが実装され、そのメソッドは <xref:System.Windows.Controls.Button> の新しいイベント ハンドラーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="803f2-109">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="803f2-110">C# の例では、`+=` 演算子を使用して、ハンドラーをイベントに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="803f2-110">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="803f2-111">これは、共通言語ランタイム (CLR) イベント処理モデルでハンドラーを割り当てるために使用される演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="803f2-111">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="803f2-112">Microsoft Visual Basic では、イベント ハンドラーを追加する手段として、この演算子はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="803f2-112">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="803f2-113">代わりに、次の 2 つの方法のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="803f2-113">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="803f2-114"><xref:System.Windows.UIElement.AddHandler%2A> メソッドを `AddressOf` 演算子と共に使用して、イベント ハンドラーの実装を参照します。</span><span class="sxs-lookup"><span data-stu-id="803f2-114">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="803f2-115">イベント ハンドラー定義の一部として、`Handles` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="803f2-115">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="803f2-116">この方法はここでは紹介されていません。「[Visual Basic と WPF のイベント処理](visual-basic-and-wpf-event-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="803f2-116">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="803f2-117">最初に解析された [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページでイベント ハンドラーを追加する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="803f2-117">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="803f2-118">イベント ハンドラーを追加するオブジェクト要素内で、処理するイベントの名前と一致する属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="803f2-118">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="803f2-119">次に、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページの分離コードファイルで定義したイベント ハンドラー メソッドの名前として、その属性の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="803f2-119">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="803f2-120">詳細については、「[XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」または「[ルーティング イベントの概要](routed-events-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="803f2-120">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803f2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="803f2-121">See also</span></span>

- [<span data-ttu-id="803f2-122">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="803f2-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="803f2-123">方法トピック</span><span class="sxs-lookup"><span data-stu-id="803f2-123">How-to Topics</span></span>](events-how-to-topics.md)
