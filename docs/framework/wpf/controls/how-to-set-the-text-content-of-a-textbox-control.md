---
title: '方法: TextBox コントロールのテキスト コンテンツを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024145"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="9bc77-102">方法: TextBox コントロールのテキスト コンテンツを設定する</span><span class="sxs-lookup"><span data-stu-id="9bc77-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="9bc77-103">この例は、使用する方法を示します、<xref:System.Windows.Controls.TextBox.Text%2A>の最初のテキストの内容を設定するプロパティを<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9bc77-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="9bc77-104">**注**が、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の例では、バージョンを使用、`<TextBox.Text>`の各ボタンのテキスト タグで囲みます<xref:System.Windows.Controls.TextBox>コンテンツの必要はありませんので、<xref:System.Windows.Controls.TextBox>適用されます、<xref:System.Windows.Markup.ContentPropertyAttribute>属性を<xref:System.Windows.Controls.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9bc77-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="9bc77-105">詳細については、次を参照してください。 [XAML の概要 (WPF)](../advanced/xaml-overview-wpf.md)します。</span><span class="sxs-lookup"><span data-stu-id="9bc77-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bc77-106">例</span><span class="sxs-lookup"><span data-stu-id="9bc77-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="9bc77-107">例</span><span class="sxs-lookup"><span data-stu-id="9bc77-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="9bc77-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bc77-108">See also</span></span>

- [<span data-ttu-id="9bc77-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="9bc77-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="9bc77-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="9bc77-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
