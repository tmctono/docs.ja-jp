---
title: UI オートメーションを使用した、テキストの検索と強調表示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 084a9cdeaf17d7456116c56e9a12115b478f7384
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043639"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="a0815-102">UI オートメーションを使用した、テキストの検索と強調表示</span><span class="sxs-lookup"><span data-stu-id="a0815-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="a0815-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a0815-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a0815-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="a0815-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a0815-105">このトピックでは、を使用して[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]、テキストコントロールのコンテンツ内の文字列の出現箇所を順番に検索し、強調表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a0815-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0815-106">例</span><span class="sxs-lookup"><span data-stu-id="a0815-106">Example</span></span>  
 <span data-ttu-id="a0815-107">次の例では<xref:System.Windows.Automation.TextPattern> 、テキストコントロールからオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a0815-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="a0815-108">その後、ドキュメント全体のテキストコンテンツを表す<xref:System.Windows.Automation.TextPattern.DocumentRange%2A> <xref:System.Windows.Automation.TextPattern> <xref:System.Windows.Automation.Text.TextPatternRange>オブジェクトが、こののプロパティを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0815-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="a0815-109">その後、順次検索と強調表示の機能に対して、2つのオブジェクトが作成されます。<xref:System.Windows.Automation.Text.TextPatternRange></span><span class="sxs-lookup"><span data-stu-id="a0815-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="a0815-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0815-110">See also</span></span>

- [<span data-ttu-id="a0815-111">UI オートメーションを使用した、テキストの検索と強調表示</span><span class="sxs-lookup"><span data-stu-id="a0815-111">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
