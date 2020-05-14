---
title: '方法: ページがブラウザーでホストされているかを確認する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424691"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="6c2c4-102">方法: ページがブラウザーでホストされているかを確認する</span><span class="sxs-lookup"><span data-stu-id="6c2c4-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="6c2c4-103">この例では、<xref:System.Windows.Controls.Page> がブラウザーでホストされているかどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c2c4-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c2c4-104">例</span><span class="sxs-lookup"><span data-stu-id="6c2c4-104">Example</span></span>  
 <span data-ttu-id="6c2c4-105"><xref:System.Windows.Controls.Page> はホストに依存しないので、<xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow>、ブラウザーなど、さまざまな種類のホストに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6c2c4-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="6c2c4-106">これは、1 つまたは複数のページを含むライブラリ アセンブリがあり、複数のスタンドアロンおよび閲覧可能な (XAML ブラウザー アプリケーション (XBAP)) ホスト アプリケーションによって参照されている場合に、発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c2c4-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="6c2c4-107">次の例では、<xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> を使用して <xref:System.Windows.Controls.Page> がブラウザーでホストされているかどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c2c4-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="6c2c4-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c2c4-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
