---
title: '方法: テキスト選択を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b7f0b9ee02a7ace717787fc8eeb6e15649829a49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770787"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="2faee-102">方法: テキスト選択を取得する</span><span class="sxs-lookup"><span data-stu-id="2faee-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="2faee-103">この例では、<xref:System.Windows.Controls.TextBox.SelectedText%2A> プロパティを使用して、ユーザーが <xref:System.Windows.Controls.TextBox> コントロールで選択したテキストを取得する方法の 1 つを示します。</span><span class="sxs-lookup"><span data-stu-id="2faee-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2faee-104">例</span><span class="sxs-lookup"><span data-stu-id="2faee-104">Example</span></span>  
 <span data-ttu-id="2faee-105">次の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] の例は、"some text to select" を含む <xref:System.Windows.Controls.TextBox> コントロールの定義と、指定された <xref:System.Windows.Controls.Button.OnClick%2A> メソッドの <xref:System.Windows.Controls.Button> コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="2faee-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="2faee-106">この例では、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーが関連付けられているボタンを使用して、テキスト選択を取得します。</span><span class="sxs-lookup"><span data-stu-id="2faee-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="2faee-107">ユーザーがボタンをクリックすると、<xref:System.Windows.Controls.Button.OnClick%2A> メソッドによって、テキストボックス内の選択したテキストが文字列にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2faee-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="2faee-108">テキスト選択を取得する特定の状況 (ボタンをクリックする)、およびその選択によって実行されるアクション (テキスト選択を文字列にコピーする) は、さまざまなシナリオに対応するように簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="2faee-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="2faee-109">例</span><span class="sxs-lookup"><span data-stu-id="2faee-109">Example</span></span>  
 <span data-ttu-id="2faee-110">次の C# の例は、この例の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で定義されているボタンの <xref:System.Windows.Controls.Button.OnClick%2A> イベント ハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="2faee-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="2faee-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2faee-111">See also</span></span>

- [<span data-ttu-id="2faee-112">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="2faee-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="2faee-113">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="2faee-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
