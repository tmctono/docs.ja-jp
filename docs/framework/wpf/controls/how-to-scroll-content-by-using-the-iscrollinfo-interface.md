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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051248"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="8e60a-102">方法: IScrollInfo インターフェイスを使用してコンテンツをスクロールする</span><span class="sxs-lookup"><span data-stu-id="8e60a-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="8e60a-103">この例では、<xref:System.Windows.Controls.Primitives.IScrollInfo> インターフェイスを使用し、コンテンツをスクロールする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e60a-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e60a-104">例</span><span class="sxs-lookup"><span data-stu-id="8e60a-104">Example</span></span>  
 <span data-ttu-id="8e60a-105">次の例では、<xref:System.Windows.Controls.Primitives.IScrollInfo> インターフェイスの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="8e60a-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="8e60a-106">この例では、親 <xref:System.Windows.Controls.ScrollViewer> で入れ子になっている [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] で <xref:System.Windows.Controls.StackPanel> 要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8e60a-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="8e60a-107"><xref:System.Windows.Controls.StackPanel> の子要素は、<xref:System.Windows.Controls.Primitives.IScrollInfo> インターフェイスで定義されているメソッドを利用することで論理的にスクロールできます。また、コードで <xref:System.Windows.Controls.StackPanel> のインスタンスにキャストされます (`sp1`)。</span><span class="sxs-lookup"><span data-stu-id="8e60a-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8e60a-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイル内の各 <xref:System.Windows.Controls.Button> によって、<xref:System.Windows.Controls.StackPanel> のスクロール動作を制御する関連カスタム メソッドがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="8e60a-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8e60a-109">次の例では、<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> メソッドと <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> メソッドの使用方法を示します。<xref:System.Windows.Controls.Primitives.IScrollInfo> クラスによって定義されるあらゆる配置メソッドの一般的な使用方法もわかります。</span><span class="sxs-lookup"><span data-stu-id="8e60a-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8e60a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e60a-110">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="8e60a-111">ScrollViewer の概要</span><span class="sxs-lookup"><span data-stu-id="8e60a-111">ScrollViewer Overview</span></span>](scrollviewer-overview.md)
- [<span data-ttu-id="8e60a-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8e60a-112">How-to Topics</span></span>](scrollviewer-how-to-topics.md)
- [<span data-ttu-id="8e60a-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8e60a-113">Panels Overview</span></span>](panels-overview.md)
