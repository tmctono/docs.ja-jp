---
title: '方法: TextBox コントロールを読み取り専用にする'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3784471020210f995c8bb0a377d56a2466d97da1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364538"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="50613-102">方法: TextBox コントロールを読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="50613-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="50613-103">この例は、構成する方法を示します、<xref:System.Windows.Controls.TextBox>コントロールをユーザー入力または変更できません。</span><span class="sxs-lookup"><span data-stu-id="50613-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50613-104">例</span><span class="sxs-lookup"><span data-stu-id="50613-104">Example</span></span>  
 <span data-ttu-id="50613-105">内容を変更できないようにする、<xref:System.Windows.Controls.TextBox>設定、制御、<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性を**true**します。</span><span class="sxs-lookup"><span data-stu-id="50613-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="50613-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性がユーザー入力のみに影響; 内のテキスト セットには影響しません、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の説明、<xref:System.Windows.Controls.TextBox>コントロール、またはプログラムにより設定されたテキスト、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="50613-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="50613-107">既定値<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>は**false**します。</span><span class="sxs-lookup"><span data-stu-id="50613-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50613-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="50613-108">See also</span></span>
- [<span data-ttu-id="50613-109">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="50613-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="50613-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="50613-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
