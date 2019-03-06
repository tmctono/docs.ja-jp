---
title: '方法: ページがブラウザーでホストされているかを判断します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: ebc5612f059a6cf26f2568bbc08e705b4b3014c1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359992"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="cecd3-102">方法: ページがブラウザーでホストされているかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cecd3-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="cecd3-103">かどうか確認する方法を示します、<xref:System.Windows.Controls.Page>がブラウザーでホストされています。</span><span class="sxs-lookup"><span data-stu-id="cecd3-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cecd3-104">例</span><span class="sxs-lookup"><span data-stu-id="cecd3-104">Example</span></span>  
 <span data-ttu-id="cecd3-105">A<xref:System.Windows.Controls.Page>ホストに依存しないことができ、その結果、読み込むことができるなど、ホストのさまざまな種類に、 <xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Navigation.NavigationWindow>、またはブラウザー。</span><span class="sxs-lookup"><span data-stu-id="cecd3-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="cecd3-106">これは、1 つまたは複数のページを格納していると、複数のスタンドアロンによって参照されると、参照可能であるライブラリ アセンブリがある場合に発生することができます ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) アプリケーションをホストします。</span><span class="sxs-lookup"><span data-stu-id="cecd3-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="cecd3-107">次の例を使用する方法を示します<xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>どうかを判断する<xref:System.Windows.Controls.Page>がブラウザーでホストされています。</span><span class="sxs-lookup"><span data-stu-id="cecd3-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="cecd3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="cecd3-108">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
