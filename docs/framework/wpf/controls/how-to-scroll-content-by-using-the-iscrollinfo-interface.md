---
title: '方法: IScrollInfo インターフェイスを使用してコンテンツをスクロールする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 6ebd8268e1358b45709885c07e6b096d5f806ebb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051248"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="14968-102">方法: IScrollInfo インターフェイスを使用してコンテンツをスクロールする</span><span class="sxs-lookup"><span data-stu-id="14968-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="14968-103">この例を使用してコンテンツをスクロール、<xref:System.Windows.Controls.Primitives.IScrollInfo>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="14968-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14968-104">例</span><span class="sxs-lookup"><span data-stu-id="14968-104">Example</span></span>  
 <span data-ttu-id="14968-105">次の例では、機能、<xref:System.Windows.Controls.Primitives.IScrollInfo>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="14968-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="14968-106">例は、作成、<xref:System.Windows.Controls.StackPanel>要素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]親で入れ子になっている<xref:System.Windows.Controls.ScrollViewer>します。</span><span class="sxs-lookup"><span data-stu-id="14968-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="14968-107">子要素、<xref:System.Windows.Controls.StackPanel>によって定義されたメソッドを使用して論理的にスクロールできる、<xref:System.Windows.Controls.Primitives.IScrollInfo>インターフェイスとのインスタンスへのキャスト<xref:System.Windows.Controls.StackPanel>(`sp1`) コード。</span><span class="sxs-lookup"><span data-stu-id="14968-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="14968-108">各<xref:System.Windows.Controls.Button>で、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイルでのスクロール動作を制御する、関連付けられているカスタム メソッドをトリガーする<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="14968-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="14968-109">次の例は、使用する方法を示します、<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A>と<xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>メソッドも一般的にすべての配置方法を使用する方法を示します<xref:System.Windows.Controls.Primitives.IScrollInfo>クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="14968-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="14968-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="14968-110">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="14968-111">ScrollViewer の概要</span><span class="sxs-lookup"><span data-stu-id="14968-111">ScrollViewer Overview</span></span>](scrollviewer-overview.md)
- [<span data-ttu-id="14968-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="14968-112">How-to Topics</span></span>](scrollviewer-how-to-topics.md)
- [<span data-ttu-id="14968-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="14968-113">Panels Overview</span></span>](panels-overview.md)
