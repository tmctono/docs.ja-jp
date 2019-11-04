---
title: '方法 : TextBox コントロールのテキスト コンテンツを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 9b16f2d99295a28725255361b0be3ef7f4245fd2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459302"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="dac34-102">方法 : TextBox コントロールのテキスト コンテンツを設定する</span><span class="sxs-lookup"><span data-stu-id="dac34-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="dac34-103">この例では、<xref:System.Windows.Controls.TextBox.Text%2A> プロパティを使用して、<xref:System.Windows.Controls.TextBox> コントロールの初期テキストコンテンツを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dac34-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="dac34-104">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] バージョンの例では、各ボタンの <xref:System.Windows.Controls.TextBox> コンテンツのテキストを囲む `<TextBox.Text>` タグを使用できますが、<xref:System.Windows.Markup.ContentPropertyAttribute> 属性が <xref:System.Windows.Controls.TextBox> によって <xref:System.Windows.Controls.TextBox.Text%2A> プロパティに適用されるため、これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dac34-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="dac34-105">詳細については、「 [XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dac34-105">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="dac34-106">例</span><span class="sxs-lookup"><span data-stu-id="dac34-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="dac34-107">例</span><span class="sxs-lookup"><span data-stu-id="dac34-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="dac34-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="dac34-108">See also</span></span>

- [<span data-ttu-id="dac34-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="dac34-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="dac34-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="dac34-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
