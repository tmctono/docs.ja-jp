---
title: '方法: イベント ハンドラーでソース要素を検索する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104560"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="2f122-102">方法: イベント ハンドラーでソース要素を検索する</span><span class="sxs-lookup"><span data-stu-id="2f122-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="2f122-103">この例では、イベント ハンドラーでソース要素を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f122-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f122-104">例</span><span class="sxs-lookup"><span data-stu-id="2f122-104">Example</span></span>  
 <span data-ttu-id="2f122-105">次の例は、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>分離コード ファイルで宣言されているイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="2f122-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="2f122-106">ハンドラーがアタッチされているボタンをクリックすると、ハンドラーは、プロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="2f122-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="2f122-107">ハンドラー コードを使用して、<xref:System.Windows.RoutedEventArgs.Source%2A>のルーティング イベントのデータを変更するイベントの引数で報告されるプロパティ、<xref:System.Windows.FrameworkElement.Width%2A>プロパティ値、<xref:System.Windows.RoutedEventArgs.Source%2A>要素。</span><span class="sxs-lookup"><span data-stu-id="2f122-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="2f122-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f122-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="2f122-109">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="2f122-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="2f122-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="2f122-110">How-to Topics</span></span>](events-how-to-topics.md)
