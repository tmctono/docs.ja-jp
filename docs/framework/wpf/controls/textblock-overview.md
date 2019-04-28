---
title: TextBlock の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791015"
---
# <a name="textblock-overview"></a><span data-ttu-id="26771-102">TextBlock の概要</span><span class="sxs-lookup"><span data-stu-id="26771-102">TextBlock Overview</span></span>
<span data-ttu-id="26771-103"><xref:System.Windows.Controls.TextBlock>コントロールは、柔軟なテキスト サポートを提供します。[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="26771-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="26771-104">この要素は、主として、複数段落のテキストを必要としない、基本的な [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] シナリオを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="26771-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="26771-105">さまざまななどのプレゼンテーションでは、正確に制御を有効にするプロパティがサポートしている<xref:System.Windows.Controls.TextBlock.FontFamily%2A>、 <xref:System.Windows.Controls.TextBlock.FontSize%2A>、 <xref:System.Windows.Controls.TextBlock.FontWeight%2A>、 <xref:System.Windows.Controls.TextBlock.TextEffects%2A>、および<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>します。</span><span class="sxs-lookup"><span data-stu-id="26771-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="26771-106">使用して、テキスト コンテンツを追加することができます、<xref:System.Windows.Controls.TextBlock.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="26771-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="26771-107">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で使用すると、オープン タグとクローズ タグの間の内容は、要素のテキストとして暗黙的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="26771-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="26771-108">A<xref:System.Windows.Controls.TextBlock>要素は非常に単純を使用してインスタンス化できる[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="26771-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="26771-109">同様の使用状況、<xref:System.Windows.Controls.TextBlock>コード内の要素は比較的単純です。</span><span class="sxs-lookup"><span data-stu-id="26771-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="26771-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="26771-110">See also</span></span>

- <xref:System.Windows.Controls.Label>
