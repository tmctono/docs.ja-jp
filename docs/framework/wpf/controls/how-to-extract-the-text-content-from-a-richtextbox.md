---
title: '方法: RichTextBox からテキスト コンテンツを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001703"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="b3d78-102">方法: RichTextBox からテキスト コンテンツを抽出する</span><span class="sxs-lookup"><span data-stu-id="b3d78-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="b3d78-103">この例では、<xref:System.Windows.Controls.RichTextBox> のコンテンツをプレーンテキストとして抽出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3d78-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3d78-104">例</span><span class="sxs-lookup"><span data-stu-id="b3d78-104">Example</span></span>  
 <span data-ttu-id="b3d78-105">次の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] コードでは、単純コンテンツが含まれる名前付き <xref:System.Windows.Controls.RichTextBox> コントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3d78-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="b3d78-106">例</span><span class="sxs-lookup"><span data-stu-id="b3d78-106">Example</span></span>  
 <span data-ttu-id="b3d78-107">次のコードでは、引数として <xref:System.Windows.Controls.RichTextBox> を受け取り、<xref:System.Windows.Controls.RichTextBox> のプレーンテキスト コンテンツを表す文字列を返すメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="b3d78-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="b3d78-108">このメソッドでは、<xref:System.Windows.Controls.RichTextBox> のコンテンツから新しい <xref:System.Windows.Documents.TextRange> を作成し、<xref:System.Windows.Documents.FlowDocument.ContentStart%2A> と <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> を使用して、抽出するコンテンツの範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="b3d78-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="b3d78-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> プロパティと <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> プロパティはそれぞれ <xref:System.Windows.Documents.TextPointer> を返し、<xref:System.Windows.Controls.RichTextBox> のコンテンツを表す、基になる FlowDocument からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b3d78-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="b3d78-110"><xref:System.Windows.Documents.TextRange> は、Text プロパティを提供し、これにより、<xref:System.Windows.Documents.TextRange> のプレーンテキスト部分が文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="b3d78-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="b3d78-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3d78-111">See also</span></span>

- [<span data-ttu-id="b3d78-112">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b3d78-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="b3d78-113">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b3d78-113">TextBox Overview</span></span>](textbox-overview.md)
