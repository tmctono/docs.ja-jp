---
title: '方法: ページに移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: c8e808180682bfd97f397d8cadd1e4deafd7eb06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947741"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="d3bce-102">方法: ページに移動する</span><span class="sxs-lookup"><span data-stu-id="d3bce-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="d3bce-103">この例で、ページからナビゲートできますをいくつかの方法を示しています、<xref:System.Windows.Navigation.NavigationWindow>します。</span><span class="sxs-lookup"><span data-stu-id="d3bce-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3bce-104">例</span><span class="sxs-lookup"><span data-stu-id="d3bce-104">Example</span></span>  
 <span data-ttu-id="d3bce-105">可能性があります、<xref:System.Windows.Navigation.NavigationWindow>を使用して、次のいずれかのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d3bce-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="d3bce-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d3bce-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="d3bce-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> メソッド。</span><span class="sxs-lookup"><span data-stu-id="d3bce-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] <span data-ttu-id="d3bce-108">相対または絶対のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d3bce-108">can be either relative or absolute.</span></span> <span data-ttu-id="d3bce-109">詳細については、「[WPF におけるパック URI](pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3bce-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bce-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3bce-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
