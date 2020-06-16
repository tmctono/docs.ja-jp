---
title: '方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 3d7da5daf09e06938b8366e0f5f98a599cae4571
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770618"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="8ebbb-102">方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する</span><span class="sxs-lookup"><span data-stu-id="8ebbb-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="8ebbb-103">この例からは、<xref:System.Windows.Controls.TextBox> コントロールのテキスト コンテンツの先頭または末尾にカーソルを置く方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="8ebbb-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ebbb-104">例</span><span class="sxs-lookup"><span data-stu-id="8ebbb-104">Example</span></span>  
 <span data-ttu-id="8ebbb-105">次の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] コードでは、<xref:System.Windows.Controls.TextBox> コントロールが説明され、それに名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8ebbb-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="8ebbb-106">例</span><span class="sxs-lookup"><span data-stu-id="8ebbb-106">Example</span></span>  
 <span data-ttu-id="8ebbb-107"><xref:System.Windows.Controls.TextBox> コントロールのコンテンツの先頭にカーソルを置くには、<xref:System.Windows.Controls.TextBox.Select%2A> メソッドを呼び出し、選択範囲の開始位置を 0 に、選択範囲の長さを 0 に指定します。</span><span class="sxs-lookup"><span data-stu-id="8ebbb-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="8ebbb-108">例</span><span class="sxs-lookup"><span data-stu-id="8ebbb-108">Example</span></span>  
 <span data-ttu-id="8ebbb-109"><xref:System.Windows.Controls.TextBox> コントロールのコンテンツの末尾にカーソルを配置するには、<xref:System.Windows.Controls.TextBox.Select%2A> メソッドを呼び出し、選択範囲の開始位置をテキスト コンテンツの長さと同じに、選択範囲の長さを 0 に指定します</span><span class="sxs-lookup"><span data-stu-id="8ebbb-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="8ebbb-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ebbb-110">See also</span></span>

- [<span data-ttu-id="8ebbb-111">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="8ebbb-111">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="8ebbb-112">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="8ebbb-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
