---
title: '方法: ScrollViewer を持つエキスパンダーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910794"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="9b881-102">方法: ScrollViewer を持つエキスパンダーを作成する</span><span class="sxs-lookup"><span data-stu-id="9b881-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="9b881-103">この例は、作成する方法を示します、<xref:System.Windows.Controls.Expander>イメージやテキストなどの複雑なコンテンツを格納しているコントロール。</span><span class="sxs-lookup"><span data-stu-id="9b881-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="9b881-104">例では、コンテンツを囲むことも、<xref:System.Windows.Controls.Expander>で、<xref:System.Windows.Controls.ScrollViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9b881-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b881-105">例</span><span class="sxs-lookup"><span data-stu-id="9b881-105">Example</span></span>  
 <span data-ttu-id="9b881-106">次の例を作成する方法を示しています、<xref:System.Windows.Controls.Expander>します。</span><span class="sxs-lookup"><span data-stu-id="9b881-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="9b881-107">この例では、 <xref:System.Windows.Controls.Primitives.BulletDecorator> 、コントロールを定義するには、画像とテキストを含む、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>します。</span><span class="sxs-lookup"><span data-stu-id="9b881-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="9b881-108">A<xref:System.Windows.Controls.ScrollViewer>コントロールが展開されたコンテンツ スクロール メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9b881-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="9b881-109">例では、設定に注意してください、<xref:System.Windows.FrameworkElement.Height%2A>プロパティを<xref:System.Windows.Controls.ScrollViewer>の代わりに、コンテンツにします。</span><span class="sxs-lookup"><span data-stu-id="9b881-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="9b881-110">場合、 <xref:System.Windows.FrameworkElement.Height%2A> 、コンテンツが設定されて、<xref:System.Windows.Controls.ScrollViewer>ユーザー コンテンツをスクロールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b881-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="9b881-111"><xref:System.Windows.FrameworkElement.Width%2A>プロパティが設定されて、<xref:System.Windows.Controls.Expander>に制御し、この設定が適用されます、<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>と展開されたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="9b881-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="9b881-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b881-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="9b881-113">エキスパンダーの概要</span><span class="sxs-lookup"><span data-stu-id="9b881-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="9b881-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="9b881-114">How-to Topics</span></span>](expander-how-to-topics.md)
