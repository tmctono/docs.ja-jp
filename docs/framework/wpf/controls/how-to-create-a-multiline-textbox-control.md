---
title: '方法: 複数行の TextBox コントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 75bbee806b2b7039656d6c8e7c9a64359e77d16f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352348"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="d44f9-102">方法: 複数行の TextBox コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d44f9-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="d44f9-103">この例は、使用する方法を示します[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]を定義する、<xref:System.Windows.Controls.TextBox>複数行のテキストに合わせて自動的に拡張するコントロール。</span><span class="sxs-lookup"><span data-stu-id="d44f9-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d44f9-104">例</span><span class="sxs-lookup"><span data-stu-id="d44f9-104">Example</span></span>  
 <span data-ttu-id="d44f9-105">設定、<xref:System.Windows.Controls.TextBox.TextWrapping%2A>属性を**ラップ**により、入力したテキストを新しいをラップするときに行の端、<xref:System.Windows.Controls.TextBox>コントロールに達すると、自動的に拡大、<xref:System.Windows.Controls.TextBox>場合、新しい行に含まれるコントロールいる。</span><span class="sxs-lookup"><span data-stu-id="d44f9-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="d44f9-106">設定、<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>属性を**true**が再び自動的に拡大、戻り値のキーが押されたときに挿入する改行を発生させる、<xref:System.Windows.Controls.TextBox>に必要な場合に、新しい行を含めます。</span><span class="sxs-lookup"><span data-stu-id="d44f9-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="d44f9-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>属性によってスクロール バーを表示、追加、<xref:System.Windows.Controls.TextBox>いるための内容、<xref:System.Windows.Controls.TextBox>場合をスクロール、<xref:System.Windows.Controls.TextBox>フレームまたはこれを囲むウィンドウのサイズします。</span><span class="sxs-lookup"><span data-stu-id="d44f9-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="d44f9-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d44f9-108">See also</span></span>
- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="d44f9-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="d44f9-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d44f9-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="d44f9-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
