---
title: '方法: 複数行の TextBox コントロールを作成する'
description: XAML を使用して、Windows Presentation Foundation アプリケーション内の複数行のテキストに合わせて拡張する TextBox コントロールを定義する方法について学習します。
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166257"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="bffa1-103">方法: 複数行の TextBox コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="bffa1-103">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="bffa1-104">次の例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用して、複数行のテキストに合わせて自動的に拡張する <xref:System.Windows.Controls.TextBox> コントロールを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bffa1-104">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bffa1-105">例</span><span class="sxs-lookup"><span data-stu-id="bffa1-105">Example</span></span>  
 <span data-ttu-id="bffa1-106"><xref:System.Windows.Controls.TextBox.TextWrapping%2A> 属性を **Wrap** に設定すると、入力されたテキストは <xref:System.Windows.Controls.TextBox> コントロールの端に達すると新しい行に折り返され、必要に応じて新しい行の空間が含まれるように <xref:System.Windows.Controls.TextBox> コントロールが自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bffa1-106">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="bffa1-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 属性を **true** に設定すると、RETURN キーが押されたときに新しい行が挿入されて、必要に応じて新しい行の空間が含まれるようにもう一度 <xref:System.Windows.Controls.TextBox> が自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bffa1-107">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="bffa1-108"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 属性によってスクロール バーが <xref:System.Windows.Controls.TextBox> に追加されるため、<xref:System.Windows.Controls.TextBox> がこれを囲むフレームまたはウィンドウのサイズよりも大きくなった場合、スクロール バーを使用して <xref:System.Windows.Controls.TextBox> の内容をスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="bffa1-108">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="bffa1-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="bffa1-109">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="bffa1-110">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bffa1-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="bffa1-111">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="bffa1-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
