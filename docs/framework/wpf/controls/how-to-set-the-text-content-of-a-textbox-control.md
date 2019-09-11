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
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856113"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="bd4bd-102">方法: TextBox コントロールのテキスト コンテンツを設定する</span><span class="sxs-lookup"><span data-stu-id="bd4bd-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="bd4bd-103">この例では、 <xref:System.Windows.Controls.TextBox.Text%2A>プロパティを使用して、 <xref:System.Windows.Controls.TextBox>コントロールのテキストの初期内容を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd4bd-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="bd4bd-104"><xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox> `<TextBox.Text>` <xref:System.Windows.Controls.TextBox.Text%2A>この例の<xref:System.Windows.Controls.TextBox>バージョンでは、各ボタンの内容のテキストを囲むタグを使用できますが、では属性がプロパティに適用されるため、これは必要ありません。 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd4bd-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="bd4bd-105">詳細については、「 [XAML の概要 (WPF)](../advanced/xaml-overview-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4bd-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="bd4bd-106">例</span><span class="sxs-lookup"><span data-stu-id="bd4bd-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="bd4bd-107">例</span><span class="sxs-lookup"><span data-stu-id="bd4bd-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="bd4bd-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd4bd-108">See also</span></span>

- [<span data-ttu-id="bd4bd-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bd4bd-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="bd4bd-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bd4bd-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
