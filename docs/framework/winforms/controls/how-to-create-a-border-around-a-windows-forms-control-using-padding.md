---
title: パディングを使用してコントロールの周囲に罫線を作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742188"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="1d577-102">方法 : 埋め込みを使用して Windows フォーム コントロールの周囲に境界線を作成する</span><span class="sxs-lookup"><span data-stu-id="1d577-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="1d577-103">次のコード例では、<xref:System.Windows.Forms.RichTextBox> コントロールの周囲に罫線を作成したりアウトラインを作成したりする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d577-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="1d577-104">この例では、<xref:System.Windows.Forms.Panel> コントロールの <xref:System.Windows.Forms.Padding> プロパティの値を5に設定し、子 <xref:System.Windows.Forms.RichTextBox> コントロールの <xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="1d577-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="1d577-105"><xref:System.Windows.Forms.Panel> コントロールの <xref:System.Windows.Forms.Control.BackColor%2A> は <xref:System.Drawing.Color.Blue%2A>に設定されます。これにより、<xref:System.Windows.Forms.RichTextBox> コントロールの周囲に青い境界線が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d577-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d577-106">例</span><span class="sxs-lookup"><span data-stu-id="1d577-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1d577-107">参照</span><span class="sxs-lookup"><span data-stu-id="1d577-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="1d577-108">Windows フォーム コントロールでのマージンと埋め込み</span><span class="sxs-lookup"><span data-stu-id="1d577-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
