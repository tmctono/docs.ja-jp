---
title: '方法: TextBox へのウォーターマークの追加'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923577"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="6379b-102">方法: TextBox へのウォーターマークの追加</span><span class="sxs-lookup"><span data-stu-id="6379b-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="6379b-103">次の例では、イメージが削除さ<xref:System.Windows.Controls.TextBox>れた時点でユーザーがテキストを入力<xref:System.Windows.Controls.TextBox>するまで、の内部に説明の背景イメージを表示することによっての使いやすさを支援する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6379b-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="6379b-104">さらに、ユーザーが入力を削除した場合、背景画像も復元されます。</span><span class="sxs-lookup"><span data-stu-id="6379b-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="6379b-105">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6379b-105">See illustration below.</span></span>  
  
 <span data-ttu-id="6379b-106">![背景画像を含むテキストボックス](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="6379b-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6379b-107">この例では、の<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを単に操作するの<xref:System.Windows.Controls.TextBox>ではなく、背景画像が使用されるため、背景画像がデータバインディングに干渉することはありません。</span><span class="sxs-lookup"><span data-stu-id="6379b-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6379b-108">例</span><span class="sxs-lookup"><span data-stu-id="6379b-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6379b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="6379b-109">See also</span></span>

- [<span data-ttu-id="6379b-110">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6379b-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6379b-111">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="6379b-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
