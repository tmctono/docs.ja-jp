---
title: '方法: フロー コンテンツ要素を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: f61116c0bf52ac726238d9e21c2422cedbb4716f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663327"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="5a605-102">方法: フロー コンテンツ要素を使用する</span><span class="sxs-lookup"><span data-stu-id="5a605-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="5a605-103">次の例では、さまざまなフロー コンテンツ要素および関連付けられた属性の宣言型の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5a605-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="5a605-104">例で使用される要素および属性には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a605-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="5a605-105"><xref:System.Windows.Documents.Bold> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="5a605-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="5a605-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="5a605-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="5a605-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="5a605-108"><xref:System.Windows.Documents.Italic> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="5a605-109"><xref:System.Windows.Documents.LineBreak> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="5a605-110"><xref:System.Windows.Documents.List> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="5a605-111"><xref:System.Windows.Documents.ListItem> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="5a605-112"><xref:System.Windows.Documents.Paragraph> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="5a605-113"><xref:System.Windows.Documents.Run> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="5a605-114"><xref:System.Windows.Documents.Section> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="5a605-115"><xref:System.Windows.Documents.Span> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="5a605-116"><xref:System.Windows.Documents.Typography.Variants%2A> 属性 (上付き文字と下付き文字)</span><span class="sxs-lookup"><span data-stu-id="5a605-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="5a605-117"><xref:System.Windows.Documents.Underline> 要素</span><span class="sxs-lookup"><span data-stu-id="5a605-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a605-118">例</span><span class="sxs-lookup"><span data-stu-id="5a605-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
