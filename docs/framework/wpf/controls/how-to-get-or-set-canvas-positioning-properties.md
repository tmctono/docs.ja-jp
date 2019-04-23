---
title: '方法: Canvas の配置プロパティを取得または設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194410"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="b251d-102">方法: Canvas の配置プロパティを取得または設定する</span><span class="sxs-lookup"><span data-stu-id="b251d-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="b251d-103">この例の配置のメソッドを使用する方法を示しています、<xref:System.Windows.Controls.Canvas>要素は子コンテンツを配置します。</span><span class="sxs-lookup"><span data-stu-id="b251d-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="b251d-104">この例でコンテンツを使用して、<xref:System.Windows.Controls.ListBoxItem>を表す位置の値し、のインスタンスに値を変換します。 <xref:System.Double>、配置に必要な引数であります。</span><span class="sxs-lookup"><span data-stu-id="b251d-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="b251d-105">値が文字列に変換し、テキストとして表示、<xref:System.Windows.Controls.TextBlock>要素を使用して、<xref:System.Windows.Controls.Canvas.GetLeft%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b251d-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b251d-106">例</span><span class="sxs-lookup"><span data-stu-id="b251d-106">Example</span></span>  
 <span data-ttu-id="b251d-107">次の例では、作成、<xref:System.Windows.Controls.ListBox>選択可能な 11 個の要素<xref:System.Windows.Controls.ListBoxItem>要素。</span><span class="sxs-lookup"><span data-stu-id="b251d-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="b251d-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>イベント トリガー、`ChangeLeft`カスタム メソッドは、後続のコード ブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="b251d-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="b251d-109">各<xref:System.Windows.Controls.ListBoxItem>を表す、<xref:System.Double>引数の 1 つの値を<xref:System.Windows.Controls.Canvas.SetLeft%2A>メソッドの<xref:System.Windows.Controls.Canvas>受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b251d-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="b251d-110">使用するには、<xref:System.Windows.Controls.ListBoxItem>のインスタンスを表す<xref:System.Double>、最初に変換する必要があります、<xref:System.Windows.Controls.ListBoxItem>正しいデータ型にします。</span><span class="sxs-lookup"><span data-stu-id="b251d-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b251d-111">ユーザーが変更されたとき、<xref:System.Windows.Controls.ListBox>選択した場合、起動、`ChangeLeft`カスタム メソッド。</span><span class="sxs-lookup"><span data-stu-id="b251d-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="b251d-112">このメソッドは、<xref:System.Windows.Controls.ListBoxItem>を<xref:System.Windows.LengthConverter>に変換するオブジェクト、<xref:System.Windows.Controls.ContentControl.Content%2A>の<xref:System.Windows.Controls.ListBoxItem>のインスタンスに<xref:System.Double>(この値は既にに変換されたに注意してください、<xref:System.String>を使用して、 <xref:System.Windows.Controls.Control.ToString%2A>メソッドの場合)。</span><span class="sxs-lookup"><span data-stu-id="b251d-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="b251d-113">この値が渡されたし、<xref:System.Windows.Controls.Canvas.SetLeft%2A>と<xref:System.Windows.Controls.Canvas.GetLeft%2A>メソッドの<xref:System.Windows.Controls.Canvas>の位置を変更するには、`text1`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b251d-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b251d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b251d-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="b251d-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="b251d-115">Panels Overview</span></span>](panels-overview.md)
