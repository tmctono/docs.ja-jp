---
title: '方法: TextBox コントロールにフォーカスを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: 8c3b9881ada843d65db035835fc5f4c865a177e9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368481"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="6de8e-102">方法: TextBox コントロールにフォーカスを設定する</span><span class="sxs-lookup"><span data-stu-id="6de8e-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="6de8e-103">この例は、使用する方法を示します、<xref:System.Windows.UIElement.Focus%2A>にフォーカスを設定する方法、<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6de8e-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6de8e-104">例</span><span class="sxs-lookup"><span data-stu-id="6de8e-104">Example</span></span>  
 <span data-ttu-id="6de8e-105">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]例で、単純な<xref:System.Windows.Controls.TextBox>という名前のコントロール*は*</span><span class="sxs-lookup"><span data-stu-id="6de8e-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="6de8e-106">例</span><span class="sxs-lookup"><span data-stu-id="6de8e-106">Example</span></span>  
 <span data-ttu-id="6de8e-107">次の例では、<xref:System.Windows.UIElement.Focus%2A>にフォーカスを設定する方法、<xref:System.Windows.Controls.TextBox>名前を持つコントロール*は*します。</span><span class="sxs-lookup"><span data-stu-id="6de8e-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="6de8e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="6de8e-108">See also</span></span>
- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="6de8e-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6de8e-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6de8e-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6de8e-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
